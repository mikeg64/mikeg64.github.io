---
layout: post
title:  "Solar Washing Machine Model Atmosphere and Field Generation"
date:   2020-10-05 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug configuration matlab
---
In this post we describe the configurations used for the solar washing machine simulations. We consider 


1. a model atmosphere which is gravitationally stratified and based on the [VAL IIIc model](https://www.researchgate.net/figure/Density-and-temperature-profiles-as-functions-of-height-z-These-profiles-are-constructed_fig8_44195124)..
2. An idealised flux tube model.

We outlined the simulations in the project description "[Solar Washing Machine](http://mikeg64.github.io/projects/2020-10-02-Solar-Washing-Machine.html)"

All the simulations and models are detailed on git hub
[smaug_wash@github](https://github.com/mikeg64/smaug_wash)

---
# Configuration Generation


Creating atmospheric profiles

We used the solar atmosphere profiles of [Vernazza, J. E., Avrett, E. H., & Loeser](https://ui.adsabs.harvard.edu/abs/1981ApJS...45..635V/abstract)
The data from the valIIIc and [McWhirter](https://ui.adsabs.harvard.edu/abs/1975A%26A....40...63M/abstract) model is contained in [atmos.xls](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/atmos.xls)

The table in atmos.xls has 4 columns described as follows:
1. atmospheric height (m)
2. Temperature (K)
3. Density (kg/m^3)
4. Pressure

The following matlab files use this model data to generate the atmospheric 

1. An idealised flux tube model [createmodel_uniformdensity_vertmagfluxtube.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/createmodel_uniformdensity_vertmagfluxtube.m)
2. a model atmosphere which is gravitationally stratified and based on VAL IIIc [createextatmosmodel.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/createextatmosmodel.m)

we also use the hdf inspired data structures

Main routines to use here are
createmodel - uses valiiic data to interpolate between photosphere and 6Mm
createextmodel  - uses valiiic data to interpolate between photosphere and 6Mm. Use data fitting to extrapolate data
                  to corona upto 12Mm

Both of these routines can call generatefield
generatefield  - build magnetic flux tube uses hydrostatic pressure balance to compute correct pressure and energy for the model


The field generation routines are based on IDL routines which were used to generate the configurations for some of the earlier simulation work with gravitationally stratified solar atmospheres.

[Oscillatory Response of the 3D Solar Atmosphere to the Leakage of Photospheric Motion](https://ui.adsabs.harvard.edu/abs/2009SoPh..258..219F/abstract)

[Three-dimensional Simulations of Magnetohydrodynamic Waves in Magnetized Solar Atmosphere](https://ui.adsabs.harvard.edu/abs/2012ApJ...755...18V/abstract)

The original IDL code is available at 
[B_field_3D_tube.pro](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/idl/B_field_3D_tube.pro)
[B_field_3D_vertical.pro](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/idl/B_field_3D_vertical.pro)
[B_field_vertical_tube.pro](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/idl/B_field_vertical_tube.pro)

These are for the case of a flux tube, a uniform vertical field and a vertical tube.

The codes construct the fields in such a way as to maintain hydrostatic balance. See for example our post 
[magnetohydrostatic equlibria](http://solarwavetheory.blogspot.com/2013/11/solar-atmospheric-mhd-flux-tube.html)

[testgeneratefield](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/testgeneratefield.m)
[testsac3dread](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/testwritesac3d.m)
[testsac3dwrite](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/testwritesac3d.m)


For the simulations consider here labelled with the prefix uni1, uni2, uni3 and uni4 we used the matlab code [createmodel_uniformdensity_vertmagfluxtube.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/createmodel_uniformdensity_vertmagfluxtube.m) this code generates a uniform cylindrical vertical field with a uniform density. The density is 0.0001 outside the tube and 0.0002 inside the tube. We generated a configuration with a maximum field of 1.5kG
[generatefield_verttube_rhouni.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/solatmoswaves/generatefield_verttube_rhouni.m)





