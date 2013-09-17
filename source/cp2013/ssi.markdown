---
layout: page
title: "The Recomputation Manifesto: Draft Blog for SSI"
date: 2013-07-01 12:45
comments: true
sharing: true
footer: true
---

## Here's How It Is. 

At the start of this year there was a wonderful stream of tweets with hashtag <a href="https://twitter.com/search?q=%23overlyhonestmethods&amp;src=hash">#overlyhonestmethods</a>. 
Many scientists posted the kind of methods descriptions which are true but would never appear in a paper.
This is my favourite:

<blockquote class="twitter-tweet"><p>You can download our code from the URL supplied. Good luck downloading the only postdoc who can get it to run, though <a href="https://twitter.com/search?q=%23overlyhonestmethods&amp;src=hash">#overlyhonestmethods</a></p>&mdash; Ian Holmes (@ianholmes) <a href="https://twitter.com/ianholmes/statuses/288689712636493824">January 8, 2013</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Although every scientific primer says that replication of scientific experiments is key, to quote this tweet, *good luck* replicating experiments in computational science. There has been 
significant [recent pressure](http://sciencecodemanifesto.org) for scientists to make their code open, but this is not enough.
Even if I hired the only postdoc who can get the code to run,
she might have forgotten the *exact* details of how an experiment was run. 
Or just might not know that there's a critical dependency in her code on an obsolete version of a library.

The current state of experimental reproducibility in computer science is lamentable. 
The result is inevitable: occasionally, experimental results enter the literature which are just wrong. I don't mean that the results don't generalise. I mean that an algorithm 
which was claimed to do something just does not do that thing: for example if the original implementation was bugged and was in fact a different algorithm.
I suspect this is common but I know for certain that this has happened: [here's an example](http://link.springer.com/chapter/10.1007/11402763_4) from my own research area, discovered by my friend and 
[tenacious pursuer of replication](http://www.mdpi.com/1999-4893/5/4/545)
[Patrick Prosser](www.dcs.gla.ac.uk/~pat).

## Here's How It Should Be: The Recomputation Manifesto

I've written the "The Recomputation Manifesto" says how I think things should be. The [full text](http://arxiv.org/pdf/1304.3674v1.pdf) is available at [arxiv](http://arxiv.org/abs/1304.3674v1).
I'm going to talk about the six points of the manifesto, giving an example, and saying a bit more about the last two points because they often prompt discussion.

> 1. Computational experiments should be recomputable for all time
2. Recomputation of recomputable experiments should be very easy.
3. It should be easier to make experiments recomputable than not to
4. Tools and repositories can help recomputation become standard
5. The *only* way to ensure recomputability is to provide virtual machines
6. Runtime performance is a secondary issue




### 1. Computational experiments should be recomputable for all time

A quick word about the word. I'm using the word "recomputation" to mean exact replication of a computational experiment. 
I wanted to avoid a nameclash with [replication](https://en.wikipedia.org/wiki/Replication_(computing\)). 
Recomputation isn't a neologism - the word 
[predates the USA](http://www.oed.com/view/Entry/271854?redirectedFrom=recomputation#eid) - but it is adding a nuance. 

But should experiments be recomputable for all time? I think so. I don't see any sensible notion of a useful life beyond which 
experiments are discardable. 
Imagine if physicists could keep Galileo's telescopes for almost nothing, but couldn't be bothered.

Computer storage gets [exponentially cheaper over the time](http://www.mkomo.com/cost-per-gigabyte), so the cost of storing for a few years 
is almost the same as storing forever.
There are issues to do with changing machines, but [people are on it](http://www.openplanetsfoundation.org/blogs/2012-12-27-state-art-system-preservation).

### 2. Recomputation of recomputable experiments should be very easy.


The next paragraph contains a claim about a chess position.
It's based on an experiment I ran. Anyone in the world can check that the experiment does what I say.
The instructions for rerunning it are a few lines. 

{% img right /images/Puzzle9Q.png 400 Solution to a chess puzzle %}
> The illustrated position contains the king and all nine possible queens of each colour, i.e. the original and eight promoted pawns. No queen is on the same row, column or diagonal as any piece of the opposite colour.
The illustrated position is the only possible chess position for which the description of the previous paragraph is true, excepting rotations and reflections of the chessboard, or swapping black and white. 

This experiment is available at [http://recomputation.org/cp2013/experiment1.html](http://recomputation.org/cp2013/experiment1.html). 
After downloading the experiment box and booting, it takes only about 1 minute to run. 

It's *not true* that I can make available an experiment which proves my scientific claims are true. 
My code could be wrong, or the libraries I'm using (the excellent [Gecode](gecode.org) constraint library)
could be bugged. But it *is true* that I can make available an experiment which allows any scientist in the world - or anyone else - the chance to recompute my experiment to make sure its results are as I said. 
And it *is true* that anyone can look inside my experiment to see if they can spot any mistakes, or use any good aspects of my experimental setup in their own experiments.
The experiment also contains the source code and all scripts necessary to run the experiment.

By the way, to confirm that the instructions for rerunning are brief, here they are *in toto* in a Linux/Mac environment.
Before running it you need two free tools, 
[Vagrant](vagrantup.com) and [Virtual Box](http://www.virtualbox.org). Open a terminal and ... 

    mkdir anydir
    cd anydir
    vagrant init experiment1 http://recomputation.org/cp2013/experiment1/recomputation-QueensPuzzle-b.box
    vagrant up

In a few minutes the experiment should have run and the results should be in `anydir`. The only thing I omitted are the instructions to free up the resources used at the end: `vagrant destroy` and then `vagrant box remove experiment1 virtualbox`, since you ask.

An aside: while it looks like I am blowing my own trumpet by giving you an example of an experiment, this is not how I have normally done things. Probably none of my own scientific 
experiments are recomputable. The example is an example of how things should be, not the way I have done them in the past.  If you want me to blow somebody's trumpet, I choose C. Titus Brown, 
who has made available a virtual machine (VM) with experiments [for a serious paper](http://ivory.idyll.org/blog/replication-i.html) instead of a toy chess puzzle.

### 3. It should be easier to make experiments recomputable than not to

There's a technical sense in which this can never be true: i.e. just don't do the extra step to make your experiment recomputable.
So this needs a little justification. What I really believe is that we can make it very easy to make experiments recomputable, 
and that the benefits will be large. Not so much the benefit of feeling good that an experiment is repeatable, but 
the benefit of being *able* to rerun experiments for final copy of a paper instead of *not* being able to. Or being able to 
rerun them with new data, or a new experiment like the old one... all made easy by having your old experiments be recomputable.

### 4. Tools and repositories can help recomputation become standard

There are already a number of tools out there, and a smaller number of repositories. Among new repositories springing up is 
one I started at [recomputation.org](recomputation.org). The particular focus of this one will be scientific experiments, and trying to make them 
recomputable for all time (or as long as we can.) I've started a list of [resources](recomputation.org/resources) which points you at some 
interesting tools, repositories, and other stuff.

### 5. The *only* way to ensure recomputability is to provide virtual machines

The reason that we need to store virtual machines with experiments in them is that nothing else can guarantee to get the original experiment to run. 
It may be true that code you make available today can be built with only minor pain by many people on current computers. That is unlikely to be true in 5 years, and hardly credible in 20. 
So the best - and I think only realistic - way to ensure recomputability is to provide virtual machines.
I don't think this claim is either novel or controversial. [Bill Howe](https://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=6193081) 
has made the case in detail. Very recently [David Flanders](http://dfflanders.wordpress.com/2012/06/07/a-new-era-for-open-source-free-open-and-easily-reusable-software-for-academia/) 
made a similar case.

There is a problem that using virtual machines brings. Basically, they are big. The VM for the experiment above is almost 400MB to download. And it's downloading and uploading that is the real 
problem. As well as being cheap, disk space is scalable (because I can buy more disks). But download speeds limit how many VMs sombody can download and run. Upload speeds limit how fast they can give us VMs: and some experiments might need hundreds of gigabytes of data. 

One thing I hate is when people say "No, there's no problem" and then say "because you can do X". What they mean is: *"Yes,* there's a problem and you can do X as a workaround."

Yes there's a real problem, but I think there are workarounds. 

We are currently working on making experiments for the conference [CP2013 recomputable](http://recomputation.org/blog/2013/06/10/welcome-to-cp-2013-authors/). 
"We" means [Lars Kotthoff](http://4c.ucc.ie/~larsko/) and I. We'll be running a tutorial at the conference on recomputation.
We are not asking people to send us VMs, but to send us what they think we need to get the experiment to run. This is usually a few megabytes of code and maybe executables. Assuming we can run it in a standard environment, we can make our own VM without one ever being sent to us. We can also provide zipped versions of the experiment directory for people to download also. If they have the right environment they can run the experiment too. So the huge up or download is not always necessary. But we still have to create and store the full VM: because we can't know what trivial change to the environment might stop the experiment working, or (worse) make it appear to work but actually have a major change in it.



### 6. Runtime performance is a secondary issue

This is a second point that causes a lot of discussion. Many scientific experiments in computing seek to show that one method is faster than another method.
But my manifesto says that this is a secondary issue. This can - understandably - produce incredulity.
My response to this one is a little bit different to the last one. But it does start the same. Yes there's a real problem. Run time performance is often critical and normally can't be reproduced 
in a VM. 

But instead of offering workarounds I suggest these two thoughts. 

First is the obvious point. If I can't run your experiment at all, then I can't reproduce your times. So recomputation is the *sine qua non* of reproducing runtimes. 

Second is a less obvious one. The more I think about it, the less I think there is a meaningful definition of the one true run time. I have myself put significant effort into making sure that runtimes are consistent. But however we do this, it makes our experiments less realistic. With rare exceptions (perhaps some safety critical systems) our algorithms will not be used in highly 
controlled situations, moderated to reduce variability between runs or to maximise speed of this particular process. Algorithms will be run as part of a larger system, in a computer 
sometimes with many other processes and sometimes with few. And because of the way that computing has developed, sometimes in raw silicon and sometimes in virtual machines.
So the more I think about it, the more I think that what matters is the distribution of run times.  For this, your experiment on your hardware is important. But so are future recomputations
on a wide variety of VMs running on a variety of different hardware.

So my claim remains: runtime performance is secondary to the crux of recomputation. *And* if you make your experiments recomputable, maybe over time we will get a better understanding how your performance is affected by the underlying real or virtualised hardware . 


## recomputation.org and Software Sustainibility

I've mentioned the website [recomputation.org](recomputation.org), intended to be a repository of recomputable experiments for all time. Our slogan is "If we can compute your experiment now, anyone can recompute it 20 years from now". Twenty years - never mind all time - is an ambitious target, especially for a repository which now holds one experiment (the chess puzzle).
We are ambitious, and unashamedly so. We want to change the way Computer Science is done. 
We might not make it. But this is something where it is better to try and fail than not to try. Computer Science can be better, and one way is by 
those of us who care putting effort into making experiments recomputable and keeping them that way. 

I look forward to working with the Software Sustainability Institute. I think the interest crosses both ways. There may be things that SSI do that we can help with. 
But of course 
there are many many things that SSI do that can help us. Apart from anything else, a critical point is to ensure sustainability of our own
software and systems over the long term.

Oh, and by the way, it's not just Sotware Sustainability I'm looking forward to working with. If something I've said sparks your interest - or your disagreement - I'd love to hear from you 
and maybe work with you to make computing more recomputable in the future.


## About the Author

[Ian Gent](http://www.cs.st-andrews.ac.uk/~ipg)
is Professor of Computer Science at the University of St
Andrews, Scotland. Of his non peer-reviewed papers, his most cited by
far is [“How Not To Do It”](http://scholar.google.co.uk/citations?view_op=view_citation&hl=en&user=-ufUvmEAAAAJ&cstart=20&citation_for_view=-ufUvmEAAAAJ:MXK_kJrjxJIC),
a collection of
embarrassing mistakes he and colleagues have made in computational
experiments. To show how good we are at not doing things right, we even
mis-spelt the name of one of the authors: it's Ewan, not Ewen MacIntyre! 


