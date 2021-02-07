---
layout: post
title:  "Analysis of Washing Machine Simulation Using Proper Orthogonal Decomposition:Part 2"
date:   2021-02-03 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine  analysis matlab POD
---


# Analysis of Washing Machine Simulation Using Proper Orthogonal Decomposition

Objective: Describe the methods used to analyse the wave components for washing machine simulations.

In this post I describe further work for analysing the signals generated using the "Washing Machine" simulations.
* We use the pod analysis to explore modes of interest
* Reconstruction is used to compare the mode to the original/full symbol
* FFT analysis is applied to the reconstructed mode and signal frequencies verified


# Matlab Scripts

As well as the additional scripts described in [part 1](http://mikeg64.github.io/washing/machine/update/2020/11/13/podanalysis-washmc-1.html) we developed an additional script 

1. [fftorig.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/fftorig.m)

2. [reconstruct_pod.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/reconstruct_pod.m)

First generate sections of data for example the vertical component of the velocity and the z component of the B field using
3. [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m)

Using matlab script described in reference 1  generate amplitudes for series of mode components.
4. [pod.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pod.m)

Simple line plots to compare amplitudes for different components at a given time step 
5. [podtest.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podtest.m)

Four plots comparing the slices for vz and Bz, generate surface plots here
6. [podsurftest.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podsurftest.m)

Use the amplitudes from the pod analysis to regenerate the signal and plot the surface
7. [podregen.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podregen.m)




# Initial Fourier Analysis


Given that we use routine  [3](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m) to generate time profile for each chunk of data. The Fourier transform  for each section through the model, was computed for a point in the box at a height of 1.0Mm (20 grid units) through the chromosphere.  Given that we have square sections the result is the FFT of the data at a given height (1.0Mm) at the middle of the box (1.16Mm, i.e. 36 units across) the FFT is computed at each point across the remaining dimension of the box, these will correspond to individual modes when POD analysis is undertaken.

The FFT's were generated using the routine [fftorig.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/fftorig.m).

The results of the FFT are shown below.

For the uni6 model (driver amplitude aa=20 m/s). (see [Solar Washing Machine Single Frequency Driver Rerun 2](http://mikeg64.github.io/washing/machine/update/2020/11/11/uni1singlefreq-washmc-2.html)


![pic](https://drive.google.com/uc?export=view&id=1Yoiu6UzceD4hOrqKWPq-ABD3yGOhkVnT)  



For the uni5 model (driver amplitude aa=5 m/s)

![pic](https://drive.google.com/uc?export=view&id=1VAv7pstUgjIbaPnmNoyl2myXSLZqR2Df)  




For the uni1 model (driver amplitude aa=10 m/s)

![pic](https://drive.google.com/uc?export=view&id=1861xkZP-zKqoT3P8iwLgBagmHAP0tFRK)  


The results exhibit a strong peak corresponding to the driver but there is clear evidence of other frequencies which are now investigated using POD analysis.

# POD Analysis

Using the matlab [AppDesigner](https://uk.mathworks.com/help/matlab/creating_guis/create-a-simple-app-or-gui-using-app-designer.html) to create a simple visualisation experiment to investigate mode decomposition different time steps. This was based on the tutorial application but rapidly developed and very effective.

* [tutorialApp.mlapp](https://github.com/mikeg64/smaug_wash/blob/master/matlab/appdes/tutorialApp.mlapp)  

See the earlier post for details of the time-dist plot outputs, [Solar Washing Machine Distance Time Plots (2)](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podtest2.m).

We use pod analysis to identify the different modes,  fft's on reconstructed modes are used to compute the frequencies for these modes
include the dominant mode with a frequency close to that of the driver [pod.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pod.m)




















