---
layout: post
title:  "Importing MHD Simulation Data into Paraview"
date:   2021-01-08 15:11:28 +0100
categories: Visualisation Paraview
tags: MHD Paraview Visualisation
---


# Importing MHD Simulation Data into Paraview


## Introduction to Paraview

Based on the [VTK](https://vtk.org/) toolkit, [Paraview](https://www.paraview.org/) is an excellent open source tool for data analysis and visualisation. ParaView users can quickly build visualizations to analyze their data using qualitative and quantitative techniques. The data exploration can be done interactively in 3D or programmatically using ParaView’s batch processing capabilities. (that's a fair description of exactly what paraview does from their front page)

In this post I describe some of the processes we have followed to get data into paraview this is by making use of a couple of formats
* [hdf5](https://www.hdfgroup.org/solutions/hdf5/) [Hdf5 data model](http://davis.lbl.gov/Manuals/HDF5-1.8.7/UG/03_DataModel.html)
* legacy [VTK](https://vtk.org/wp-content/uploads/2015/04/file-formats.pdf)

We then describe options for paraview for exporting the scene generation into a python script which may be run in batch mode or adapted.

## Scripts for converting MHD Output  Between Different Formats

First step is to convert data (or output data) to hdf5 format

* for this we used a matlab routine
[https://github.com/mikeg64/smaug_wash/blob/master/matlab/hdf5_and_gdf/sac3Dtohdf5.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/hdf5_and_gdf/sac3Dtohdf5.m)

* this was executed with the following task execution script
[https://github.com/mikeg64/smaug_wash/blob/master/matlab/hdf5_and_gdf/con2h5.sh](https://github.com/mikeg64/smaug_wash/blob/master/matlab/hdf5_and_gdf/con2h5.sh)

Another converter used is written in [IDL](http://www.idlcoyote.com/) this converts data into the legacy VTK format 
it creates a lot of text and large files

* working IDL script [https://github.com/mikeg64/smaug_wash/blob/master/Idl/run_convert_wash_vtk.pro](https://github.com/mikeg64/smaug_wash/blob/master/Idl/run_convert_wash_vtk.pro)
* Driver script file [https://github.com/mikeg64/smaug_wash/blob/master/Idl/runconvert_wash_vtk](https://github.com/mikeg64/smaug_wash/blob/master/Idl/runconvert_wash_vtk)
* Dependent IDL scripts
* [https://github.com/mikeg64/smaug_wash/blob/master/Idl/vacscalar2vtk3d.pro](https://github.com/mikeg64/smaug_wash/blob/master/Idl/vacscalar2vtk3d.pro)
* [https://github.com/mikeg64/smaug_wash/blob/master/Idl/vac2vtk3d.pro](https://github.com/mikeg64/smaug_wash/blob/master/Idl/vac2vtk3d.pro)


## Process 


In Paraview our first step is to import our data into paraview use either h5 or vtk format.

* Import data using file open Legacy VTK files
* Import data using file open Pixie file (.h5) - then select the VisIt Pixie Reader

A problem with using the h5 import was that the fields were imported as scalars we employed the following calculator to generate the required vector fields.

You can use the Calculator to create a vector field from your three
scalar fields.

Say your three scalar fields are named X_VELOCITY, Y_VELOCITY, and
Z_VELOCITY. Then in the main text field just above the various
functions/operators, you should enter

    (iHat*X_VELOCITY) + (jHat*Y_VELOCITY) + (kHat*Z_VELOCITY)

I've just added this (9/1/2020) as practicing and testing these procedures made me realise what the best approach for generating a python script is. It is as follows:

### Method 1

Select File->Save State
The state file can either be saved as a .pvsm (that's paraview's method of storing the state of paraview).
The state file can be saved as a .py file which can be run independently

An example file saved using this method is here
[https://github.com/mikeg64/smaug_wash/blob/master/python/paraviewimport/pywash5_uni3.py](https://github.com/mikeg64/smaug_wash/blob/master/python/paraviewimport/pywash5_uni3.py)

This file has been adapted so that a loop reads a number of configurations and repeats the paraview steps.

### Method 2

from Catalyst menu Select generate script
Wizard deprecated in favour of the export inspector in paraview 5.6
from the menu 
* select the data set
* add option 
* select state configuration options - output rendering components i.e.views, view selection and image type

### Method 3

The other option which is not deprecated is to do the following
* set options in catalyst Define Exports
* Catalyst->Export Catalyst script

Other options include the possibility of saving scene elements to a range of formats for example PLY (.ply) which might be used to generate the scenes for rendering tools such as [Blender](https://www.blender.org/).

## Conclusion

* Save configurations as hdf5 format - this is a recognised and powerful standard also saves space
* Use the save state method to generate the a python script file






















