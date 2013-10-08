---
layout: page
title: "Experiment: Akgun, Frisch, Gent, Hussain, Jefferson, Kotthoff, Miguel, Nightingale"
date: 2013-10-08 11:30
comments: true
sharing: true
footer: true
---

## Experiment id: cp2013-AFGHJKMN

This experiment are results presented in the following paper in the proceedings of CP 2013, edited by Christian Schulte,
[published by Springer](https://www.springer.com/computer/theoretical+computer+science/book/978-3-642-40626-3).

[Automated Symmetry Breaking and Model Selection in Conjure](http://link.springer.com/chapter/10.1007/978-3-642-40627-0_11),
by 
Ozgur Akgun, Alan M. Frisch, Ian P. Gent, Bilal Hussain, Christopher A. Jefferson, Lars Kotthoff, Ian Miguel, Peter Nightingale


*Note: the experiment id and url contained here are not persistent and are subject to change*

* Experiment authors: 
Ozgur Akgun, Alan M. Frisch, Ian P. Gent, Bilal Hussain, Christopher A. Jefferson, Lars Kotthoff, Ian Miguel, Peter Nightingale
* Made recomputable by: Lars Kotthoff
* Approximate timescale after boot: Weeks.
* Experiment URL: [http://recomputation.org/cp2013/AFGHJKMN.html](http://recomputation.org/cp2013/AFGHJKMN.html)
* Live URL: [https://live.recomputation.org:8443/job/conjure-cp/](https://live.recomputation.org:8443/job/conjure-cp/)

## Recomputation Downloads

* [Vagrant Box](http://4c.ucc.ie/~larsko/downloads/r/conjure-cp.box). Approx 2.3 GB. 
Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `95a9e74fc0878ef6c91daa4db3bdc321`

## Quick Instructions for running 

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://4c.ucc.ie/~larsko/downloads/r/conjure-cp.box`

    mkdir anydir
    cd anydir
    vagrant init cp2013-AFGHJKMN http://4c.ucc.ie/~larsko/downloads/r/conjure-cp.box
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

October 08, 2013.  Page set up.

