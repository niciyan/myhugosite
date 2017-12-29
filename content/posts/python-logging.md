---
title: "PythonのLoggingについて"
date: 2017-12-29T10:28:32+09:00
draft: false
tags: [ "python" ]
---

必ず、以下のような作法にする。

    from logging import getLogger, StreamHandler, DEBUG, Formatter

    myformat = Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')

    logger = getLogger("Sample")
    handler = StreamHandler()
    handler.setLevel(DEBUG)
    handler.setFormatter(myformat)
    logger.setLevel(DEBUG)
    logger.addHandler(handler)
    # logger.propagate = False

    logger.debug('hello')



    try:
        logger.info("Program started.")
        for i in range(3):
            print("count {}".format(i))
        raise Exception
    except Exception as e:
        logger.error("We got error while excuting program. {}".format(e))

## 主要ロギングハンドラ

* StreamHandler
* FileHandler

## フォーマッタの種類

* %(asctime)s 
* %(name)s 
* %(levelname)s 
* %(message)s
