---
layout:     post
title:      Honing my Arch-ery skills
categories: gadgetic philosophic
tags:       arch archlinux user repository aur pkgbuild sed
---

Over the weekend, I started working on a couple packages for the Arch User Repository (AUR for short). The first one is for QtSixA which I adopted from maandree and then updated. The updates included adding udev rules for 
automatically pairing SixAxis controllers with sixpair as well as fixing a couple errors that namcap had pointed out to me (wrong version of python being called). I ended up learning how to best setup a <code>PKGBUILD</code> 
and how to use <code>diff</code> (as opposed to git and vimdiff). The second one is for GIMP Painter which I'm working on for myself and will be sharing with the community. There is a PKGBUILD for GIMP Painter in the AUR already but it's for version 2.6.10 
which is over two years old. The PKGBUILD that I'll be uploading for GIMP Painter will pull its code from the <code>gimp-painter-2.7</code> branch of the GIMP Painter git repository and compile it.

Today, I started working on the 32-bit chroot for the 64-bit installation that I needed for Steam and for compiling WINE. I used xyne's arch32-light package to setup and configure the chroot. All that needed to be done was:

    sudo pacman32 -Sy bash coreutils filesystem grep gzip licenses sed base-devel xorg-xhost infinality-bundle xf86-video-intel libtxc_dxtn ttf-liberation flashplugin


