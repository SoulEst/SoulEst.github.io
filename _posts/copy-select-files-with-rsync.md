---
layout:     post
title:      Copy select files with rsync
categories: gadgetic philosophic
tags:       arch linux archlinux rsync bash zsh shell backup
---

A few months ago, the BTRFS filesystem that I using on my external hard drive became corrupted. I put in much work trying to recover the filesystem using the tools made for it, but to no avail. I finally opted to recover what 
files I could using PhotoRec. It was a bittersweet moment as I knew that my work was only half done. The external hard drive was also one of my backup system backup drives, and as such had files from a few Arch Linux 
installations. This was all mixed in with the files that I truly wanted, no, needed (especially the music). At the end of the recovery process, I ended up with nearly 1990 folders containing what PhotoRec was able to recover. 
Removing the excess folders (all 1300 of them) came next. Sorting and reviewing were the last two steps, with which I was having trouble creating a solution to the former. I decided on using rsync in a for loop to handle the 
sorting issue. Coming across a post on [Bash For Loop Examples][1], gave me the form I needed to put the code in to accomplish the task.

for
in {1301..1985}
do
for j in png jpg gif
do
rsync -auhP backup/recup_dir.$i/*.$j pictures/
done
for j in mp3 ogg flac
do
rsync -auhP backup/recup_dir.$i/*.$j audio/
done
for j in img dmg iso
do
rsync -auhP backup/recup_dir.$i/*.$j images/
done
for j in zip rar 7z
do
rsync -auhP backup/recup_dir.$i/*.$j archives/
done
for j in doc docx pdf
do
rsync -auhP backup/recup_dir.$i/*.$j documents/
done
done

The shell goes into each recup_dir folder and has rsync copy each specific subtype of a filetype to a certain folder. The process of sorting the files only took an hour for ~110 GB of data on a 2.5" 1 TB hard drive spinning at 
5900 RPM.

Now all I have to do is review the files that I recovered which will take a while.
