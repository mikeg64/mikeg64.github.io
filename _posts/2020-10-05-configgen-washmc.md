---
layout: post
title:  "Solar Washing Machine Model Configurations"
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

testgeneratefield
testsac3dread
testsac3dwrite






