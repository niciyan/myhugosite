---
title: "MYSQLの操作あれこれ"
date: 2017-12-24T16:05:37+09:00
draft: false
---

### 権限設定
    mysql> flush privileges on <schema>.* to '<user>'@'<host>';

### 権限を見る
    mysql> show grants;

### データベースのステータスを見る。
    mysql> status;

### DDLを見る。
    mysql> show create table <tablename>;
    mysql> show create user <tablename>;

### sample eer
{{% zoom-img src="/images/eer.png" %}}


