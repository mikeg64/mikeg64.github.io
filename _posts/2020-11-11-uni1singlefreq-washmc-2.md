---
layout: post
title:  "Solar Washing Machine Single Frequency Driver Rerun 2"
date:   2020-11-11 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug configuration matlab idl
---


# Rerun of the uni1 driver - part2 (uni5 and uni6)

We want to measure the phase difference between oscillations of Bz. and vz i.e. the vertical component of the B field and the plasma velocity respectively.
With the recent series of models this was challenging  for the following reasons:

* One of the drivers had multiple frequencies
* Driver had a damping factor
* The first model run uni1 did not have a damping factor but the amplitude was too low

[Solar washing machine model configurations](http://mikeg64.github.io/washing/machine/update/2020/10/03/model-washmc.html)


The model amplitude was set to aa=10.0

* For model uni5 amplitude set to aa/2 i.e. aa=5
* For model uni6 amplitude set to 2aa ii aa=20

The revised input files for this run are linked on git below

git commit id[8247a1dcf99140dbbef1f32e7d7ed08564672761](https://github.com/mikeg64/smaug_wash/commit/8247a1dcf99140dbbef1f32e7d7ed08564672761)

When converting the output files to an ascii format for input we used an IDL script.

 
[make_ini_file_3D_bintoascii.pro](https://github.com/mikeg64/smaug_wash/blob/master/Idl/make_ini_file_3D_bintoascii.pro).
After editing the file names in the idl script this is run from the idl prompt using:

.r make_ini_file_3D_bintoascii

TODO: write script in matlab/python to do the conversion [matlab/python - code convert iput file formats](https://trello.com/c/GVPcXs0A/21-matlab-python-code-convert-iput-file-formats)




