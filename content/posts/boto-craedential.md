---
title: "[AWS boto] botoでAWSのcreadentialを指定する"
date: 2018-01-22T13:42:29+09:00
draft: false
---

AWSのPython　SDKであるbotoのメモ。


botoはデフォルトでaws　configureによって設定される情報を使用して認証を行う。  
今回紹介する方法は、その認証情報を利用せずに、自分でAccess　KeyとSecret　Keyを指定する。

クライアント作成時の、パラメータを以下のように、指定する。

{{< highlight python "linenos=table" >}}
import boto3

# 本来は、認証情報のハードコードは、やってはいけません。
client = boto3.client('ec2',  
    aws_access_key_id='<Your Access Key>',
    aws_secret_access_key='<Your Secret Key>'
)
{{< / highlight >}}
