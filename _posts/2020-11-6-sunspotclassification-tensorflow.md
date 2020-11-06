---
layout: post
title:  "Sunspot classification with Tensor Flow Using Bede 1"
date:   2020-11-06 15:11:28 +0100
categories: Sunspot Classification Tensor-flow Bede N8
tags: Sunspot Classification Tensor-flow Bede N8
---




# Sunspot Classification Using Tensor Flow on Bede - Part 1


## Introduction 

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

Unable to run the test model as tensor flow unable to detect a GPU. Solution is probably found in sharc documentation on tensorflow.
* [TensorFlow](https://docs.hpc.shef.ac.uk/en/latest/bessemer/software/apps/tensorflow.html)
* [Tensor flow tutorials](https://www.tensorflow.org/tutorials/)



## sunspot classification analysis

* [tensorflow model - github](https://github.com/mikeg64/solar/tree/master/tensorflow)
* [CME Arrival Time Prediction Using Convolutional Neural Network](https://github.com/PyDL/CME-CNN)





