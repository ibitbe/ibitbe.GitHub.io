---
layout: post
title:  "dataframe写入postgresql数据库中"
date:   2018-10-21 14:09:30
description: python pandas dataframe postgresql
---


```python
from sqlalchemy import create_engine
import pandas as pd
import numpy as np
```

* 连接数据库

```python
engine = create_engine('postgresql://rolename@localhost:5432/databasename') 

# create_engine说明：dialect[+driver]://user:password@host/dbname[?key=value..]
```

* 写入数据库

```python
data = pd.DataFrame(np.arange(15).reshape(3,5),index=['one','two','three'],columns=['a','b','c','d','e'])
try:
    data.to_sql('tablename',engine,index=False,if_exists='append')
except Exception as e:
    print(e)
```
