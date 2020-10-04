---
layout: post
title:  "Solar Washing Machine Model Configurations"
date:   2020-10-03 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug
---
In this post we describe the smaug models and the set up of each of the simulations

We outlined the simulations in the project description "[Solar Washing Machine](http://mikeg64.github.io/projects/2020-10-02-Solar-Washing-Machine.html)"

All the simulations and models are detailed on git hub
[smaug_wash@github](https://github.com/mikeg64/smaug_wash)

---
# Model Parameters 

## Model Dimensions and Driver Location

For example see: [Model include file](https://github.com/mikeg64/smaug_wash/blob/master/include/iosmaugparams.washing_mach_180_h12p5Mm_kg_uni1.h)
 
| Name          | Value |   Notes|
|------------------------------|--------------------------|
| xc1 | 0.5 Mm        |Driver location |
| xc2                | 1.27 Mm           |     |
| xc3                | 1.27 Mm          |     |
|xmax. | 12.8496 Mm  |Model dimensions  (maximum)|
|ymaz  | 2.56 Mm  |.  |
|zmax.  |2.56 Mm    |.  |
|xmin | 0.2057 Mm  |Model dimensions  (minimum)|
|ymin | 0.04098 Mm  |.  |
|zmin |0.04098 Mm    |.  |
|n1,n2,n3  | 128,128,128    |Number of mesh elements for each dimension |


## Driver Parameters

For example : [Driver source file](https://github.com/mikeg64/smaug_wash/blob/master/src/usersource.washing_mach_180_h12p5Mm_kg_uni1.cu)

| Name          | Value |   Notes|
|------------------------------|--------------------------|
| aa | 0.1 m/s        |Amplitude |
| s_period | 180 s       |Driver period |
| tdep | 1        | Switches tdepenedence on/off |
| dx,dy,dz | 0.5,0.5,0.25Mm       | Gaussian width of driver |


Driver amplitude

<img src="https://render.githubusercontent.com/render/math?math=amp=aa.\exp{(-\frac{x^2}{dx^2})}\times\exp{(-\frac{y^2}{dy^2})}\times\exp{(-\frac{z^2}{dz^2})}">

<img src="https://render.githubusercontent.com/render/math?math=tdepx=\sin{\frac{2\pi t}{T}}">

<img src="https://render.githubusercontent.com/render/math?math=tdepy=\sin{\frac{2\pi (t-0.25T)}{T}}">

## Veloc

<img src="https://render.githubusercontent.com/render/math?math=v_x=amp \times tdepx">

<img src="https://render.githubusercontent.com/render/math?math=v_y=amp \times tdepy">


### uni2

<img src="https://render.githubusercontent.com/render/math?math=aa= aa\times\exp{\frac{-(t-582)}{90}}">


### uni3

<img src="https://render.githubusercontent.com/render/math?math=aa= aa\times\exp{\frac{-(t-120.5)}{90}}">



### uni4

<img src="https://render.githubusercontent.com/render/math?math=tdepx=\sin{\frac{2\pi t}{T}}%2B\sin{\frac{2\pi t}{T_2}}%2B\sin{\frac{2\pi t}{T_3}}">

<img src="https://render.githubusercontent.com/render/math?math=tdepy=\sin{\frac{2\pi (t-0.25T)}{T}}%2B\sin{\frac{2\pi (t-0.25T_2)}{T_2}}%2B\sin{\frac{2\pi (t-0.25T_3)}{T_3}}">

<img src="https://render.githubusercontent.com/render/math?math=aa= aa\times\exp{\frac{-(t-120.5)}{90}}">


## Rendering examples

Note use %2B to represent +

<img src="https://render.githubusercontent.com/render/math?math=e^{i %2B\pi} =x%2B1">

## LaTeX
$$x_{1,2} = {-b\pm\sqrt{b^2 - 4ac} \over 2a}.$$


This math is inline $`a^2+b^2=c^2`$.

This is on a separate line

```math
a^2+b^2=c^2
```

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
