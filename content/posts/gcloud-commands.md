---
title: "gcloud コマンドのメモ"
date: 2017-12-27T16:03:32+09:00
draft: false
---

### gcloud のアップデートや、インストール
    $ gcloud components update
    $ gcloud components install app-engine-go

### App Engine 
デプロイ時にバージョンを指定する

    $ gcloud app deploy --version <version-name>
    ↓例: devのバージョン名でデプロイする。
    $ gcloud app deploy --version dev

