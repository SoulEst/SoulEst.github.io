---
layout:         post
title:          Chugging Along Using Steam
description:    "Installing and setting up Steam on my Arch powered workstation"
modified:       2013-10-08
categories:     gadgetic
tags:           steam valve source arch linux archlinux pacman multilib
comments:       true
---

While Steam is meant to be installed on Debian based operating systems (Ubuntu especially), I prefer Arch. With that in mind, I set out to install and properly set up Steam on my Arch powered workstation. First off, I read the [Steam][1] in the [ArchWiki][2]. Secondly, I 
installed the 

    sudo pacman -S infinality-bundle-multilib/infinality-bundle steam ttf-liberation \
    libtxc_dxtn lib32-libtxc_dxtn lib32-nvidia-utils lib32-nvidia-libgl lib32-flashplugin

After doing that, I linked the flash plugin into the right folder:

    mkdir ~/.steam/bin32/plugins/
    ln -s /usr/lib32/mozilla/plugins/libflashplayer.so ~/.steam/bin32/plugins/

and then enabled unicode version of the <code>en_US</code> locale:

    sudo sed -i 's/#en_US.UTF-8/en_US.UTF-8' /etc/locale.gen

Steam runs excellently on the machine and its Big Picture UI looks great on my monitor. Now I just need to get my DualShock3 controller connected to the computer and I'm all set.

[1]:    https://wiki.archlinux.org/index.php/Steam      "Steam article on the ArchWiki"
[2]:    https://wiki.archlinux.org/index.php/Main_Page  "Main page of the ArchWiki"
