
---
layout: post
title:  "遍历目录及子层目录下的所有文件"
date:   2018-10-21 13:09:30
description: Python dir path files
---


```python
for dirpath,dirnames,filenames in os.walk('D:\'):
    for name in filenames:
        f = os.path.join(dirpath,name)
        print(f)  #f即使所有的文件的绝对路径
```