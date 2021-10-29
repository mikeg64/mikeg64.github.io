---
layout: post
title:  "Solar Washing Machine Model Configurations - Part 2"
date:   2021-10-29 15:11:28 +0100
categories: Washing Machine Update
tags: washingmachine simulation smaug
---
In this post we describe the models which are being used for the final analysis.

We outlined the simulations in the project description "[Solar Washing Machine](http://mikeg64.github.io/projects/2020-10-02-Solar-Washing-Machine.html)"

We outlined the simulations in the project description "[Solar Washing Machine Model Configurations](http://mikeg64.github.io/washing/machine/update/2021/03/06/model-analysis-washmc.html)"


Initial model configurations were detailed at [Solar Washing Machine Model Configurations](http://mikeg64.github.io/washing/machine/update/2020/10/03/model-washmc.html) 

The configuration generation method was defined at
[Solar Washing Machine Model Atmosphere and Field Generation](http://mikeg64.github.io/washing/machine/update/2020/10/05/configgen-washmc.html)

All the simulations and models are detailed on git hub
[smaug_wash@github](https://github.com/mikeg64/smaug_wash)
Earlier simulations had been run with a solar gravitational field these exhibited an instability. Since we are modelling an idealized flux tube.
The simulations were re-run with 0 gravitational field


---

# Results Table

| Name          | Amplitude |  Mag Field (T) | hhverustime | data of last update  |data of run | 
|------------------------------|--------------------------|-------|-------|----|-----------|
| uni1                | 10      |.15 | y | 18/6/2021 |.   ?   |         
| uni5                | 5        |  .15   |.  y.   |  18/6/2021     |.     ?     |.     
| uni6                | 20      |   .15  |. y.  |  18/6/2021     |.   17/3/2021    |.      



---




| Name          | Amplitude |  Mag Field (T) | hhverustime | data of last update    | data of run | 
|------------------------------|--------------------------|-------|-------|----|-----------|
| uni8               | 20      |.0375 |.  y.  | 31/7/2021 | 3/4/2021   |.     
| uni6              | 20       |  .15   |.  y.   | 31/7/2021    | 3/4/2021     |.    
| uni10               | 20      |   .0755  |. n  | 18/6/2021    |.   ?    |.   




---




| Name          | Amplitude |  Mag Field (T) | hhverustime | data of last update   | data of run  | 
|------------------------------|--------------------------|-------|-------|----|-----------|
| uni11               | 10      |.0375 |.  y.  | 31/7/2021  |  3/4/2021  |.     
| uni9              | 10       |  .0755   |.  y.   | 31/7/2021    | 3/4/2021     |.      
| uni1               | 10      |   .15  |. y  | 18/6/2021      |     |.      




The uni5 configuration with amplitude 5 and magnetic field .15T was re-run. See the updated model file
[iosmaugparams_washing_mach_180_h12p5Mm_kg_uni5.h](https://github.com/mikeg64/smaug_wash/blob/master/include/iosmaugparams.washing_mach_180_h12p5Mm_kg_uni5.h)

Test uni9 was extracted from the archive with the objective of undertaking analysis.
Outputs were converted to hdf5 and the converted slices were stored in a .mat file  (hhverustime files)











## Rendering examples

<img src="https://render.githubusercontent.com/render/math?math=aa= aa\times\exp{\frac{-(t-120.5)}{90}}">



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
