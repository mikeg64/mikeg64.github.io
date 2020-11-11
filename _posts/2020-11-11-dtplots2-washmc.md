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


| matlab script      | mat file variable name | notes   | output file |
|-------------------|:--------------|:--------------:|--------------:|
| [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m) | evelv2Mm_v,1Mm_v, p5Mm_v  |v_z vertical sections 62, 31,15 (2Mm, 1Mm, 0.5Mm)  | hhzverustime.mat|
| [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m) | evelv2Mm_bz,1Mm_bz, p5Mm_bz  |b_z vertical sections 62, 31,15 (2Mm, 1Mm, 0.5Mm)  | hhzverustime.mat|
| [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m) | evelchrom_vh, eveltran_vh, evelcor_vh  |v_z horizontal sections 20,42,90  | hhzverustime.mat|
| [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m) | evelchrom_bz, eveltran_bz, evelcor_bz  |bz horizontal sections 20,42,90  | hhzverustime.mat|
|  [pvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvvt.m)          | evelv2Mm_v,1Mm_v, p5Mm_v      |v vertical sections 62, 31,15 (2Mm, 1Mm, 0.5Mm) magnitude of speed       | hmagverustime.mat      |





evelchrom_vh, eveltran_vh, evelcor_vh


# Pictures

## uni1


![dt-vz](https://drive.google.com/uc?export=view&id=1GEuEd4plu077lkQhz9eVC2FRjoQDaPEz)  




## uni2


![dt-vz](https://drive.google.com/uc?export=view&id=1GFQOlMX5TRwUvrhmBWMHQ4anzO4lwOCy)  



## uni3


![dt-vz](https://drive.google.com/uc?export=view&id=1GP_aFpk_IYNkKvS3rSSJIq1Awgkldaa6)  


## uni4


![dt-vz](https://drive.google.com/uc?export=view&id=1GSHOrLjqDcM4Iap2fcpO5gwUh3IgZcPM)  


