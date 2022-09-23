---
title: Tech Stack
category: Tools
tags: [ WSL , vim , zsh, tmux, Linux ]

tech_stack_img: https://lh3.googleusercontent.com/I91ndAUusoY4emaTOwQPmPPiQf1A4YDX-x1CTle-nici4Py3Nwuy1SmC74AuXzd6gj6R5blLWnqZDEKd2mbfovj5xStnp3yrFyHMav_ksDD3juXqbgXQ_uMFlA7sy9UAUF_xYt-F=w2400
---

![tech stack image]({{page.tech_stack_img}})

I personally have had my fill for testing the waters in terms of my work environment:- be they due to compulsion, curiosity or a complete coincidence.  
This is just a quick overview of my vanilla tech stack : my limbs, one could say; we'll get into tools sometime soon.

## WSL : Windows Subsystem for Linux

 - I started my bachelors in the monsoon of 2018 and I was in for a surprise when I discovered that my workstation did not support dual boot. 
 - I wondered, what's all the big fuss about using Linux - what's the problem with Windows... 
 - I found out quickly the hard way and had to spend a big chunk of my first semester rearing a virtual machine off the left-overs of a hungry host OS.
 - I will post the complete story some other day but for now...

WSL is a life-saver, in fact I would go ahead and say that it's better than dual booting (except when you are a systems' programmer) in most cases.   
Anyway, Not just WSL but what Microsoft has been doing with open source as a whole is commendable - making the life of developers (and gamers: large intersection there) all around easier.  

WSL(2.0) , in a nutshell, is a different kind of hypervisor compared to your conventional virtualisation solutions. It allows you to run Linux binaries and manipulate data on the same file system. No cryptic disk images, shared folders; nothing of that sort - just one common environment. 


There are, however, a few setbacks:-
 - The X windowing interface has not yet been integrated with the tool itself and I hope that happens soon,
 	- however (again), we like living on the command line - and who in the right mind would miss the opportunity of not having a GUI.
 - The support for specific daemons (background processes) is not that elaborate as of now, and this doesn't play well when you'd like get low (level). 
 	- I discovered this in my Operating Systems class and had to switch to good old virtual box for those couple assignments : hope they sort this out too.
	- I know that is a bit too much to ask, but if they're shipping a Linux kernel with windows, why shouldn't they try to pass the Turing test (for a native linux experience).

## Vim
 
This is a contagious one. Once you get past the learning curve, you start seeking vim key-bindings everywhere: your browser, your OS, your texting clients...,everywhere.  

I'm not really a hardcore vim ninja yet (don't have my own plugin) but it does pay off. I'm also considering getting into emacs, specifically for Lisp. The transfer shouldn't be that big of an issue as extensions like viper ease off the adapting process from *vim*my habits to whatever  emacs' philosophy is (I don't know).  

## tmux

I added this one to the arsenal when I started working with long process on remote servers. Prior to that, my go to multiplexer was neovim, but this does that job with more capabilities, so why not...  
Windows Terminal also has its own multiplexer by the way, but it doesn't feel complete.  

## zsh

This one does help you taint your environment according to your own tastes.   
I personally use the powerline 10k config with OH-MY-ZSH, with a customized utf-8 encoded font - enhances the cli experience.

