---
title: rust-diesel配置使用与踩坑
date: 2021-11-29 13:50:55
tags: [rust, diesel]
---

## # diesel_cli安装报错

```
cargo install diesel_cli --no-default-features --features postgres

LINK : fatal error LNK1181: cannot open input file 'libpq.lib'
```

window解决办法

```
https://www.postgresql.org/download/windows/
下载安装postgresql
配置环境变量

PATH C:\Program Files\PostgreSQL\10\bin
PATH C:\Program Files\PostgreSQL\10\lib
PQ_LIB_DIR C:\Program Files\PostgreSQL\10\lib
```

即可正常安装diesel_cli

应用也可以正常编译通过