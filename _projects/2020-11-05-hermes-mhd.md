---
layout: post
title: "Hermes: SAC Implementation Using Athena"
date: "2020-11-05"
tags:
 SAC SMAUG Athena MHD
---




# Hermes
Using athena as a basis for implementation of SAC and SMAUG


Magnetohydrodynamic code for gravitationally-stratified media : SAC
http://adsabs.harvard.edu/abs/2008A%26A...486..655S

A Fast MHD Code for Gravitationally Stratified Media using Graphical Processing Units: SMAUG
http://eprints.whiterose.ac.uk/86864/

Athena: A New Code for Astrophysical MHD
http://arxiv.org/abs/0804.0402

Objectives:
===========

1.  Improve software engineering and enhance software sustainability
2.  Build in perturbed MHD using Athena CTU method
3.  Implement perturbed MHD with central differencing and hyperdiffusion (i.e. SAC)
4.  Integrate GPU code for CTU method re. [Wasiljew & Murawski] (http://kft.umcs.lublin.pl/kmur/download/papers/2013/Wasiljew_Murawski_2013.pdf)
5.  Integrate SMAUG
6.  Exploit SMR implementation in SAC/SMAUG
7.  Use multi-architectural approach (hybrid multi-core accelerator approach) [targetDP](http://arxiv.org/abs/1405.6162)




BKG  used to define problem including background fields
SAC_INTEGRATOR   sac integrator for use with background fields

Next job to compile with SAC_INTEGRATOR, BKG and SAC_FLUX

./configure --with-problem=shkset1d --enable-bkg --with-integrator=sac --with-flux=sac

./configure  --with-problem=orszag-tang --with-order=3 --enable-bkg --with-integrator=sac --with-flux=sac

./configure --with-gas=hydro --with-problem=shkset1d  --enable-bkg --with-integrator=sac --with-flux=sac

./configure --with-gas=hydro --with-problem=shkset1d  --enable-bkg --with-integrator=smaug --with-flux=smaug --enable-smaug

./configure --with-problem=orszag-tang --with-order=3 --enable-bkg --with-integrator=smaug --with-flux=smaug --enable-smaug

all of the above problems will define USE_SAC  3D problems must include --enable-sac-3d  this will activate USE_SAC_3D instead of USE_SAC

./configure --with-problem=orszag-tang --with-order=3 --enable-bkg --with-integrator=smaug --with-flux=smaug --enable-smaug

Helpful Links with Athena
=========================

Source code description
http://www.astro.princeton.edu/~jstone/Athena/doxygen/html.with_source/annotated.html


Configuring and setting up Athena
https://trac.princeton.edu/Athena/wiki/AthenaDocsUGConfigure

Configuring Integrators
https://trac.princeton.edu/Athena/wiki/AthenaDocsUGInt

Quickstart
https://trac.princeton.edu/Athena/wiki/AthenaDocsTutQuickStart

1D Sod Shock tube test (HD)
https://trac.princeton.edu/Athena/wiki/AthenaDocsTutSod

2D Orszag-Tang Test (MHD)
https://trac.princeton.edu/Athena/wiki/AthenaDocsTutOT1






# p-Mode Oscillations in Highly Gravitationally Stratified Magnetic Solar Atmospheres





## Background

Observational, theoretical and computational studies of the sun reveal a diversity of  structures and complex dynamics. This is clearly revealed by imagery from solar telescopes. The culmination of studies of the dynamics of the coronal loop structures  in the solar atmosphere and in the solar chromosphere has developed our understanding of the range of different magnetic field structures. The images from SDO in nine AIA passbands (\ref{sdoaia}) display some of these structures such as active regions, coronal holes and quiet regions. Despite our armoury of observations and diverse range of computational models it still remains a challenge to make sense of this complex menagerie of dynamical structures, understand solar coronal heating and more generally space weather phenomena. Development of our understanding requires computational models enabling us to study the relationship between structures in the solar atmosphere and the continual dynamical processes.

We report on the results of numerical simulations of photospheric p-mode oscillations in a model solar atmosphere with a uniform and vertical magnetic field. First, we consider the variety of magnetic structures in the solar atmosphere and review the wave motions which are observed in these regions. This is followed with a description of the solar atmospheric model, magnetic field configuration and the simulation method we used to model p-mode oscillations in a model magnetic solar atmosphere.


## References




1. [project description and tracking trello](https://trello.com/c/AOyAs8To/19-pmode-vertical-fields)
2. [Github repository](https://github.com/mikeg64/smaug_realpmode)
3. [overleaf - pmode paper](https://www.overleaf.com/project/5ef5e8bd0e1c36000168dc8e)
4. [p-mode paper on google](https://drive.google.com/drive/folders/13H8wj1_HqDwlEV5Df_8EUNqaCZ_6w6p0)
5. [p-mode paper pdf](https://drive.google.com/file/d/13BynIop0q0L5KsiLEm9aAU2lJHhJVKN5/view?usp=sharing)
6. [paper library harvard ads](https://ui.adsabs.harvard.edu/user/libraries/Tdy1OxdTQgyZvRlUIMZFYg)
7. [p-Mode Oscillations in Highly Gravitationally Stratified Magnetic Solar Atmospheres - blogpost notes](http://solarwavetheory.blogspot.com/2018/03/p-mode-oscillations-in-magnetic-solar.html)
8. [p-modes hydrodynamics - github repo.](https://github.com/mikeg64/smaug_pmode)
9. [Solar Atmosphere Wave Dynamics Generated by Solar Global Oscillating Eigenmodes](http://solarwavetheory.blogspot.com/2017/12/solar-atmosphere-wave-dynamics.html)
10. [Solar Atmosphere Wave Dynamics Generated by Solar Global Oscillating Eigenmodes](https://drive.google.com/file/d/1za41jar2NaYe1IsK-yNroG1YZhQVs9bW/view)
11. [Solar atmosphere wave dynamics generated by solar global oscillating eigenmodes:https://doi.org/10.1016/j.asr.2017.10.053](https://www.sciencedirect.com/science/article/pii/S0273117717307925?via%3Dihub)

[name](http://link.lk)



