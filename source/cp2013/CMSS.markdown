---
layout: page
title: "Experiment: Cambazard, Mehta, O'Sullivan, Simonis"
date: 2013-09-17 12:45
comments: true
sharing: true
footer: true
---

## Experiment id: cp2013-CMSS 

This experiment are results presented in the following paper in the proceedings of CP 2013, edited by Christian Schulte,
[published by Springer](https://www.springer.com/computer/theoretical+computer+science/book/978-3-642-40626-3).

[Bin Packing with Linear Usage Costs - An Application to Energy Management in Data Centres](http://link.springer.com/chapter/10.1007/978-3-642-40627-0_7),
by 
Hadrien Cambazard, Deepak Mehta, Barry O'Sullivan, Helmut Simonis


*Note: the experiment id and url contained here are not persistent and are subject to change*

* Experiment authors: 
Hadrien Cambazard, Deepak Mehta, Barry O'Sullivan, Helmut Simonis
* Made recomputable by: Lars Kotthoff
* Experiment URL: [http://recomputation.org/cp2013/CMSS.html](http://recomputation.org/cp2013/CMSS.html)
* Live URL: [https://live.recomputation.org:8443/job/binpacking-cp/](https://live.recomputation.org:8443/job/binpacking-cp/)

## Recomputation Downloads

* [Vagrant Box](CMSS/recomputation-cp2013-CMSS.box). Approx 490 MB. 
Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `14efb14632a664b3c04da38117a364ae`

## Quick Instructions for running 

*Note:* Part of the experiments use [IBM CPLEX](http://www-01.ibm.com/software/commerce/optimization/cplex-optimizer/), which we are unable to include in the virtual machine because of licensing restrictions. To run the experiments that require CPLEX, put the CPLEX native libraries (the .so files) into the same directory as the virtual machine before starting it. They will be picked up automatically when the virtual machine is started.

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://recomputation.org/cp2013/CMSS/recomputation-cp2013-CMSS.box`

    mkdir anydir
    cd anydir
    vagrant init cp2013-CMSS http://recomputation.org/cp2013/CMSS/recomputation-cp2013-CMSS.box
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

September 18, 2013. Add note about CPLEX. Add live URL.


