+++
title = 'Free as in Freedom'
date = 2025-03-09T15:58:57-03:00
draft = false
tags = ['programming']
+++

FREE AS IN FREEDOM
<!--more-->
---
I've wanted to write a post about [free
software](https://www.fsf.org/about/what-is-free-software) for some time, and
this week's Oscars inspired me to do so. _Flow_ (2024), which won the Best
Animated Feature award, was created by a small team of enthusiasts using
Blender an open-source and free software.  

Some people were amazed that a film made with a tool anyone can use could
achieve such greatness. But what they fail to realize is that open-source
software is the state of the art in many fields and should be in even more. 

This victory for free software is just another reminder: _we’ve already won in
the grand scheme of things_, but the work isn’t finished. In this post, I’d
like to delve into the my thoughts of free software

I highly advise reading the [what is free software](https://www.fsf.org/about/what-is-free-software)if you are not familiar with the term. I cant explain it better than the ones that coined the term.


# Free Software Already Won  

The pioneers of free software did not have the privilege of a fully functional system. Today, I am running Debian, and when I check with VMRS (Virtual Richard Stallman), it shows I have only four non-free packages.  

![vmrs](/images/vrms.png)

Being able to achieve this is already a huge victory for users.  

## Free Hardware is Still a Problem  

One of my non-free packages is [Intel's microcode](https://wiki.debian.org/Microcode). Intel has had major security issues, and running a system without its microcode is nearly impossible. Another major problem with proprietary hardware is the [Intel Management Engine](https://en.wikipedia.org/wiki/Intel_Management_Engine).  

If you have never heard of it, read the Wikipedia page. It is a proprietary subsystem with deep access to the system, raising serious security concerns. If you think AMD is free from this issue, think again they have a similar system, the AMD Platform Security Processor (PSP), which also operates outside the user’s control.  

However, free hardware is growing. Open ISAs like RISC-V are gaining momentum, allowing anyone to design a processor without corporate restrictions. Once RISC-V reaches the consumer market, I believe it will be embraced by freedom enthusiasts.  

## The Path to a Fully Free System  

The foundation for a completely free operating system is already here, with **Libreboot** and **Linux-libre**, allowing for a system with no proprietary blobs. However, using such a system daily is still difficult due to processor microcode, as well as **network interface card (NIC) drivers**, which are often proprietary something my VRS output confirms.  

In my opinion, to be truly 100% free, we would need open schematics for the **CPU, all parts of the SoC, DRAM, PCIe, USB controllers**, and more. This is an extreme position within the free software movement, but it is closer to reality than ever before.  

## Eternal Vigilance is the Price of Liberty  

Free software has already achieved what once seemed impossible. We now have fully functional systems that respect user freedom, with only a few remaining proprietary components. This is a significant victory, but the work is not done.  

The fight for free hardware continues, and we will win!

