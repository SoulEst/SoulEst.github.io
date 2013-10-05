---
layout:     post
title:      
categories: 
tags:       
---

for i in {1301..1985}
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
