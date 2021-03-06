---
layout: post
title:  "Running hermes using a docker container"
date:   2020-12-14 15:11:28 +0100
categories: Hermes Docker
tags: hermes MHD Docker
---


# Running Hermes Using a Docker Container

Notes on a docker container for building MHD codes.

docker run -v /Users/mikegriffiths/proj:/home/jupyter/notebooks --rm -p 8888:8888 mikeg64/sac-smaug

Rebuild docker image using Dockerfile at 
[Dockerfile for sac-smaug](https://github.com/mikeg64/smaug/blob/master/smaug/docker/Dockerfile)

Notes on using docker
[Notes on Using Docker](https://notesrcg.blogspot.com/2019/06/getting-started-with-containerization.html)
will need to use the docker push command 


Need to update dockerfile as follows

* Use latest version of cuda with ubuntu image e.g. [nvidia/cuda:11.1.0-devel-ubuntu18.04](https://hub.docker.com/r/nvidia/cuda/)
* Include gdb compiler using the command RUN apt-get install -y gdb
* valgrind using the command RUN apt-get install -y valgrind
* install tau using sudo apt-get install -y tau

Useful tutorial
* [GDB tutorial](http://www.iro.umontreal.ca/~mignotte/IFT2425/Documents/Debugger_gdb.pdf)
* [GDB documentation](https://www.gnu.org/software/gdb/documentation/)
* [C programming GDB tutorial](https://www.cprogramming.com/gdb.html)
* [Valgrind quickstart](https://www.valgrind.org/docs/manual/quick-start.html)
* [Valgrind tutorial](http://cs.ecs.baylor.edu/~donahoo/tools/valgrind/)
* [TAU Performance System](https://www.cs.uoregon.edu/research/tau/home.php)
* [TAU Userguide](https://www.cs.uoregon.edu/research/tau/tau-usersguide.pdf)
* [TAU By example](https://wiki.mpich.org/mpich/index.php/TAU_by_example)


Commands for configuring and running models in hermes use make all to actually build before running

    ./configure --with-gas=hydro --with-problem=shkset1d
    ../bin/athena -i ../tst/1D-hydro/athinput.sod


    ./configure --with-gas=hydro --with-problem=shkset1d --enable-bkg --with-integrator=sac --with-flux=sac
    ../bin/athena -i ../tst/1D-hydro/athinput.sod-sac


## Installing and Configuring Tau with Spack

    spack install tau@2.28.1 openmp=True

You can also force installation with a specific compiler version by typing:

    spack install tau@2.28.1 %gcc@8.2.0 openmp=True

Define environment variables for TAU as shown below.

    # TAU home location
    export TAU_HOME=$(spack location -i tau)

    # Put the location of tau_f90.sh in the search path
    export PATH=$PATH:$TAU_HOME/bin

    # Define options for TAU
    export TAU_OPTIONS="-optRevert -optVerbose -optPreProcess -optContinueBeforeOMP -optPdtGnuFortranParser"

    # Define location of TAU makefile
    export TAU_MAKEFILE=$TAU_HOME/x86_64/lib/Makefile.tau-papi-pthread-pdt-openmp

These instructions were taken from
[http://wiki.seas.harvard.edu/geos-chem/index.php/Profiling_GEOS-Chem_with_the_TAU_performance_system](http://wiki.seas.harvard.edu/geos-chem/index.php/Profiling_GEOS-Chem_with_the_TAU_performance_system)


## Using gprof 

Gprof gives users an execution profile of their C, Pascal, or Fortran77 programs. What Gprof basically does is, it calculates the amount of time spent in each routine or function. "Next, these times are propagated along the edges of the call graph. Cycles are discovered, and calls into a cycle are made to share the time of the cycle."

Install gprof on ubuntu using

    sudo apt-get install binutils

* [https://www.thegeekstuff.com/2012/08/gprof-tutorial/](https://www.thegeekstuff.com/2012/08/gprof-tutorial/)
* [https://users.cs.duke.edu/~ola/courses/programming/gprof.html](https://users.cs.duke.edu/~ola/courses/programming/gprof.html)
* [https://sourceware.org/binutils/docs/gprof/](https://sourceware.org/binutils/docs/gprof/)
* [https://www.cs.princeton.edu/courses/archive/fall07/cos217/lectures/16MakeGprof.pdf](https://www.cs.princeton.edu/courses/archive/fall07/cos217/lectures/16MakeGprof.pdf)



















