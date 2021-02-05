---
layout: post
title:  "Solar Washing Machine Distance Time Plots (2)"
date:   2020-11-11 15:11:28 +0100
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


**Need to repeat the phase difference analysis  with uni5 and uni6 models i.e. for different amplitudes**

# Pictures for uni1 with amplitude 10m/s

## podtest2.m

[podtest2.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podtest2.m)

### evel

Using the findpeaks function in matlab to determine the frequency and phase shifts

Graphs show time (s) on the x axis and amplitude on the vertical axis. Amplitude for magnetic field perturbation has been multiplied by 10^5.


![p5Mm](https://drive.google.com/uc?export=view&id=1J7VkOAdGUrMlHC2hrbMT72cP7q6wQWws)  





![1Mm](https://drive.google.com/uc?export=view&id=1J8jIT8h1SgThGVly85jC26MK8-ucVu-F)  





![2Mm](https://drive.google.com/uc?export=view&id=1JFqW_WAPKapr9Ph3uDJ9Q5xH0fis_W94)  


### Positions of peaks

| component      | time (s) | time(s)   |  time(s) |
|-------------------|:--------------|:--------------:|
| vz| 144  | 332 | 520 |
| bz          | 161     | 358      | 529     |

### Periods

| component      | time (s) | time(s)   |  
|-------------------|:--------------|:--------------:|
| vz| 188  | 188 | 
| bz          | 197     | 171      | 

### Phase Difference (s)

Phase difference between the magnetic and vz wave

| component      | time (s) | time(s)   |  time(s) |
|-------------------|:--------------|:--------------:|
| phase difference| 17  | 26 | 9 | 

0.1 pi radian phase difference

## podsurftest.m

[podsurftest.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podsurftest.m)








Chromosphere

![chrom](https://drive.google.com/uc?export=view&id=1JG55dWBLDUV7DNqqkUyTf7c7Me88YdIq)  



Transition Layer

![tran](https://drive.google.com/uc?export=view&id=1JGUGiJscrJE_iclvd7P_7ntFc5sjVNJU)  


Corona

![cor](https://drive.google.com/uc?export=view&id=1JK95hKms2lZIKgxspQu-6BfFPHbg5P3u)  


### vertical slices





0.5Mm

![surf p5Mm](https://drive.google.com/uc?export=view&id=1JMgUrOO3XPZU3X5Df0d0SGC62JqmBCKq)  


1Mm

![tsurf 1Mm](https://drive.google.com/uc?export=view&id=1JPHPCrpr8kemKM9sm4UFWXdXmmf4jVU3)  


2Mm

![surf 2Mm](https://drive.google.com/uc?export=view&id=1JQaRv2p6dc0GDd2Gy8V2sO8JYQPVv0BL)  



