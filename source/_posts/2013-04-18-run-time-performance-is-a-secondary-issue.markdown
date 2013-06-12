---
layout: post
title: "Run Time Performance Is A Secondary Issue"
date: 2013-04-18 11:23
comments: true
categories: 
---

I have been surprised and pleased that the [Recomputation Manifesto](2013-04-12-the-recomputation-manifesto.html) has 
attracted some attention after I put it on arXiv.  As well as comments on this blog, I have had various emails and 
also a [reddit discussion](http://redd.it/1cdhgb)
was started by an interested user (shii).    Not everyone has agreed with me, but there's been no offensive or insulting posting, which is great.

I have responded to individual comments but I have a couple of general points to make on issues which keep coming up. This post is about the first one.

I said "runtime performance is a secondary issue". Many people have reacted that often runtime is *the* most important issue in an experiment.  Of course I accept that. I see now I expressed myself badly. What I mean is that runtime performance is a secondary issue compared to the critical fact of making an experiment recomputable.
The argument I was trying to make - 
not very clearly apparently - was that in 
attempting to set up tools to make experiments reproducible, being able to reproduce the exact run 
times from the original should be treated as a secondary concern. In large part because it is so difficult, if not impossible. 

One assumption some people make - I think I did until recently - is that there is some ideal runtime that our experiment should strive to get.   Runtime is influenced by factors like load on the machine, hyperthreading, and many other factors.  One can spend all one's time eliminating these factors to get some "true" runtime, but then... the code one has optimised this way will be used in a heavily loaded machine with hyperthreading switched back on. I was particularly pleased by Simon Gog's [comment](http://recomputation.com/blog/2013/04/12/the-recomputation-manifesto/#comment-864915074).   "Running it on a virtual machine might produce different results, but hey: that might give you new insights about your algorithm."   Having experiments available to be recomputed in a variety of hardware and virtual environments should allow us to get a handle on the *distribution* of runtimes.   There is not normally one true hardware environment we need to work to.   Occasionally there is a specific hardware setup of interest, and that is the only thing that counts, but that is the exception.


A second assumption people make is that you can't get meaningful run times out of virtual machines or in the cloud. 
Actually, [Lars Kotthoff](http://4c.ucc.ie/~larsko/) 
and I wrote a paper about getting reliable run times in the cloud: [Reliability of Computational Experiments on Virtualised Hardware](http://arxiv.org/abs/1110.6288).  The results were pretty positive.  


If we can provide frameworks in which people can rerun experiments, we can then investigate how to get the most useful run times 
and distributions of run times out of our experiments.   But this is a secondary issue to the recomputation effort, compared to getting experiments to be recomputable in the first place.

I'm going to write a second post, about the practicality and ease of use of Virtual Machines for storing and distributing experiments.

