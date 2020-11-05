---
layout: post
title: "Hermes: SAC Implementation Using Athena"
date: "2020-11-05"
tags:
 SAC SMAUG Athena MHD
---




# Hermes
Using athena as a basis for implementation of SAC and SMAUG


[Magnetohydrodynamic code for gravitationally-stratified media : SAC](http://adsabs.harvard.edu/abs/2008A%26A...486..655S)

[A Fast MHD Code for Gravitationally Stratified Media using Graphical Processing Units: SMAUG](http://eprints.whiterose.ac.uk/86864/)

[Athena: A New Code for Astrophysical MHD](http://arxiv.org/abs/0804.0402)

Objectives:
===========

1.  Improve software engineering and enhance software sustainability
2.  Build in perturbed MHD using Athena CTU method
3.  Implement perturbed MHD with central differencing and hyperdiffusion (i.e. SAC)
4.  Integrate GPU code for CTU method re. [Wasiljew & Murawski](http://kft.umcs.lublin.pl/kmur/download/papers/2013/Wasiljew_Murawski_2013.pdf)
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

[Source code description](http://www.astro.princeton.edu/~jstone/Athena/doxygen/html.with_source/annotated.html)

[AthenaMHDCode](https://princetonuniversity.github.io/Athena-Cversion/)

[Configuring and setting up Athena](https://trac.princeton.edu/Athena/wiki/AthenaDocsUGConfigure)

[Configuring and setting up Athena](https://princetonuniversity.github.io/Athena-Cversion/AthenaDocsUGConfigure)

[Configuring Integrators](https://princetonuniversity.github.io/Athena-Cversion/AthenaDocsUGInt)

[Quickstart](https://princetonuniversity.github.io/Athena-Cversion/AthenaDocsTutQuickStart)

[1D Sod Shock tube test (HD)](https://princetonuniversity.github.io/Athena-Cversion/AthenaDocsTutSod)

[2D Orszag-Tang Test (MHD)](https://princetonuniversity.github.io/Athena-Cversion/AthenaDocsTutOT1)

