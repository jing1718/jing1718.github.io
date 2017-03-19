---
layout: post
category: "oracle"
title:  "Oracle 删除用户和表空间"
tags: [Oracle,用户,表空间]
summary: "Oracle 删除用户和表空间"
---

###oracle 用sysdba 登陆
sqlplus / as sysdba;

###查看用户的连接状况 
select username,sid,serial# from v$session;
<br>
USERNAME			      SID    SERIAL#<br>
------------------------------ ----------<br>
JKSCORE 			      151      31773<br>

<br>
###找到要删除用户的sid,和serial，并删除
<br>
alter system kill session'151,31773';<br>

<br>
###删除用户
<br>
drop user ${用户名} cascade;<br>

<br>
###删除表空间
<br>
drop tablespace ${表空间} including contents and datafiles;<br>

<br>
###创建表空间
<br>
create tablespace ${表空间} datafile '/表空间存放目录/${表空间}.dbf' size 1024M autoextend on next 100M;<br>

<br>
###创建用户
<br>
create user ${用户名} identified by ${用户密码} default tablespace ${表空间};<br>