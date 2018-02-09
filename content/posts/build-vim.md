---
title: "Vimをビルドする時のconfigureオプション"
date: 2018-02-09T15:55:30+09:00
draft: false
---

{{< highlight "linenos=table" >}}
$ cd vim/src/
$ ./configure \
    --with-features=huge \
    --enable-fail-if-missing \
    --enable-perlinterp \
    --enable-pythoninterp \
    --enable-python3interp \
    --enable-rubyinterp \
    --enable-luainterp 
{{< / highlight >}}

### オプションについて補足
luaはプラグインの依存関係で必須となる。  
pythonとpython3は、個人的にスクリプトを書くことがあるので、入れている。  
perlとrubyはおまけ。  
