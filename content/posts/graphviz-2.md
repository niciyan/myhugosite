---
title: "Graphvizサンプル2"
date: 2017-12-29T18:08:43+09:00
draft: false
tags: [ "graphviz" ]
---

## コード

{{< highlight "linenos=table" >}}
digraph graph_name {

  graph [ ranksep = 2; ]

  root -> Child1 [ color = "red" ];
  root -> Child1 [ color = "red" ];
  root -> Child1 [ color = "red" ];
  root -> Child1 [ color = "red" ];

  root -> Child1 [ color = "blue" ];
  root -> Child2 [ color = "blue" ];
  root -> Child3 [ color = "blue" ];
  root -> Child4 [ color = "blue" ];
  root -> Child5 [ color = "blue" ];
  root -> Child6 [ color = "blue" ];
  root -> Child7 [ color = "blue" ];
}
{{< / highlight >}}

## 出来上がった図

{{% zoom-img src="/images/graphviz/multi.png" %}}


## コード

{{< highlight "linenos=table" >}}
digraph graph_name {

  graph [ ranksep = 2; ]

  root -> root_child [ color = "red" ];
  root -> root_child [ color = "red" ];
  root -> root_child [ color = "red" ];
  root -> root_child [ color = "red" ];

  root_child -> Child1 [ color = "blue" ];
  root_child -> Child2 [ color = "blue" ];
  root_child -> Child3 [ color = "blue" ];
  root_child -> Child4 [ color = "blue" ];
  root_child -> Child5 [ color = "blue" ];
  root_child -> Child6 [ color = "blue" ];
  root_child -> Child7 [ color = "blue" ];
}
{{< / highlight >}}


## 出来上がった図

{{% zoom-img src="/images/graphviz/multi2.png" %}}

