---
layout: post
title:  "python发送邮件给多个人"
date:   2018-10-21 17:16:30
description: 亲测qq邮箱可以，网易邮箱不行
---
```python
import smtplib
from email.mime.text import MIMEText

sender = 'aaa@qq.com'
passwd = '****'
receiver = ["aaaaa@outlook.com","bbbbb@outlook.com"] # 多个收件人放在一个list里面

content = 'hello world'
subject = 'this is a test'

msg = MIMEText(content, 'plain', 'utf-8')  # 中文需参数‘utf-8’，单字节字符不需要

msg['Subject'] = subject
msg['From'] = sender
msg['To'] = ','.join(receiver) # 这里必须要把多个邮箱按照逗号拼接为字符串

server = smtplib.SMTP_SSL("smtp.qq.com", 465) # 亲测qq邮箱才有用，163没用
server.login(sender,passwd)

try:
    server.sendmail(sender, receiver, msg.as_string())
    print('email sent')
except smtplib.SMTPException as e:
    print(e)
```
