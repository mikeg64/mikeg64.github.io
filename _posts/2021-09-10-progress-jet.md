---
layout: post
title:  "Progress Solar Jet Model"
date:   2021-09-10 15:11:28 +0100
categories: Washing Machine Update
tags: jet simulation smaug
---
# Progress Update 10/9/2021

We outlined the simulations in the project description "[Solar Jets](http://mikeg64.github.io/projects/2021-07-30-Solar-jet-bede.html)"

All the simulations and models are detailed on git hub these are the 
[smaug_jet@github](https://github.com/mikeg64/smaug_jet)

* Created branch in smaug_jet project for the MPI developments [smaug_jet_mpi](https://github.com/mikeg64/smaug_jet/tree/smaug_jet_mpi)
* Initial testing of jacobi-bede a cuda enabled MPI example [cuda examples in smaug_jet_mpi](https://github.com/mikeg64/smaug_jet/tree/smaug_jet_mpi/basiccudaexamples/jacobi-bede)
* Main branch of smaug_jet used for single GPU testing and model runs [smaug_jet](https://github.com/mikeg64/smaug_jet/tree/main)


NVIVO is helpful for  annotating papers and for coding. As a guide to tracking data each directory on the compute systems will have  a file list.
A data folder in the git repo will contain subdirectories corresponding to each of the systems used. Each subdirectory will have a directory contents txt file detailing the data. These may be coded as external files within NVIVO.

## Preparation of point source model

* source term checked  [Driver source file](https://github.com/mikeg64/smaug_jet/blob/main/src/usersource_jet_hydro.cu)
* include file checked  [Model include file](https://github.com/mikeg64/smaug_jet/blob/main/include/iosmaugparams_jet_hydro.h)
* config file checked
* driver script ready

Need to check the following

* boundary term
* data output location on bede (see [bede docs](https://bede-documentation.readthedocs.io/en/latest/usage/index.html#file-storage). )


## Comments about compilation flags and compiler selection

openmpi/ucx is known to be buggy when doing MPI one-sided operations.
Cliff seemed to have better luck if he added the "--map-by ppr:2:socket" flag.

If that flag helps, can you give admin more details about what you are doing?

e.g. job script

Alternatively, building against the MPI in module mvapich2/2.3.5-2 works
much better in this situation.


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
