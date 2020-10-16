---
layout: post
title:  "Solar Washing Machine Distance Time Plots (1)"
date:   2020-10-14 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug configuration matlab d-t
---
In this post we describe the configurations used for the solar washing machine simulations. We consider 

# Matlab routines  used to generate distance-time plots

* [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m) evelv2Mm_v,1Mm_v, p5Mm_v v_z vertical sections 62, 31,15 (2Mm, 1Mm, 0.5Mm) saved as hhzverustime.mat
* [pvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvvt.m)  evelv2Mm_v,1Mm_v, p5Mm_v v vertical sections 62, 31,15 (2Mm, 1Mm, 0.5Mm) magnitude of speed. saved as hmagverustime.mat


## test
The following matlab routines were used to generate videos illustrating the variation fo plasma field flow in the model

*  [plotsecs_densslice_vecarrows_array.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/plotsecs_densslice_vecarrows_array.m) used to generate Velocity slice with velocity quiver. (rhosecs_vquiv)
* [iplotsecs_array_v.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/plotsecs_array_v.m) used to generate velocity slices at different layers for vertical component
* [iplotsecs_array_h.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/plotsecs_array_h.m) used to generate velocity slices at different layers for radial component



# [plotsecs_densslice_vecarrows_array.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/plotsecs_densslice_vecarrows_array.m) 

This is git commit [https://github.com/mikeg64/smaug_wash/commit/fe2f1f2079ef905b5e4d205fc9d31a12057039ac](https://github.com/mikeg64/smaug_wash/commit/fe2f1f2079ef905b5e4d205fc9d31a12057039ac)
Colours show plasma velocity magnitude at 3rd layer of the model i.e. taken perpendicular to the x-axis, contours show the perturbed magnetic field magnitude quiver arrows indicate the plasma velocity. 







