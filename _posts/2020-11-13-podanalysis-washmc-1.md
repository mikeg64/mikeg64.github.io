---
layout: post
title:  "Analysis of Washing Machine Simulation Using Proper Orthogonal Decomposition"
date:   2020-11-13 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine  analysis matlab POD
---


# Analysis of Washing Machine Simulation Using Proper Orthogonal Decomposition

Describe methods used to analyse wave components for washing machine simulations.

We want to measure the phase difference between oscillations of Bz. and vz i.e. the vertical component of the B field and the plasma velocity respectively.
With the recent series of models this was challenging  for the following reasons:

* One of the drivers had multiple frequencies
* Driver had a damping factor
* The first model run uni1 did not have a damping factor but the amplitude was too low



## Background Information and Papers


1. [A Tutorial on the Proper Orthogonal Decomposition](https://arc.aiaa.org/doi/10.2514/6.2019-3333)
2. [Proper Orthogonal and Dynamic Mode Decomposition of Sunspot Data](https://ui.adsabs.harvard.edu/abs/2020arXiv201008530A/abstract)


## Matlab Scripts

First generate sections of data for example the vertical component of the velocity and the z component of the B field using
* [pvertvvt.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pvertvvt.m)

Using matlab script described in reference 1  generate amplitudes for series of mode components.
* [pod.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/pod.m)

Simple line plots to compare amplitudes for different components at a given time step 
* [podtest.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podtest.m)

Four plots comparing the slices for vz and Bz, generate surface plots here
* [podsurftest.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podsurftest.m)

Use the amplitudes from the pod analysis to regenerate the signal and plot the surface
* [podregen.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podregen.m)



Using the matlab [AppDesigner](https://uk.mathworks.com/help/matlab/creating_guis/create-a-simple-app-or-gui-using-app-designer.html) to create a simple visualisation experiment to investigate mode decomposition different time steps. This was based on the tutorial application but rapidly developed and very effective.

* [tutorialApp.mlapp](https://github.com/mikeg64/smaug_wash/blob/master/matlab/appdes/tutorialApp.mlapp)  

See the earlier post for details of the time-dist plot outputs, [Solar Washing Machine Distance Time Plots (2)](https://github.com/mikeg64/smaug_wash/blob/master/matlab/podtest2.m).
















