---
layout: post
title: "On Virtual Machines Considered Harmful for Reproducibility"
date: 2013-07-16 18:07
comments: true
categories: 
---
This post is to summarise a couple of comments I made to a post from Titus Brown.
But I'm crossposting here 
because I really want to be the kind of scientist who focusses on points made against his point of view, and 
gives them air. 

First some background. I recently wrote a [a blog post about the recomputation manifesto](http://www.software.ac.uk/blog/2013-07-09-recomputation-manifesto)
at the [Software Sustainability Institute](http://www.software.ac.uk/). I was very pleased to see this cause some interesting discussion 
take place at [Hacker News](https://news.ycombinator.com/item?id=6050138).

By far the most interesting response I saw today was this tweet.

<blockquote class="twitter-tweet"><p>The Recomputation Manifest is great (<a href="http://t.co/uKkwkRw9kC">http://t.co/uKkwkRw9kC</a>) but I fundamentally disagree with loaded-VM approach <a href="http://t.co/UjkLN6BLwF">http://t.co/UjkLN6BLwF</a></p>&mdash; Titus Brown (@ctitusbrown) <a href="https://twitter.com/ctitusbrown/statuses/357147872971603969">July 16, 2013</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

This gave me a scare and a thrill because Titus Brown - as I mention in the blog post - has gone out of his way to make his experiments recomputable so I really 
admire him... so the thrill was him saying the Manifesto is great.  The scare was the fundamental disagreement and when I saw the blog post title ["Virtual Machines Considered Harmful for Reproducibility"](http://ivory.idyll.org/blog/vms-considered-harmful.html), I got even more scared.  And then embarrassed when I realised the post was 7 months old.

Please read Titus's post in full, but here are some taster quotes:

> This idea -- that posting a VM is sufficient for reproducibility -- has hit my Twitter feed a couple of times now, and each time I feel compelled to make the point that this isn't useful reproducibility.  ... 

> To put it another way, it is certainly true that posting a virtual machine is a way to make your research reproducible. It's just not a very useful way, in the sense that it effectively blocks remixing or mashing up the code. ... 

> In essence, providing a gigantic black box of custom installed code that was installed, set up, and executed by experts just isn't very useful to many people.

To my relief, there's almost nothing I disagree with in Titus's post.  He makes a lot of great points.   Really. Read the post. 

What I'm going to do is (slightly edited) repost my comments on more or less the only things I did disagree with... but honestly, these are minor points.

Basically I agree with almost everything you say. *From now on "you" means Titus Brown since I was commenting on his post*.

You have probably seen but this is a paper also arguing against pure replication: 
[Replicability is not Reproducibility: Nor is it Good Science](http://cogprints.org/7691/7/icmlws09.pdf)

Perhaps my overall response can be summarised as this. 
You say "that posting a VM is sufficient for reproducibility" and I agree completely. But I would say that a VM is _necessary_ for reproducibility.

But yes, making it as easy as possible for anyone to reproduce your work will help everyone including yourself. And most importantly yourself.

Actually it's NOT necessary for you to provide the VM. It's fine if you can provide an installer or other workflow which works in my VM. Then I can archive it, and the community has a safe VM we can fall back on if the installer stops working for some weird reason.

So there are a few things I disagree with.

The title. I don't agree VMs are harmful for reproducibility, although I can see that focussing primarily on VMs could lead to people thinking that they are sufficient as well as necessary - and I'll try to avoid this in my own prosletizing in future.  And it's a title of a blog post, it's fine if the title is slightly more provocative than the content.

I think I agree with Bill Howe and disagree with your disagreement with him. That is I would rather have shoddy VMs than nothing, and unfortunately I think that's the choice we face. If we can bring people in to the area of making experiments reproducible then we have a chance to persuade them to do it in better and more useful ways.

Incidentally I'm trying to sell the word "recomputation" for replication of computational experiments. Without doubt or ambiguity that means what you describe as non-useful reproducibility.

And finally I think a VM is still very useful for makers too - though I think that's a lovely point to make about users/makers. One thing I like about making a VM available is that if I can't get your installer to work, I can go in and look at the exact machine and see if I can figure out what's up - and maybe other nice aspects of your setup I can copy.

Anyway, I remain a huge fan and No idea why I only spotted this blog post today.
Thanks for the really interesting post.
