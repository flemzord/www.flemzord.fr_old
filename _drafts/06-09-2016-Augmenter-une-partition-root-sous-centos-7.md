---
layout: post
title:  "Comment augmenter une partition root sous centos 7"
category: Serveur
---

Avec centos7, les deux partitions sytèmes minimals son en LVM (SWAP & ROOT).
vpvcreate /dev/xvda3
vgextend /dev/centos /dev/xvda3
vgdisplay -v
lvextend -l+100%FREE /dev/centos/root
xfs_growfs /dev/centos/root
df -h
