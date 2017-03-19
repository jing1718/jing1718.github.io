---
layout: post
category: "oracle"
title:  "Oracle ɾ���û��ͱ�ռ�"
tags: [Oracle,�û�,��ռ�]
summary: "Oracle ɾ���û��ͱ�ռ�"
---

###oracle ��sysdba ��½
sqlplus / as sysdba;

###�鿴�û�������״�� 
select username,sid,serial# from v$session;
<br>
USERNAME			      SID    SERIAL#<br>
------------------------------ ----------<br>
JKSCORE 			      151      31773<br>

<br>
###�ҵ�Ҫɾ���û���sid,��serial����ɾ��
<br>
alter system kill session'151,31773';<br>

<br>
###ɾ���û�
<br>
drop user ${�û���} cascade;<br>

<br>
###ɾ����ռ�
<br>
drop tablespace ${��ռ�} including contents and datafiles;<br>

<br>
###������ռ�
<br>
create tablespace ${��ռ�} datafile '/��ռ���Ŀ¼/${��ռ�}.dbf' size 1024M autoextend on next 100M;<br>

<br>
###�����û�
<br>
create user ${�û���} identified by ${�û�����} default tablespace ${��ռ�};<br>