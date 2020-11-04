---
layout: post
title:  "Solar Washing Machine Results Discussion 1"
date:   2020-11-04 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug results discussion
---


# Solar Washing Machine Results Discussion - Part 1


[name](http://link.lk)

[Coupled Alfvén and Kink Oscillations in Coronal Loops:Pascoe 2010](https://ui.adsabs.harvard.edu/abs/2010ApJ...711..990P/abstract)
[Propagating Wave Phenomena Detected in Observations and Simulations of the Lower Solar Atmosphere:Jess 2012](https://ui.adsabs.harvard.edu/abs/2012ApJ...746..183J/abstract)
[Proper Orthogonal and Dynamic Mode Decomposition of Sunspot Data:Albidah 2020](https://ui.adsabs.harvard.edu/abs/2020arXiv201008530A/abstract)
[Phase relations for seismology of photospheric flux tubes: Moreels 2013](https://ui.adsabs.harvard.edu/abs/2013A%26A...551A.137M/abstract)
[Oscillations and Waves in Sunspots: Khomenko 2015](https://ui.adsabs.harvard.edu/abs/2015LRSP...12....6K/abstract)

We want to measure the phase difference between oscillations of Bz. and vz i.e. the vertical component of the B field and the plasma velocity respectively.
With the recent series of models this was challenging  for the following reasons:

* One of the drivers had multiple frequencies
* Driver had a damping factor
* The first model run uni1 did not have a damping factor but the amplitude was too low

[Solar washing machine model configurations](http://mikeg64.github.io/washing/machine/update/2020/10/03/model-washmc.html)


The model amplitude was set to aa=10.0

The revised input files for this run are linked on git below

git commit id[da9600eab0e4b4c9766c72a376d9b6d996b60ea6](https://github.com/mikeg64/smaug_wash/commit/da9600eab0e4b4c9766c72a376d9b6d996b60ea6)

When converting the output files to an ascii format for input we used an IDL script.

 
[make_ini_file_3D_bintoascii.pro](https://github.com/mikeg64/smaug_wash/blob/master/Idl/make_ini_file_3D_bintoascii.pro).
After editing the file names in the idl script this is run from the idl prompt using:

.r make_ini_file_3D_bintoascii

TODO: write script in matlab/python to do the conversion [matlab/python - code convert iput file formats](https://trello.com/c/GVPcXs0A/21-matlab-python-code-convert-iput-file-formats)




