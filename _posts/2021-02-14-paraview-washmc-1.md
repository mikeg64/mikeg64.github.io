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



* [stream_contour_extract_slices_magslices_dualview](https://github.com/mikeg64/smaug_wash/blob/master/paraview/py27-pv570/stream_contour_extract_slices_magslices_dualview.pvsm)

![pic](https://drive.google.com/uc?export=view&id=1tKPKc13Cgoxi3tZiYqsuRXFnwXcp7V6R)  

Example below includes generated python script which we can run using pvpython


* [createvecs-visosurf-slice-vstreamline-denslicebase-extract.pvsm](https://github.com/mikeg64/smaug_wash/blob/master/paraview/createvecs-visosurf-slice-vstreamline-denslicebase-extract.pvsm)
* [createvecs-visosurf-slice-vstreamline-denslicebase-extract.pvsm](https://github.com/mikeg64/smaug_wash/blob/master/paraview/createvecs-visosurf-slice-vstreamline-denslicebase-jpg-loop.py)


![pic](https://drive.google.com/uc?export=view&id=1Nba7AfzGQguQT8FUwCBuAfbvCL6mgd3X)  



https://drive.google.com/file/d/1Qcww2KSFQ0IpHdOv4nBecciSyxB9IX8u/view?usp=sharing

https://drive.google.com/file/d/1eLglFaFlnl4UCEFP3TzKm9Zp51fVmlRp/view?usp=sharing         mov





 [![2d-secs-mags](https://drive.google.com/uc?export=view&id=1Qcww2KSFQ0IpHdOv4nBecciSyxB9IX8u)](https://drive.google.com/file/d/1eLglFaFlnl4UCEFP3TzKm9Zp51fVmlRp/view?usp=sharing)






# Experiences Using pvserver

running the pvserver ...




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




