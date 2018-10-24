---
layout: post
title:  "查询schema利的所有表"
date:    2018-10-24 11:22:49
description: postgresql schema table
---

```
select * from information_schema.tables where table_schema='public'
```