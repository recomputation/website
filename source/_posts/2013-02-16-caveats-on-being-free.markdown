---
layout: post
title: "Caveats on being free, and licences"
date: 2013-02-16 11:36
comments: true
categories: 
---

I have just posted the [Guiding principles](/mission/index.html) for [recomputation.org](http://recomputation.org).  One principle needs some elaboration:


>[recomputation.org](http://recomputation.org)  will always be free to those lodging bona-fide scientific experiments and to those obtaining past experiments, provided that

>  * all aspects of the experiments are freely available,
>  * experimenter's contributions are open source,  and
>  * fees are not charged for the related scientific publication.


The price - eternally free - is a key part of our mission.   

It needs to be easy to use recomputation.org, and being free is a key part of ease of use.   Even well funded scientists cannot always provide funds to pay for services without significant administrative overheads.  If I need to pay $1 for something out of my research funds, I can make that choice freely, but I have to ask our purchase officer to do it, which might involve him (non-sexist, he's male) jumping through some hoops.   This can be enough to stop me doing something, and we need to put as few obstacles as we can in the way of lodging experiments at recomputation.org.

The principle is, unfortunately, hedged with caveats.  I want to express my thoughts more about these caveats, and why I have put them in place.  As we develop the repository we should be able to make things clearer.  

> "bona-fide scientific experiments"

We will be providing massive amounts of storage to people, enough to put their virtual machines in.   We cannot afford to and do not want to become a competitor to storage services like Dropbox.  so we have to limit ourselves to scientific experiments.   What we mean by "bona fide" experiment will develop over time, but it is meant to be interpreted generously.   We don't mean e.g. only experiments for published papers.

> "to those obtaining past experiments"

I was careful to avoid saying "running past experiments".   We aim to provide the virtual machine and tools to run experiments for free.   This requires significant amounts of storage in perpetuity, and bandwidth to allow people to download those experiments.  However, it seems to me that the computational costs of *rerunning* experiments will typically be much larger than these storage and bandwidth costs.  Therefore we can make no promise that we can provide you a button to rerun an experiment for free.   We should provide - for free - the tools and data to rerun the experiment, if you can afford the computational resources to rerun it. 

> "experimenter's contributions are open source"

I have signed the  [Science Code Manifesto](http://sciencecodemanifesto.org), which is aimed at making scientific code open source. I think this is something that recomputation.org should encourage.   

But I think code openness and recomputability are orthogonal problems.  In fact it might be *more* important to make non-open source experiments recomputable: because binaries typically become non-runnable faster than source code becomes non-buildable.   

But if you as an experimenter are not making your code open source, I can think of a number of reasons, and none of these are ones that I feel recomputation.org should support with free services.

* You wish to have the option to make money from your closed-source code.  That's fine, but if money is entering into the equation you should be prepared to pay the costs your experiments cause recomputation.org.

* You do not believe in the Science Code Manifesto and feel research code should be private, perhaps to avoid giving away clever implementation tricks to other researchers.  We can't force you to change your opinion, but we can make you pay for the privilege of lodging you experiments with us. Of course you can freely download our tools to form your own repository, and that is great: of course that will also incur costs on you in storage and bandwidth.

* In principle you believe in the Science Code Manifesto but are incredibly embarrassed about the low quality and maintainability of your code.   I have great sympathy with this view because I have in the past refused to give code away for exactly this reason.  But don't be embarrassed!  Read the wonderful [CRAPL: An academic-strength open source license]("http://matt.might.net/articles/crapl/").   The rude name (CRAP) is entirely deliberate.  We all write horrible research code and you should not be embarrassed.  Share anyway!

The phrase "experimenter's contributions" is meant to indicate that we are only asking that your own work as an experimenter (and programmer, etc) is open source.  If you are working on a freely available system, it is not your problem to make the original thing you are extending open source.

> "all aspects of the experiment are freely available"

Putting aside open source for the moment, what about "freely available"?  Free is of course a loaded word in this area.  The above discussion was mostly about "free as in speech" but here I am talking about "free as in beer".   

In the short to medium term it's not my intention that recomputation.org invests significant resources studying licences.   This is a legal area and legal fees are not my top priority for changing the way computational sciences are done.   I take this to mean, at least at first, that we can only host experiments where all the software being used in the experiment is licensed as free (beer) to use by anybody.   This could be closed source software, as long as it is freely available.

If the code is yours to give away and you choose not to do so, then I refer you to some of the above comments.  Good luck to you, but you will have to bear the costs you impose on recomputation.org.  

If the code is not yours to give away, then of course you have no right to give it away and we cannot ask you to.  If the terms of use do not make it clear that it can be used freely by anyone, we may (sadly) have to refuse access to recomputation.org.

Basically the licence that all code needs to be under has to be clearly and unambiguously free for end users and for us to distribute.  As an example of a licence which does not satisfy this, it is not unusual to licence code as free for academic use, but not for other uses.  While it is clear that the intended use at recomputation.org is academic, we cannot guarantee that when we distribute such code nobody would use it for non-academic uses.  This is an example of a licence that code might be distributed under, superficially freely, that we could not accept at recomputation.org, at least for the time being.

> "fees are not charged for the related scientific publication"

This caveat is not meant to exclude authors who wish to make their experiments available for papers published in charged-for publications.  Looking further ahead, we wish to encourage journals and conferences to request experimenters to lodge experiments with us.   For example, we might provide a service where a journal can have a dedicated area where experiments are placed under embargo for reviewers to attempt to recompute.  A journal which charges either authors or readers might have to pay for this service.

Why this somewhat stern approach?  Because it is not the job of recomputation.org to provide services for nothing to those who charge.   If - as we hope they will - academic journals wish to encourage or require the use of recomputation.org, we would expect recompense from journals who charge either readers or authors for access.   This includes most, but not all, open access publications, since they typically charge authors or funding bodies to make publications open.  
On the other hand, we would not consider charging to ["platinum level"](http://journals.kent.ac.uk/index.php/feministsatlaw/article/view/59/179) open access journals, i.e. those which charge neither authors nor readers. 
Platinum level open access is not utopian. Even though the term appears to be about a year old, 
I published a paper in a platinum level open access journal [20 years ago](http://jair.org/papers/paper7.html), and in the same journal on the same terms 
[this year](http://jair.org/papers/paper3749.html).


## To Conclude

The free price as a guiding principle is important to recomputation.org.  It seemed to be necessary to put some caveats on this principle, and this post is intended to elucidate my current thinking on what those caveats are and what they mean.


