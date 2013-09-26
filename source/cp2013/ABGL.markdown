---
layout: page
title: "Experiment: Ansótegui, Bonet, Gabàs, Levy"
date: 2013-09-17 12:45
comments: true
sharing: true
footer: true
---

## Experiment id: cp2013-ABGL 

This experiment are results presented in the following paper in the proceedings of CP 2013, edited by Christian Schulte,
[published by Springer](https://www.springer.com/computer/theoretical+computer+science/book/978-3-642-40626-3).

[Improving WPM2 for (Weighted) Partial MaxSAT](http://link.springer.com/chapter/10.1007/978-3-642-40627-0_12),
by 
Carlos Ansótegui, Maria Luisa Bonet, Joel Gabàs, Jordi Levy


*Note: the experiment id and url contained here are not persistent and are subject to change*

* Experiment authors: 
Carlos Ansótegui, Maria Luisa Bonet, Joel Gabàs, Jordi Levy
* Made recomputable by: Lars Kotthoff
* Approximate timescale after boot: years if all solvers supplied.
* Experiment URL: [http://recomputation.org/cp2013/ABGL.html](http://recomputation.org/cp2013/ABGL.html)
* Live URL: [https://live.recomputation.org:8443/job/maxsat-cp/](https://live.recomputation.org:8443/job/maxsat-cp/)

## Recomputation Downloads

* [Vagrant Box](ABGL/recomputation-cp2013-ABGL.box). Approx 2.3 GB.
Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `74ec128ba1ac571817b98145022841ae`

## Quick Instructions for running 

*Note:* Unfortunately we are not able to distribute the full experiment, because it includes a portfolio of MaxSAT solvers which we do not have the licence permission to distribute. All of the problem instances the experiments were run on are part of the virtual machine, but no solvers are. The virtual machine assumes that the directory it is started from contains a directory "solvers/" that contains the actual solver binaries. It will run all executable files in that directory on all problem instances. If there are no solvers in the specified place, nothing will be run.

For a list of solvers used and more information, please contact the authors.

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://recomputation.org/cp2013/ABGL/recomputation-cp2013-ABGL.box`

    mkdir anydir
    cd anydir
    vagrant init cp2013-ABGL http://recomputation.org/cp2013/ABGL/recomputation-cp2013-ABGL.box
    vagrant up
   
This should run the experiment and create a new results directory in the current directory. 
It will leave the virtual machine running.  When the experiments are finished, enter

    vagrant halt

which will stop the virtual machine (but leave a copy of it on your system.)
     
## Further Instructions 

General instructions for installing and running experiments from recomputation are contained on a [general page](general_instructions.html). We also give further instructions on e.g. removing a box or repackaging it after you make changes.

The experiment will run automatically when the box is started by "vagrant up".  To disable this use this command instead 

    vagrant up --no-provision

Note that the experiments in this box use a work queueing system that will run
the experiments asynchronously. This means that "vagrant up" will return, but
the experiments will still be running. You need to verify yourself that the
experiments have finished before shutting down the virtual machine.

# Security Warning

There are inevitable security risks in running any executable and/or virtual machine downloaded from the internet. You should take appropriate precautions.

## History

September 17, 2013.  Page set up.

September 18, 2013. Clarify that solvers need to be supplied separately. Add live URL.
