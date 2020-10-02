---
layout: post
title: "Solar Washing Machine"
date: "2020-10-02"
tags:
 washingmachine
---



# Background

Dave Jess  discovered in some observations a very interesting feature: solar washing machine :) 


We have a magnetic flux tube model (up to 1 Mm) which we used for [SMAUG](http://solarwavetheory.blogspot.com/2015/12/smaug-is-sheffield-magnetohydrodynamics.html) paper. 


Can you, pls, run a simulation with exactly the same solar atmosphere model but with a different driver?

Driver should be just a  superposition
of two slow kink waves with the same phase speed, but different polarisation  ( one 0 and second one shifted by pi/2) 
and a constant phase difference in time.

Practically this is one  + another horizontal driver (which we have used before).

## some details below 

The sunspot movie has been filtered  *both* spatially and temporally using the following parameters:

frequency = 2-4 minutes with the Gaussian peaking at 3 minutes
spatial size = 5-10 arcsecond size (to break the sunspot umbra up into ~4 quadrants)





The resulting movie (just a 10 minute cut-out from the time sequence) can be viewed here:
* [HARDcam_AR11371_Halpha_Spatially_Filtered](https://drive.google.com/file/d/1-0zbJYa93CcD5SBUAxNwGE-VYfuf5NUb/view?usp=sharing)

* [info about the hardcam ](https://star.pst.qub.ac.uk/wiki/doku.php/public/research_areas/solar_physics/hardcam)

* [Driver photos](https://drive.google.com/file/d/10UWz8XDMkziq2OAgOp6QAGAsC3NAb4be/view?usp=sharing)

*[ROSA_AR11371_continuum_Spatially_Filtered](https://drive.google.com/file/d/10N8hYYLCldx1jh12ZPjTzWDeePV1dDZI/view?usp=sharing)

* [Reconstructed data info](https://star.pst.qub.ac.uk/wiki/doku.php/public/research_areas/solar_physics/rosa_reconstructed_archive#section2011)


The green contour marks the umbra/penumbra boundary, and hopefully it’s obvious that strong-power oscillations are not only present in the umbra, but they also appear to rotate torsionally. This motion is much more apparent than in the previous spatially-unfiltered movies.





# Simulation Details
Washing machine  using smaug 
Washing Machine Simulation
Kink mode driver Driver
180s period
amplitude 20m/s
y-dir lags x-dir by 0.2 period

Driver gaussian width 0.1Mm (6 grid points)
Driver gaussian width (in height direction) 0.05Mm (3 grid points)

Flux tube 8gp wide at foot point
80G flux tube at foot point 
2.5G units at 64  0.8Mm

Flux tube width 0.1Mm

2x2x1.6Mm 128^3 grid points

[Magnetic Flux Tube - Kink Mode - Slow Branch 1 - Quarter Wavelength - Velocity Field](https://youtu.be/1NisZFw7ek4)

