---
title: "Linuxでランレベルを見る"
date: 2018-01-19T11:50:56+09:00
draft: false
---

## Linuxで現在のランレベルを見るためのコマンド

{{< highlight "linenos=table" >}}
代表例。
$ runlevel
もうひとつ。
$ who -r

おまけ
# chkconfig (各ランレベルでのサービス利用可能状況を見る)
{{< / highlight >}}



## ランレベルとは
次から引用。
http://www.linfo.org/runlevel_def.html

> 0 - System halt; no activity, the system can be safely powered down.   
> 1 - Single user; rarely used.   
> 2 - Multiple users, no NFS (network filesystem); also used rarely.  
> 3 - Multiple users, command line (i.e., all-text mode) interface; the standard runlevel for most Linux-based server hardware.   
> 4 - User-definable   
> 5 - Multiple users, GUI (graphical user interface); the standard runlevel for most Linux-based desktop systems.   
> 6 - Reboot; used when restarting the system.  
