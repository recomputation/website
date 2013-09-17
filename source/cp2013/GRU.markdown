---
layout: page
title: "Experiment: Di Gaspero, Rendl, Urli"
date: 2013-09-16 12:45
comments: true
sharing: true
footer: true
---

## Experiment id: cp2013-GRU 

This experiment are results presented in the following paper in the proceedings of CP 2013, edited by Christian Schulte,
[published by Springer](https://www.springer.com/computer/theoretical+computer+science/book/978-3-642-40626-3).

[Constraint-based approaches for Balancing Bike Sharing Systems](http://link.springer.com/chapter/10.1007/978-3-642-40627-0_56),
by 

Luca Di Gaspero, Andrea Rendl, Tommaso Urli

*Note: the experiment id and url contained here are not persistent and are subject to change*

* Experiment authors: 
Luca Di Gaspero, Andrea Rendl, Tommaso Urli.
* Made recomputable by: Lars Kotthoff
## * Approximate timescale after boot: weeks.
* Experiment URL: [http://recomputation.org/cp2013/GRU.html](http://recomputation.org/cp2013/GRU.html)

## Recomputation Downloads

* [Vagrant Box](GRU/recomputation-cp2013-GRU.box). Approx 588 MB. 
Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `51d02a6c8ef7135a650fc239df522e01`

## Quick Instructions for running 

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://recomputation.org/cp2013/GRU/recomputation-cp2013-GRU.box`

    mkdir anydir
    cd anydir
    vagrant init http://recomputation.org/cp2013/GRU/recomputation-cp2013-GRU.box
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



