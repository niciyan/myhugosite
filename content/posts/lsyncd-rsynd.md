---
title: "LsyncdとRsyndにより、サーバ間でファイルを同期する。"
date: 2018-02-14T16:24:11+09:00
draft: false
---

# 概要
２つのサーバ間でファイルの同期を図る。
lsyncdとrsyncdを使用する。

# 手順
* 同期元をマスター、同期先をスレーブとする。
* マスターにlsyncdを導入し、ファイル変更を検知する。
* 変更があれば、スレーブのrsyncdとやりとりをして、ファイルを同期する。

> マスターに変更があるたびに、同期をする仕掛けとなっている。

### 設定ファイル マスター

{{< highlight lua "linenos=table" >}}
-- # vim /etc/lsyncd.conf
settings {
    logfile = "/var/log/lsyncd/lsyncd.log",
    pidfile = "/var/run/lsyncd.pid",
    statusFile = "/var/log/lsyncd/lsyncd.stat",
    nodaemon     = false,
    maxProcesses = 3,
    insist       = 1,
    statusInterval = 1
}

sync {
    default.rsync,
    source = "/home/ec2-user/sync_src",
    target = "ip-172-30-2-36.ap-northeast-1.compute.internal::hoge",
    delay     = 5,
    delete = true,
    rsync     = {
        archive = true,
        password_file = "/etc/rsync.passwd",
        compress = false
    }
}

-- # vim /etc/rsync.passwd
---
{ password string }

{{< / highlight >}}


### 設定ファイル スレーブ

{{< highlight lua "linenos=table" >}}
-- # vim /etc/rsyncd.conf
uid = root
gid = root
read only = no
log file = /var/log/rsyncd.log
pid file = /var/run/rsyncd.pid
hosts allow = 172.30.2.9
hosts deny = *
read only = false
exclude = .svn
secrets file = /etc/rsync.passwd

[hoge]
path = /home/ubuntu/try_lsync/
comment = "testing lsyncd and rsyncd."

-- # vim /etc/default/rsync
----
RSYNC_ENABLE=true

-- # vim /etc/rsyncd.passwd
{ password string }
{{< / highlight >}}

# どうなるか
マスター側でファイルを変更するたびに、スレーブに対して同期される。

> What is lsyncd?  
> Lsyncd watches a local directory trees event monitor interface (inotify or fsevents). It aggregates and combines events for a few seconds and then spawns one (or more) process(es) to synchronize the changes. By default this is rsync. Lsyncd is thus a light-weight live mirror solution that is comparatively easy to install not requiring new filesystems or block devices and does not hamper local filesystem performance.  
> https://github.com/axkibe/lsyncd

