---
layout: post
title:  "Solar Washing Machine Movies of Model Evolution (1)"
date:   2020-10-13 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug configuration matlab movies
---
In this post we describe the configurations used for the solar washing machine simulations. We consider 


# uni1

## Velocity slice with velocity quiver


[![rhosecs-vquiv](https://drive.google.com/uc?export=view&id=1FGPalJfnkLemhIh833kqYk1H6uvqfaWc)](https://drive.google.com/file/d/1FGPalJfnkLemhIh833kqYk1H6uvqfaWc/view?usp=sharing)


## Velocity slices at different layers - vertical

[![3d_vsecs_v](https://drive.google.com/uc?export=view&id=1FJncyQVUK_Jh0S6QJjy3GRTeJFEV6Ojr)](https://drive.google.com/file/d/1EWXHqH6VpKOwrelu_03YUhq6bFSfTDwL/view?usp=sharing)

## Velocity slices at different layers - radial

[![3d_vsecs_h](https://drive.google.com/uc?export=view&id=1FHD-lbETk-n5H44uZSw54YcdiMcxvD3w)](https://drive.google.com/file/d/1EbjIVR4EEDBb0FUnMK6isIR6c2MOhcIT/view?usp=sharing)



# uni2


## Velocity slice with velocity quiver


[![rhosecs-vquiv](https://drive.google.com/uc?export=view&id=1FM__MUfSVpoPRubFKt5Oxhjt6wU-s5FU)](https://drive.google.com/file/d/1EblJ-094zZ-l4EsmLzn3zD-EX_shxaQN/view?usp=sharing)


## Velocity slices at different layers - vertical

[![3d_vsecs_v](https://drive.google.com/uc?export=view&id=1Fh373sY1KSQTjP1Ez70_x-tAUjTfLUw5)](https://drive.google.com/file/d/1EiIihIB3S61R-kGloNgB-wNoBX19por_/view?usp=sharing)

## Velocity slices at different layers - radial

[![3d_vsecs_h](https://drive.google.com/uc?export=view&id=1FTIFcLPjMUl2OEDvn_yZgrnmDmJMRZUI)](https://drive.google.com/file/d/1EjRHvJiLQLrPHLfJFlHUnCLMU5BgvbWz/view?usp=sharing)





# uni3


## Velocity slice with velocity quiver


[![rhosecs-vquiv](https://drive.google.com/uc?export=view&id=1Fnf85zc9mQPF8SckRNKI5n8D4b83ONlR)](https://drive.google.com/file/d/1Es-Z9xFAw8HMojYI6xByk-9djWkdYPTu/view?usp=sharing)






## Velocity slices at different layers - vertical

[![3d_vsecs_v](https://drive.google.com/uc?export=view&id=1FqIUqC0y6HZ1HN9AWOOjK3DaZFEIElms)](https://drive.google.com/file/d/1EtCPB11RLyGbqX8VuX0_QuccKse10pgG/view?usp=sharing)






## Velocity slices at different layers - radial

[![3d_vsecs_h](https://drive.google.com/uc?export=view&id=1FpbCYDpTvkFNuSoAUeT5fW4yXOMSidRX)](https://drive.google.com/file/d/1Eui0p8tJYCyfxOIHTYOLP1Ru3KYWinVz/view?usp=sharing)






# uni4


## Velocity slice with velocity quiver


[![rhosecs-vquiv](https://drive.google.com/uc?export=view&id=1G66eIep2PJBFt6zCZeWem3ho203a0czB)](https://drive.google.com/file/d/1F8nUZNeka_dLl0CUDEqRqSgjDqheSwjN/view?usp=sharing)





## Velocity slices at different layers - vertical

[![3d_vsecs_v](https://drive.google.com/uc?export=view&id=1G3RENP21WlUojpm3WAvmN6Awr3o-LdCV)](https://drive.google.com/file/d/1Ezw5AAyv6GRNNUnhfIp_mBQJnbCnXEf5/view?usp=sharing)





## Velocity slices at different layers - radial

[![3d_vsecs_h](https://drive.google.com/uc?export=view&id=1Fx-X8B1sojGTkhWWsdXcJMbYDOOaGgUQ)](https://drive.google.com/file/d/1Ezw5AAyv6GRNNUnhfIp_mBQJnbCnXEf5/view?usp=sharing)




## Pictures with hyperlinks in markdown

![pic](https://drive.google.com/uc?export=view&id=1FGPalJfnkLemhIh833kqYk1H6uvqfaWc)  

Copy the link to share and you will have something like
https://drive.google.com/file/d/<FILE_ID>/view?usp=sharing

Copy the <FILE_ID> to make a link like this:
https://drive.google.com/uc?export=view&id=<FILE_ID>

Insert image in Markdown as ususal using the link from step 4.
For example: ![image](https://drive.google.com/uc?export=view&id=<FILE_ID>)




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





