---
layout: post
title:  "Reading VAC/SAC/SMAUG Data into Paraview"
date:   2021-05-21 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine  analysis matlab paraview Visualisation
---


# Reading Data into Paraview


Version 5.7.0 of paraview featured a Visit reader importing pixie hdf5 format files. This is a generic hdf5 format which can be loaded into paraview. In an earlier post.  [Visualisation Using Paraview of Washing Machine Results](http://mikeg64.github.io/washing/machine/update/2021/02/14/paraview-washmc-1.html) I described how that reader was used.

Now installing a later version on the compute service at The University of Sheffield reveals that the latest version does not support that reader. This creates difficulties, there is a number of options.


* Copy some data to the local workstation and run paraview 5.7.0 with the visit/pixie reader use the remote platform to run a batch task with paraview using a singularity container (as described in the blog)
* Do the post processing bu convert all the data to VTK format using the converters at [tovtk.py](https://gist.github.com/mikeg64/42cf2d5ef3a3d47bdb280c58db30d6d1).
* Use an existing idl based converter e.g. see [run_convert_wash_vtk](https://github.com/mikeg64/smaug_wash/blob/master/Idl/runconvert_wash_vtk)

A post detailing the problem on kitwares discussion group explains the problem as follows.
[Implementing a Visit Reader in Paraview 5.8.0 ADD_VISIT_PLUGIN_READER](https://discourse.paraview.org/t/implementing-a-visit-reader-in-paraview-5-8-0-add-visit-plugin-reader/3726)





















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




