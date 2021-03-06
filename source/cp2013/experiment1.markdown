---
layout: page
title: "Experiment: Solution to a Chessboard Puzzle"
date: 2013-07-01 12:45
comments: true
sharing: true
footer: true
---

## Experiment id: cp2013-experiment1 

*Note: the experiment id and url contained here are not persistent and are subject to change*


This experiment confirms the claim made in this [one page pdf](experiment1/8x8puzzle.pdf), and also on the first page 
of [Symmetry in Constraint Programming](http://ipg.host.cs.st-andrews.ac.uk/papers/GentPetriePugetFinalDraft.pdf)
by Ian Gent, Karen Petrie and Jean-Francois Puget, Handbook of Constraint PRogramming, 2006.


* Experiment author: Ian Gent
* Made recomputable by: Ian Gent
* Approximate timescale after boot: 1 minute
* [Readme file](experiment1/AAReadme) from the experiment top level directory.
* A sample results directory is available as [gzipped tar file](experiment1/results-201306210540-Xae.tgz) or
[zip file](experiment1/results-201306210540-Xae.zip)
* Experiment URL: [http://recomputation.org/cp2013/experiment1.html](http://recomputation.org/cp2013/experiment1.html)

## Recomputation Downloads

* [Vagrant Box](experiment1/recomputation-QueensPuzzle-b.box). Ubuntu 12.04. Approx 391 MiB. Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum `34a2e4b53268da0a0362375595d8d137`
* [Experiment directory, gzipped tar file](experiment1/recomputation-QueensPuzzle.tgz) including executable. Approx 33 MiB.
    * md5sum `f005e54d1210cc7a6c42c00c4afb4d49`
* [Experiment directory sources only, gzipped tar file](experiment1/recomputation-QueensPuzzle-src.tgz) of source only. Approx 1.8 MiB.
    * md5sum `fb962ce560099a4180a13d733c3abbf4`

## Quick Instructions for running 

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
    
The URL to obtain the Vagrant box for this experiment is 
`http://recomputation.org/cp2013/experiment1/recomputation-QueensPuzzle-b.box`

    mkdir anydir
    cd anydir
    vagrant init cp2013-experiment1 http://recomputation.org/cp2013/experiment1/recomputation-QueensPuzzle-b.box
    vagrant up
   
This should run the experiment and create a new results directory in the current directory. 
It will leave a virtual machine running.  When ready enter

    vagrant halt

which will stop the virtual machine (but leave a copy of it on your system.)
     
## Further Instructions 

General instructions for installing and running experiments from recomputation are contained on a [general page](general_instructions.html). We also give further instructions on e.g. removing a box or repackaging it after you make changes.

The experiment will run automatically when the box is started by "vagrant up".  To disable this use this command instead 

    vagrant up --no-provision

# Security Warning

There are inevitable security risks in running any executable and/or virtual machine downloaded from the internet. You should take appropriate precautions.

## History

Some older files are available.

* [Vagrant Box](experiment1/recomputation-QueensPuzzle.box). Older box with incorrect vagrant file so that experiment did not run on vagrant up.
 Ubuntu 12.04. Approx 391 MiB. Note that this file is actually a tarfile containing VirtualBox files so may also be used directly with VirtualBox.  All code in this machine is open source except for VirtualBox Guest Additions, which are included in binary form.  
    * md5sum 548da40e7580726fccb4db914d26498e  

