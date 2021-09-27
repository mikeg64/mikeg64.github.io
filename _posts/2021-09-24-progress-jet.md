---
layout: post
title:  "Progress Solar Jet Model 2"
date:   2021-09-24 15:11:28 +0100
categories: Jet Update
tags: jet simulation smaug
---
# Progress Update 24/9/2021

We outlined the simulations in the project description "[Solar Jets](http://mikeg64.github.io/projects/2021-07-30-Solar-jet-bede.html)"

All the simulations and models are detailed on git hub these are the 
[smaug_jet@github](https://github.com/mikeg64/smaug_jet)


Three checkins were made which have working and correctly configured scripts for running smaug with a point driver model in as solar atmosphere. There was a number of errors in the configuration file

* The model dimensions and simulation box size had been set incorrectly
* A define parameter to call the user source file had not been set up and the driver term was not called
* There simulation exhibited edge features
* Gravity was set in the wrong direction!

The following modifications were made

* [adding a second p-mode test model - github ](https://github.com/mikeg64/smaug_jet/commit/298768ec748a1efb0ab417ae0720a57ab200fd26)

* [edits to call model correctly](https://github.com/mikeg64/smaug_jet/commit/298768ec748a1efb0ab417ae0720a57ab200fd26)
* [Continuous boundary conditions set correctly ](https://github.com/mikeg64/smaug_jet/commit/ec3b071c4f79ecef4012fe4d052d5701982e4ddc)

The following flags were used in the file make_inputs_bede

`CUDACCFLAGS = --ptxas-options=-v -gencode=arch=compute_70,code=sm_70 -gencode=arch=compute_70,code=compute_70  -maxrregcount=32 -DUSE_SAC -DUSE_USERSOURCE`

`CCFLAGS = -DUSE_SAC -DD1D -DUSE_USERSOURCE`

In the include file iosmaugparams_jet_hydro2.h, the dx and dy values were defined as follows (note the n-1 term where n includes the ghost cells)

`real dx = (xmax-xmin)/(ni-1);`

In the file boundary_jet_hydro.cu the functions for calling continuous boundary conditions were updated. The continuos BC's are called using the cuda kernel function 

`__global__ void boundary0_cont_parallel(struct params *p, struct bparams *bp, struct state *s,  real *wmod, int order, int dir, int field)`

For the 2D model the key lines are as follows:

    `           if((i==0 || i==1) )              
                    wmod[  shift+encode3_b(p,i,j,k,f)]=wmod[  shift+encode3_b(p,3,j,k,f)];             
                else if((( i==((p->n[0])-1)   )) )               
                    wmod[  shift+encode3_b(p,i,j,k,f)]=wmod[  shift+encode3_b(p,(p->n[0])-3,j,k,f)];
                else if(((  i==((p->n[0])-2) ))  )               
                    wmod[  shift+encode3_b(p,i,j,k,f)]=wmod[  shift+encode3_b(p,(p->n[0])-3,j,k,f)]; `

The lines above set the values in the ghost cell regions to be identical to the values at the true edge of the model.

The final modification was to change the dimensions. This model comprises 1024 cells in the vertical (y direction) and 2048 cells across the box ( x direction). The box size is 8nmx8nm.

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
