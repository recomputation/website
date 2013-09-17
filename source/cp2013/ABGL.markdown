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
* Experiment URL: [http://recomputation.org/cp2013/ABGL.html](http://recomputation.org/cp2013/ABGL.html)

## Recomputation Downloads

* [Vagrant Box](ABGL/recomputation-cp2013-ABGL.box). Approx 2.3 GB.
Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `74ec128ba1ac571817b98145022841ae`

## Quick Instructions for running 

*Note:* Unfortunately we are not able to distribute the full experiment, because it includes a portfolio of MaxSAT solvers which we do not 
have the licence permission to distribute.  For further details please contact the authors.  The following instructions apply to 
the partial experiment we are able to distribute.

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://recomputation.org/cp2013/ABGL/recomputation-cp2013-ABGL.box`

    mkdir anydir
    cd anydir
    vagrant init http://recomputation.org/cp2013/ABGL/recomputation-cp2013-ABGL.box
    vagrant up
   
This should run the experiment and create a new results directory in the current diectory. 
It will leave a virtual machine running.  When this has finished enter

    vagrant halt

which will stop the virtual machine (but leave a copy of it on your system.)
     
## Further Instructions 

General instructions for installing and running experiments from recomputation are contained on a [general page](general_instructions.html). We also give further instructions on e.g. removing a box or repackaging it after you make changes.

The experiment will run automatically when the box is started by "vagrant up".  To disable this use this command instead 

    vagrant up --no-provision

# Security Warning

There are inevitable security risks in running any executable and/or virtual machine downloaded from the internet. You should take appropriate precautions.

## History

September 17, 2013.  Page set up.



