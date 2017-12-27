---
title: "今週のメモ　2017-12-27"
date: 2017-12-27T15:44:28+09:00
draft: "false"
---


### AWS cli で処理を待つ（コマンド）
次のようなコマンドで待つことができる。

    # create vpc command with specifying ipv4 cidr
    # output format : json
    $ aws ec2 create-vpc --cidr-block 10.0.0.0/16

    # view wait help doc
    $ aws ec2 wait help

    # wait until vpc is ready 
    $ aws ec2 wait vpc-available --vpc-ids

### Linuxでユーザをsudo権限のグループに入れる
    usermod -aG sudo <username>  ( Ubuntu )
    usermod -aG wheel <username>  ( CentOS )

### dateコマンドで「YYYYMMDD」形式で表示する
    date "+%Y%m%d"

