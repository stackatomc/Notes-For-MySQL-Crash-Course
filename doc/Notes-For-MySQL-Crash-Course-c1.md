---
layout: post
title:  "Notes-For-MySQL-Crash-Course-c1"
categories: Notes-For-MySQL-Crash-Course
tags: MySQL
author: stackc
---

>该笔记用于简记数据库和SQL的基本概念




**Outline**

- [第1章 了解SQL](#第1章 了解SQL)
	- [数据库的基本概念](#数据库的基本概念)
		- [数据库和DBMS的概念区分](#数据库和DBMS的概念区分)
		- [三种模式和两层映像](#三种模式和两层映像)
	- [数据类型](#数据类型)
	- [主键](#主键)
	- [SQL 的概念](#SQL 的概念)
	- [本书所需样例表](#本书所需样例表)



---

# 第1章 了解SQL

标签：MYSQL

## 数据库的基本概念

### 数据库和DBMS的概念区分

- 数据库
	- database，抽象，指保存有组织的数据的容器
- DBMS
	- database manager system，数据库管理系统。指数据库软件，如MYSQL

### 三种模式和两层映像

- 模式
	- 描述数据库和表的布局及特性的信息，如数据在表中如何存储,可以存储什么样的数据，数据如何分解等
    - 三种模式
	    - 外模式、模式、内模式
        - 外模式：可以有多个,是不同**数据库用户能够看到的局部数据的逻辑结构**和特征的描述，即**数据视图**. 有关权限，也是保证数据库安全性的有力措施.**(一个数据库中可以有多个外模式)**
        - 模式：指数据库中**全体数据的逻辑结构**和特征的描述，是所有用户的公共数据视图. 不涉及数据的物理存储细节.**(一个数据库只有一个模式)**
        - 内模式：数据在数据库中的**物理存储结构**和存储方式的描述. 如描述数据在表中是如何存放的，可以存储什么样的数据等.**(一个数据库中只有一个内模式)**
        
- 映像
	- 即外模式、模式、内模式之间两种模式间的对应关系,保证了数据库库数据的逻辑独立性和物理独立性。
    - 两级映像
	    - 外模式/模式映像, 模式/内模式映像
        - 外模式/模式映像：对每一个外模式, 都有一个外模式/模式映像定义了外模式与模式的对应关系.当模式改变如增加了新的属性等,数据库管理员只需对外模式/模式映像进行修改,而不需要改变外模式。**优点在于外模式/模式保证了当模式改变时,外模式不用变——逻辑独立性.**
        - 模式/内模式映像：一个数据库中只有一个模式和一个内模式。当数据的存储结构发生改变(如选用了另一个存储结构), 数据库管理员只需对模式/内模式映像进行修改,而不需要改变模式。**优点在于模式/内模式报获赠了当内模式发生改变时,模式不用变——物理独立性**

>[「有且仅有」博客](https://blog.csdn.net/u010297957/article/details/50846279)(参考来源)

### 数据类型

- 正确定义数据库类型限制有助于正确排列数据，并在优化磁盘使用方面其了重要作用

---

## 主键

- 特点
    - 唯一性
    - 可定义一个或不止一个
    - 非空
- 主键的最好习惯
    - 不更新主键列的值(主键用于唯一标识)
    - 不重用主键列的值(唯一性)
    - 不再主键列中使用可能会更改的值(如某个用户的手机号等) 

---

## SQL 的概念

- SQL
	- Structured Query Language，结构化查询语言缩写。专门用来与数据库通信的语言

---

## 本书所需样例表

- 在附录B可下载得到. zip文件，内含 create.sql和populate.sql文件
网址链接如下: [http://www.forta.com/books/0672327120/](http://www.forta.com/books/0672327120/)

 