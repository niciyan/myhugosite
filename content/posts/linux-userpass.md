---
title: "Linuxでユーザを作成し、パスワードを変更する。"
date: 2018-01-11T10:56:49+09:00
draft: false
---

Create new user and Change password for the user.

{{< highlight "linenos=table" >}}
adduser <username>
echo <username> | passwd <password> --stdin
{{< / highlight >}}

