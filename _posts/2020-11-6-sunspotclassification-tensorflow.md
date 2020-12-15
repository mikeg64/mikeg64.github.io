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



## ML tools for space weather forecasting

* [CME Arrival Time Prediction Using Convolutional Neural Network](https://github.com/PyDL/CME-CNN)


## Solution for Correct Installation and Configuration of Tensorflow on Bede
Needed to install annd build correct distribution of tensorflow for GPUs
(inspired by clues here)

[https://github.com/DurhamARC/bede/wiki#ibm-powerai-and-watson-machine-learning-community-edition-wmlce](https://github.com/DurhamARC/bede/wiki#ibm-powerai-and-watson-machine-learning-community-edition-wmlce)







    cd /nobackup/projects/bdshe01/cs1mkg

 

    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-ppc64le.sh

    sh Miniconda3-latest-Linux-ppc64le.sh



    conda update conda

    conda config --set channel_priority strict

    conda config --prepend channels https://public.dhe.ibm.com/ibmdl/export/pub/software/server/ibm-ai/conda/

    conda create -n tensorflow-gpu python=3.6

    conda activate tensorflow-gpu

    conda install --strict-channel-priority tensorflow-gpu




