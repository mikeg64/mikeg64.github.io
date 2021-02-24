---
layout: post
title:  "Visualisation Using Paraview of Washing Machine Results"
date:   2021-02-14 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine  analysis matlab paraview Visualisation
---


# Visualisation Using Paraview of Washing Machine Results

Objective: Describe the methods used to import data into paraview

[Paraview](https://www.paraview.org/) is a powerful interactive tool for data visualisation and analysis it is developed using the [VTK](https://vtk.org/) toolkit. Our objective is to rapidly get our data into the visualisation platform and to explore that data se, gain new insights.

1. Data formats for paraview VTK, VTU, h5
2. Develop custom interface

There is a number of approaches we can adopt, if our data is not in a format which can be ported into Paraview then it will be necessary to develop our own converter. Paraview supports many file formats ( [https://www.paraview.org/Wiki/ParaView/Data_formats](https://www.paraview.org/Wiki/ParaView/Data_formats) ). Examples include the hdf format  and the [VTK format](https://vtk.org/wp-content/uploads/2015/04/file-formats.pdf).

Example converters which were tested include implementations using Matlab and these have been published on Matlab Central, for example:

1. [vtkwrite : Exports various 2D/3D data to ParaView in VTK file format](https://uk.mathworks.com/matlabcentral/fileexchange/47814-vtkwrite-exports-various-2d-3d-data-to-paraview-in-vtk-file-format)
2. [WriteToVTK](https://uk.mathworks.com/matlabcentral/fileexchange/23416-writetovtk)

Implementations which were tested included codes in both Matlab and IDL.
1. [WriteToVTK](https://github.com/mikeg64/solar/tree/master/matlab/readwriteconvert/vtk)

The method which was most successful involved converting the output of the modelling code ([SMAUG](http://solarwavetheory.blogspot.com/2015/12/a-quick-start-to-using-smaug.html) and [SAC](http://solarwavetheory.blogspot.com/search/label/SAC)) into [hdf5](http://solarwavetheory.blogspot.com/2015/02/data-standards-for-computational.html) format.

Converters were easily developed using Matlab e.g. see .
1. [hdf5tosac3d](https://github.com/mikeg64/smaug_wash/blob/master/matlab/hdf5_and_gdf/hdf5tosac3D.m)
2. [sac3dtohdf5](https://github.com/mikeg64/smaug_wash/blob/master/matlab/hdf5_and_gdf/sac3Dtohdf5.m)

# Method

For the the visualisations developed here a number of steps were followed.

* Develop a visualisation using the Paraview GUI
* Generate a python script
* Run a sequence  of visualisations using a task array 
* Run Paraview using a docker container implementation

The data set being visualised consisted of approximately 1000 separate files each containing the data for an MHD run for one a single time step. For the 128x128x128 grids considered here the file size was

1.  218MB for and hff5 format file
2.  268MB for a SAC3d output format

As well as a recognised standard and an efficient file format for read/write the hdf5 format is 20% smaller... bonus!

Conveniently Paraview provides a number of readers for hdf5. The import method has already been described in an earlier post [Importing MHD Simulation Data into Paraview](http://mikeg64.github.io/visualisation/paraview/2021/01/08/importing-MHD-simulationdatatoParaview.html).





## Paraview State Scripts

As described earlier, Paraview provides a range of file loaders and filters for loading, transformation and visualisation of processed data. The ease with which this can be achieved greatly enhances our ability to explore  a data sets view them in a variety of ways and to gain   insights.

One of the first steps is to save and reload the state of paraview at a particular time. The paraview state can be saved either in Paraview's own xml based format or as a python script which can be rerun using the pvpython command. When saving using this method it is possible to select which properties will be saved ( modified, visible or all properties). 

* [stream_contour_extract_slices_magslices_dualview](https://github.com/mikeg64/smaug_wash/blob/master/paraview/py27-pv570/stream_contour_extract_slices_magslices_dualview.pvsm)

![pic](https://drive.google.com/uc?export=view&id=1tKPKc13Cgoxi3tZiYqsuRXFnwXcp7V6R)  

Example below includes generated python script which we can run using pvpython


* [createvecs-visosurf-slice-vstreamline-denslicebase-extract.pvsm](https://github.com/mikeg64/smaug_wash/blob/master/paraview/createvecs-visosurf-slice-vstreamline-denslicebase-extract.pvsm)
* [createvecs-visosurf-slice-vstreamline-denslicebase-jpg-loop.py](https://github.com/mikeg64/smaug_wash/blob/master/paraview/createvecs-visosurf-slice-vstreamline-denslicebase-jpg-loop.py)

The visualisation below revealed an interesting kinking effect of the magnetic flux tube.the decision was made to investigate the evolution of this effect over time. Given the size of the full data set, it was impractical to generate a significant number of images on a personal workstation. This was the point at which the pvpython task became useful. to make use of it some modifications were made.

The image creation part of the script was written into a  create image function

```

def createimage(i,renderView1):

    id=1000+i*1000
    fnameroot='/Users/xxxxx/proj/washmc-data/uni6/h5/washmc_'
    ifnameroot='/Users/xxxxx/proj/washmc-data/uni6/images/washmc_'
    
    fname=fnameroot+str(id)+'.h5'
    ifname=ifnameroot+str(id)+'.jpg'

    # ----------------------------------------------------------------
    # setup the data processing pipelines
    # ----------------------------------------------------------------    
    # create a new 'VisItPixieReader'
    washmc_h5 = VisItPixieReader(FileName=fname)
    washmc_h5.Meshes = ['mesh_128x128x128']
    washmc_h5.CellArrays = ['data/grid_0000000000/density_bg', 'data/grid_0000000000/density_pert', 'data/grid_0000000000/internal_energy_bg', 'data/grid_0000000000/internal_energy_pert', 'data/grid_0000000000/mag_field_x_bg', 'data/grid_0000000000/mag_field_x_pert', 'data/grid_0000000000/mag_field_y_bg', 'data/grid_0000000000/mag_field_y_pert', 'data/grid_0000000000/mag_field_z_bg', 'data/grid_0000000000/mag_field_z_pert', 'data/grid_0000000000/velocity_x', 'data/grid_0000000000/velocity_y', 'data/grid_0000000000/velocity_z', 'grid_left_index', 'grid_level', 'grid_parent_id', 'grid_particle_count']


.
.
.
.
.
.

```


The second code fragment, below, shows the loop in the main part of the routine and the loop which repeatedly calls the createimafe() routine.



```
# ----------------------------------------------------------------
# restore active view
SetActiveView(renderView1)
# ----------------------------------------------------------------

for i in range(0,1271): 
    #### disable automatic camera reset on 'Show'
    paraview.simple._DisableFirstRenderCameraReset()
    
    # get the material library
    materialLibrary1 = GetMaterialLibrary()
    id=1000+i*20000
    fnameroot='/Users/xxxxxxx/proj/washmc-data/uni6/h5/washmc_'
    ifnameroot='/Users/xxxxxxx/proj/washmc-data/uni6/images/washmc_'
    
    # Create a new 'Render View'
    renderView1 = CreateView('RenderView')
    renderView1.ViewSize = [1942, 1412]
    renderView1.AxesGrid = 'GridAxes3DActor'
    renderView1.CenterOfRotation = [32.0, 64.0, 64.0]
    renderView1.StereoType = 'Crystal Eyes'
    renderView1.CameraPosition = [239.76251878719324, 0.640916434808301, 308.3771165833229]
    renderView1.CameraFocalPoint = [4.065694001785766, 72.51882254031378, 31.142749358984677]
    renderView1.CameraViewUp = [0.705407579263351, -0.24797493532912449, -0.6640094717444442]
    renderView1.CameraFocalDisk = 1.0
    renderView1.CameraParallelScale = 96.0
    renderView1.BackEnd = 'OSPRay raycaster'
    renderView1.OSPRayMaterialLibrary = materialLibrary1
    
    #SetActiveView(None)    
    # ----------------------------------------------------------------
    # setup view layouts
    # ----------------------------------------------------------------    
    # create new layout object 'Layout #1'
    layout1 = CreateLayout(name='Layout #1')
    layout1.AssignView(0, renderView1)    
    # ----------------------------------------------------------------
    # restore active view
    #SetActiveView(renderView1)
    # ----------------------------------------------------------------
    
    createimage(i, renderView1) 
'
'
.
.
.

```



![pic](https://drive.google.com/uc?export=view&id=1Nba7AfzGQguQT8FUwCBuAfbvCL6mgd3X)  

The resulting movie (generated using QuickTime (or [ffmpeg](https://ffmpeg.org/) is shown below:







 [![2d-secs-mags](https://drive.google.com/uc?export=view&id=1Qcww2KSFQ0IpHdOv4nBecciSyxB9IX8u)](https://drive.google.com/file/d/1eLglFaFlnl4UCEFP3TzKm9Zp51fVmlRp/view?usp=sharing)


The task to  generate the images was run using a singularity container ( see [Singularity on ShARC](https://docs.hpc.shef.ac.uk/en/latest/sharc/software/apps/singularity.html) )  the singularity container was built using a [paraview docker container](https://hub.docker.com/r/kitware/paraview).

This was highly effective. The procedure which worked was as follows:
1. Run a conversion script  generating .h5 (or even .vtu) files which can be read into Paraview
2. Copy a small number of files from remote system to local desktop
3. Investigate sample using Paraview and save states 
4. For the selected  scenes of interest generate the python script and convert  so that it can generate multiple frames
5. Run the task using Paraview in the singularity container 




# Experiences Using pvserver

Methods which were used for the visualisation included the following
1. Mounting the remote storage on the desktop system
2. Running paraview using [Oracle desktop](https://www.oracle.com/virtualization/technologies/vm/secure-desktop-overview.html), application similar to [x2go](https://wiki.x2go.org/doku.php) or [openondemand](https://openondemand.org/)
3. Using a VirtualGL type client e.g. with tigerVNC

Another method which is highly effective is the use of a paraview client server system in which we can run paraview on a local desktop and the paraview server processes the data on the remote generating a rendered image. This proved problematic and the solution was not fully resolved, we look forward to resolving this soon!

Guidelines for running and using pvserver are at [Running ParaView in Client-Server Mode
](Running ParaView in Client-Server Mode).

# Future Developments

Custom loader plugin e.g. see:
1. [Paraview Plugin / how to](https://www.paraview.org/Wiki/ParaView/Plugin_HowTo)
2. [ParaView Plugins Implementation](https://www.paraview.org/ParaView/index.php/ParaView_Plugins_Implementation)
3. [ParaView/Plugin HowTo#Adding a Reader ](https://www.paraview.org/Wiki/ParaView/Plugin_HowTo#Adding_a_Reader)

# Useful Links

1. [https://www.paraview.org/Wiki/The_ParaView_Tutorial](https://www.paraview.org/Wiki/The_ParaView_Tutorial)
2. [Introduction to Paraview](https://docs.paraview.org/en/latest/UsersGuide/introduction.html)








## Pictures with hyperlinks in markdown

embedding moview

### 2d view showing mutually perpendicular slices  and the B field magnitude, lower figure shows a horizontal slice at the bae of the model

 [![2d-secs-mags](https://drive.google.com/uc?export=view&id=17c29VYA05VPScr4gST3Qj_9Yf3jp0qgF)](https://drive.google.com/file/d/1UqvwW9Vu126W45BDwyPJwMU2yXOG3jBH/view?usp=sharing)




![pic](https://drive.google.com/uc?export=view&id=1FGPalJfnkLemhIh833kqYk1H6uvqfaWc)  

Copy the link to share and you will have something like
https://drive.google.com/file/d/<FILE_ID>/view?usp=sharing

Copy the <FILE_ID> to make a link like this:
https://drive.google.com/uc?export=view&id=<FILE_ID>

Insert image in Markdown as ususal using the link from step 4.
For example: ![image](https://drive.google.com/uc?export=view&id=<FILE_ID>)




