---
layout: post
category: "reading"
title:  "SuSE linux 防火墙打开多端口"
tags: [SuSE,linux,防火墙,端口]
summary: "允许访问多个端口"
---

编辑SuSEfirewall2
vi /etc/sysconfig/SuSEfirewall2

找到FW_SERVICES_EXT_TCP参数，修改为
FW_SERVICES_EXT_TCP="7080 ssh 8080 5901 53 8443 443 80"

修改完以后重启防火墙即可
SuSEfirewall2  restart

