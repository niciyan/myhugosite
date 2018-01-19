---
title: "vsftpdの設定メモ"
date: 2017-12-31T01:43:13+09:00
draft: false
---

## 前置き
vsftpdによる設定で最初にしておいた方がいいもの。  
インストールした後の段階。  
chrootの設定は、また別の記事で。

<dl>
    <dt>OS</dt>
    <dd>Ubuntu16.04LTS</dd>
</dl>

## 手順
/etc/vsftpd.confのファイルを編集する。

{{< highlight "linenos=table" >}}
# コメント外す
write_enable=YES

# コメント外す
chroot_local_user=YES

# 行追加
pasv_min_port=40000
pasv_max_port=50000
{{< / highlight >}}

