
---
layout: post
title:  "万得数据写CSV"
date:   2018-10-21 13:09:30
description: Python 万得 pandas dataframe CSV
---


```python
from WindPy import w
import pandas as pd

w.start()
wdata = w.wset("sectorconstituent","date=2017-05-08;sectorid=a001010100000000")

df = pd.DataFrame()
df['code'] = wdata.Data[1]
df['sec_name'] = wdata.Data[2]
df.to_csv('allstocks.csv',index=False)
```
