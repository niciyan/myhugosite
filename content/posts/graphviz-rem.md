---
title: "Graphvizのサンプル1"
date: 2017-12-29T10:45:50+09:00
draft: false
---

## コード

    digraph { 

        graph [
            rankdir = LR;
        ]

        Ins1 -> Ins2;
        Ins2 -> Ins1;
    }

## 出来上がった図

{{% zoom-img src="/images/graphviz/one.png" %}}

## グラフに与えた設定

* rankdir : LR

