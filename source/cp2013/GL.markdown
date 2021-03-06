---
layout: page
title: "Experiment: Gualandi, Lombardi"
date: 2013-09-17 12:45
comments: true
sharing: true
footer: true
---

## Experiment id: cp2013-GL 

This experiment are results presented in the following paper in the proceedings of CP 2013, edited by Christian Schulte,
[published by Springer](https://www.springer.com/computer/theoretical+computer+science/book/978-3-642-40626-3).

[A Simple and Effective Decomposition for the Multidimensional Binpacking Constraint](http://link.springer.com/chapter/10.1007/978-3-642-40627-0_29),
by 
Stefano Gualandi and Michele Lombardi

*Note: the experiment id and url contained here are not persistent and are subject to change*

* Experiment authors: Stefano Gualandi and Michele Lombardi.
* Made recomputable by: Lars Kotthoff
* Approximate timescale after boot: 6 hours.
* Experiment URL: [http://recomputation.org/cp2013/GL.html](http://recomputation.org/cp2013/GL.html)
* Live URL: [https://live.recomputation.org:8443/job/binpacking-decomp-cp/](https://live.recomputation.org:8443/job/binpacking-decomp-cp/)

## Recomputation Downloads

* [Vagrant Box](GL/recomputation-cp2013-GL.box). Approx 876 MB. 
Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `6155ffcfa7fc9be997a76090e9e003a7`

## Quick Instructions for running 

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://recomputation.org/cp2013/GL/recomputation-cp2013-GL.box`

    mkdir anydir
    cd anydir
    vagrant init cp2013-GL http://recomputation.org/cp2013/GL/recomputation-cp2013-GL.box
    vagrant up
   
This should run the experiment and create a new results directory in the current directory. 
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

September 18, 2013. Add live URL.


