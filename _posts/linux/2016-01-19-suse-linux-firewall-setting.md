---
title: SuSE linux 防火墙配置之开发端口设置
date: 2016-01-19 17:09:00 +0800
tags:
- SuSE
- linux
- 防火墙
- 端口
---

* toc
{:toc}

# 允许访问多个端口

编辑SuSEfirewall2
- vi /etc/sysconfig/SuSEfirewall2

找到FW_SERVICES_EXT_TCP参数，修改为
- FW_SERVICES_EXT_TCP="7080 ssh 8080 5901 53 8443 443 80"

修改完以后重启防火墙即可
- SuSEfirewall2  restart
或者
- SuSEfirewall2 stop
- SuSEfirewall2 start

