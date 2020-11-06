---
layout: post
title:  "Running SMAUG on  Bede 1"
date:   2020-11-06 15:11:28 +0100
categories: SMAUG MHD Bede N8
tags: SMAUG MHD GPU Bede N8
---




# Running the SMAUG Code on Bede


## Introduction

[The SMAUG project](http://mikeg64.github.io/projects/2020-11-06-smaug-mhd.html) 

### What is Bede?

* [Bede](https://n8cir.org.uk/supporting-research/facilities/nice/)
* [Bede has been Formally Handed Over](https://n8cir.org.uk/news/bede-has-been-formally-handed-over/)
* [Bede hardware](https://n8cir.org.uk/supporting-research/facilities/nice/hardware/)


## Documentation

* [Bede Wiki](https://github.com/DurhamARC/bede/wiki)
* [Hackathon docs.](https://gpuhackshef.readthedocs.io/en/latest/bede/index.html)

## Installing Python Environment

Request interactive session

    module load slurm
    srun -A bdshe01 --pty bash

## Steps which were taken

    git clone https://github.com/smaug
    
From the source directory
    
    make ot

* [Modified makefile for Bede](https://github.com/mikeg64/smaug/blob/master/smaug/src/Makefile_3d_v100)
* [make_inputs_bede](https://github.com/mikeg64/smaug/blob/master/smaug/src/make_inputs_bede)

[Using the GPU hackathon docs](https://gpuhackshef.readthedocs.io/en/latest/bede/software/cuda.html)

Main changes:
* The CUDA path
    CUDA = /opt/software/apps/libs/CUDA/10.1.243

* cuda FLAGS
    CUDACCFLAGS = --ptxas-options=-v -gencode=arch=compute_70,code=sm_70 -gencode=arch=compute_70,code=compute_70  -maxrregcount=32 -DUSE_SAC

Comment the code documentation needs much improvement! However, it wasn't a major challenge to get the code to run on Bede. Next steps are as follows:
* Test jupyter notebook and plot outputs
* Check timings
* Check 3D codes






