---
layout: post
title:  "python对文件的操作"
date:    2018-10-24 11:11:49
description: Python file path
---

```python

# 路径和文件名的拼接
import os
fullpath = os.path.join(path,filename)

# 判断文件是否存在，存在则删除
if os.path.exists(fullpath):
    os.remove(fullpath)

```

