---
layout: post
title:  "Solar Washing Machine Movies of Model Evolution (2)"
date:   2021-01-24 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug configuration matlab movies
---
In this post we describe the configurations used for the solar washing machine simulations. We consider 

# Matlab routines  used to generate sections

The following matlab routine was used to generate videos illustrating the variation of the  vertical component of the plasma flow velocity  in the model

*  [plotsecs_array.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/plotsecs_array.m) used to generate Velocity slice with velocity quiver. (rhosecs_vquiv)


This is git commit [https://github.com/mikeg64/smaug_wash/commit/21b55d398b43195b3ffec5f7974bdbccc7d97108](https://github.com/mikeg64/smaug_wash/commit/21b55d398b43195b3ffec5f7974bdbccc7d97108)
Colours show plasma velocity magnitude at 3rd layer of the model i.e. taken perpendicular to the x-axis, contours show the perturbed magnetic field magnitude quiver arrows indicate the plasma velocity. 

# Method

The results presented here were generated from the configurations uni1, uni5 and uni6 described at:
[Solar Washing Machine Single Frequency Driver Rerun 2](http://mikeg64.github.io/washing/machine/update/2020/11/11/uni1singlefreq-washmc-2.html).

For this series of runs  the driver amplitude was varied.

 * uni1 aa=10m/s
 * uni5  aa=5m/s
 * uni6 aa=20m/s

We used the matlab routine  [plotsecs_array.m](https://github.com/mikeg64/smaug_wash/blob/master/matlab/plotsecs_array.m) to generate  the plots for all timesteps.

The results display clear evidence of MHD waves.

# Results

## uni1

### 3d view of vertical component of velocity

 [![3d-secs-v](https://drive.google.com/uc?export=view&id=1-ofQsbT_YFBFP2VAEjdpYLjm7fzmzdyG)](https://drive.google.com/file/d/1gTjlA-HIZUPFth3i0FnQjElhRDV1HLj0/view?usp=sharing)


## uni5

### 3d view of vertical component of velocity

 [![3d-secs-v](https://drive.google.com/uc?export=view&id=1OepZqkjQbQzRHyiWAkKZz7DlqPWVnNmR)](https://drive.google.com/file/d/1qWC0OTNSd3YvFpMeBfDNmidypEChe1yP/view?usp=sharing)

### 2d view showing mutually perpendicular slices  and the B field magnitude, lower figure shows a horizontal slice at the bae of the model

 [![2d-secs-mags](https://drive.google.com/uc?export=view&id=1qaabNWqHgKu3nr441QJ3aIaPfn9yvvSR)](https://drive.google.com/file/d/149FRejXsdvTyUlzpS7E7TGiJxhEbjyhj/view?usp=sharing)



## uni6

### 3d view of vertical component of velocity

 [![3d-secs-v](https://drive.google.com/uc?export=view&id=16XUofhcO6RpoEniDoprPrAn2OTUxPzNA)](https://drive.google.com/file/d/145iU3aV7FrW8ZV_W9ElSUA2fZjrIBPY8/view?usp=sharing)

### 2d view showing mutually perpendicular slices  and the B field magnitude, lower figure shows a horizontal slice at the bae of the model

 [![2d-secs-mags](https://drive.google.com/uc?export=view&id=17c29VYA05VPScr4gST3Qj_9Yf3jp0qgF)](https://drive.google.com/file/d/1UqvwW9Vu126W45BDwyPJwMU2yXOG3jBH/view?usp=sharing)





The magnetic field movies illustrate kink motions of the magnetic flux tube, along with a propagating wavefront. This was revealed after some data exploration using [paraview](https://www.paraview.org/). We illustrate some results generated using paraview and describe the techniques used.


## Pictures with hyperlinks in markdown

![pic](https://drive.google.com/uc?export=view&id=1FGPalJfnkLemhIh833kqYk1H6uvqfaWc)  

Copy the link to share and you will have something like
https://drive.google.com/file/d/<FILE_ID>/view?usp=sharing

Copy the <FILE_ID> to make a link like this:
https://drive.google.com/uc?export=view&id=<FILE_ID>

Insert image in Markdown as ususal using the link from step 4.
For example: ![image](https://drive.google.com/uc?export=view&id=<FILE_ID>)





