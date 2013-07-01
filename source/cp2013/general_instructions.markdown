---
layout: page
title: "General Instructions for Running Experiments using VirtualBox and Vagrant"
date: 2013-06-22 20:45
comments: true
sharing: true
footer: true
---

To run an experiment which we distribute using VirtualBox and Vagrant, no software downloads from 
[recomputation.org](recomputation.org) are necessary.  However, you will need to install the 
tools VirtualBox and Vagrant if you do not have these already.  Both tools are free.  We provide 
brief descriptions and download links for [VirtualBox](#vbox) and [Vagrant](#vagrant) below.
If you cannot install these tools we discuss [workarounds](#workarounds) below.

# Security Warning

There are inevitable security risks in running any executable and/or virtual machine downloaded from the internet. This is particularly true for virtual machines representing experiments in computational science, since they might represent 
a historical version of an operating system which may have security flaws fixed in later versions.
You should take appropriate precautions before running any virtual machines from recomputation.org.  

# Using Vagrant in Unix

These instructions should work in a unix-like system with vagrant and VirtualBox installed.
These instructions are limited to Unix-like systems (e.g. Linux, MacOS X). VirtualBox and Vagrant are available for Windows 
but we have not yet used Vagrant in Windows so have not provided instructions for doing so.  (We would be very glad to hear of any
experiences using Vagrant in Windows.)

For the following instructions will assume that you create a new directory to do your work in, e.g.

    $ mkdir anydir
    $ cd anydir

From now on we assume that commands we give below are in `anydir` or a subdirectory.  We use $ as the Unix command line prompt in the Host machine, % for the prompt in the guest machine, and lines without the prompt represent some form of output.

## Instructions for Obtaining and Starting a Vagrant Box 

We distribute virtual machines as "Vagrant Boxes".  A box is just Vagrant's package format for a Virtual Machine, some configuration information, and possibly additional files.
To get a box you need its URL, to be found on each experiment's page.  We use the [CP 2013 Experiment 1](experiment1.html)
 experiment as an example. The URL for this Vagrant box is 

    http://recomputation.org/cp2013/experiment1/recomputation-QueensPuzzle-b.box

You also need to give your experiment a name of your choice. We'll use the name "cp2013-experiment1" but you could use any local name. 
Replace URL in the following by the URL for the box.  (If you have downloaded the box manually to your filesystem, you can use the path to the file instead of the URL.) 

    $ vagrant init cp2013-experiment1 URL

This initialises the directory but will not download the machine.  To download the machine and start it up just type

    $ vagrant up

When the box is downloaded, Vagrant will pass the VM to VirtualBox and congfigure it for Vagrant's needs, then start the VM.  

## Disabling initialisation scripts

When it is booted, typically the whole experiment is run immediately after booting.  To disable this behaviour, instead of the above command run:

    $ vagrant up --no-provision

## Using a virtual machine

The VM should now be running in VirtualBox in your machine.   You could interact with it via VirtualBox, but Vagrant allows you to shortcut this. 

To log in to the VM simply enter

    $ vagrant ssh

You should now be in the machine as user vagrant in ~vagrant (/home/vagrant).  This user is normally configured to be a passwordless sudoer in this machine.

## Sharing files between host and guest

If you want to share work between the VM and the host machine, then do your work in `/vagrant`.  `/vagrant` is automatically cross mounted with the directory (`anydir` above) that you started the VM in.  This is achieved by using the shared folders facility of VirtualBox.  
Note that care may be necessary, since directories actually live in the host OS.  So details of the filesystem may not be consistent 
between the guest and host machine.   

## Changing properties of the VM

If you need more RAM or cpus (or less) in the VM as distributed in the box, or to change other features, you can use VBoxManage.

E.g. 

    $ VBoxManage list vms
    "recomp-cp2013_1371632000" {451e2506-b2b4-4587-8b60-b24e3ea596a2}


To see what you have
    $ VBoxManage showvminfo 451e2506-b2b4-4587-8b60-b24e3ea596a2
    lots of information about the VM

Then you can do 

    $ VBoxManage modifyvm 451e2506-b2b4-4587-8b60-b24e3ea596a2 --memory 65536 --cpus 16

to eg. get 64GB RAM and 16 cpus (though I found this incredibly inefficient in practice.)  See [the VBoxManage](http://www.virtualbox.org/manual/ch08.html) manual page for more options.

Note that what you change will get stored if you do a vagrant package (see below).   You can also change these settings in the configuration Vagrantfile.

Because the VM is running in VirtualBox, you can also use all other aspects of VirtualBox (e.g. its GUI) to control the box. 

## Freeing Up Resources used by an Experiment

This machine will continue running so you can stop it in the VM or externally.  It can be halted by the normal method of the guest OS.  
To do it externally do:

    $ vagrant halt

This will stop the virtual machine (but leave a copy of it on your system.)
This machine can be restarted by running in this directory:

    $ vagrant up 

The machine will continue as a VM on your system, either active or passive, as long as you wish it.  If you no longer have any need of it and wish to save the disk space it uses, you can do (where `cp2013-experiment1` is the local name you gave above)

    $ vagrant destroy
    $ vagrant box remove cp2013-experiment1 virtualbox


**Important** vagrant destroy does what it says it does.  It destroys the machine so you will lose any changes.  The exception is that files in `anydir` will be preserved, e.g. if you have stored results of the experiment there.

Destroying a VM is sensible if you wish to run an experiment, check and/or save its results, and then get rid of the machine.  Obviously it is not appropriate if you have made changes to the VM that you wish to save.  In that case you should keep the machine and/or repackage it for 
distribution to others.   

## Saving a new copy of the machine

If you have made changes to the VM and want to save them - e.g. when your experiment is ready to run, you can do this in the host in directory "anydir".

    vagrant package --output NewName.box --vagrantfile Vagrantfile

Then this machine can be used by others freely - including yourself in the future.   

This will leave NewName.box in anydir, but of course you can use any path in your filesystem.

An optional step before doing the above (if the guest is Linux).  If you want to save disk space (e.g. you have written and deleted lots of files) then first clean out the VM.  Then zero the free space by this command (which will take a while)

    % dd if=/dev/zero of=test.file
    % rm test.file

This will let VBox compress the disk better, but will take some time if the virtual disk is large.  


<a id="passwords"></a>
## Passwords in the VM


Because of the way the VM is set up you do not normally need to know, but we follow Vagrant conventions to set:

* Root password: vagrant
* Main account login: vagrant
* Main account password: vagrant

Also the user vagrant is a passwordless sudoer in the machine. 

     

## Vagrant Documentation

For further documentation on Vagrant see [http://docs.vagrantup.com/v2/](http://docs.vagrantup.com/v2/).


<a id="downloads"></a>
# Downloads

<a id="vbox"></a>
## VirtualBox

[Virtual Box](https://www.virtualbox.org/) is a mainly free and open source product from Oracle, 
although some parts of it are closed. It [describes itself](https://www.virtualbox.org/wiki/VirtualBox) 
as a "a general-purpose full virtualizer for x86 hardware, targeted at server, desktop and embedded use" 
https://www.virtualbox.org/wiki/VirtualBox

The bulk of Virtual Box is open source under GPL.  However there are extensions of it which are closed and not free, 
although can be used for Personal Use, Education and Evaluation.
For details of these licence terms see the [Virtual Box PUEL](https://www.virtualbox.org/wiki/VirtualBox_PUEL).
The most important thing we use from the extensions are the "Virtual Box Guest Additions", as these are required for 
Vagrant to work.  We distribute the guest additions in the vagrant boxes we distribute, 
under the right granted to us by the [Virtual Box PUEL](https://www.virtualbox.org/wiki/VirtualBox_PUEL).

You can download Virtual Box for [many operating systems](https://www.virtualbox.org/wiki/Downloads) and it can also often be installed through Linux package managers.

<a id="vagrant"></a>
## Vagrant

[Vagrant](http://www.vagrantup.com/) is a tool which makes interaction with VirtualBox or other virtualisation products much much easier. 
It is entirely free and open source for use with VirtualBox.  

Vagrant can be downloaded from [vagrantup.com](http://downloads.vagrantup.com/).  It can be installed from package managers in some versions of Linux, but be careful you have a recent version.  The version we used (as of June 2013) is 1.2.2.

Vagrant was started by [Mitchell Hashimoto](https://twitter.com/mitchellh) and commercialised by [HashiCorp](http://www.hashicorp.com/). 
It remains open source with a [github page](https://github.com/mitchellh/vagrant).

<a id="workarounds"></a>
# Workarounds

If you have VirtualBox but not Vagrant, you should have little problem running our experiments.
A Vagrant "box" is actually just a tarfile containing some configuration information 
and an exported virtual machine from VirtualBox. Therefore you could do:

    $ mkdir anydir
    $ cd anydir
    $ wget URL          ## (if not downloaded already) 
    $ tar xf FILENAME.box


If using the VM without Vagrant you will need to know the 
default passwords [given earlier](#passwords).
You should now have the files in `anydir` to give to VirtualBox.   


The only difficulty you might find is how 
to run the experiment if it is run automatically by vagrant up.   If you are having difficulty
then you should look at the experiment documentation on this site, any readme files in the machine,
or the vagrantfiles included with the box. 


If you have another virtualisation product (e.g. VMWare), it might be possible to import the VM 
using that product.  We have not tested this but programs are often able to import each others' machines. 
(Note that it is very unwise to install more than one virtualisation product unless you know exactly
what you are doing, as their low level functions can interfere catastrophically with each other.) 

If you have no virtualisation product available, then we normally try to release other files which can be
used to run the experiment.  E.g. we might release a tarred and/or zipped copy of the experimental directory. 
You might find this is able to run in your system, but also there might be problems doing so because of 
version inconsistencies of software: these are precisely the reason for providing Virtual Machines.





