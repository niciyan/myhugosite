---
title: "MYSQLのIP制限を解除したい"
date: 2017-12-23T20:00:01+09:00
draft: false
tags: [ "mysql" ]
---

MYSQLのbind-address制限を解除する。  
bind-addressの行をコメントアウトする。  


    $ sudo vim /etc/mysql/mysql.conf.d/mysqld.conf ( /etc/mysql/mysql.conf )
    --途中は省略--
    # bind-address 127.0.0.1
