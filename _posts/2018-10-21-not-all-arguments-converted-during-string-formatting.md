---
layout: post
title:  "python往postgresql数据库插入数据出错"
date:   2018-10-21 17:09:30
description: not all arguments converted during string formatting
---


```python

cur.execute("INSERT INTO foo VALUES (%s)", "bar")    # WRONG
cur.execute("INSERT INTO foo VALUES (%s)", ("bar"))  # WRONG
cur.execute("INSERT INTO foo VALUES (%s)", ("bar",)) # correct
cur.execute("INSERT INTO foo VALUES (%s)", ["bar"])  # correct

```