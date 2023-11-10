---
title: MySQL数据库
date: 2022-09-23 18:49:36
tags:
  - MySQL
categories:
  - 数据库
cover: image/cover3.jpg
author: ChenZheng
---

# 第 00 章_写在前面

- 讲师：尚硅谷-宋红康（康师傅）
官网： **[http://www.atguigu.comhttp://www.atguigu.com/](http://www.atguigu.comhttp//www.atguigu.com/)** )

## 一、MySQL数据库基础篇大纲

**MySQL数据库基础篇分为 5 个篇章：**

## 1. 数据库概述与MySQL安装篇

- 第 01 章：数据库概述
- 第 02 章：MySQL环境搭建

## 2. SQL之SELECT使用篇

- 第 03 章：基本的SELECT语句
- 第 04 章：运算符
- 第 05 章：排序与分页
- 第 06 章：多表查询
- 第 07 章：单行函数
- 第 08 章：聚合函数
- 第 09 章：子查询

## 3. SQL之DDL、DML、DCL使用篇

- 第 10 章：创建和管理表
- 第 11 章：数据处理之增删改
- 第 12 章：MySQL数据类型精讲
- 第 13 章：约束

## 4. 其它数据库对象篇

- 第 14 章：视图
- 第 15 章：存储过程与函数
- 第 16 章：变量、流程控制与游标
- 第 17 章：触发器

## 5. MySQL 8 新特性篇

- 第 18 章：MySQL 8 其它新特性

## 二、MySQL高级特性篇大纲

**MySQL高级特性分为 4 个篇章：**

### 1. MySQL架构篇

- 第 01 章：Linux下MySQL的安装与使用
- 第 02 章：MySQL的数据目录
- 第 03 章：用户与权限管理
- 第 04 章：逻辑架构
- 第 05 章：存储引擎
- 第 06 章：InnoDB数据页结构

### 2. 索引及调优篇

- 第 07 章：索引
- 第 08 章：性能分析工具的使用
- 第 09 章：索引优化与SQL优化
- 第 10 章：数据库的设计规范
- 第 11 章：数据库其他调优策略

### 3. 事务篇

- 第 12 章：事务基础知识
- 第 13 章：MySQL事务日志
- 第 14 章：锁
- 第 15 章：多版本并发控制(MVCC)

### 4. 日志与备份篇

- 第 16 章：其它数据库日志
- 第 17 章：主从复制
- 第 18 章：数据库备份与恢复

## 三、MySQL高手是怎样炼成的

**针对开发工程师、DBA、运维**

- mysql服务器的安装配置
- SQL编程(自定义函数、存储过程、触发器、定时任务)
- 数据库索引建立
- SQL语句优化
- 数据库内部结构和原理
- 数据库的性能监控分析与系统优化
- 各种参数常量设定
- 数据库建模优化
- 主从复制
- 分布式架构搭建、垂直切割和水平切割
- MyCat
- 数据迁移
- 容灾备份和恢复
- 对开源数据库进行二次开发

**数据库就像一棵常青的技能树** ，不管是普通开发还是首席架构、CTO 都能够从中汲取足够的技术养料。

**普通开发** 往往积累单点技术、比如 CRUD、锁类型、索引的数据结构...而对于 **技术骨干、架构师** 则往往需要对底层原理吃透，数据库事务 ACID 是如何实现的？何时命中索引、何时不能，为什么？
分布式场景下数据库怎么优化才能保持高性能？

说白了，知道怎么用是一方面，知道为什么则是更为 **稀缺的能力** 。

很多技术专家在总结程序员核心能力的时候都会提到至关重要的一点： **精通数据库。精通意味着**：

- 第一形成知识网，更灵活地应对突发问题；
- 第二底层原理要懂，懂了才能更自由地应对复杂多变的业务场景。

## 四、本套课程适合人群

1 、MySQL数据库初学者。建议按照顺序从套课程的“基础篇”开始学习。

2 、从事后台开发(Java、Python、GO、PHP等)、MySQL开发 1~3 年的开发人员和运维人员。建议选择“基础篇”部分内容学习，或者跳过“基础篇”，直接从“高级特性篇”开始学习。

3 、有资历的MySQL DBA。本课程可以作为“案头书”。在解决问题时，如果记不清某些概念或者细节比较模糊，则可以拿来参考。

## 五、希望你能获取的

先说一个笑话。这个笑话是我从万维钢的专栏里看到的。

三个逻辑学家走进酒吧，酒保问他们，三位都喝啤酒吗？ 第一个逻辑学家说，我不知道。 第二个逻辑学家说，我不知道。 第三个逻辑学家说，是的。

对于知识，是需要**认真**和**讲究逻辑**的。希望这份认真、严谨你在课程的每个细节都能体会到。希望通过这套课程的系统性训练，你也能感受到这种思维方式的美，最终也能获得这种思维方式。

**具备优秀的思维能力**才是在未来可以迁移的能力，如果只是学习一些命令，则很快会过时，**思维能力**和**学习能力**的提升才是不会变的东西。






# 第 01 章_数据库概述

## 1. 为什么要使用数据库


- 持久化(persistence)： **把数据保存到可掉电式存储设备中以供之后使用** 。大多数情况下，特别是企业级应用， **数据持久化意味着将内存中的数据保存到硬盘上加以”固化”** ，而持久化的实现过程大多通过各种关系数据库来完成。
- 持久化的主要作用是 **将内存中的数据存储在关系型数据库中** ，当然也可以存储在磁盘文件、XML数据文件中。

![image-20220726093912035](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726093912035.png)

生活中的例子：

![image-20220726094346629](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726094346629.png)



## 2. 数据库与数据库管理系统

### 2. 1 数据库的相关概念

| DB：数据库（Database）                                       |
| ------------------------------------------------------------ |
| 即存储数据的“仓库”，其本质是一个文件系统。它保存了一系列有组织的数据。 |
| **DBMS：数据库管理系统（Database Management System）**       |
| 是一种操纵和管理数据库的大型软件，用于建立、使用和维护数据库，对数据库进行统一管理和控制。用户通过数据库管理系统访问数据库中表内的数据。 |
| **SQL：结构化查询语言（Structured Query Language）**         |
| 专门用来与数据库通信的语言。                                 |

### 2. 2 数据库与数据库管理系统的关系
数据库管理系统(DBMS)可以管理多个数据库，一般开发人员会针对每一个应用创建一个数据库。为保存应用中实体的数据，一般会在数据库创建多个表，以保存程序中实体用户的数据。

数据库管理系统、数据库和表的关系如图所示：

![image-20220726094328550](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726094328550.png)





### 2. 3 常见的数据库管理系统排名(DBMS)

目前互联网上常见的数据库管理软件有Oracle、MySQL、MS SQL Server、DB2、PostgreSQL、Access、Sybase、Informix这几种。以下是 2021 年 **DB-Engines Ranking** 对各数据库受欢迎程度进行调查后的统计结果：（查看数据库最新排名: **https://db-engines.com/en/ranking** ）

![image-20220726094501457](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726094501457.png)

![image-20220726094515597](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726094515597.png)

对应的走势图：（ **https://db-engines.com/en/ranking_trend**）

![image-20220726094536043](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726094536043.png)

### 2. 4 常见的数据库介绍
**Oracle**

1979 年，Oracle 2 诞生，它是第一个商用的 RDBMS（关系型数据库管理系统）。随着 Oracle 软件的名气越来越大，公司也改名叫 Oracle 公司。

2007 年，总计 85 亿美金收购BEA Systems。

2009 年，总计 74 亿美金收购SUN。此前的 2008 年，SUN以 10 亿美金收购MySQL。意味着Oracle 同时拥有了MySQL 的管理权，至此 Oracle 在数据库领域中成为绝对的领导者。

2013 年，甲骨文超越IBM，成为继Microsoft后全球第二大软件公司。

如今 Oracle 的年收入达到了 400 亿美金，足以证明商用（收费）数据库软件的价值。

**SQL Server**
SQL Server 是微软开发的大型商业数据库，诞生于 1989 年。C#、.net等语言常使用，与WinNT完全集成，也可以很好地与Microsoft BackOffice产品集成。

**DB2**
IBM公司的数据库产品,收费的。常应用在银行系统中。

**PostgreSQL**
PostgreSQL 的稳定性极强，最符合SQL标准，开放源码，具备商业级DBMS质量。PG对数据量大的文本以及SQL处理较快。

**SyBase**
已经淡出历史舞台。提供了一个非常专业数据建模的工具PowerDesigner。

**SQLite**
嵌入式的小型数据库，应用在手机端。 零配置，SQlite3不用安装，不用配置，不用启动，关闭或者配数据库实例。当系统崩溃后不用做任何恢复操作，再下次使用数据库的时候自动恢复。

**informix**
IBM公司出品，取自Information 和Unix的结合，它是第一个被移植到Linux上的商业数据库产品。仅运行于unix/linux平台，命令行操作。 性能较高，支持集群，适应于安全性要求极高的系统，尤其是银行，证券系统的应用。



## 3. MySQL介绍

![image-20220726102623233](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726102623233.png)

### 3. 1 概述

- MySQL是一个**开放源代码的关系型数据库管理系统**，由瑞典MySQL AB（创始人Michael Widenius）公司 1995 年开发，迅速成为开源数据库的 No.1。
- 2008 被**Sun**收购（ 10 亿美金）， 2009 年Sun被**Oracle**收购。**MariaDB**应运而生。（MySQL 的创造者担心 MySQL 有闭源的风险，因此创建了 MySQL 的分支项目 MariaDB）
- MySQL6.x 版本之后分为**社区版**和**商业版**。
- MySQL是一种关联数据库管理系统，将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。
- MySQL是开源的，所以你不需要支付额外的费用。
- MySQL是可以定制的，采用了**GPL（GNU General Public License）**协议，你可以修改源码来开发自己的MySQL系统。
- MySQL支持大型的数据库。可以处理拥有上千万条记录的大型数据库。
- MySQL支持大型数据库，支持 5000 万条记录的数据仓库， 32 位系统表文件最大可支持**4GB**， 64 位系统支持最大的表文件为**8TB**。
- MySQL使用**标准的SQL数据语言**形式。
- MySQL可以允许运行于多个系统上，并且支持多种语言。这些编程语言包括C、C++、Python、Java、Perl、PHP和Ruby等。



### 3. 2 MySQL发展史重大事件
MySQL的历史就是整个互联网的发展史。互联网业务从社交领域、电商领域到金融领域的发展，推动着应用对数据库的需求提升，对传统的数据库服务能力提出了挑战。高并发、高性能、高可用、轻资源、易维护、易扩展的需求，促进了MySQL的长足发展。

![image-20220726102712158](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726102712158.png)



### 1. 4 关于MySQL 8. 0

**MySQL从5.7版本直接跳跃发布了8.0版本**，可见这是一个令人兴奋的里程碑版本。MySQL 8版本在功能上做了显著的改进与增强，开发者对MySQL的源代码进行了重构，最突出的一点是多MySQL  Optimizer优化器进行了改进。不仅在速度上得到了改善，还为用户带来了更好的性能和更棒的体验。



### 1.5 Why choose MySQL?

![image-20220726095216632](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726095216632.png)

为什么如此多的厂商要选用MySQL？大概总结的原因主要有以下几点：

1. 开放源代码，使用成本低。
2. 性能卓越，服务稳定。
3. 软件体积小，使用简单，并且易于维护。
4. 历史悠久，社区用户非常活跃，遇到问题可以寻求帮助。
5. 许多互联网公司在用，经过了时间的验证。



### 1.6 Oracle vs MySQL

Oracle 更适合大型跨国企业的使用，因为他们对费用不敏感，但是对性能要求以及安全性有更高的要求。

MySQL 由于其 **体积小、速度快、总体拥有成本低，可处理上千万条记录的大型数据库，尤其是开放源码这一特点，使得很多互联网公司、中小型网站选择了MySQL作为网站数据库** （Facebook，Twitter，YouTube，阿里巴巴/蚂蚁金服，去哪儿，美团外卖，腾讯）。



## 4. RDBMS 与 非RDBMS

从排名中我们能看出来，关系型数据库绝对是 DBMS 的主流，其中使用最多的 DBMS 分别是 Oracle、MySQL 和 SQL Server。这些都是关系型数据库（RDBMS）。

### 4.1 关系型数据库(RDBMS)
#### 4. 1. 1 实质
- 这种类型的数据库是**最古老**的数据库类型，关系型数据库模型是把复杂的数据结构归结为简单的**二元关系**（即二维表格形式）。

![image-20220726095255154](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726095255154.png)



- 关系型数据库以**行(row)**和**列(column)**的形式存储数据，以便于用户理解。这一系列的行和列被称为**表(table)**，一组表组成了一个库(database)。
- 表与表之间的数据记录有关系(relationship)。现实世界中的各种实体以及实体之间的各种联系均用**关系模型**来表示。关系型数据库，就是建立在**关系模型**基础上的数据库。
- SQL 就是关系型数据库的查询语言。

![image-20220726095317374](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726095317374.png)


#### 4. 1. 2 优势
- **复杂查询** 

  可以用SQL语句方便的在一个表以及多个表之间做非常复杂的数据查询。

- **事务支持** 

  使得对于安全性能很高的数据访问要求得以实现。



### 4. 2 非关系型数据库(非RDBMS)
#### 4. 2. 1 介绍
**非关系型数据库** ，可看成传统关系型数据库的功能**阉割版本**，基于键值对存储数据，不需要经过SQL层的解析，**性能非常高**。同时，通过减少不常用的功能，进一步提高性能。

目前基本上大部分主流的非关系型数据库都是免费的。

#### 4. 2. 2 有哪些非关系型数据库

相比于 SQL，NoSQL 泛指非关系型数据库，包括了榜单上的键值型数据库、文档型数据库、搜索引擎和列存储等，除此以外还包括图形数据库。也只有用 NoSQL 一词才能将这些技术囊括进来。

**键值型数据库**

键值型数据库通过 Key-Value 键值的方式来存储数据，其中 Key 和 Value 可以是简单的对象，也可以是复杂的对象。Key 作为唯一的标识符，优点是查找速度快，在这方面明显优于关系型数据库，缺点是无法像关系型数据库一样使用条件过滤（比如 WHERE），如果你不知道去哪里找数据，就要遍历所有的键，这就会消耗大量的计算。

键值型数据库典型的使用场景是作为**内存缓存**。**Redis**是最流行的键值型数据库。

![image-20220726095702944](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726095702944.png)

**文档型数据库**

此类数据库可存放并获取文档，可以是XML、JSON等格式。在数据库中文档作为处理信息的基本单位，一个文档就相当于一条记录。文档数据库所存放的文档，就相当于键值数据库所存放的“值”。MongoDB是最流行的文档型数据库。此外，还有CouchDB等。

**搜索引擎数据库**

虽然关系型数据库采用了索引提升检索效率，但是针对全文索引效率却较低。搜索引擎数据库是应用在搜索引擎领域的数据存储形式，由于搜索引擎会爬取大量的数据，并以特定的格式进行存储，这样在检索的时候才能保证性能最优。核心原理是“倒排索引”。

典型产品：Solr、Elasticsearch、Splunk 等。

**列式数据库**

列式数据库是相对于行式存储的数据库，Oracle、MySQL、SQL Server 等数据库都是采用的行式存储（Row-based），而列式数据库是将数据按照列存储到数据库中，这样做的好处是可以大量降低系统的I/O，适合于分布式文件系统，不足在于功能相对有限。典型产品：HBase等。

![image-20220726095849770](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726095849770.png)

**图形数据库**

图形数据库，利用了图这种数据结构存储了实体（对象）之间的关系。图形数据库最典型的例子就是社交网络中人与人的关系，数据模型主要是以节点和边（关系）来实现，特点在于能高效地解决复杂的关系问题。

图形数据库顾名思义，就是一种存储图形关系的数据库。它利用了图这种数据结构存储了实体（对象）之间的关系。关系型数据用于存储明确关系的数据，但对于复杂关系的数据存储却有些力不从心。如社交网络中人物之间的关系，如果用关系型数据库则非常复杂，用图形数据库将非常简单。典型产品：Neo4J、InfoGrid等。

![image-20220726095950715](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726095950715.png)


#### 4. 2. 3 NoSQL的演变
由于 SQL 一直称霸 DBMS，因此许多人在思考是否有一种数据库技术能远离 SQL，于是 NoSQL 诞生了，但是随着发展却发现越来越离不开 SQL。到目前为止 NoSQL 阵营中的 DBMS 都会有实现类似 SQL 的功能。下面是“NoSQL”这个名词在不同时期的诠释，从这些释义的变化中可以看出 **NoSQL 功能的演变**：

1970 ：NoSQL = We have no SQL

1980 ：NoSQL = Know SQL

2000 ：NoSQL = No SQL!

2005 ：NoSQL = Not only SQL

2013 ：NoSQL = No, SQL!

NoSQL 对 SQL 做出了很好的补充，比如实际开发中，有很多业务需求，其实并不需要完整的关系型数据库功能，非关系型数据库的功能就足够使用了。这种情况下，使用**性能更高、成本更低**的非关系型数据库当然是更明智的选择。比如：日志收集、排行榜、定时器等。

### 4. 3 小结
NoSQL 的分类很多，即便如此，在 DBMS 排名中，还是 SQL 阵营的比重更大，影响力前 5 的 DBMS 中有4 个是关系型数据库，而排名前 20 的 DBMS 中也有 12 个是关系型数据库。所以说，掌握 SQL 是非常有必要的。整套课程将围绕 SQL 展开。

## 5. 关系型数据库设计规则


- 关系型数据库的典型数据结构就是**数据表**，这些数据表的组成都是结构化的（Structured）。
- 将数据放到表中，表再放到库中。
- 一个数据库中可以有多个表，每个表都有一个名字，用来标识自己。表名具有唯一性。
- 表具有一些特性，这些特性定义了数据在表中如何存储，类似Java和Python中 “类”的设计。


### 5. 1 表、记录、字段

- E-R（entity-relationship，实体-联系）模型中有三个主要概念是：**实体集、属性、联系集**。
- 一个实体集（class）对应于数据库中的一个表（table），一个实体（instance）则对应于数据库表中的一行（row），也称为一条记录（record）。一个属性（attribute）对应于数据库表中的一列（column），也称为一个字段（field）。

![image-20220726100223471](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726100223471.png)
```java
ORM思想 (Object Relational Mapping)体现：
数据库中的一个表 <---> Java或Python中的一个类
表中的一条数据 <---> 类中的一个对象（或实体）
表中的一个列 <----> 类中的一个字段、属性(fild)
```

### 5.2表的关联关系

- 表与表之间的数据记录有关系(relationship)。现实世界中的各种实体以及实体之间的各种联系均用关系模型来表示。
- 四种：一对一关联、一对多关联、多对多关联、自我引用


#### 5.2.1 一对一关联（one-to-one）
- 在实际的开发中应用不多，因为一对一可以创建成一张表。

- 举例：设计**学生表**：学号、姓名、手机号码、班级、系别、身份证号码、家庭住址、籍贯、紧急 联系人、...
  - 拆为两个表：两个表的记录是一一对应关系。
  - **基础信息表**（常用信息）：学号、姓名、手机号码、班级、系别
  - **档案信息表**（不常用信息）：学号、身份证号码、家庭住址、籍贯、紧急联系人、..
  
- 两种建表原则：

  - 外键唯一：主表的主键和从表的外键（唯一），形成主外键关系，外键唯一。

  - 外键是主键：主表的主键和从表的主键，形成主外键关系。

![image-20220726100435230](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726100435230.png)



#### 5.2.2 一对多关系（one-to-many）
- 常见实例场景：**客户表和订单表，分类表和商品表，部门表和员工表**。

- 举例：

  - 员工表：编号、姓名、...、所属部门

  - 部门表：编号、名称、简介

- 一对多建表原则：在从表(多方)创建一个字段，字段作为外键指向主表(一方)的主键

![image-20220726101022499](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726101022499.png)

![image-20220726101050705](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726101050705.png)


#### 5. 2. 3 多对多（many-to-many）
 要表示多对多关系，必须创建第三个表，该表通常称为**联接表**，它将多对多关系划分为两个一对多关系。将这两个表的主键都插入到第三个表中。

![image-20220726101115961](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726101115961.png)

- **举例 1 ：学生-课程**

   - **学生信息表**：一行代表一个学生的信息（学号、姓名、手机号码、班级、系别...）

   - **课程信息表**：一行代表一个课程的信息（课程编号、授课老师、简介...）

   - **选课信息表**：一个学生可以选多门课，一门课可以被多个学生选择

```
学号 课程编号
1    1001
2    1001
1    1002
```



- **举例 2 ：产品-订单**
   “订单”表和“产品”表有一种多对多的关系，这种关系是通过与“订单明细”表建立两个一对多关系来定义的。一个订单可以有多个产品，每个产品可以出现在多个订单中。
   - **产品表**：“产品”表中的每条记录表示一个产品。
   - **订单表**：“订单”表中的每条记录表示一个订单。
   - **订单明细表**：每个产品可以与“订单”表中的多条记录对应，即出现在多个订单中。一个订单可以与“产品”表中的多条记录对应，即包含多个产品。

![image-20220726101253257](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726101253257.png)

- **举例 3 ：用户-角色**
- 多对多关系建表原则：需要创建第三张表，中间表中至少两个字段，这两个字段分别作为外键指向各自一方的主键。

![image-20220726101316038](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726101316038.png)

#### 5.2.4 自我引用(Self reference)

![image-20220726101336782](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726101336782.png)





------

# 第 02 章_MySQL环境搭建
## 1. MySQL的卸载
### 步骤 1 ：停止MySQL服务

在卸载之前，先停止MySQL8.0的服务。按键盘上的“Ctrl + Alt + Delete”组合键，打开“任务管理器”对话框，可以在“服务”列表找到“MySQL8.0”的服务，如果现在“正在运行”状态，可以右键单击服务，选择“停止”选项停止MySQL8.0的服务，如图所示。

![image-20220921141605050](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141605050.png)



### 步骤 2 ：软件的卸载
**方式 1 ：通过控制面板方式**

卸载MySQL8.0的程序可以和其他桌面应用程序一样直接在“控制面板”选择“卸载程序”，并在程序列表中找到MySQL8.0服务器程序，直接双击卸载即可，如图所示。这种方式删除，数据目录下的数据不会跟着删除。

![image-20220921141631153](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141631153.png)



**方式 2 ：通过 360 或电脑管家等软件卸载**

略

**方式 3 ：通过安装包提供的卸载功能卸载**

你也可以通过安装向导程序进行MySQL8.0服务器程序的卸载。

① 再次双击下载的mysql-installer-community-8.0.26.0.msi文件，打开安装向导。安装向导会自动检测已安装的MySQL服务器程序。

② 选择要卸载的MySQL服务器程序，单击“Remove”（移除），即可进行卸载。

![image-20220921141656145](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141656145.png)

③ 单击“Next”（下一步）按钮，确认卸载。

![image-20220921141722824](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141722824.png)

④ 弹出是否同时移除数据目录选择窗口。如果想要同时删除MySQL服务器中的数据，则勾选“Remove thedata directory”，如图所示。

![image-20220921141746332](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141746332.png)

⑤ 执行卸载。单击“Execute”（执行）按钮进行卸载。

![image-20220921141802464](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141802464.png)

⑥ 完成卸载。单击“Finish”（完成）按钮即可。如果想要同时卸载MySQL8.0的安装向导程序，勾选“Yes，Uninstall MySQL Installer”即可，如图所示。

![image-20220921141817257](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921141817257.png)



### 步骤 3 ：残余文件的清理

如果再次安装不成功，可以卸载后对残余文件进行清理后再安装。

（ 1 ）服务目录：mysql服务的安装目录
（ 2 ）数据目录：默认在C:\ProgramData\MySQL
如果自己单独指定过数据目录，就找到自己的数据目录进行删除即可。

注意：

- 请在卸载前做好数据备份
- 在操作完以后，需要重启计算机，然后进行安装即可。 **如果仍然安装失败，需要继续操作如下步骤 4** 。



### 步骤 4 ：清理注册表（选做）

如果前几步做了，再次安装还是失败，那么可以清理注册表。

如何打开注册表编辑器：在系统的搜索框中输入`regedit`

```
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Eventlog\Application\MySQL服务 目录删除
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\MySQL服务 目录删除
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\Eventlog\Application\MySQL服务 目录删除
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\MySQL服务 目录删除
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Eventlog\Application\MySQL服务目录删除
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MySQL服务删除
```

- 注册表中的ControlSet001,ControlSet002,不一定是001和002,可能是ControlSet005、006之类



### 步骤 5 ：删除环境变量配置

找到path环境变量，将其中关于mysql的环境变量删除， **切记不要全部删除。**
例如：删除 D:\develop_tools\mysql\MySQLServer8.0.26\bin; 这个部分

![image-20220921142249274](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921142249274.png)



## 2. MySQL的下载、安装、配置

### 2. 1 MySQL的 4 大版本

```
MySQL Community Server 社区版本 ，开源免费，自由下载，但不提供官方技术支持，适用于大多数普通用户。
MySQL Enterprise Edition 企业版本 ，需付费，不能在线下载，可以试用 30 天。提供了更多的功能和更完备的技术支持，更适合于对数据库的功能和可靠性要求较高的企业客户。
MySQL Cluster 集群版 ，开源免费。用于架设集群服务器，可将几个MySQL Server封装成一个Server。需要在社区版或企业版的基础上使用。
MySQL Cluster CGE 高级集群版 ，需付费。
```

- 目前最新版本为` 8.0.27`，发布时间 `2021 年 10 月`。此前，8.0.0 在 2016.9.12日就发布了。

- 本课程中使用`8.0.26`版本。

此外，官方还提供了`MySQL Workbench`（GUITOOL）一款专为MySQL设计的`图形界面管理工具`。
MySQLWorkbench又分为两个版本，分别是`社区版`（MySQL Workbench OSS）、`商用版`（MySQL  WorkbenchSE）。



### 2. 2 软件的下载

**1.下载地址**

官网： **https://www.mysql.com**

**2. 打开官网，点击DOWNLOADS**

然后，点击`MySQL Community(GPL) Downloads`

![image-20220921142740271](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921142740271.png)

**3. 点击 MySQL Community Server**

![image-20220921142825278](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921142825278.png)

**4. 在General Availability(GA) Releases中选择适合的版本**

Windows平台下提供两种安装文件：MySQL二进制分发版（.msi安装文件）和免安装版（.zip压缩文件）。一般来讲，应当使用二进制分发版，因为该版本提供了图形化的安装向导过程，比其他的分发版使用起来要简单，不再需要其他工具启动就可以运行MySQL。

- 这里在Windows 系统下推荐下载MSI安装程序；点击Go to Download Page进行下载即可

![image-20220921142911928](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921142911928.png)

![image-20220921142925308](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921142925308.png)

- Windows下的MySQL 8. 0 安装有两种安装程序
  - `mysql-installer-web-community-8.0.26.0.msi` 下载程序大小： 2. 4 M；安装时需要联网安装组件。
  - `mysql-installer-community-8.0.26.0.msi` 下载程序大小： 450. 7 M；安装时离线安装即可。 **推荐。**
- 如果安装MySQL 5. 7 版本的话，选择`Archives`，接着选择MySQL 5. 7 的相应版本即可。这里下载最近期的MySQL 5. 7. 34 版本。

![image-20220921143044018](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143044018.png)

![image-20220921143059341](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143059341.png)



### 2. 3 MySQL 8. 0 版本的安装

MySQL下载完成后，找到下载文件，双击进行安装，具体操作步骤如下。

步骤 1 ：双击下载的mysql-installer-community-8.0.26.0.msi文件，打开安装向导。

步骤 2 ：打开“Choosing a Setup Type”（选择安装类型）窗口，在其中列出了 5 种安装类型，分别是Developer Default（默认安装类型）、Server only（仅作为服务器）、Client only（仅作为客户端）、Full（完全安装）、Custom（自定义安装）。这里选择“Custom（自定义安装）”类型按钮，单击“Next(下一步)”按钮。

![image-20220921143155203](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143155203.png)

步骤 3 ：打开“Select Products” （选择产品）窗口，可以定制需要安装的产品清单。例如，选择“MySQL Server 8.0.26-X64”后，单击“→”添加按钮，即可选择安装MySQL服务器，如图所示。采用通用的方法，可以添加其他你需要安装的产品。

![image-20220921143214777](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143214777.png)

此时如果直接“Next”（下一步），则产品的安装路径是默认的。如果想要自定义安装目录，则可以选中对应的产品，然后在下面会出现“Advanced Options”（高级选项）的超链接。

![image-20220921143229911](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143229911.png)

单击“Advanced Options”（高级选项）则会弹出安装目录的选择窗口，如图所示，此时你可以分别设置MySQL的服务程序安装目录和数据存储目录。如果不设置，默认分别在C盘的Program Files目录和ProgramData目录（这是一个隐藏目录）。如果自定义安装目录，请避免“中文”目录。另外，建议服务目录和数据目录分开存放。

![image-20220921143246115](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143246115.png)

步骤 4 ：在上一步选择好要安装的产品之后，单击“Next”（下一步）进入确认窗口，如图所示。单击“Execute”（执行）按钮开始安装。

![image-20220921143258202](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143258202.png)

步骤 5 ：安装完成后在“Status”（状态）列表下将显示“Complete”（安装完成），如图所示。

![image-20220921143317370](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143317370.png)



### 2. 4 配置MySQL 8. 0

MySQL安装之后，需要对服务器进行配置。具体的配置步骤如下。

步骤 1 ：在上一个小节的最后一步，单击“Next”（下一步）按钮，就可以进入产品配置窗口。

![image-20220921143342524](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143342524.png)

步骤 2 ：单击“Next”（下一步）按钮，进入MySQL服务器类型配置窗口，如图所示。端口号一般选择默认端口号 3306 。

![image-20220921143401067](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143401067.png)

其中，“Config Type”选项用于设置服务器的类型。单击该选项右侧的下三角按钮，即可查看 3 个选项，如图所示。

![image-20220921143415162](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143415162.png)

- `Development Machine（开发机器）`：该选项代表典型个人用桌面工作站。此时机器上需要运行多个应用程序，那么MySQL服务器将占用最少的系统资源。
- `Server Machine（服务器）`：该选项代表服务器，MySQL服务器可以同其他服务器应用程序一起运行，例如Web服务器等。MySQL服务器配置成适当比例的系统资源。
- `Dedicated Machine（专用服务器）`：该选项代表只运行MySQL服务的服务器。MySQL服务器配置成使用所有可用系统资源。

步骤 3 ：单击“Next”（下一步）按钮，打开设置授权方式窗口。其中，上面的选项是MySQL8.0提供的新的授权方式，采用SHA256基础的密码加密方法；下面的选项是传统授权方法（保留5.x版本兼容性）。

![image-20220921143543992](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143543992.png)

步骤 4 ：单击“Next”（下一步）按钮，打开设置服务器root超级管理员的密码窗口，如图所示，需要输入两次同样的登录密码。也可以通过“Add User”添加其他用户，添加其他用户时，需要指定用户名、允许该用户名在哪台/哪些主机上登录，还可以指定用户角色等。此处暂不添加用户，用户管理在MySQL高级特性篇中讲解。

![image-20220921143607894](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143607894.png)

步骤 5 ：单击“Next”（下一步）按钮，打开设置服务器名称窗口，如图所示。该服务名会出现在Windows服务列表中，也可以在命令行窗口中使用该服务名进行启动和停止服务。本书将服务名设置为“MySQL80”。如果希望开机自启动服务，也可以勾选“Start the MySQL Server at System Startup”选项（推荐）。

下面是选择以什么方式运行服务？可以选择“Standard System Account”(标准系统用户)或者“Custom User”(自定义用户)中的一个。这里推荐前者。

![image-20220921143625819](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143625819.png)

步骤 6 ：单击“Next”（下一步）按钮，打开确认设置服务器窗口，单击“Execute”（执行）按钮。

![image-20220921143638770](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143638770.png)

步骤 7 ：完成配置，如图所示。单击“Finish”（完成）按钮，即可完成服务器的配置。

![image-20220921143650482](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143650482.png)

步骤 8 ：如果还有其他产品需要配置，可以选择其他产品，然后继续配置。如果没有，直接选择“Next”（下一步），直接完成整个安装和配置过程。

![image-20220921143710728](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143710728.png)

步骤 9 ：结束安装和配置。

![image-20220921143721372](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143721372.png)



### 2. 5 配置MySQL 8. 0 环境变量

如果不配置MySQL环境变量，就不能在命令行直接输入MySQL登录命令。下面说如何配置MySQL的环境变量：
步骤 1 ：在桌面上右击【此电脑】图标，在弹出的快捷菜单中选择【属性】菜单命令。 
步骤 2 ：打开【系统】窗口，单击【高级系统设置】链接。 
步骤 3 ：打开【系统属性】对话框，选择【高级】选项卡，然后单击【环境变量】按钮。 
步骤 4 ：打开【环境变量】对话框，在系统变量列表中选择path变量。 
步骤5 ：单击【编辑】按钮，在【编辑环境变量】对话框中，将MySQL应用程序的bin目录（C:\Program Files\MySQL\MySQL Server 8.0\bin）添加到变量值中，用分号将其与其他路径分隔开。 
步骤 6 ：添加完成之后，单击【确定】按钮，这样就完成了配置path变量的操作，然后就可以直接输入MySQL命令来登录数据库了。



### 2. 6 MySQL 5. 7 版本的安装、配置

- **安装**

此版本的安装过程与上述过程除了版本号不同之外，其它环节都是相同的。所以这里省略了MySQL5.7.34版本的安装截图。

- **配置**

配置环节与MySQL8.0版本确有细微不同。大部分情况下直接选择“Next”即可，不影响整理使用。
这里配置MySQL5.7时，重点强调： **与前面安装好的MySQL 8. 0 不能使用相同的端口号。**



### 2. 7 安装失败问题

MySQL的安装和配置是一件非常简单的事，但是在操作过程中也可能出现问题，特别是初学者。

**问题 1 ：无法打开MySQL 8. 0 软件安装包或者安装过程中失败，如何解决？**

在运行MySQL8.0软件安装包之前，用户需要确保系统中已经安装了.Net Framework相关软件，如果缺少此软件，将不能正常地安装MySQL8.0软件。

![image-20220921143918162](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921143918162.png)

解决方案：到这个地址 **https://www.microsoft.com/en-us/download/details.aspx?id=42642** 下载Microsoft.NET Framework 4.5并安装后，再去安装MySQL。

另外，还要确保Windows Installer正常安装。windows上安装mysql8.0需要操作系统提前已安装好Microsoft Visual C++ 2015-2019。

![image-20220921144056522](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921144056522.png)

![image-20220921144107404](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921144107404.png)

解决方案同样是，提前到微软官网 **https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0** ，下载相应的环境。

**问题 2 ：卸载重装MySQL失败？**

该问题通常是因为MySQL卸载时，没有完全清除相关信息导致的。

解决办法是，把以前的安装目录删除。如果之前安装并未单独指定过服务安装目录，则默认安装目录是“C:\Program Files\MySQL”，彻底删除该目录。同时删除MySQL的Data目录，如果之前安装并未单独指定过数据目录，则默认安装目录是“C:\ProgramData\MySQL”，该目录一般为隐藏目录。删除后，重新安装即可。

**问题 3 ：如何在Windows系统删除之前的未卸载干净的MySQL服务列表？**

操作方法如下，在系统“搜索框”中输入“cmd”，按“Enter”（回车）键确认，弹出命令提示符界面。然后输入“sc delete MySQL服务名”,按“Enter”（回车）键，就能彻底删除残余的MySQL服务了。



## 3. MySQL的登录

### 3. 1 服务的启动与停止
MySQL安装完毕之后，需要启动服务器进程，不然客户端无法连接数据库。
在前面的配置过程中，已经将MySQL安装为Windows服务，并且勾选当Windows启动、停止时，MySQL也自动启动、停止。

#### 方式 1 ：使用图形界面工具

- 步骤 1 ：打开windows服务
  - 方式 1 ：计算机（点击鼠标右键）→ 管理（点击）→ 服务和应用程序（点击）→ 服务（点击）
  - 方式 2 ：控制面板（点击）→ 系统和安全（点击）→ 管理工具（点击）→ 服务（点击）
  - 方式 3 ：任务栏（点击鼠标右键）→ 启动任务管理器（点击）→ 服务（点击）
  - 方式 4 ：单击【开始】菜单，在搜索框中输入“services.msc”，按Enter键确认
- 步骤 2 ：找到MySQL80（点击鼠标右键）→ 启动或停止（点击）

![image-20220921144328115](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921144328115.png)

#### 方式 2 ：使用命令行工具

```
# 启动 MySQL 服务命令：
net start MySQL服务名
# 停止 MySQL 服务命令：
net stop MySQL服务名
```

![image-20220921144430044](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921144430044.png)

说明：

1. start和stop后面的服务名应与之前配置时指定的服务名一致。
2. 如果当你输入命令后，提示“拒绝服务”，请以系统管理员身份打开命令提示符界面重新尝试。



### 3. 2 自带客户端的登录与退出

当MySQL服务启动完成后，便可以通过客户端来登录MySQL数据库。注意：确认服务是开启的。

#### 登录方式 1 ：MySQL自带客户端

开始菜单 → 所有程序 → MySQL → MySQL 8.0 Command Line Client

![image-20220921144529869](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921144529869.png)

说明：仅限root用户

#### 登录方式 2 ：windows命令行
- 格式：

```
mysql -h 主机名 -P 端口号 -u 用户名 -p密码
```

- 举例：

```
mysql -h localhost -P 3306 -u root -pabc123 # 这里我设置的root用户的密码是abc123
```

![image-20220921144650655](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921144650655.png)

注意：

（ 1 ）-p与密码之间不能有空格，其他参数名与参数值之间可以有空格也可以没有空格。如：

```
mysql -hlocalhost -P3306 -uroot -pabc123
```

（ 2 ）密码建议在下一行输入，保证安全

```
mysql -h localhost -P 3306 -u root -p
Enter password:****
```

（ 3 ）客户端和服务器在同一台机器上，所以输入localhost或者IP地址127.0.0.1。同时，因为是连接本机： -hlocalhost就可以省略，如果端口号没有修改：-P3306也可以省略
简写成：

```
mysql -u root -p
Enter password:****
```

连接成功后，有关于MySQL Server服务版本的信息，还有第几次连接的id标识。
也可以在命令行通过以下方式获取MySQL Server服务版本的信息：

```
c:\> mysql -V
```

```
c:\> mysql --version
```

或 **登录** 后，通过以下方式查看当前版本信息：

```
mysql> select version();
```

#### 退出登录

```
exit
或
quit
```



## 4. MySQL演示使用
### 4. 1 MySQL的使用演示
1 、查看所有的数据库

```sql
show databases;
```

```
“information_schema”是 MySQL 系统自带的数据库，主要保存 MySQL 数据库服务器的系统信息，比如数据库的名称、数据表的名称、字段名称、存取权限、数据文件 所在的文件夹和系统使用的文件夹，等等
“performance_schema”是 MySQL 系统自带的数据库，可以用来监控 MySQL 的各类性能指标。
“sys”数据库是 MySQL 系统自带的数据库，主要作用是以一种更容易被理解的方式展示 MySQL 数据库服务器的各类性能指标，帮助系统管理员和开发人员监控 MySQL 的技术性能。
“mysql”数据库保存了 MySQL 数据库服务器运行时需要的系统信息，比如数据文件夹、当前使用的字符集、约束检查信息，等等
```

为什么 Workbench 里面我们只能看到“demo”和“sys”这 2 个数据库呢？

这是因为，Workbench 是图形化的管理工具，主要面向开发人 员，“demo”和“sys”这 2 个数据库已经够用了。如果有特殊需求，比如，需要监控 MySQL 数据库各项性能指标、直接操作 MySQL 数据库系统文件等，可以由 DBA 通过 SQL 语句，查看其它的系统数据库。

2 、创建自己的数据库

```sql
create database 数据库名;
#创建atguigudb数据库，该名称不能与已经存在的数据库重名。
create database atguigudb;
```

3 、使用自己的数据库

```sql
use 数据库名;
#使用atguigudb数据库
use atguigudb;
```

说明：如果没有使用use语句，后面针对数据库的操作也没有加“数据名”的限定，那么会报“ERROR 1046(3D000): No database selected”（没有选择数据库）

使用完use语句之后，如果接下来的SQL都是针对一个数据库操作的，那就不用重复use了，如果要针对另一个数据库操作，那么要重新use。

4 、查看某个库的所有表格

```sql
show tables;  #要求前面有use语句
show tables from 数据库名;
```

5 、创建新的表格

```sql
create table 表名称(
    字段名 数据类型,
    字段名 数据类型
);
```

说明：如果是最后一个字段，后面就用加逗号，因为逗号的作用是分割每个字段。

```sql
#创建学生表
create table student(
    id int,
    name varchar(20) #说名字最长不超过20个字符
);
```

6 、查看一个表的数据

```sql
select * from 数据库表名称;
```

```sql
#查看学生表的数据
select * from student;
```

7 、添加一条记录

```sql
insert into 表名称 values(值列表);
#添加两条记录到student表中
insert into student values(1,'张三');
insert into student values(2,'李四');
```

报错：

```sql
mysql> insert into student values(1,'张三');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'name' at
row 1
mysql> insert into student values(2,'李四');
ERROR 1366 (HY000): Incorrect string value: '\xC0\xEE\xCB\xC4' for column 'name' at
row 1
mysql> show create table student;
```

字符集的问题。

8 、查看表的创建信息

```sql
show create table 表名称\G
#查看student表的详细创建信息
show create table student\G
```

```sql
#结果如下
*************************** 1. row ***************************
Table: student
Create Table: CREATE TABLE `student` (
`id` int(11) DEFAULT NULL,
`name` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1
1 row in set (0.00 sec)
```

上面的结果显示student的表格的默认字符集是“latin1”不支持中文。

9 、查看数据库的创建信息

```sql
show create database 数据库名\G
#查看atguigudb数据库的详细创建信息
show create database atguigudb\G
```

```sql
#结果如下
*************************** 1. row ***************************
Database: atguigudb
Create Database: CREATE DATABASE `atguigudb` /*!40100 DEFAULT CHARACTER SET latin1 */
1 row in set (0.00 sec)
```

上面的结果显示atguigudb数据库也不支持中文，字符集默认是latin1。

10 、删除表格

```sql
drop table 表名称;
```

```sql
#删除学生表
drop table student;
```

11 、删除数据库

```sql
drop database 数据库名;
```

```sql
#删除atguigudb数据库
drop database atguigudb;
```



### 4. 2 MySQL的编码设置

#### MySQL 5. 7 中

**问题再现：命令行操作sql乱码问题**

```sql
mysql> INSERT INTO t_stu VALUES(1,'张三','男');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'sname' at
row 1
```

**问题解决**

步骤 1 ：查看编码命令

```
show variables like 'character_%';
show variables like 'collation_%';
```

步骤 2 ：修改mysql的数据目录下的my.ini配置文件

```sql
[mysql] #大概在63行左右，在其下添加
...
default-character-set=utf8 #默认字符集
[mysqld] # 大概在76行左右，在其下添加
...
character-set-server=utf8
collation-server=utf8_general_ci
```

```
注意：建议修改配置文件使用notepad++等高级文本编辑器，使用记事本等软件打开修改后可能会
导致文件编码修改为“含BOM头”的编码，从而服务重启失败。
```

步骤 3 ：重启服务

步骤 4 ：查看编码命令

```sql
show variables like 'character_%';
show variables like 'collation_%';
```

![image-20220921150012517](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150012517.png)

![image-20220921150022637](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150022637.png)

- 如果是以上配置就说明对了。接着我们就可以新创建数据库、新创建数据表，接着添加包含中文的数据了。

#### MySQL 8. 0 中

在MySQL 8.0版本之前，默认字符集为latin1，utf8字符集指向的是utf8mb3。网站开发人员在数据库设计的时候往往会将编码修改为utf8字符集。如果遗忘修改默认的编码，就会出现乱码的问题。从MySQL 8.0开始，数据库的默认编码改为`utf8mb4`，从而避免了上述的乱码问题。



## 5. MySQL图形化管理工具

MySQL图形化管理工具极大地方便了数据库的操作与管理，常用的图形化管理工具有：MySQL Workbench、phpMyAdmin、Navicat Preminum、MySQLDumper、SQLyog、dbeaver、MySQL ODBC  Connector。

### 工具1. MySQL Workbench

MySQL官方提供的图形化管理工具MySQL Workbench完全支持MySQL 5.0以上的版本。MySQL Workbench分为社区版和商业版，社区版完全免费，而商业版则是按年收费。

MySQL Workbench 为数据库管理员、程序开发者和系统规划师提供可视化设计、模型建立、以及数据库管理功能。它包含了用于创建复杂的数据建模ER模型，正向和逆向数据库工程，也可以用于执行通常需要花费大量时间的、难以变更和管理的文档任务。

下载地址： **http://dev.mysql.com/downloads/workbench/** 

使用：

首先，我们点击 Windows 左下角的“开始”按钮，如果你是 Win10 系统，可以直接看到所有程序。接着，找到“MySQL”，点开，找到“MySQL Workbench 8.0 CE”。点击打开 Workbench，如下图所示：

![image-20220921150204752](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150204752.png)

左下角有个本地连接，点击，录入 Root 的密码，登录本地MySQL 数据库服务器，如下图所示：

![image-20220921150218223](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150218223.png)

![image-20220921150346258](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150346258.png)

这是一个图形化的界面，我来给你介绍下这个界面。

- 上方是菜单。左上方是导航栏，这里我们可以看到 MySQL 数据库服务器里面的数据 库，包括数据表、视图、存储过程和函数；左下方是信息栏，可以显示上方选中的数据 库、数据表等对象的信息。
- 中间上方是工作区，你可以在这里写 SQL 语句，点击上方菜单栏左边的第三个运行按 钮，就可以执行工作区的 SQL 语句了。
- 中间下方是输出区，用来显示 SQL 语句的运行情况，包括什么时间开始运行的、运行的 内容、运行的输出，以及所花费的时长等信息。

好了，下面我们就用 Workbench 实际创建一个数据库，并且导入一个 Excel 数据文件， 来生成一个数据表。数据表是存储数据的载体，有了数据表以后，我们就能对数据进行操作了。

### 工具2. Navicat

Navicat MySQL是一个强大的MySQL数据库服务器管理和开发工具。它可以与任何3.21或以上版本的MySQL一起工作，支持触发器、存储过程、函数、事件、视图、管理用户等，对于新手来说易学易用。其精心设计的图形用户界面（GUI）可以让用户用一种安全简便的方式来快速方便地创建、组织、访问和共享信息。Navicat支持中文，有免费版本提供。 下载地址： **http://www.navicat.com/** 。

![image-20220921150518636](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150518636.png)

### 工具3. SQLyog

SQLyog 是业界著名的 Webyog 公司出品的一款简洁高效、功能强大的图形化 MySQL 数据库管理工具。
这款工具是使用C++语言开发的。该工具可以方便地创建数据库、表、视图和索引等，还可以方便地进行插入、更新和删除等操作，同时可以方便地进行数据库、数据表的备份和还原。该工具不仅可以通过SQL文件进行大量文件的导入和导出，还可以导入和导出XML、HTML和CSV等多种格式的数据。

下载地址： **http://www.webyog.com/** ，读者也可以搜索中文版的下载地址。

![image-20220921150605161](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150605161.png)

### 工具 4 ：dbeaver

DBeaver是一个通用的数据库管理工具和 SQL 客户端，支持所有流行的数据库：MySQL、PostgreSQL、SQLite、Oracle、DB2、SQL Server、 Sybase、MS Access、Teradata、 Firebird、Apache Hive、Phoenix、Presto等。DBeaver比大多数的SQL管理工具要轻量，而且支持中文界面。DBeaver社区版作为一个免费开源的产品，和其他类似的软件相比，在功能和易用性上都毫不逊色。

唯一需要注意是 DBeaver 是用Java编程语言开发的，所以需要拥有 JDK（Java Development ToolKit）环境。如果电脑上没JDK，在选择安装DBeaver组件时，勾选“Include Java”即可。

下载地址： **https://dbeaver.io/download/**

![image-20220921150650914](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150650914.png)

![image-20220921150707548](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150707548.png)

### 可能出现连接问题：

有些图形界面工具，特别是旧版本的图形界面工具，在连接MySQL8时出现“Authentication plugin'caching_sha2_password' cannot be loaded”错误。

![image-20220921150743771](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150743771.png)

出现这个原因是MySQL8之前的版本中加密规则是mysql_native_password，而在MySQL8之后，加密规则是caching_sha2_password。解决问题方法有两种，第一种是升级图形界面工具版本，第二种是把MySQL8用户登录密码加密规则还原成mysql_native_password。

第二种解决方案如下，用命令行登录MySQL数据库之后，执行如下命令修改用户密码加密规则并更新用户密码，这里修改用户名为“root@localhost”的用户密码规为“mysql_native_password”，密码值为“123456”，如图所示。

```sql
#使用mysql数据库
USE mysql;
#修改'root'@'localhost'用户的密码规则和密码
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'abc123';
#刷新权限
FLUSH PRIVILEGES;
```

![image-20220921150850823](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150850823.png)



## 6. MySQL目录结构与源码

### 6. 1 主要目录结构

![image-20220921150926221](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921150926221.png)

### 6. 2 MySQL 源代码获取

首先，你要进入 MySQL下载界面。 这里你不要选择用默认的“Microsoft Windows”，而是要通过下拉栏，找到“Source Code”，在下面的操作系统版本里面， 选择 Windows（Architecture Independent），然后点击下载。

接下来，把下载下来的压缩文件解压，我们就得到了 MySQL 的源代码。

MySQL 是用 C++ 开发而成的，我简单介绍一下源代码的组成。

mysql-8.0.22 目录下的各个子目录，包含了 MySQL 各部分组件的源代码：

![image-20220921151004024](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151004024.png)

- sql 子目录是 MySQL 核心代码；
- libmysql 子目录是客户端程序 API；
- mysql-test 子目录是测试工具；
- mysys 子目录是操作系统相关函数和辅助函数；

源代码可以用记事本打开查看，如果你有 C++ 的开发环境，也可以在开发环境中打开查看。

![image-20220921151033988](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151033988.png)

如上图所示，源代码并不神秘，就是普通的 C++ 代码，跟你熟悉的一样，而且有很多注释，可以帮助你理解。阅读源代码就像在跟 MySQL 的开发人员对话一样，十分有趣。



## 7. 常见问题的解决(课外内容)

### 问题 1 ：root用户密码忘记，重置的操作

1: 通过任务管理器或者服务管理，关掉mysqld(服务进程) 

2: 通过命令行+特殊参数开启mysqld mysqld --defaults-file="D:\ProgramFiles\mysql\MySQLServer5.7Data\my.ini" --skip-grant-tables

3: 此时，mysqld服务进程已经打开。并且不需要权限检查

4: mysql -uroot 无密码登陆服务器。另启动一个客户端进行 

5: 修改权限表 

（ 1 ） use mysql; 

（ 2 ）update user set authentication_string=password('新密码') where user='root' and Host='localhost'; 

（ 3 ）flush privileges;

6: 通过任务管理器，关掉mysqld服务进程。 

7: 再次通过服务管理，打开mysql服务。 

8: 即可用修改后的新密码登陆。

### 问题 2 ：mysql命令报“不是内部或外部命令”

如果输入mysql命令报“不是内部或外部命令”，把mysql安装目录的bin目录配置到环境变量path中。如下：

![image-20220921151240089](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151240089.png)



### 问题 3 ：错误ERROR ：没有选择数据库就操作表格和数据

![image-20220921151312934](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151312934.png)

### 问题 4 ：命令行客户端的字符集问题

```sql
mysql> INSERT INTO t_stu VALUES(1,'张三','男');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'sname' at
row 1
```

原因：服务器端认为你的客户端的字符集是utf- 8 ，而实际上你的客户端的字符集是GBK。

![image-20220921151353092](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151353092.png)

查看所有字符集： **SHOW VARIABLES LIKE 'character_set_%';**

![image-20220921151411354](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151411354.png)

解决方案，设置当前连接的客户端字符集 “**SET NAMES GBK;**”

![image-20220921151441816](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151441816.png)

### 问题 5 ：修改数据库和表的字符编码

修改编码：

（1)先停止服务，（ 2 ）修改my.ini文件（ 3 ）重新启动服务

说明：

如果是在修改my.ini之前建的库和表，那么库和表的编码还是原来的Latin1，要么删了重建，要么使用alter语句修改编码。

```sql
mysql> create database 0728 db charset Latin1;
Query OK, 1 row affected (0.00 sec)
```

```sql
mysql> use 0728db;
Database changed
```

![image-20220921151807383](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151807383.png)

![image-20220921151816673](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151816673.png)

![image-20220921151825858](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151825858.png)

![image-20220921151834430](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220921151834430.png)



# 第 03 章_基本的SELECT语句

## 1. SQL概述

### 1. 1 SQL背景知识

- 1946 年，世界上第一台电脑诞生，如今，借由这台电脑发展起来的互联网已经自成江湖。在这几十年里，无数的技术、产业在这片江湖里沉浮，有的方兴未艾，有的已经几幕兴衰。但在这片浩荡的波动里，有一门技术从未消失，甚至“老当益壮”，那就是 SQL。
  - 45 年前，也就是 1974 年，IBM 研究员发布了一篇揭开数据库技术的论文《SEQUEL：一门结构化的英语查询语言》，直到今天这门结构化的查询语言并没有太大的变化，相比于其他语言，**SQL 的半衰期可以说是非常长了**。
- 不论是前端工程师，还是后端算法工程师，都一定会和数据打交道，都需要了解如何又快又准确地提取自己想要的数据。更别提数据分析师了，他们的工作就是和数据打交道，整理不同的报告，以便指导业务决策。
- SQL（Structured Query Language，结构化查询语言）是使用关系模型的数据库应用语言，**与数据直接打交道**，由**IBM**上世纪 70 年代开发出来。后由美国国家标准局（ANSI）开始着手制定SQL标准，先后有**SQL- 86 ，SQL- 89 ，SQL- 92 ，SQL- 99** 等标准。
  - SQL 有两个重要的标准，分别是 SQL92 和 SQL99，它们分别代表了 92 年和 99 年颁布的 SQL 标准，我们今天使用的 SQL 语言依然遵循这些标准。
- 不同的数据库生产厂商都支持SQL语句，但都有特有内容。

![image-20220726104029071](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726104029071.png)


### 1. 2 SQL语言排行榜
自从 SQL 加入了 TIOBE 编程语言排行榜，就一直保持在 Top 10。

![image-20220726104142235](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726104142235.png)

### 1. 3 ==SQL 分类==
SQL语言在功能上主要分为如下 3 大类：

- **DDL（Data Definition Languages、数据定义语言）** ，这些语句定义了不同的数据库、表、视图、索引等数据库对象，还可以用来创建、删除、修改数据库和数据表的结构。
  - 主要的语句关键字包括==CREATE==、==DROP==、==ALTER==、==RENAME==、==TRUNCATE==等。
- **DML（Data Manipulation Language、数据操作语言）** ，用于添加、删除、更新和查询数据库记录，并检查数据完整性。
- 主要的语句关键字包括==INSERT==、==DELETE==、==UPDATE==、==SELECT==等。
  
- **SELECT是SQL语言的基础，最为重要**。
- **DCL（Data Control Language、数据控制语言）** ，用于定义数据库、表、字段、用户的访问权限和安全级别。
  - 主要的语句关键字包括==GRANT==、==REVOKE==、==COMMIT==、==ROLLBACK==、==SAVEPOINT==等。

​	因为查询语句使用的非常的频繁，所以很多人把查询语句单拎出来一类：DQL（数据查询语言）。

​	还有单独将==COMMIT==、==ROLLBACK== 取出来称为TCL （Transaction Control Language，事务控制语言）。

## 2. SQL语言的规则与规范

### 2. 1 基本规则

- SQL 可以写在一行或者多行。为了提高可读性，各子句分行写，必要时使用缩进

- 每条命令以 ; 或 \g 或 \G 结束

- 关键字不能被缩写也不能分行

- 关于标点符号

  - 必须保证所有的()、单引号、双引号是成对结束的

  - 必须使用英文状态下的半角输入方式

  - 字符串型和日期时间类型的数据可以使用单引号（' '）表示

  - 列的别名，尽量使用双引号（" "），而且不建议省略as

### 2. 2 SQL大小写规范 （建议遵守）

- **MySQL 在 Windows 环境下是大小写不敏感的**

- **MySQL 在 Linux 环境下是大小写敏感的**

  - 数据库名、表名、表的别名、变量名是严格区分大小写的

  - 关键字、函数名、列名(或字段名)、列的别名(字段的别名) 是忽略大小写的。

- **推荐采用统一的书写规范：**

  - 数据库名、表名、表别名、字段名、字段别名等都**小写**

  - SQL 关键字、函数名、绑定变量等都**大写**

### 2. 3 注 释
可以使用如下格式的注释结构
```sql
单行注释：#注释文字(MySQL特有的方式)
单行注释：-- 注释文字(--后面必须包含一个空格。)
多行注释：/* 注释文字 */
```


### 2. 4 命名规则（暂时了解）

- 数据库、表名不得超过 30 个字符，变量名限制为 29 个
- 必须只能包含 A–Z, a–z, 0–9, _共 63 个字符
- 数据库名、表名、字段名等对象名中间不要包含空格
- 同一个MySQL软件中，数据库不能同名；同一个库中，表不能重名；同一个表中，字段不能重名
- 必须保证你的字段没有和保留字、数据库系统或常用方法冲突。如果坚持使用，请在SQL语句中使用`（着重号）引起来
- 保持字段名和类型的一致性，在命名字段并为其指定数据类型的时候一定要保证一致性。假如数据类型在一个表里是整数，那在另一个表里可就别变成字符型了

举例：

```mysql
 #以下两句是一样的，不区分大小写
show databases;
SHOW DATABASES;

 #创建表格
#create table student info(...); #表名错误，因为表名有空格
create table student_info(...);

#其中order使用``飘号，因为order和系统关键字或系统函数名等预定义标识符重名了
CREATE TABLE `order`(
        id INT,
        lname VARCHAR( 20 )
);

select id as "编号", `name` as "姓名" from t_stu; #起别名时，as都可以省略
select id as 编号, `name` as 姓名 from t_stu; #如果字段别名中没有空格，那么可以省略""
select id as 编 号, `name` as 姓 名 from t_stu; #错误，如果字段别名中有空格，那么不能省略""
```

### 2. 5 数据导入指令
在命令行客户端登录mysql（mysql -uroot -P3306 -p），使用source指令导入
```mysql
mysql> source d:\mysqldb.sql
```
```mysql
mysql> desc employees;
+----------------+-------------+------+-----+---------+-------+
| Field | Type | Null | Key | Default | Extra |
+----------------+-------------+------+-----+---------+-------+
| employee_id | int( 6 ) | NO | PRI | 0 | |
| first_name | varchar( 20 ) | YES | | NULL | |
| last_name | varchar( 25 ) | NO | | NULL | |
| email | varchar( 25 ) | NO | UNI | NULL | |
| phone_number | varchar( 20 ) | YES | | NULL | |
| hire_date | date | NO | | NULL | |
| job_id | varchar( 10 ) | NO | MUL | NULL | |
| salary | double( 8 , 2 ) | YES | | NULL | |
| commission_pct | double( 2 , 2 ) | YES | | NULL | |
| manager_id | int( 6 ) | YES | MUL | NULL | |
| department_id | int( 4 ) | YES | MUL | NULL | |
+----------------+-------------+------+-----+---------+-------+
11 rows in set (0.00 sec)
```

## 3. 基本的SELECT语句

### 3. 0 SELECT...

```mysql
SELECT 1 ; #没有任何子句
SELECT 9 /2; #没有任何子句
```

### 3. 1 SELECT ... FROM

- 语法：
```mysql
SELECT 标识选择哪些列
FROM 标识从哪个表中选择
```

- 选择全部列：
```mysql
SELECT *
FROM departments;
```

![image-20220726110634303](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726110634303.png)

-  一般情况下，除非需要使用表中所有的字段数据，最好不要使用通配符‘*’。使用通配符虽然可以节 省输入查询语句的时间，但是获取不需要的列数据通常会降低查询和所使用的应用程序的率。通配符的优势是，当不知道所需要的列的名称时，可以通过它获取它们。

- 在生产环境下，不推荐你直接使用**SELECT ***进行查询。

- 选择特定的列：
```mysql
SELECT department_id, location_id
FROM departments;
```

![image-20220726110651298](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726110651298.png)

​		MySQL中的SQL语句是不区分大小写的，因此SELECT和select的作用是相同的，但是，许多开发人员习惯将关键字大写、数据列和表名小写，读者也应该养成一个良好的编程习惯，这样写出来的代码更容易阅读和维护。

### 3. 2 列的别名

- 重命名一个列
- 便于计算
- 紧跟列名，也可以 **在列名和别名之间加入关键字AS(alias别名)，别名使用双引号** ，以便在别名中包含空格或特殊的字符并区分大小写。
- AS(alias) 可以省略
- 别名用一对双引号“ ”引起来，不要使用单引号'  '
- 建议别名简短，见名知意
- 举例
```mysql
SELECT last_name AS name, commission_pct comm
FROM employees;
```

![image-20220726110745497](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726110745497.png)

```mysql
SELECT last_name "Name", salary* 12 "Annual Salary"
FROM employees;
```
![image-20220726110806853](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726110806853.png)

### 3. 3 去除重复行

默认情况下，查询会返回全部行，包括重复行。
```mysql
SELECT department_id
FROM employees;
```

![image-20220726110842543](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726110842543.png)

**在SELECT语句中使用关键字==DISTINCT==去除重复行**

```mysql
SELECT DISTINCT department_id
FROM employees;
```
![image-20220726110906556](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726110906556.png)

针对于：

```mysql
SELECT DISTINCT department_id,salary
FROM employees;
```

这里有两点需要注意：

- 1. DISTINCT 需要放到所有列名的前面，如果写成`SELECT salary, DISTINCT department_id FROM employees`会报错。

- 2. DISTINCT 其实是对后面所有列名的组合进行去重，你能看到最后的结果是 74 条，因为这 74 个部门id不同，都有 salary 这个属性值。如果你想要看都有哪些不同的部门（department_id），只需要写`DISTINCT department_id`即可，后面不需要再加其他的列名了。

### 3. 4 空值参与运算
- 所有运算符或列值遇到null值，运算的结果都为null
```mysql
SELECT employee_id,salary,commission_pct,12 * salary * ( 1 + commission_pct) "annual_sal"
FROM employees;
SELECT employee_id,salary"月工资",salary*(1+IFNULL(commission_pct,0))*12 "年工资",commission_pct
FROM employees;
```

- 这里你一定要注意，在 MySQL 里面， 空值不等于空字符串。**一个空字符串的长度是 0 ，而一个空值的长度是空**。而且，在MySQL 里面，空值是占用空间的。

### 3. 5 着重号
- 错误的
```mysql
mysql> SELECT * FROM ORDER;
ERROR 1064 ( 42000 ): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ORDER' at line 1
```

- 正确的
```mysql
mysql> SELECT * FROM `ORDER`;
+----------+------------+
| order_id | order_name |
+----------+------------+
| 1 | shkstart |
| 2 | tomcat |
| 3 | dubbo |
+----------+------------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM `order`;
+----------+------------+
| order_id | order_name |
+----------+------------+
| 1 | shkstart |
| 2 | tomcat |
| 3 | dubbo |
+----------+------------+
3 rows in set (0.00 sec)
```

- 结论：
我们需要保证表中的字段、表名等没有和保留字、数据库系统或常用方法冲突。如果真的相同，请在SQL语句中使用一对 ``（着重号）引起来。


### 3. 6  查询常数

 SELECT 查询还可以对常数进行查询。对的，就是在 SELECT 查询结果中增加一列固定的常数列。这列的取值是我们指定的，而不是从数据表中动态取出的。

你可能会问为什么我们还要对常数进行查询呢？

SQL 中的 SELECT 语法的确提供了这个功能，一般来说我们只从一个表中查询数据，通常不需要增加一个固定的常数列，但如果我们想整合不同的数据源，用常数列作为这个表的标记，就需要查询常数。

比如说，我们想对 employees 数据表中的员工姓名进行查询，同时增加一列字段corporation，这个字段固定值为“尚硅谷”，可以这写：
```mysql
SELECT '尚硅谷' AS corporation, last_name 
FROM employees;
```

## 4. 显示表结构

使用==DESCRIBE== 或 ==DESC== 命令，表示表结构。
```mysql
DESCRIBE employees;
或
DESC employees;
```
```mysql
mysql> desc employees;
+----------------+-------------+------+-----+---------+-------+
| Field | Type | Null | Key | Default | Extra |
+----------------+-------------+------+-----+---------+-------+
| employee_id | int( 6 ) | NO | PRI | 0 | |
| first_name | varchar( 20 ) | YES | | NULL | |
| last_name | varchar( 25 ) | NO | | NULL | |
| email | varchar( 25 ) | NO | UNI | NULL | |
| phone_number | varchar( 20 ) | YES | | NULL | |
| hire_date | date | NO | | NULL | |
| job_id | varchar( 10 ) | NO | MUL | NULL | |
| salary | double( 8 , 2 ) | YES | | NULL | |
| commission_pct | double( 2 , 2 ) | YES | | NULL | |
| manager_id | int( 6 ) | YES | MUL | NULL | |
| department_id | int( 4 ) | YES | MUL | NULL | |
+----------------+-------------+------+-----+---------+-------+
11 rows in set (0.00 sec)
```
其中，各个字段的含义分别解释如下：

- Field：表示字段名称。
- Type：表示字段类型，这里 barcode、goodsname 是文本型的，price 是整数类型的。
- Null：表示该列是否可以存储NULL值。
- Key：表示该列是否已编制索引。PRI表示该列是表主键的一部分；UNI表示该列是UNIQUE索引的一部分；MUL表示在列中某个给定值允许出现多次。
- Default：表示该列是否有默认值，如果有，那么值是多少。
- Extra：表示可以获取的与给定列有关的附加信息，例如AUTO_INCREMENT等。


## 5. 过滤数据
- 背景：

![image-20220726111140295](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726111140295.png)


- 语法：
```mysql
 SELECT 字段1,字段 2
 FROM 表名
 WHERE 过滤条件
```
- 使用WHERE 子句，将不满足条件的行过滤掉
- **WHERE子句紧随 FROM子句**

- 举例

```mysql
SELECT employee_id, last_name, job_id, department_id
FROM employees
WHERE department_id = 90 ;
```

![image-20220726111231409](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726111231409.png)





# 第 04 章_运算符

## 1. 算术运算符

算术运算符主要用于数学运算，其可以连接运算符前后的两个数值或表达式，对数值或表达式进行加 （+）、减（-）、乘（*）、除（/）和取模（%）运算。

![image-20220726120357351](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726120357351.png)



### 1 ．加法与减法运算符
```mysql
mysql> SELECT 100, 100 + 0, 100 - 0, 100 + 50, 100 + 50 -30, 100 + 35.5, 100 - 35.5
FROM dual;
+-----+---------+---------+----------+--------------+------------+------------+
| 100 | 100 + 0 | 100 - 0 | 100 + 50 | 100 + 50 -30 | 100 + 35.5 | 100 - 35.5 |
+-----+---------+---------+----------+--------------+------------+------------+
| 100 | 100 | 100 | 150 | 120 | 135.5 | 64.5 |
+-----+---------+---------+----------+--------------+------------+------------+
1 row in set (0.00 sec)
```

**由运算结果可以得出如下结论：**

- 一个整数类型的值对整数进行加法和减法操作，结果还是一个整数；
- 一个整数类型的值对浮点数进行加法和减法操作，结果是一个浮点数；
- 加法和减法的优先级相同，进行先加后减操作与进行先减后加操作的结果是一样的；
- 在Java中，+的左右两边如果有字符串，那么表示字符串的拼接。但是在MySQL中+只表示数值相加。如果遇到非数值类型，先尝试转成数值，如果转失败，就按 0 计算。（补充：MySQL中字符串拼接要使用字符串函数CONCAT()实现）

### 2 ．乘法与除法运算符

```mysql
mysql> SELECT 100, 100 * 1, 100 * 1.0, 100 / 1.0, 100 / 2,100 + 2 * 5 / 2,100 /3, 100
DIV 0 FROM dual;
+-----+---------+-----------+-----------+---------+-----------------+---------+-------
----+
| 100 | 100 * 1 | 100 * 1.0 | 100 / 1.0 | 100 / 2 | 100 + 2 * 5 / 2 | 100 /3 | 100
DIV 0 |
+-----+---------+-----------+-----------+---------+-----------------+---------+-------
----+
| 100 | 100 | 100.0 | 100.0000 | 50.0000 | 105.0000 | 33.3333 |
NULL |
+-----+---------+-----------+-----------+---------+-----------------+---------+-------
----+
1 row in set (0.00 sec)
```
```mysql
#计算出员工的年基本工资
SELECT employee_id,salary,salary * 12 annual_sal
FROM employees;
```

**由运算结果可以得出如下结论：**

- 一个数乘以整数 1 和除以整数 1 后仍得原数；
- 一个数乘以浮点数 1 和除以浮点数 1 后变成浮点数，数值与原数相等；
- 一个数除以整数后，不管是否能除尽，结果都为一个浮点数；
- 一个数除以另一个数，除不尽时，结果为一个浮点数，并保留到小数点后 4 位；
- 乘法和除法的优先级相同，进行先乘后除操作与先除后乘操作，得出的结果相同。
- 在数学运算中， 0 不能用作除数，在MySQL中，一个数除以 0 为NULL。

### 3 ．求模（求余）运算符 

将t 22 表中的字段i对 3 和 5 进行求模（求余）运算。

```mysql
mysql> SELECT 12 % 3 , 12 MOD 5 FROM dual;
+--------+----------+
| 12 % 3 | 12 MOD 5 |
+--------+----------+
| 0 | 2 |
+--------+----------+
1 row in set (0.00 sec)
```
```mysql
#筛选出employee_id是偶数的员工
SELECT * FROM employees
WHERE employee_id MOD 2 = 0 ;
```
可以看到， 100 对 3 求模后的结果为 3 ，对 5 求模后的结果为 0 。



## 2. 比较运算符

比较运算符用来对表达式左边的操作数和右边的操作数进行比较，比较的结果为真则返回 1 ，比较的结果为假则返回 0 ，其他情况则返回NULL。

比较运算符经常被用来作为SELECT查询语句的条件来使用，返回符合条件的结果记录。

![image-20220726120741228](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726120741228.png)



### 1 .等号运算符
- 等号运算符（=）判断等号两边的值、字符串或表达式是否相等，如果相等则返回 1 ，不相等则返回0 。

- 在使用等号运算符时，遵循如下规则：

  - 如果等号两边的值、字符串或表达式都为字符串，则MySQL会按照字符串进行比较，其比较的是每个字符串中字符的ANSI编码是否相等。

  - 如果等号两边的值都是整数，则MySQL会按照整数来比较两个值的大小。

  - 如果等号两边的值**一个是整数，另一个是字符串**，则MySQL会**将字符串转化为数字**进行比较。

  - 如果等号两边的值、字符串或表达式中**有一个为NULL，则比较结果为NULL**。

- 对比：SQL中赋值符号使用 :=
```mysql
mysql> SELECT 1 = 1 , 1 = '1', 1 = 0 , 'a' = 'a', ( 5 + 3 ) = ( 2 + 6 ), '' = NULL , NULL =
NULL;
+-------+---------+-------+-----------+-------------------+-----------+-------------+
| 1 = 1 | 1 = '1' | 1 = 0 | 'a' = 'a' | ( 5 + 3 ) = ( 2 + 6 ) | '' = NULL | NULL = NULL |
+-------+---------+-------+-----------+-------------------+-----------+-------------+
| 1 | 1 | 0 | 1 | 1 |  NULL |  NULL |
+-------+---------+-------+-----------+-------------------+-----------+-------------+
1 row in set (0.00 sec)
```
```mysql
mysql> SELECT 1 = 2 , 0 = 'abc', 1 = 'abc' FROM dual;
+-------+-----------+-----------+
| 1 = 2 | 0 = 'abc' | 1 = 'abc' |
+-------+-----------+-----------+
| 0 | 1 | 0 |
+-------+-----------+-----------+
1 row in set, 2 warnings (0.00 sec)
```
```mysql
#查询salary=10000，注意在Java中比较是==
SELECT employee_id,salary FROM employees WHERE salary = 10000 ;
```

### 2 .安全等于运算符 
安全等于运算符（<=>）与等于运算符（=）的作用是相似的，唯一的区别是‘<=>’可以用来对NULL进行判断。在两个操作数均为NULL时，其返回值为 1 ，而不为NULL；当一个操作数为NULL时，其返回值为 0 ，而不为NULL。
```mysql
mysql> SELECT 1 <=> '1', 1 <=> 0 , 'a' <=> 'a', ( 5 + 3 ) <=> ( 2 + 6 ), '' <=> NULL,NULL
<=> NULL FROM dual;
+-----------+---------+-------------+---------------------+-------------+-------------
--+
| 1 <=> '1' | 1 <=> 0 | 'a' <=> 'a' | ( 5 + 3 ) <=> ( 2 + 6 ) | '' <=> NULL | NULL <=>
NULL |
+-----------+---------+-------------+---------------------+-------------+-------------
--+
| 1 | 0 | 1 | 1 | 0 |
1 |
+-----------+---------+-------------+---------------------+-------------+-------------
--+
1 row in set (0.00 sec)
```
```mysql
#查询commission_pct等于0.
SELECT employee_id,commission_pct FROM employees WHERE commission_pct = 0.40;

SELECT employee_id,commission_pct FROM employees WHERE commission_pct <=> 0.40;
#如果把0.40改成 NULL 呢？
```

可以看到，使用安全等于运算符时，两边的操作数的值都为NULL时，返回的结果为 1 而不是NULL，其他返回结果与等于运算符相同。

### 3 .不等于运算符 
不等于运算符（<>和!=）用于判断两边的数字、字符串或者表达式的值是否不相等，如果不相等则返回 1 ，相等则返回 0 。不等于运算符不能判断NULL值。如果两边的值有任意一个为NULL，或两边都为NULL，则结果为NULL。 SQL语句示例如下：
```mysql
mysql> SELECT 1 <> 1 , 1 != 2 , 'a' != 'b', ( 3 + 4 ) <> ( 2 + 6 ), 'a' != NULL, NULL <> NULL;
+--------+--------+------------+----------------+-------------+--------------+
| 1 <> 1 | 1 != 2 | 'a' != 'b' | ( 3 + 4 ) <> ( 2 + 6 ) | 'a' != NULL | NULL <> NULL |
+--------+--------+------------+----------------+-------------+--------------+
| 0 | 1 | 1 | 1 | NULL | NULL |
+--------+--------+------------+----------------+-------------+--------------+
1 row in set (0.00 sec)
```

**此外，还有非符号类型的运算符：**

![image-20220726121109956](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726121109956.png)






### 4. 空运算符 
空运算符（IS NULL或者ISNULL）判断一个值是否为NULL，如果为NULL则返回 1 ，否则返回 0 。 SQL语句示例如下：
```mysql
mysql> SELECT NULL IS NULL, ISNULL(NULL), ISNULL('a'), 1 IS NULL;
+--------------+--------------+-------------+-----------+
| NULL IS NULL | ISNULL(NULL) | ISNULL('a') | 1 IS NULL |
+--------------+--------------+-------------+-----------+
| 1 | 1 | 0 | 0 |
+--------------+--------------+-------------+-----------+
1 row in set (0.00 sec)
```
```mysql
#查询commission_pct等于NULL。比较如下的四种写法
SELECT employee_id,commission_pct FROM employees WHERE commission_pct IS NULL;
SELECT employee_id,commission_pct FROM employees WHERE commission_pct <=> NULL;
SELECT employee_id,commission_pct FROM employees WHERE ISNULL(commission_pct);
SELECT employee_id,commission_pct FROM employees WHERE commission_pct = NULL;
```
```mysql
SELECT last_name, manager_id
FROM employees
WHERE manager_id IS NULL;
```

### 5. 非空运算符 
非空运算符（IS NOT NULL）判断一个值是否不为NULL，如果不为NULL则返回 1 ，否则返 回 0 。 SQL语句示例如下：
```mysql
mysql> SELECT NULL IS NOT NULL, 'a' IS NOT NULL, 1 IS NOT NULL;
+------------------+-----------------+---------------+
| NULL IS NOT NULL | 'a' IS NOT NULL | 1 IS NOT NULL |
+------------------+-----------------+---------------+
| 0                | 1               | 1             |
+------------------+-----------------+---------------+
1 row in set (0.01 sec)
```
```mysql
#查询commission_pct不等于NULL
SELECT employee_id,commission_pct FROM employees WHERE commission_pct IS NOT NULL;
SELECT employee_id,commission_pct FROM employees WHERE NOT commission_pct <=> NULL;
SELECT employee_id,commission_pct FROM employees WHERE NOT ISNULL(commission_pct);
```

### 6. 最小值运算符 
语法格式为：LEAST(值 1 ，值 2 ，...，值n)。其中，“值n”表示参数列表中有n个值。在有两个或多个参数的情况下，返回最小值。
```mysql
mysql> SELECT LEAST (1,0,2), LEAST('b','a','c'), LEAST(1,NULL,2);
+---------------+--------------------+-----------------+
| LEAST (1,0,2) | LEAST('b','a','c') | LEAST(1,NULL,2) |
+---------------+--------------------+-----------------+
| 0 | a | NULL |
+---------------+--------------------+-----------------+
1 row in set (0.00 sec)
```

由结果可以看到，当参数是整数或者浮点数时，LEAST将返回其中最小的值；当参数为字符串时，返回字母表中顺序最靠前的字符；当比较值列表中有NULL时，不能判断大小，返回值为NULL。

### 7. 最大值运算符 
语法格式为：GREATEST(值 1 ，值 2 ，...，值n)。其中，n表示参数列表中有n个值。当有两个或多个参数时，返回值为最大值。假如任意一个自变量为NULL，则GREATEST()的返回值为NULL。
```mysql
mysql> SELECT GREATEST(1,0,2), GREATEST('b','a','c'), GREATEST(1,NULL,2);
+-----------------+-----------------------+--------------------+
| GREATEST(1,0,2) | GREATEST('b','a','c') | GREATEST(1,NULL,2) |
+-----------------+-----------------------+--------------------+
| 2 | c | NULL |
+-----------------+-----------------------+--------------------+
1 row in set (0.00 sec)
```

由结果可以看到，当参数中是整数或者浮点数时，GREATEST将返回其中最大的值；当参数为字符串时，返回字母表中顺序最靠后的字符；当比较值列表中有NULL时，不能判断大小，返回值为NULL。

### 8. BETWEEN AND运算符 
BETWEEN运算符使用的格式通常为SELECT D FROM TABLE WHERE C BETWEEN A  AND B，此时，当C大于或等于A，并且C小于或等于B时，结果为 1 ，否则结果为 0 。
```mysql
mysql> SELECT 1 BETWEEN 0 AND 1, 10 BETWEEN 11 AND 12, 'b' BETWEEN 'a' AND 'c';
+-------------------+----------------------+-------------------------+
| 1 BETWEEN 0 AND 1 | 10 BETWEEN 11 AND 12 | 'b' BETWEEN 'a' AND 'c' |
+-------------------+----------------------+-------------------------+
| 1 | 0 | 1 |
+-------------------+----------------------+-------------------------+
1 row in set (0.00 sec)
```

```mysql
SELECT last_name, salary
FROM employees
WHERE salary BETWEEN 2500 AND 3500;
```

### 9. IN运算符 

IN运算符用于判断给定的值是否是IN列表中的一个值，如果是则返回 1 ，否则返回 0 。如果给定的值为NULL，或者IN列表中存在NULL，则结果为NULL。

```mysql
mysql> SELECT 'a' IN ('a','b','c'), 1 IN (2,3), NULL IN ('a','b'), 'a' IN ('a', NULL);
+----------------------+------------+-------------------+--------------------+
| 'a' IN ('a','b','c') | 1 IN (2,3) | NULL IN ('a','b') | 'a' IN ('a', NULL) |
+----------------------+------------+-------------------+--------------------+
| 1 | 0 | NULL | 1 |
+----------------------+------------+-------------------+--------------------+
1 row in set (0.00 sec)
```

```mysql
SELECT employee_id, last_name, salary, manager_id
FROM employees
WHERE manager_id IN (100, 101, 201);
```

### 10. NOT IN运算符 

NOT IN运算符用于判断给定的值是否不是IN列表中的一个值，如果不是IN列表中的一 个值，则返回 1 ，否则返回 0 。

```mysql
mysql> SELECT 'a' NOT IN ('a','b','c'), 1 NOT IN (2,3);
+--------------------------+----------------+
| 'a' NOT IN ('a','b','c') | 1 NOT IN (2,3) |
+--------------------------+----------------+
| 0 | 1 |
+--------------------------+----------------+
1 row in set (0.00 sec)
```

### 11. LIKE运算符 
LIKE运算符主要用来匹配字符串，通常用于模糊匹配，如果满足条件则返回 1 ，否则返回 0 。如果给定的值或者匹配条件为NULL，则返回结果为NULL。

 ==LIKE运算符通常使用如下通配符==：

```mysql
 “%”：匹配 0 个或多个字符。
 “_”：只能匹配一个字符。
```

 SQL语句示例如下：

```mysql
mysql> SELECT NULL LIKE 'abc', 'abc' LIKE NULL;
+-----------------+-----------------+
| NULL LIKE 'abc' | 'abc' LIKE NULL |
+-----------------+-----------------+
| NULL | NULL |
+-----------------+-----------------+
1 row in set (0.00 sec)
```

```mysql
SELECT first_name
FROM employees
WHERE first_name LIKE 'S%';
```

```mysql
SELECT last_name
FROM employees
WHERE last_name LIKE '_o%';
```

#### ESCAPE

- 回避特殊符号的： **使用转义符** 。例如：将[%]转为[$%]、[]转为[$]，然后再加上[ESCAPE‘$’]即可。

```mysql
SELECT job_id
FROM jobs
WHERE job_id LIKE ‘IT\_%‘;
```

- 如果==使用\表示转义==，要省略ESCAPE。如果不是\，则要加上ESCAPE。

```mysql
SELECT job_id
FROM jobs
WHERE job_id LIKE ‘IT$_%‘ escape ‘$‘;
```

### 12. REGEXP运算符
REGEXP运算符用来匹配字符串，语法格式为：==expr REGEXP 匹配条件==。如果expr满足匹配条件，返回1 ；如果不满足，则返回 0 。若expr或匹配条件任意一个为NULL，则结果为NULL。

**REGEXP运算符在进行匹配时，常用的有下面几种通配符：**

```mysql
（1）‘^’匹配以该字符后面的字符开头的字符串。
（2）‘$’匹配以该字符前面的字符结尾的字符串。
（3）‘.’匹配任何一个单字符。
（4）“[...]”匹配在方括号内的任何字符。例如，“[abc]”匹配“a”或“b”或“c”。为了命名字符的范围，使用一个‘-’。“[a-z]”匹配任何字母，而“[0-9]”匹配任何数字。
（5）‘*’匹配零个或多个在它前面的字符。例如，“x*”匹配任何数量的‘x’字符，“[0-9]*”匹配任何数量的数字，而“*”匹配任何数量的任何字符。
```

 SQL语句示例如下：

```mysql
mysql> SELECT 'shkstart' REGEXP '^s', 'shkstart' REGEXP 't$', 'shkstart' REGEXP 'hk';
+------------------------+------------------------+-------------------------+
| 'shkstart' REGEXP '^s' | 'shkstart' REGEXP 't$' | 'shkstart' REGEXP 'hk' |
+------------------------+------------------------+-------------------------+
| 1 | 1 | 1 |
+------------------------+------------------------+-------------------------+
1 row in set (0.01 sec)
```

```mysql
mysql> SELECT 'atguigu' REGEXP 'gu.gu', 'atguigu' REGEXP '[ab]';
+--------------------------+-------------------------+
| 'atguigu' REGEXP 'gu.gu' | 'atguigu' REGEXP '[ab]' |
+--------------------------+-------------------------+
| 1 | 1 |
+--------------------------+-------------------------+
1 row in set (0.00 sec)
```




## 3. 逻辑运算符
逻辑运算符主要用来判断表达式的真假，在MySQL中，逻辑运算符的返回结果为 1 、 0 或者NULL。

MySQL中支持 4 种逻辑运算符如下：

![image-20220726122020196](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726122020196.png)



### 1 ．逻辑非运算符 

逻辑非（NOT或!）运算符表示当给定的值为 0 时返回 1 ；当给定的值为非 0 值时返回 0 ；当给定的值为NULL时，返回NULL。


```mysql
mysql> SELECT NOT 1, NOT 0, NOT(1+1), NOT !1, NOT NULL;
+-------+-------+----------+--------+----------+
| NOT 1 | NOT 0 | NOT(1+1) | NOT !1 | NOT NULL |
+-------+-------+----------+--------+----------+
| 0 | 1 | 0 | 1 | NULL |
+-------+-------+----------+--------+----------+
1 row in set, 1 warning (0.00 sec)
```

```mysql
SELECT last_name, job_id
FROM employees
WHERE job_id NOT IN ('IT_PROG', 'ST_CLERK', 'SA_REP');
```

### 2 ．逻辑与运算符 

逻辑与（AND或&&）运算符是当给定的所有值均为非 0 值，并且都不为NULL时，返回1 ；当给定的一个值或者多个值为 0 时则返回 0 ；否则返回NULL。

```mysql
mysql> SELECT 1 AND -1, 0 AND 1, 0 AND NULL, 1 AND NULL;
+----------+---------+------------+------------+
| 1 AND -1 | 0 AND 1 | 0 AND NULL | 1 AND NULL |
+----------+---------+------------+------------+
| 1 | 0 | 0 | NULL |
+----------+---------+------------+------------+
1 row in set (0.00 sec)
```

```mysql
SELECT employee_id, last_name, job_id, salary
FROM employees
WHERE salary >=10000 AND job_id LIKE '%MAN%';
```


### 3 ．逻辑或运算符 
逻辑或（OR或||）运算符是当给定的值都不为NULL，并且任何一个值为非 0 值时，则返回 1 ，否则返回 0 ；当一个值为NULL，并且另一个值为非 0 值时，返回 1 ，否则返回NULL；当两个值都为 NULL时，返回NULL。

```mysql
mysql> SELECT 1 OR -1, 1 OR 0, 1 OR NULL, 0 || NULL, NULL || NULL;
+---------+--------+-----------+-----------+--------------+
| 1 OR -1 | 1 OR 0 | 1 OR NULL | 0 || NULL | NULL || NULL |
+---------+--------+-----------+-----------+--------------+
| 1 | 1 | 1 | NULL | NULL |
+---------+--------+-----------+-----------+--------------+
1 row in set, 2 warnings (0.00 sec)
```

```mysql
#查询基本薪资不在9000-12000之间的员工编号和基本薪资
SELECT employee_id,salary FROM employees
WHERE NOT (salary >= 9000 AND salary <= 12000);
SELECT employee_id,salary FROM employees
WHERE salary <9000 OR salary > 12000;
SELECT employee_id,salary FROM employees
WHERE salary NOT BETWEEN 9000 AND 12000;
```

```mysql
SELECT employee_id, last_name, job_id, salary
FROM employees
WHERE salary >= 10000
OR job_id LIKE '%MAN%';
```

- 注意：
		OR可以和AND一起使用，但是在使用时要注意两者的优先级，由于**AND的优先级高于OR**，因此先对AND两边的操作数进行操作，再与OR中的操作数结合。

### 4 ．逻辑异或运算符 
逻辑异或（XOR）运算符是当给定的值中任意一个值为NULL时，则返回NULL；如果两个非NULL的值都是 0 或者都不等于 0 时，则返回 0 ；如果一个值为 0 ，另一个值不为 0 时，则返回 1 。


```mysql
mysql> SELECT 1 XOR -1, 1 XOR 0, 0 XOR 0, 1 XOR NULL, 1 XOR 1 XOR 1, 0 XOR 0 XOR 0;
+----------+---------+---------+------------+---------------+---------------+
| 1 XOR -1 | 1 XOR 0 | 0 XOR 0 | 1 XOR NULL | 1 XOR 1 XOR 1 | 0 XOR 0 XOR 0 |
+----------+---------+---------+------------+---------------+---------------+
| 0 | 1 | 0 | NULL | 1 | 0 |
+----------+---------+---------+------------+---------------+---------------+
1 row in set (0.00 sec)
```

```mysql
select last_name,department_id,salary
from employees
where department_id in (10,20) XOR salary > 8000;
```



## 4. 位运算符

位运算符是在二进制数上进行计算的运算符。位运算符会先将操作数变成二进制数，然后进行位运算， 最后将计算结果从二进制变回十进制数。

MySQL支持的位运算符如下：

![image-20220726122404302](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726122404302.png)




### 1 .按位与运算符 
按位与（&）运算符将给定值对应的二进制数逐位进行逻辑与运算。当给定值对应的二进制位的数值都为 1 时，则该位返回 1 ，否则返回 0 。

```mysql
mysql> SELECT 1 & 10, 20 & 30;
+--------+---------+
| 1 & 10 | 20 & 30 |
+--------+---------+
| 0 | 20 |
+--------+---------+
1 row in set (0.00 sec)
```

1 的二进制数为 0001 ， 10 的二进制数为 1010 ，所以 1 & 10 的结果为 0000 ，对应的十进制数为 0 。 20 的二进制数为 10100 ， 30 的二进制数为 11110 ，所以 20 & 30 的结果为 10100 ，对应的十进制数为 20 。

### 2. 按位或运算符 
按位或（|）运算符将给定的值对应的二进制数逐位进行逻辑或运算。当给定值对应的二进制位的数值有一个或两个为 1 时，则该位返回 1 ，否则返回 0 。

```mysql
mysql> SELECT 1 | 10, 20 | 30;
+--------+---------+
| 1 | 10 | 20 | 30 |
+--------+---------+
| 11 | 30 |
+--------+---------+
1 row in set (0.00 sec)
```

1 的二进制数为 0001 ， 10 的二进制数为 1010 ，所以 1 | 10 的结果为 1011 ，对应的十进制数为 11 。 20 的二进制数为 10100 ， 30 的二进制数为 11110 ，所以 20 | 30 的结果为 11110 ，对应的十进制数为 30 。

### 3. 按位异或运算符 
按位异或（^）运算符将给定的值对应的二进制数逐位进行逻辑异或运算。当给定值对应的二进制位的数值不同时，则该位返回 1 ，否则返回 0 。

```mysql
mysql> SELECT 1 ^ 10, 20 ^ 30;
+--------+---------+
| 1 ^ 10 | 20 ^ 30 |
+--------+---------+
| 11 | 10 |
+--------+---------+
1 row in set (0.00 sec)

```

1 的二进制数为 0001 ， 10 的二进制数为 1010 ，所以 1 ^ 10 的结果为 1011 ，对应的十进制数为 11 。 20 的二进制数为 10100 ， 30 的二进制数为 11110 ，所以 20 ^ 30 的结果为 01010 ，对应的十进制数为 10 。

再举例：

```mysql
mysql> SELECT 12 & 5, 12 | 5,12 ^ 5 FROM DUAL;
+--------+--------+--------+
| 12 & 5 | 12 | 5 | 12 ^ 5 |
+--------+--------+--------+
| 4 | 13 | 9 |
+--------+--------+--------+
1 row in set (0.00 sec)
```

![image-20220726122550485](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726122550485.png)


### 4. 按位取反运算符 
按位取反（~）运算符将给定的值的二进制数逐位进行取反操作，即将 1 变为 0 ，将 0 变为 1 。

```mysql
mysql> SELECT 10 & ~1;
+---------+
| 10 & ~1 |
+---------+
| 10 |
+---------+
1 row in set (0.00 sec)
```

由于按位取反（~）运算符的优先级高于按位与（&）运算符的优先级，所以 10 & ~ 1 ，首先，对数字 1 进行按位取反操作，结果除了最低位为 0 ，其他位都为 1 ，然后与 10 进行按位与操作，结果为 10 。

### 5. 按位右移运算符 
按位右移（>>）运算符将给定的值的二进制数的所有位右移指定的位数。右移指定的位数后，右边低位的数值被移出并丢弃，左边高位空出的位置用 0 补齐。

```mysql
mysql> SELECT 1 >> 2, 4 >> 2;
+--------+--------+
| 1 >> 2 | 4 >> 2 |
+--------+--------+
| 0 | 1 |
+--------+--------+
1 row in set (0.00 sec)
```


1 的二进制数为 0000 0001 ，右移 2 位为 0000 0000 ，对应的十进制数为 0 。 4 的二进制数为 0000 0100 ，右移 2位为 0000 0001 ，对应的十进制数为 1 。

### 6. 按位左移运算符 
按位左移（<<）运算符将给定的值的二进制数的所有位左移指定的位数。左移指定的位数后，左边高位的数值被移出并丢弃，右边低位空出的位置用 0 补齐。

```mysql
mysql> SELECT 1 << 2, 4 << 2;
+--------+--------+
| 1 << 2 | 4 << 2 |
+--------+--------+
| 4 | 16 |
+--------+--------+
1 row in set (0.00 sec)
```

1 的二进制数为 0000 0001 ，左移两位为 0000 0100 ，对应的十进制数为 4 。 4 的二进制数为 0000 0100 ，左移两位为 0001 0000 ，对应的十进制数为 16 。

## 5. 运算符的优先级

![image-20220726122732248](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726122732248.png)

数字编号越大，优先级越高，优先级高的运算符先进行计算。可以看到，赋值运算符的优先级最低，使用“()”括起来的表达式的优先级最高。



## 拓展：使用正则表达式查询
​	正则表达式通常被用来检索或替换那些符合某个模式的文本内容，根据指定的匹配模式匹配文本中符合 要求的特殊字符串。例如，从一个文本文件中提取电话号码，查找一篇文章中重复的单词或者替换用户输入的某些敏感词语等，这些地方都可以使用正则表达式。正则表达式强大而且灵活，可以应用于非常 复杂的查询。

​	MySQL中**使用REGEXP关键字**指定正则表达式的字符匹配模式。下表列出了REGEXP操作符中常用字符匹配列表。

![image-20220726122806299](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726122806299.png)

- 1. **查询以特定字符或字符串开头的记录** 字符‘^’匹配以特定字符或者字符串开头的文本。
在fruits表中，查询f_name字段以字母‘b’开头的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^b';
```

- 2. **查询以特定字符或字符串结尾的记录** 字符‘$’匹配以特定字符或者字符串结尾的文本。
在fruits表中，查询f_name字段以字母‘y’结尾的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'y$';
```


- 3. **用符号"."来替代字符串中的任意一个字符** 字符‘.’匹配任意一个字符。 在fruits表中，查询f_name字段值包含字母‘a’与‘g’且两个字母之间只有一个字母的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'a.g';
```

- 4. **使用"" 和 "+"来匹配多个字符** 星号‘’匹配前面的字符任意多次，包括 0 次。加号‘+’匹配前面的字符至少一次。
 在fruits表中，查询f_name字段值以字母‘b’开头且‘b’后面出现字母‘a’的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^ba*';
```
在fruits表中，查询f_name字段值以字母‘b’开头且‘b’后面出现字母‘a’至少一次的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^ba+';
```

- 5. **匹配指定字符串** 正则表达式可以匹配指定字符串，只要这个字符串在查询文本中即可，如要匹配多个字符串，多个字符串之间使用分隔符‘|’隔开。
      在fruits表中，查询f_name字段值包含字符串“on”的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'on';
```

在fruits表中，查询f_name字段值包含字符串“on”或者“ap”的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'on|ap';
```
 		之前介绍过，LIKE运算符也可以匹配指定的字符串，但与REGEXP不同，LIKE匹配的字符串如果在文本中间出现，则找不到它，相应的行也不会返回。REGEXP在文本内进行匹配，如果被匹配的字符串在文本中出现，REGEXP将会找到它，相应的行也会被返回。对比结果如下所示。

在fruits表中，使用LIKE运算符查询f_name字段值为“on”的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name like 'on';
Empty set(0.00 sec)
```


- 6. **匹配指定字符中的任意一个** 方括号“[]”指定一个字符集合，只匹配其中任何一个字符，即为所查找的文本。
 在fruits表中，查找f_name字段中包含字母‘o’或者‘t’的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '[ot]';
```
 在fruits表中，查询s_id字段中包含 4 、 5 或者 6 的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE s_id REGEXP '[456]';
```

- 7. **匹配指定字符以外的字符** “ [ ^ 字符集合  ] ”匹配不在指定集合中的任何字符。
在fruits表中，查询f_id字段中包含字母a~e和数字1~2以外字符的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_id REGEXP '[^a-e1-2]';
```
- 8. **使用{n,}或者{n,m}来指定字符串连续出现的次数** “字符串{n,}”表示至少匹配n次前面的字符；“字符串{n,m}”表示匹配前面的字符串不少于n次，不多于m次。例如，a{2,}表示字母a连续出现至少 2 次，也可以大于 2 次；a{2,4}表示字母a连续出现最少 2 次，最多不能超过 4 次。

在fruits表中，查询f_name字段值出现字母‘x’至少 2 次的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'x{2,}';
```
在fruits表中，查询f_name字段值出现字符串“ba”最少 1 次、最多 3 次的记录，SQL语句如下：
```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'ba{1,3}';
```






# 第 05 章_排序与分页

## 1. 排序数据
### 1. 1 排序规则
- 使用 ORDER BY 子句排序
  - **ASC（ascend）: 升序**
  - **DESC（descend）:降序**

- **ORDER BY 子句在SELECT语句的结尾**。

### 1. 2 单列排序

```mysql
SELECT last_name, job_id, department_id, hire_date
FROM employees
ORDER BY hire_date ;
```

![image-20220726131617963](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726131617963.png)

```mysql
SELECT last_name, job_id, department_id, hire_date
FROM employees
ORDER BY hire_date DESC ;
```

![image-20220726131630907](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726131630907.png)

```mysql
SELECT employee_id, last_name, salary* 12 annsal
FROM employees
ORDER BY annsal;
```

![image-20220726131643892](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726131643892.png)

### 1. 3 多列排序

```mysql
SELECT last_name, department_id, salary
FROM employees
ORDER BY department_id, salary DESC;
```

![image-20220726131743604](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726131743604.png)

- 可以使用不在SELECT列表中的列排序。

- 在对多列进行排序的时候，首先排序的第一列必须有相同的列值，才会对第二列进行排序。如果第一列数据中所有值都是唯一的，将不再对第二列进行排序。

## 2. 分页

### 2. 1 背景

背景 1 ：查询返回的记录太多了，查看起来很不方便，怎么样能够实现分页查询呢？

背景 2 ：表里有 4 条数据，我们只想要显示第 2 、 3 条数据怎么办呢？

### 2. 2 实现规则

- 分页原理

  所谓分页显示，就是将数据库中的结果集，一段一段显示出来需要的条件。

- **MySQL中使用 LIMIT 实现分页**

- 格式：

  ```mysql
  LIMIT [位置偏移量], 行数
  ```

- 第一个“位置偏移量”参数指示MySQL从哪一行开始显示，是一个可选参数，如果不指定“位置偏移量”，将会从表中的第一条记录开始（第一条记录的位置偏移量是 0 ，第二条记录的位置偏移量是1 ，以此类推）；第二个参数“行数”指示返回的记录条数。

- 举例

```mysql
--前10条记录：
SELECT * FROM 表名 LIMIT 0,10;
或者
SELECT * FROM 表名 LIMIT 10;
--第11至20条记录：
SELECT * FROM 表名 LIMIT 10,10;
--第21至30条记录：
SELECT * FROM 表名 LIMIT 20,10;
```

MySQL 8.0中可以使用“LIMIT 3 OFFSET 4”，意思是获取从第 5 条记录开始后面的 3 条记录，和“LIMIT4,3;”返回的结果相同。

- ==分页显式公式 ：**（当前页数- 1 ）*每页条数，每页条数**==

```mysql
SELECT * FROM table
LIMIT(PageNo - 1)*PageSize,PageSize;
```

- 注意：**LIMIT 子句必须放在整个SELECT语句的最后！**

- 使用 LIMIT 的好处

约束返回结果的数量可以**减少数据表的网络传输量**，也可以**提升查询效率**。

如果我们知道返回结果只有1 条，就可以使用**LIMIT 1**，告诉 SELECT 语句只需要返回一条记录即可。这样的好处就是 SELECT 不需要扫描完整的表，只需要检索到一条符合条件的记录即可返回。

### 2. 3 拓展

在不同的 DBMS 中使用的关键字可能不同。在 MySQL、PostgreSQL、MariaDB 和 SQLite 中使用 LIMIT 关键字，而且需要放到 SELECT 语句的最后面。

- 如果是 SQL Server 和 Access，需要使用==TOP==关键字，比如：

```mysql
SELECT TOP 5 name, hp_max FROM heros ORDER BY hp_max DESC
```

- 如果是 DB2，使用==FETCH FIRST 5 ROWS ONLY==这样的关键字：

```mysql
SELECT name, hp_max FROM heros ORDER BY hp_max DESC FETCH FIRST 5 ROWS ONLY
```

- 如果是 Oracle，你需要基于 ==ROWNUM== 来统计行数：

```mysql
SELECT rownum,last_name,salary FROM employees WHERE rownum < 5 ORDER BY salary DESC;
```

需要说明的是，这条语句是先取出来前 5 条数据行，然后再按照 hp_max 从高到低的顺序进行排序。但这样产生的结果和上述方法的并不一样。我会在后面讲到子查询，你可以使用

```mysql
SELECT rownum, last_name,salary
FROM (
SELECT last_name,salary
FROM employees
ORDER BY salary DESC)
WHERE rownum < 10;
```

得到与上述方法一致的结果。





------

# 第 06 章_多表查询

- 多表查询，也称为关联查询，指两个或更多个表一起完成查询操作。

- 前提条件：这些一起查询的表之间是有关系的（一对一、一对多），它们之间一定是有关联字段，这个关联字段可能建立了外键，也可能没有建立外键。比如：员工表和部门表，这两个表依靠“部门编号”进行关联。

## 1. 一个案例引发的多表连接

### 1. 1 案例说明

![image-20220726132803968](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726132803968.png)

从多个表中获取数据：

![image-20220726132821399](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726132821399.png)

```mysql
#案例：查询员工的姓名及其部门名称
SELECT last_name, department_name
FROM employees, departments;
```

![image-20220924152005976](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220924152005976.png)

查询结果：

```mysql
+-----------+----------------------+
| last_name | department_name |
+-----------+----------------------+
| King | Administration |
| King | Marketing |
| King | Purchasing |
| King | Human Resources |
| King | Shipping |
| King | IT |
| King | Public Relations |
| King | Sales |
| King | Executive |
| King | Finance |
| King | Accounting |
| King | Treasury |
...
| Gietz | IT Support |
| Gietz | NOC |
| Gietz | IT Helpdesk |
| Gietz | Government Sales |
| Gietz | Retail Sales |
| Gietz | Recruiting |
| Gietz | Payroll |
+-----------+----------------------+
2889 rows in set (0.01 sec)
```

分析错误情况：

```mysql
SELECT COUNT(employee_id) FROM employees;
#输出107行
SELECT COUNT(department_id)FROM departments;
#输出27行
SELECT 107*27 FROM dual;
```

我们把上述多表查询中出现的问题称为：**笛卡尔积的错误**。

### 1. 2 笛卡尔积（或交叉连接）的理解

笛卡尔乘积是一个数学运算。假设我有两个集合 X 和 Y，那么 X 和 Y 的笛卡尔积就是 X 和 Y 的所有可能组合，也就是第一个对象来自于 X，第二个对象来自于 Y 的所有可能。组合的个数即为两个集合中元素个数的乘积数。

![image-20220726133219961](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726133219961.png)

SQL 92 中，笛卡尔积也称为**交叉连接**，英文是 **CROSS JOIN**。在 SQL 99 中也是使用 CROSS JOIN表示交叉连接。它的作用就是可以把任意表进行连接，即使这两张表不相关。在MySQL中如下情况会出现笛卡尔积：

```mysql
#查询员工姓名和所在部门名称
SELECT last_name,department_name FROM employees,departments;
SELECT last_name,department_name FROM employees CROSS JOIN departments;
SELECT last_name,department_name FROM employees INNER JOIN departments;
SELECT last_name,department_name FROM employees JOIN departments;
```

### 1.3 案例分析与问题解决

- **笛卡尔积的错误会在下面条件下产生** ：
  - 省略多个表的连接条件（或关联条件）
  - 连接条件（或关联条件）无效
  - 所有表中的所有行互相连接

- 为了避免笛卡尔积， 可以 **在 WHERE 加入有效的连接条件**。

- 如果有n个表实现多表查询，则需要至少n-1个连接条件

- 加入连接条件后，查询语法：

```mysql
SELECT table1.column, table2.column
FROM table1, table2
WHERE table1.column1 = table2.column2; #连接条件
```

- **在 WHERE子句中写入连接条件**。

- 正确写法：

```mysql
#案例：查询员工的姓名及其部门名称
SELECT last_name, department_name
FROM employees, departments
WHERE employees.department_id = departments.department_id;
```

- **在表中有相同列时，在列名之前加上表名前缀。**

## 2. 多表查询分类讲解

#### **分类 1 ：等值连接 vs 非等值连接**

##### 等值连接

![image-20220726133651676](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726133651676.png)

```mysql
SELECT employees.employee_id, employees.last_name,
employees.department_id,departments.department_id,departments.location_id
FROM employees, departments
WHERE employees.department_id = departments.department_id;
```

![image-20220726133709091](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726133709091.png)

**拓展 1 ：多个连接条件与 AND 操作符**

![image-20220726133810504](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726133810504.png)

**拓展 2 ：区分重复的列名**

- **多个表中有相同列时，必须在列名之前加上表名前缀**。

- 在不同表中具有相同列名的列可以用**表名**加以区分。

```mysql
SELECT employees.last_name, departments.department_name,employees.department_id
FROM employees, departments
WHERE employees.department_id = departments.department_id;
```

**拓展 3 ：表的别名**

- 使用别名可以简化查询。

- 列名前使用表名前缀可以提高查询效率。

```mysql
SELECT e.employee_id, e.last_name, e.department_id,
d.department_id, d.location_id
FROM employees e , departments d
WHERE e.department_id = d.department_id;
```

- 需要注意的是，如果我们使用了表的别名，在查询字段中、过滤条件中就只能使用别名进行代替，不能使用原有的表名，否则就会报错。

**阿里开发规范：**

- 【强制】对于数据库中表记录的查询和变更，只要涉及多个表，都需要在列名前加表的别名（或表名）进行限定。

- 说明：对多表进行查询记录、更新记录、删除记录时，如果对操作列没有限定表的别名（或表名），并且操作列在多个表中存在时，就会抛异常。

- 正例：select t1.name from table_first as t1 , table_second as t2 where t1.id=t2.id;

- 反例：在某业务中，由于多表关联查询语句没有加表的别名（或表名）的限制，正常运行两年后，最近在 某个表中增加一个同名字段，在预发布环境做数据库变更后，线上查询语句出现出1052 异常：Column 'name' in field list is ambiguous。

**拓展 4 ：连接多个表**

![image-20220726134214604](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726134214604.png)

- **总结：连接 n个表,至少需要n- 1 个连接条件**。 比如，连接三个表，至少需要两个连接条件。

练习：查询出公司员工的 last_name,department_name, city



##### 非等值连接

![image-20220726134320051](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726134320051.png)

```mysql
SELECT e.last_name, e.salary, j.grade_level
FROM employees e, job_grades j
WHERE e.salary BETWEEN j.lowest_sal AND j.highest_sal;
```



#### **分类 2 ：自连接 vs 非自连接**

![image-20220726134625423](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726134625423.png)

- 当table1和table2本质上是同一张表，只是用取别名的方式虚拟成两张表以代表不同的意义。然后两个表再进行内连接，外连接等查询。

题目：查询employees表，返回“Xxx works for Xxx”

```mysql
SELECT CONCAT(worker.last_name ,' works for ', manager.last_name)
FROM employees worker, employees manager
WHERE worker.manager_id = manager.employee_id ;
```

![image-20220726134644592](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726134644592.png)

练习：查询出last_name为 ‘Chen’ 的员工的 manager 的信息。



#### **分类 3 ：内连接 vs 外连接**

除了查询满足条件的记录以外，外连接还可以查询某一方不满足条件的记录。

![image-20220726134745709](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726134745709.png)

- 内连接: 合并具有同一列的两个以上的表的行, **结果集中不包含一个表与另一个表不匹配的行**

- 外连接: 两个表在连接过程中除了返回满足连接条件的行以外 **还返回左（或右）表中不满足条件的行 ，这种连接称为左（或右） 外连接** 。没有匹配的行时, 结果表中相应的列为空(NULL)。

- 如果是左外连接，则连接条件中左边的表也称为==主表==，右边的表称为==从表==。

- 如果是右外连接，则连接条件中右边的表也称为==主表==，左边的表称为==从表==。

##### SQL 92 ：使用(+)创建连接

- 在 SQL92 中采用（+）代表从表所在的位置。即左或右外连接中，(+) 表示哪个是从表。

- Oracle 对 SQL92 支持较好，而 MySQL 则不支持 SQL92 的外连接。

```mysql
#左外连接
SELECT last_name,department_name
FROM employees ,departments
WHERE employees.department_id = departments.department_id(+);
#右外连接
SELECT last_name,department_name
FROM employees ,departments
WHERE employees.department_id(+) = departments.department_id;
```

- 而且在 SQL92 中，只有左外连接和右外连接，没有满（或全）外连接。



## 3. SQL 99 语法实现多表查询

### 3. 1 基本语法

- 使用JOIN...ON子句创建连接的语法结构：

```mysql
SELECT table1.column, table2.column,table3.column
FROM table1
JOIN table2 ON table1 和 table2 的连接条件
JOIN table3 ON table2 和 table3 的连接条件
```

- 它的嵌套逻辑类似我们使用的 FOR 循环：

```mysql
for t1 in table1:
for t2 in table2:
if condition1:
for t3 in table3:
if condition2:
output t1 + t2 + t3
```

SQL 99 采用的这种嵌套结构非常清爽、层次性更强、可读性更强，即使再多的表进行连接也都清晰可见。如果你采用 SQL 92 ，可读性就会大打折扣。

- 语法说明：
  - **可以使用 ON 子句指定额外的连接条件** 。
  - 这个连接条件是与其它条件分开的。
  - **ON 子句使语句具有更高的易读性** 。
  - 关键字 JOIN、INNER JOIN、CROSS JOIN 的含义是一样的，都表示内连接



### 3. 2 内连接(INNER JOIN)的实现

- 语法：

```mysql
SELECT 字段列表
FROM A表 INNER JOIN B表
ON 关联条件
WHERE 等其他子句;
```



题目 1 ：

```mysql
SELECT e.employee_id, e.last_name, e.department_id,d.department_id, d.location_id
FROM employees e JOIN departments d
ON (e.department_id = d.department_id);
```

![image-20220726135351096](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726135351096.png)



题目 2 ：

```mysql
SELECT employee_id, city, department_name
FROM employees e
JOIN departments d
ON d.department_id = e.department_id
JOIN locations l
ON d.location_id = l.location_id;
```

![image-20220726135425041](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726135425041.png)

### 3. 3 外连接(OUTER JOIN)的实现

#### 3. 3. 1 左外连接(LEFT OUTER JOIN)

- 语法：

```mysql
#实现查询结果是A
SELECT 字段列表
FROM A表 LEFT JOIN B表
ON 关联条件
WHERE 等其他子句;
```

- 举例：

```mysql
SELECT e.last_name, e.department_id, d.department_name
FROM employees e
LEFT OUTER JOIN departments d
ON (e.department_id = d.department_id) ;
```

![image-20220726135708121](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726135708121.png)

#### 3. 3. 2 右外连接(RIGHT OUTER JOIN)

- 语法：

```mysql
#实现查询结果是B
SELECT 字段列表
FROM A表 RIGHT JOIN B表
ON 关联条件
WHERE 等其他子句;
```

- 举例：

```mysql
SELECT e.last_name, e.department_id, d.department_name
FROM employees e
RIGHT OUTER JOIN departments d
ON (e.department_id = d.department_id) ;
```

![image-20220726135730366](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726135730366.png)

- 需要注意的是，LEFT JOIN 和 RIGHT JOIN 只存在于 SQL 99 及以后的标准中，在 SQL 92 中不存在，只能用 (+) 表示。

#### 3. 3. 3 满外连接(FULL OUTER JOIN)

- 满外连接的结果 = 左右表匹配的数据 + 左表没有匹配到的数据 + 右表没有匹配到的数据。

- SQL 99 是支持满外连接的。使用FULL JOIN 或 FULL OUTER JOIN来实现。

- 需要注意的是，MySQL不支持FULL JOIN，但是可以用 LEFT JOIN UNION RIGHT JOIN代替。

## 4. UNION的使用

**合并查询结果** 利用UNION关键字，可以给出多条SELECT语句，并将它们的结果组合成单个结果集。合并时，两个表对应的列数和数据类型必须相同，并且相互对应。各个SELECT语句之间使用UNION或UNIONALL关键字分隔。

语法格式：

```mysql
SELECT column,... FROM table1
UNION [ALL]
SELECT column,... FROM table2
```

##### UNION操作符

![image-20220726140051634](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726140051634.png)



**UNION 操作符返回两个查询的结果集的并集，去除重复记录。**

##### UNION ALL操作符

![image-20220726140145630](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726140145630.png)



**UNION ALL操作符返回两个查询的结果集的并集。对于两个结果集的重复部分，不去重。**

- 注意：执行UNION ALL语句时所需要的资源比UNION语句少。如果明确知道合并数据后的结果数据不存在重复数据，或者不需要去除重复的数据，则尽量使用UNION ALL语句，以提高数据查询的效率。

- 举例：查询部门编号> 90 或邮箱包含a的员工信息

```mysql
#方式1
SELECT * FROM employees WHERE email LIKE '%a%' OR department_id>90;
```

```mysql
#方式2
SELECT * FROM employees WHERE email LIKE '%a%'
UNION
SELECT * FROM employees WHERE department_id>90;
```



- 举例：查询中国用户中男性的信息以及美国用户中年男性的用户信息

```mysql
SELECT id,cname FROM t_chinamale WHERE csex='男'
UNION ALL
SELECT id,tname FROM t_usmale WHERE tGender='male';
```



## 5. ==7 种SQL JOINS的实现==

![image-20220726141859178](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726141859178.png)

### 5. 1 代码实现

```mysql
#中图：内连接 A∩B
SELECT employee_id,last_name,department_name
FROM employees e JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```mysql
#左上图：左外连接
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```mysql
#右上图：右外连接
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```mysql
#左中图：A - A∩B
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE d.`department_id` IS NULL
```

```mysql
#右中图：B-A∩B
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE e.`department_id` IS NULL
```

```mysql
#左下图：满外连接
# 左中图 + 右上图 A∪B
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE d.`department_id` IS NULL
UNION ALL #没有去重操作，效率高
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```mysql
#右下图
#左中图 + 右中图 A ∪B- A∩B 或者 (A - A∩B) ∪ （B - A∩B）
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE d.`department_id` IS NULL
UNION ALL
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE e.`department_id` IS NULL
```



### 5. 2 语法格式小结

- 左中图

```mysql
#实现A - A∩B
select 字段列表
from A表 left join B表
on 关联条件
where 从表关联字段 is null and 等其他子句;
```

- 右中图

```mysql
#实现B - A∩B
select 字段列表
from A表 right join B表
on 关联条件
where 从表关联字段 is null and 等其他子句;
```

- 左下图

```mysql
#实现查询结果是A∪B
#用左外的A，union 右外的B
select 字段列表
from A表 left join B表
on 关联条件
where 等其他子句
union
select 字段列表
from A表 right join B表
on 关联条件
where 等其他子句;
```

- 右下图

```mysql
#实现A∪B - A∩B 或 (A - A∩B) ∪ （B - A∩B）
#使用左外的 (A - A∩B) union 右外的（B - A∩B）
select 字段列表
from A表 left join B表
on 关联条件
where 从表关联字段 is null and 等其他子句
union
select 字段列表
from A表 right join B表
on 关联条件
where 从表关联字段 is null and 等其他子句
```



## 6. SQL 99 语法新特性

### 6. 1 自然连接

SQL 99 在 SQL 92 的基础上提供了一些特殊语法，比如 **NATURAL JOIN** 用来表示自然连接。我们可以把自然连接理解为 SQL 92 中的等值连接。它会帮你自动查询两张连接表中**所有相同的字段**，然后进行**等值连接**。

在SQL 92 标准中：

```mysql
SELECT employee_id,last_name,department_name
FROM employees e JOIN departments d
ON e.`department_id` = d.`department_id`
AND e.`manager_id` = d.`manager_id`;
```

在 SQL 99 中你可以写成：

```mysql
SELECT employee_id,last_name,department_name
FROM employees e NATURAL JOIN departments d;
```

### 6. 2 USING连接

当我们进行连接的时候，SQL 99 还支持使用 USING 指定数据表里的**同名字段**进行等值连接。但是只能配合JOIN一起使用。比如：

```mysql
SELECT employee_id,last_name,department_name
FROM employees e JOIN departments d
USING (department_id);
```

你能看出与自然连接 NATURAL JOIN 不同的是，USING 指定了具体的相同的字段名称，你需要在 USING的括号 () 中填入要指定的同名字段。同时使用 **JOIN...USING** 可以简化 JOIN ON 的等值连接。它与下面的 SQL 查询结果是相同的：

```mysql
SELECT employee_id,last_name,department_name
FROM employees e ,departments d
WHERE e.department_id = d.department_id;
```

## 7. 章节小结

表连接的约束条件可以有三种方式：WHERE, ON, USING

- WHERE：适用于所有关联查询

- **ON**：只能和JOIN一起使用，只能写关联条件。虽然关联条件可以并到WHERE中和其他条件一起写，但分开写可读性更好。

- USING：只能和JOIN一起使用，而且要求 **两个** 关联字段在关联表中名称一致，而且只能表示关联字段值相等

```mysql
#关联条件
#把关联条件写在where后面
SELECT last_name,department_name
FROM employees,departments
WHERE employees.department_id = departments.department_id;
#把关联条件写在on后面，只能和JOIN一起使用
SELECT last_name,department_name
FROM employees INNER JOIN departments
ON employees.department_id = departments.department_id;
SELECT last_name,department_name
FROM employees CROSS JOIN departments
ON employees.department_id = departments.department_id;
SELECT last_name,department_name
FROM employees JOIN departments
ON employees.department_id = departments.department_id;
#把关联字段写在using()中，只能和JOIN一起使用
#而且两个表中的关联字段必须名称相同，而且只能表示=
#查询员工姓名与基本工资
SELECT last_name,job_title
FROM employees INNER JOIN jobs USING(job_id);
#n张表关联，需要n-1个关联条件
#查询员工姓名，基本工资，部门名称
SELECT last_name,job_title,department_name FROM employees,departments,jobs
WHERE employees.department_id = departments.department_id
AND employees.job_id = jobs.job_id;
SELECT last_name,job_title,department_name
FROM employees INNER JOIN departments INNER JOIN jobs
ON employees.department_id = departments.department_id
AND employees.job_id = jobs.job_id;
```

- 注意：

​	我们要**控制连接表的数量**。多表连接就相当于嵌套 for 循环一样，非常消耗资源，会让 SQL 查询性能下降得很严重，因此不要连接不必要的表。在许多 DBMS 中，也都会有最大连接表的限制。

- 【强制】超过三个表禁止 join。需要 join 的字段，数据类型保持绝对一致；多表关联查询时， 保证被关联的字段需要有索引。

- 说明：即使双表 join 也要注意表索引、SQL 性能。

- 来源：阿里巴巴《Java开发手册》



## 附录：常用的 SQL 标准有哪些

在正式开始讲连接表的种类时，我们首先需要知道 SQL 存在不同版本的标准规范，因为不同规范下的表连接操作是有区别的。

SQL 有两个主要的标准，分别是 **SQL92** 和 **SQL99**。 92 和 99 代表了标准提出的时间，SQL92 就是 92 年提出的标准规范。当然除了 SQL92 和 SQL99 以外，还存在 SQL-86、SQL-89、SQL:2003、SQL:2008、SQL:2011 和 SQL:2016 等其他的标准。

这么多标准，到底该学习哪个呢？ **实际上最重要的 SQL 标准就是 SQL 92 和 SQL 99** 。一般来说 SQL92 的形式更简单，但是写的 SQL 语句会比较长，可读性较差。而 SQL99 相比于 SQL92 来说，语法更加复杂，但可读性更强。我们从这两个标准发布的页数也能看出，SQL92 的标准有 500 页，而 SQL99 标准超过了1000 页。实际上从 SQL99 之后，很少有人能掌握所有内容，因为确实太多了。就好比我们使用Windows、Linux 和 Office 的时候，很少有人能掌握全部内容一样。我们只需要掌握一些核心的功能，满足日常工作的需求即可。

**SQL 92 和 SQL 99 是经典的 SQL 标准，也分别叫做 SQL- 2 和 SQL- 3 标准**。 也正是在这两个标准发布之后，SQL 影响力越来越大，甚至超越了数据库领域。现如今 SQL 已经不仅仅是数据库领域的主流语言，还是信息领域中信息处理的主流语言。在图形检索、图像检索以及语音检索中都能看到 SQL 语言的使用。



------

# 第 07 章_单行函数

## 1. 函数的理解

### 1. 1 什么是函数

函数在计算机语言的使用中贯穿始终，函数的作用是什么呢？它可以把我们经常使用的代码封装起来， 需要的时候直接调用即可。这样既 **提高了代码效率** ，又 **提高了可维护性** 。在 SQL 中我们也可以使用函数 对检索出来的数据进行函数操作。使用这些函数，可以极大地 **提高用户对数据库的管理效率** 。

![image-20220726144417314](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726144417314.png)

从函数定义的角度出发，我们可以将函数分成 **内置函数** 和 **自定义函数** 。在 SQL 语言中，同样也包括了 内置函数和自定义函数。内置函数是系统内置的通用函数，而自定义函数是我们根据自己的需要编写 的，本章及下一章讲解的是 SQL 的内置函数。

### 1. 2 不同DBMS函数的差异

我们在使用 SQL 语言的时候，不是直接和这门语言打交道，而是通过它使用不同的数据库软件，即DBMS。**DBMS 之间的差异性很大，远大于同一个语言不同版本之间的差异**。实际上，只有很少的函数是被 DBMS 同时支持的。比如，大多数 DBMS 使用（||）或者（+）来做拼接符，而在 MySQL 中的字符串拼接函数concat()。大部分 DBMS 会有自己特定的函数，这就意味着**采用 SQL 函数的代码可移植性是很差的**，因此在使用函数的时候需要特别注意。

### 1. 3 MySQL的内置函数及分类

MySQL提供了丰富的内置函数，这些函数使得数据的维护与管理更加方便，能够更好地提供数据的分析与统计功能，在一定程度上提高了开发人员进行数据分析与统计的效率。

MySQL提供的内置函数从 **实现的功能角度** 可以分为数值函数、字符串函数、日期和时间函数、流程控制函数、加密与解密函数、获取MySQL信息函数、聚合函数等。这里，我将这些丰富的内置函数再分为两类： **单行函数 、 聚合函数（或分组函数）** 。

**两种SQL函数**

![image-20220726144749320](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726144749320.png)

**单行函数**

- 操作数据对象 
- 接受参数返回一个结果 
- **只对一行进行变换** 
- **每行返回一个结果** 
- 可以嵌套 
- 参数可以是一列或一个值

## 2. ==数值函数==

### 2. 1 基本函数

![image-20220726145001208](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145001208.png)

举例：

![image-20220726145106189](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145106189.png)

### 2. 2 角度与弧度互换函数

![image-20220726145139428](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145139428.png)

### 2. 3 三角函数

![image-20220726145154463](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145154463.png)

举例：

![image-20220726145259977](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145259977.png)

### 2. 4 指数与对数

![image-20220726145320958](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145320958.png)

### 2. 5 进制间的转换

![image-20220726145337423](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145337423.png)

## 3. ==字符串函数==

<img src="https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145536426.png" alt="image-20220726145536426" style="zoom:120%;" />

![image-20220726145553599](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145553599.png)

- 注意：MySQL中，字符串的位置是从 1 开始的。

举例：

![image-20220726145642184](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145642184.png)

## 4. ==日期和时间函数==

### 4. 1 ==获取日期、时间==

![image-20220726145709323](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145709323.png)

举例：

![image-20220726145725254](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145725254.png)

### 4. 2 日期与==时间戳==的转换

![image-20220726145836635](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145836635.png)

举例：

![image-20220726145857493](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145857493.png)

![image-20220726145949258](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726145949258.png)

### 4. 3 获取月份、星期、星期数、天数等函数

![image-20220726150006951](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150006951.png)

举例：

![image-20220726150054558](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150054558.png)

### 4. 4 日期的操作函数

![image-20220726150137896](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150137896.png)

### 4. 5 ==时间==和秒钟转换的函数

![image-20220726150224834](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150224834.png)

举例：

![image-20220726150235748](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150235748.png)

### 4. 6 ==计算日期和时间的函数==

**第 1 组：**

![image-20220726150305428](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150305428.png)

上述函数中type的取值：

![image-20220726150319490](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150319490.png)

举例：

![image-20220726150422503](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150422503.png)

**第 2 组：**

![image-20220726150438397](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150438397.png)

举例：

![image-20220726150523646](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150523646.png)

![image-20220726150549109](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150549109.png)

![image-20220726150658219](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150658219.png)


举例：查询 7 天内的新增用户数有多少？

```mysql
SELECT COUNT(*) as num FROM new_user 
WHERE TO_DAYS(NOW())-TO_DAYS(regist_time)<=7
```


### 4. 7 ==日期的格式化与解析==

![image-20220726150811539](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150811539.png)

上述**非GET_FORMAT**函数中fmt参数常用的格式符：

![image-20220726150942799](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726150942799.png)

GET_FORMAT函数中date_type和format_type参数取值如下：

![image-20220726151100435](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151100435.png)

举例：

![image-20220726151131427](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151131427.png)

## 5. ==流程控制函数==

流程处理函数可以根据不同的条件，执行不同的处理流程，可以在SQL语句中实现不同的条件选择。

MySQL中的流程处理函数主要包括**IF()、IFNULL()和CASE()函数**。

![image-20220726151216815](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151216815.png)

![image-20220726151345769](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151345769.png)

![image-20220726151410968](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151410968.png)

练习：查询部门号为 10 , 20 , 30 的员工信息, 若部门号为 10 , 则打印其工资的 1. 1 倍, 20 号部门, 则打印其工资的 1. 2 倍, 30 号部门打印其工资的 1. 3 倍,其他部门，则打印其工资的1.4倍。

```sql
SELECT employee_id,last_name,department_id,salary,
       CASE department_id
            WHEN 10 THEN salary * 1.1
            WHEN 20 THEN salary*1.2
            WHEN 30 THEN salary*1.3
            END "details"
FROM employees
WHERE department_id IN (10,20,30);
```

## 6. 加密与解密函数

加密与解密函数主要用于对数据库中的数据进行加密和解密处理，以防止数据被他人窃取。这些函数在保证数据库安全时非常有用。

![image-20220726151524317](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151524317.png)

可以看到，ENCODE(value,password_seed)函数与DECODE(value,password_seed)函数互为反函数。

举例：

![image-20220726151610579](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151610579.png)

## 7. MySQL信息函数

MySQL中内置了一些可以查询MySQL信息的函数，这些函数主要用于帮助数据库开发或运维人员更好地对数据库进行维护工作。

![image-20220726151651920](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151651920.png)

举例：

![image-20220726151807098](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151807098.png)

## 8. 其他函数

MySQL中有些函数无法对其进行具体的分类，但是这些函数在MySQL的开发和运维过程中也是不容忽视的。

![image-20220726151837846](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151837846.png)

举例：

![image-20220726151930924](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151930924.png)

![image-20220726151943295](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726151943295.png)



------

# 第 08 章_聚合函数

我们上一章讲到了 SQL 单行函数。实际上 SQL 函数还有一类，叫做聚合（或聚集、分组）函数，它是对一组数据进行汇总的函数，输入的是一组数据的集合，输出的是单个值。

## 1. 聚合函数介绍

- 什么是聚合函数

聚合函数作用于一组数据，并对一组数据返回一个值。

![image-20220726152240692](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726152240692.png)

- **聚合函数类型**
  - **AVG()** 
  - **SUM()** 
  - **MAX()** 
  - **MIN()** 
  - **COUNT()**

- 聚合函数语法

![image-20220726152439259](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726152439259.png)

- 聚合函数不能嵌套调用。比如不能出现类似“AVG(SUM(字段名称))”形式的调用。

### 1. 1 AVG和SUM函数

可以对 **数值型数据** 使用AVG 和 SUM 函数。

![image-20220726152930902](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726152930902.png)

### 1. 2 MIN和MAX函数

可以对 **任意数据类型** 的数据使用 MIN 和 MAX 函数。

![image-20220726152950864](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726152950864.png)

### 1. 3 COUNT函数

- **COUNT(*)**返回表中记录总数，适用于 **任意数据类型** 。

![image-20220726153020048](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153020048.png)

- COUNT(expr) 返回expr不为空的记录总数。

![image-20220726153043306](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153043306.png)

- **问题：用count(*)，count(1)，count(列名)谁好呢?**

​	其实，对于MyISAM引擎的表是没有区别的。这种引擎内部有一计数器在维护着行数。 Innodb引擎的表用count(*),count(1)直接读行数，复杂度是O(n)，因为innodb真的要去数一遍。但好 于具体的count(列名)。

- **问题：能不能使用count(列名)替换count(*)?**

​	不要使用 count(列名)来替代 **count(  *  ) ， count(  *  )** 是 SQL92 定义的标准统计行数的语法，跟数据库无关，跟 NULL 和非 NULL 无关。

​	 说明：**count(*)会统计值为 NULL 的行，而 count(列名)不会统计此列为 NULL 值的行**。

## 2. GROUP BY

### 2. 1 基本使用

![image-20220726153213055](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153213055.png)

- **可以使用GROUP BY子句将表中的数据分成若干组**

```mysql
SELECT column, group_function(column)
FROM table
[WHERE condition]
[GROUP BY group_by_expression]
[ORDER BY column];
```

**明确：WHERE一定放在FROM后面**

- **在SELECT列表中所有未包含在组函数中的列都应该包含在 GROUP BY子句中**
- SELECT中出现的非组函数的字段必须声明在GROUP BY中,GROUP BY中声明的字段可以不出现在SELECT 中
- GROUP BY声明在FROM后面、WHERE后面，ORDER BY前面、LIMIT前面

```mysql
SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id ;
```

![image-20220726153418234](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153418234.png)

包含在 GROUP BY 子句中的列不必包含在SELECT 列表中

```mysql
SELECT AVG(salary)
FROM employees
GROUP BY department_id ;
```

![image-20220726153454793](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153454793.png)

### 2. 2 使用多个列分组

![image-20220726153511516](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153511516.png)

```mysql
SELECT department_id dept_id, job_id, SUM(salary)
FROM employees
GROUP BY department_id, job_id ;
```

![image-20220726153540105](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153540105.png)

### 2. 3 GROUP BY中使用WITH ROLLUP

使用**WITH ROLLUP**关键字之后，在所有查询出的分组记录之后增加一条记录，该记录计算查询出的**所有记录的总和**，即统计记录数量。

```mysql
SELECT department_id,AVG(salary)
FROM employees
WHERE department_id > 80
GROUP BY department_id WITH ROLLUP;
```

- 注意：当使用ROLLUP时，不能同时使用ORDER BY子句进行结果排序，即ROLLUP和ORDER BY是互相排斥的。

## 3. HAVING

### 3. 1 基本使用

![image-20220726153651019](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153651019.png)

**过滤分组：HAVING子句**

1. 行已经被分组。

2. 使用了聚合函数。

3. 满足HAVING 子句中条件的分组将被显示。

4. HAVING 不能单独使用，必须要跟 GROUP BY 一起使用。

![image-20220726153953173](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726153953173.png)

```mysql
SELECT department_id, MAX(salary)
FROM employees
GROUP BY department_id
HAVING MAX(salary)>10000 ;
```

![image-20220726154002125](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726154002125.png)

- **非法使用聚合函数 ： 不能在 WHERE 子句中使用聚合函数**。 如下：

```mysql
SELECT department_id, AVG(salary)
FROM employees
WHERE AVG(salary) > 8000
GROUP BY department_id;
```

![image-20220726154047319](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726154047319.png)

### 3. 2 WHERE和HAVING的对比

**区别 1 ：WHERE 可以直接使用表中的字段作为筛选条件，但不能使用分组中的计算函数作为筛选条件；HAVING 必须要与 GROUP BY 配合使用，可以把分组计算的函数和分组字段作为筛选条件。**

这决定了，在需要对数据进行分组统计的时候，HAVING 可以完成 WHERE 不能完成的任务。这是因为，在查询语法结构中，WHERE 在 GROUP BY 之前，所以无法对分组结果进行筛选。HAVING 在 GROUP BY 之后，可以使用分组字段和分组中的计算函数，对分组的结果集进行筛选，这个功能是 WHERE 无法完成的。另外，WHERE排除的记录不再包括在分组中。

**区别 2 ：如果需要通过连接从关联表中获取需要的数据，WHERE 是先筛选后连接，而 HAVING 是先连接后筛选。**

 这一点，就决定了在关联查询中，**WHERE 比 HAVING 更高效**。因为 WHERE 可以先筛选，用一个筛选后的较小数据集和关联表进行连接，这样占用的资源比较少，执行效率也比较高。HAVING 则需要先把结果集准备好，也就是用未被筛选的数据集进行关联，然后对这个大的数据集进行筛选，这样占用的资源就比较多，执行效率也较低。

**小结如下：**

![image-20220726154307539](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726154307539.png)

**开发中的选择：**

WHERE 和 HAVING 也不是互相排斥的，我们可以在一个查询里面同时使用 WHERE 和 HAVING。包含分组 统计函数的条件用 HAVING，普通条件用 WHERE。这样，我们就既利用了 WHERE 条件的高效快速，又发 挥了 HAVING 可以使用包含分组统计函数的查询条件的优点。当数据量特别大的时候，运行效率会有很 大的差别。

## 4. SELECT的执行过程

### 4. 1 查询的结构

```mysql
#方式 1 ：
SELECT ...,....,...
FROM ...,...,....
WHERE 多表的连接条件
AND 不包含组函数的过滤条件
GROUP BY ...,...
HAVING 包含组函数的过滤条件
ORDER BY ... ASC/DESC
LIMIT ...,...

#方式 2 ：
SELECT ...,....,...
FROM ... JOIN ...
ON 多表的连接条件
JOIN ...
ON ...
WHERE 不包含组函数的过滤条件
AND/OR 不包含组函数的过滤条件
GROUP BY ...,...
HAVING 包含组函数的过滤条件
ORDER BY ... ASC/DESC
LIMIT ...,...
#其中：
#（ 1 ）from：从哪些表中筛选
#（ 2 ）on：关联多表查询时，去除笛卡尔积
#（ 3 ）where：从表中筛选的条件
#（ 4 ）group by：分组依据
#（ 5 ）having：在统计结果中再次筛选
#（ 6 ）order by：排序
#（ 7 ）limit：分页
```

![image-20220928205423761](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220928205423761.png)

### 4. 2 SELECT执行顺序

你需要记住 SELECT 查询时的两个顺序：

**1. 关键字的顺序是不能颠倒的：**

```mysql
SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ... LIMIT...
```

**2 .SELECT 语句的执行顺序** （在 MySQL 和 Oracle 中，SELECT 执行顺序基本相同）：

```mysql
FROM -> WHERE -> GROUP BY -> HAVING -> SELECT 的字段 -> DISTINCT -> ORDER BY -> LIMIT
```

![image-20220726154643799](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20220726154643799.png)

比如你写了一个 SQL 语句，那么它的关键字顺序和执行顺序是下面这样的：

```mysql
SELECT DISTINCT player_id, player_name, count(*) as num # 顺序 5
FROM player JOIN team ON player.team_id = team.team_id # 顺序 1
WHERE height > 1.80 # 顺序 2
GROUP BY player.team_id # 顺序 3
HAVING num > 2 # 顺序 4
ORDER BY num DESC # 顺序 6
LIMIT 2 # 顺序 7
```

在 SELECT 语句执行这些步骤的时候，每个步骤都会产生一个**虚拟表**，然后将这个虚拟表传入下一个步骤中作为输入。需要注意的是，这些步骤隐含在 SQL 的执行过程中，对于我们来说是不可见的。

### 4. 3 SQL 的执行原理

SELECT 是先执行 FROM 这一步的。在这个阶段，如果是多张表联查，还会经历下面的几个步骤：

1. 首先先通过 CROSS JOIN 求笛卡尔积，相当于得到虚拟表 vt（virtual table）1-1；
2. 通过 ON 进行筛选，在虚拟表 vt1-1 的基础上进行筛选，得到虚拟表 vt1-2；
3. 添加外部行。如果我们使用的是左连接、右链接或者全连接，就会涉及到外部行，也就是在虚拟
表 vt1-2 的基础上增加外部行，得到虚拟表 vt1-3。

当然如果我们操作的是两张以上的表，还会重复上面的步骤，直到所有表都被处理完为止。这个过程得到是我们的原始数据。

当我们拿到了查询数据表的原始数据，也就是最终的虚拟表 **vt1**，就可以在此基础上再进行 **WHERE 阶段**。在这个阶段中，会根据 vt1 表的结果进行筛选过滤，得到虚拟表 **vt2**。

然后进入第三步和第四步，也就是 **GROUP 和 HAVING 阶段**。在这个阶段中，实际上是在虚拟表 vt2 的基础上进行分组和分组过滤，得到中间的虚拟表 **vt3** 和 **vt4**。

当我们完成了条件筛选部分之后，就可以筛选表中提取的字段，也就是进入到 **SELECT** 和 **DISTINCT**阶段。

首先在 SELECT 阶段会提取想要的字段，然后在 DISTINCT 阶段过滤掉重复的行，分别得到中间的虚拟表**vt5- 1** 和 **vt5- 2** 。

当我们提取了想要的字段数据之后，就可以按照指定的字段进行排序，也就是 **ORDER BY 阶段**，得到虚拟表 **vt6**。

最后在 vt6 的基础上，取出指定行的记录，也就是 **LIMIT 阶段**，得到最终的结果，对应的是虚拟表**vt7**。

当然我们在写 SELECT 语句的时候，不一定存在所有的关键字，相应的阶段就会省略。

同时因为 SQL 是一门类似英语的结构化查询语言，所以我们在写 SELECT 语句的时候，还要注意相应的关键字顺序， **所谓底层运行的原理，就是我们刚才讲到的执行顺序。**



------

# 第 09 章_子查询

子查询指一个查询语句嵌套在另一个查询语句内部的查询，这个特性从MySQL 4. 1 开始引入。

SQL 中子查询的使用大大增强了 SELECT 查询的能力，因为很多时候查询需要从结果集中获取数据，或者需要从同一个表中先计算得出一个数据结果，然后与这个数据结果（可能是某个标量，也可能是某个集合）进行比较。

## 1. 需求分析与问题解决

### 1.1实际问题

![image-20221001171359572](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001171359572.png)

现有解决方式：

方式一：

```sql
SELECT salary
FROM employees
WHERE last_name = 'Abel';

SELECT last_name,salary
FROM employees
WHERE salary > 11000 ;
```

方式二：自连接

```sql
SELECT e2.last_name,e2.salary
FROM employees e1,employees e
WHERE e1.last_name = 'Abel'
AND e1.`salary` < e2.`salary`
```

方式三：子查询

```sql
SELECT last_name,salary
FROM employees
WHERE salary > (
    SELECT salary
    FROM employees
    WHERE last_name = 'Abel'
    );
```

![image-20221001171519669](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001171519669.png)

### 1. 2 子查询的基本使用

子查询的基本语法结构：

![image-20221001171536033](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001171536033.png)

- 子查询（内查询）在主查询之前一次执行完成。

- 子查询的结果被主查询（外查询）使用 。

- **注意事项**
  - 子查询要包含在括号内
  - 将子查询放在比较条件的右侧
  - 单行操作符对应单行子查询，多行操作符对应多行子查询

### 1. 3 子查询的分类

**分类方式 1 ：**

我们按内查询的结果返回一条还是多条记录，将子查询分为**单行子查询**、**多行子查询**。

- 单行子查询

![image-20221001171708854](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001171708854.png)

- 多行子查询

![image-20221001171725848](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001171725848.png)

**分类方式 2 ：**

我们按内查询是否被执行多次，将子查询划分为**相关(或关联)子查询**和**不相关(或非关联)子查询**。

子查询从数据表中查询了数据结果，如果这个数据结果只执行一次，然后这个数据结果作为主查询的条件进行执行，那么这样的子查询叫做不相关子查询。

同样，如果子查询需要执行多次，即采用循环的方式，先从外部查询开始，每次都传入子查询进行查询，然后再将结果反馈给外部，这种嵌套的执行方式就称为相关子查询。

## 2. 单行子查询

### 2. 1 单行比较操作符

![image-20221001171951141](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001171951141.png)

### 2. 2 代码示例

题目：查询工资大于 149 号员工工资的员工的信息

![image-20221001172041763](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172041763.png)

题目：返回job_id与 141 号员工相同，salary比 143 号员工多的员工姓名，job_id和工资

![image-20221001172102795](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172102795.png)

题目：返回公司工资最少的员工的last_name,job_id和salary

![image-20221001172121254](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172121254.png)

题目：查询与 141 号或 174 号员工的manager_id和department_id相同的其他员工的employee_id，manager_id，department_id

实现方式 1 ：不成对比较

![image-20221001172210873](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172210873.png)

实现方式 2 ：成对比较

![image-20221001172221900](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172221900.png)

### 2. 3 HAVING 中的子查询

- 首先执行子查询。

- 向主查询中的HAVING 子句返回结果。

题目：查询最低工资大于 50 号部门最低工资的部门id和其最低工资

![image-20221001172306852](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172306852.png)

### 2. 4 CASE中的子查询

在CASE表达式中使用单列子查询：

题目：显式员工的employee_id,last_name和location。其中，若员工department_id与location_id为 1800的department_id相同，则location为’Canada’，其余则为’USA’。

![image-20221001172331356](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172331356.png)

### 2. 5 子查询中的空值问题

![image-20221001172348734](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172348734.png)

- 子查询不返回任何行

### 2. 5 非法使用子查询

![image-20221001172428198](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172428198.png)

![image-20221001172438007](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172438007.png)

- 多行子查询使用单行比较符

## 3. 多行子查询

- 也称为集合比较子查询

- 内查询返回多行

- 使用多行比较操作符

### 3. 1 多行比较操作符

![image-20221001172630568](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172630568.png)

- 体会 ANY 和 ALL 的区别

### 3. 2 代码示例

题目：返回其它job_id中比job_id为‘IT_PROG’部门任一工资低的员工的员工号、姓名、job_id 以及salary

![image-20221001172655517](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172655517.png)

题目：返回其它job_id中比job_id为‘IT_PROG’部门所有工资都低的员工的员工号、姓名、job_id以及salary

![image-20221001172710097](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172710097.png)

题目：查询平均工资最低的部门id

![image-20221001172736740](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172736740.png)

### 3. 3 空值问题

![image-20221001172752073](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172752073.png)

## 4. 相关子查询

### 4. 1 相关子查询执行流程

如果子查询的执行依赖于外部查询，通常情况下都是因为子查询中的表用到了外部的表，并进行了条件关联，因此每执行一次外部查询，子查询都要重新计算一次，这样的子查询就称之为**关联子查询**。

相关子查询按照一行接一行的顺序执行，主查询的每一行都执行一次子查询。

![image-20221001172902406](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172902406.png)

说明： **子查询中使用主查询中的列**

### 4. 2 代码示例

题目：查询员工中工资大于本部门平均工资的员工的last_name,salary和其department_id

方式一：相关子查询

![image-20221001172926490](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001172926490.png)

方式二：在 FROM 中使用子查询

![image-20221001173012412](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173012412.png)

- from型的子查询：子查询是作为from的一部分，子查询要用()引起来，并且要给这个子查询取别名， 把它当成一张“临时的虚拟的表”来使用。

在ORDER BY 中使用子查询：

题目：查询员工的id,salary,按照department_name 排序

![image-20221001173044740](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173044740.png)

题目：若employees表中employee_id与job_history表中employee_id相同的数目不小于 2 ，输出这些相同id的员工employee_id,last_name和其job_id

![image-20221001173051862](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173051862.png)

### 4. 3 EXISTS 与 NOT EXISTS关键字

- 关联子查询通常也会和 EXISTS操作符一起来使用，用来检查在子查询中是否存在满足条件的行。

- **如果在子查询中不存在满足条件的行**：
  - 条件返回 FALSE
  - 继续在子查询中查找

- **如果在子查询中存在满足条件的行**：
  - 不在子查询中继续查找
  - 条件返回 TRUE

- NOT EXISTS关键字表示如果不存在某种条件，则返回TRUE，否则返回FALSE。

题目：查询公司管理者的employee_id，last_name，job_id，department_id信息

方式一：

![image-20221001173152870](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173152870.png)

方式二：自连接

![image-20221001173202976](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173202976.png)

方式三：

![image-20221001173217785](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173217785.png)

题目：查询departments表中，不存在于employees表中的部门的department_id和department_name

![image-20221001173233610](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173233610.png)

### 4. 4 相关更新

![image-20221001173257503](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173257503.png)

使用相关子查询依据一个表中的数据更新另一个表的数据。

题目：在employees中增加一个department_name字段，数据为员工对应的部门名称

![image-20221001173310030](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173310030.png)

### 4. 4 相关删除

![image-20221001173320164](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173320164.png)

使用相关子查询依据一个表中的数据删除另一个表的数据。

题目：删除表employees中，其与emp_history表皆有的数据

![image-20221001173357224](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173357224.png)

## 5. 抛一个思考题

![image-20221007182551325](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221007182551325.png)

问题： 谁的工资比Abel的高？

解答：

![image-20221001173501299](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173501299.png)



问题： 以上两种方式有好坏之分吗？

解答： 自连接方式好！

题目中可以使用子查询，也可以使用自连接。一般情况建议你使用自连接，因为在许多 DBMS 的处理过程中，对于自连接的处理速度要比子查询快得多。

可以这样理解：子查询实际上是通过未知表进行查询后的条件判断，而自连接是通过已知的自身数据表进行条件判断，因此在大部分 DBMS 中都对自连接处理进行了优化。



------

# 第 10 章_创建和管理表

## 1. 基础知识

### 1. 1 一条数据存储的过程

**存储数据是处理数据的第一步**。只有正确地把数据存储起来，我们才能进行有效的处理和分析。否则，只能是一团乱麻，无从下手。

那么，怎样才能把用户各种经营相关的、纷繁复杂的数据，有序、高效地存储起来呢？ 在 MySQL 中，一个完整的数据存储过程总共有 4 步，分别是创建数据库、确认字段、创建数据表、插入数据。

![image-20221001173721648](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173721648.png)

我们要先创建一个数据库，而不是直接创建数据表呢？

因为从系统架构的层次上看，MySQL 数据库系统从大到小依次是**数据库服务器**、**数据库**、**数据表**、数据表的**行与列**。

MySQL 数据库服务器之前已经安装。所以，我们就从创建数据库开始。

### 1. 2 标识符命名规则

- 数据库名、表名不得超过 30 个字符，变量名限制为 29 个
- 必须只能包含 A–Z, a–z, 0 – 9 , _共 63 个字符
- 数据库名、表名、字段名等对象名中间不要包含空格
- 同一个MySQL软件中，数据库不能同名；同一个库中，表不能重名；同一个表中，字段不能重名
- 必须保证你的字段没有和保留字、数据库系统或常用方法冲突。如果坚持使用，请在SQL语句中使用`（着重号）引起来
- 保持字段名和类型的一致性：在命名字段并为其指定数据类型的时候一定要保证一致性，假如数据类型在一个表里是整数，那在另一个表里可就别变成字符型了

### 1. 3 MySQL中的数据类型

![image-20221001173852011](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173852011.png)

其中，常用的几类类型介绍如下：

![image-20221001173930434](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001173930434.png)

## 2. 创建和管理数据库

### 2. 1 创建数据库

- 方式 1 ：创建数据库

```mysql
CREATE DATABASE 数据库名;
```

- 方式 2 ：创建数据库并指定字符集

```sql
CREATE DATABASE 数据库名 CHARACTER SET 字符集;
```

- 方式 3 ：判断数据库是否已经存在，不存在则创建数据库（推荐）

```sql
CREATE DATABASE IF NOT EXISTS 数据库名;
```

如果MySQL中已经存在相关的数据库，则忽略创建语句，不再创建数据库。

注意：DATABASE 不能改名。一些可视化工具可以改名，它是建新库，把所有表复制到新库，再删旧库完成的。

### 2. 2 使用数据库

- 查看当前所有的数据库

```sql
SHOW DATABASES; #有一个S，代表多个数据库
```

- 查看当前正在使用的数据库

```sql
SELECT DATABASE(); #使用的一个 mysql 中的全局函数
```

- 查看指定库下所有的表

```sql
SHOW TABLES FROM 数据库名;
```

- 查看数据库的创建信息

```sql
SHOW CREATE DATABASE 数据库名;
或者：
SHOW CREATE DATABASE 数据库名\G
```

- 使用/切换数据库

```sql
USE 数据库名;
```

注意：要操作表格和数据之前必须先说明是对哪个数据库进行操作，否则就要对所有对象加上“数据库名.”。

### 2. 3 修改数据库

- 更改数据库字符集

```sql
ALTER DATABASE 数据库名 CHARACTER SET 字符集;  #比如：gbk、utf8等
```

### 2. 4 删除数据库

- 方式 1 ：删除指定的数据库

```sql
DROP DATABASE 数据库名;
```

- 方式 2 ：删除指定的数据库（**推荐**）

```sql
DROP DATABASE IF EXISTS 数据库名;
```

## 3. 创建表

### 3. 1 创建方式 1

- **必须具备**：
  - CREATE TABLE权限
  - 存储空间

- **语法格式**：

```sql
CREATE TABLE [IF NOT EXISTS] 表名(
        字段1, 数据类型 [约束条件] [默认值],
        字段2, 数据类型 [约束条件] [默认值],
        字段3, 数据类型 [约束条件] [默认值],
        ……
        [表约束条件]
);
```

加上了IF NOT EXISTS关键字，则表示：如果当前数据库中不存在要创建的数据表，则创建数据表；如果当前数据库中已经存在要创建的数据表，则忽略建表语句，不再创建数据表。

- **必须指定**：
  - 表名
  - 列名(或字段名)，数据类型， **长度**

- **可选指定**：
  - 约束条件
  - 默认值

- 创建表举例 1 ：

```sql
-- 创建表
CREATE TABLE emp (
    -- int类型
    emp_id INT,
    -- 最多保存 20 个中英文字符
    emp_name VARCHAR( 20 ),
    -- 总位数不超过 15 位
    salary DOUBLE,
    -- 日期类型
    birthday DATE
);
```

```sql
DESC emp;
```

![image-20221001174750924](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001174750924.png)

MySQL在执行建表语句时，将id字段的类型设置为int(11)，这里的 11 实际上是int类型指定的显示宽度，默认的显示宽度为 11 。也可以在创建数据表的时候指定数据的显示宽度。

- 创建表举例 2 ：

```sql
CREATE TABLE dept(
    -- int类型，自增
    deptno INT( 2 ) AUTO_INCREMENT,
    dname VARCHAR( 14 ),
    loc VARCHAR( 13 ),
    -- 主键
    PRIMARY KEY (deptno)
);
```

```sql
DESCRIBE dept;
```

![image-20221001174908270](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001174908270.png)

在MySQL 8.x版本中，不再推荐为INT类型指定显示长度，并在未来的版本中可能去掉这样的语法。

### 3. 2 创建方式 2

- 使用 AS subquery 选项， **将创建表和插入数据结合起来**

![image-20221001174952935](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001174952935.png)

- 指定的列和子查询中的列要一一对应

- 通过列名和默认值定义列

```sql
CREATE TABLE emp1 AS SELECT * FROM employees;
CREATE TABLE emp2 AS SELECT * FROM employees WHERE 1 = 2 ; -- 创建的emp2是空表
```

```sql
CREATE TABLE dept
AS
SELECT employee_id, last_name, salary* 12 ANNSAL, hire_date
FROM employees
WHERE department_id = 80 ;
```

```sql
DESCRIBE dept80;
```

![image-20221001175059977](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001175059977.png)

### 3. 3 查看数据表结构

在MySQL中创建好数据表之后，可以查看数据表的结构。MySQL支持使用**DESCRIBE/DESC**语句查看数据表结构，也支持使用**SHOW CREATE TABLE**语句查看数据表结构。

语法格式如下：

```sql
SHOW CREATE TABLE 表名\G
```

使用SHOW CREATE TABLE语句不仅可以查看表创建时的详细语句，还可以查看存储引擎和字符编码。

## 4. 修改表

修改表指的是修改数据库中已经存在的数据表的结构。

**使用 ALTER TABLE 语句可以实现**：

- 向已有的表中添加列

- 修改现有表中的列

- 删除现有表中的列

- 重命名现有表中的列

### 4. 1 追加一个列

语法格式如下：

```sql
ALTER TABLE 表名 ADD 【COLUMN】 字段名 字段类型 【FIRST|AFTER 字段名】;
```

举例：

```sql
ALTER TABLE dept80
ADD job_id varchar(15);
```

![image-20221001175324085](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001175324085.png)

### 4. 2 修改一个列

- 可以修改列的数据类型，长度、默认值和位置

- 修改字段数据类型、长度、默认值、位置的语法格式如下：

```sql
ALTER TABLE 表名 MODIFY 【COLUMN】 字段名1 字段类型 【DEFAULT 默认值】【FIRST|AFTER 字段名 2】;
```

- 举例：

```sql
ALTER TABLE dept80
MODIFY last_name VARCHAR(30);
```

```sql
ALTER TABLE dept80
MODIFY salary double(9,2) default 1000;
```

- 对默认值的修改只影响今后对表的修改

- 此外，还可以通过此种方式修改列的约束。这里暂先不讲。

### 4. 3 重命名一个列

使用 CHANGE old_column new_column dataType子句重命名列。语法格式如下：

```sql
ALTER TABLE 表名 CHANGE 【column】 列名 新列名 新数据类型;
```

举例：

```sql
ALTER TABLE dept80
CHANGE department_name dept_name varchar(15);
```

### 4. 4 删除一个列

删除表中某个字段的语法格式如下：

```sql
ALTER TABLE 表名 DROP 【COLUMN】字段名
```

举例：

```sql
ALTER TABLE dept80
DROP COLUMN job_id;
```

## 5. 重命名表

- 方式一：使用RENAME

```sql
RENAME TABLE emp
TO myemp;
```

- 方式二：

```sql
ALTER table dept
RENAME [TO] detail_dept; -- [TO]可以省略
```

- 必须是对象的拥有者

## 6. 删除表

- 在MySQL中，当一张数据表**没有与其他任何数据表形成关联关系**时，可以将当前数据表直接删除。
- 数据和结构都被删除
- 所有正在运行的相关事务被提交
- 所有相关索引被删除
- 语法格式：

```sql
DROP TABLE [IF EXISTS] 数据表1 [, 数据表2, …, 数据表n];
```

**IF EXISTS**的含义为：如果当前数据库中存在相应的数据表，则删除数据表；如果当前数据库中不存在相应的数据表，则忽略删除语句，不再执行删除数据表的操作。

- 举例：

```sql
DROP TABLE dept80;
```

- DROP TABLE 语句不能回滚

## 7. 清空表

- TRUNCATE TABLE语句：
  - 删除表中所有的数据
  - 释放表的存储空间

- 举例：

```sql
TRUNCATE TABLE detail_dept;
```

- TRUNCATE语句 **不能回滚** ，而使用 DELETE 语句删除数据，可以回滚

- 对比：

```sql
SET autocommit = FALSE;

DELETE FROM emp2;
#TRUNCATE TABLE emp2;

SELECT * FROM emp2;

ROLLBACK;

SELECT * FROM emp2;
```

![image-20221008171800036](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221008171800036.png)

![image-20221008172645715](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221008172645715.png)

**阿里开发规范：**

【参考】TRUNCATE TABLE 比 DELETE 速度快，且使用的系统和事务日志资源少，但 TRUNCATE 无事务且不触发 TRIGGER，有可能造成事故，故不建议在开发代码中使用此语句。

说明：TRUNCATE TABLE 在功能上与不带 WHERE 子句的 DELETE 语句相同。

## 8. 内容拓展

### 拓展 1 ：阿里巴巴《Java开发手册》之MySQL字段命名

- 【强制】表名、字段名必须使用小写字母或数字，禁止出现数字开头，禁止两个下划线中间只出现数字。数据库字段名的修改代价很大，因为无法进行预发布，所以字段名称需要慎重考虑。
  - 正例：aliyun_admin，rdc_config，level3_name
  - 反例：AliyunAdmin，rdcConfig，level_3_name

- 【强制】禁用保留字，如 desc、range、match、delayed 等，请参考 MySQL 官方保留字。
- 【强制】表必备三字段：id, gmt_create, gmt_modified。
  - 说明：其中 id 必为主键，类型为BIGINT UNSIGNED、单表时自增、步长为 1 。gmt_create,gmt_modified 的类型均为DATETIME 类型，前者现在时表示主动式创建，后者过去分词表示被动式更新
- 【推荐】表的命名最好是遵循 “业务名称_表的作用”。
  - 正例：alipay_task 、 force_project、 trade_config
- 【推荐】库名与应用名称尽量一致。
- 【参考】合适的字符存储长度，不但节约数据库表空间、节约索引存储，更重要的是提升检索速度。
  - 正例：无符号值可以避免误存负数，且扩大了表示范围。

![image-20221001181500187](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001181500187.png)

### 拓展 2 ：如何理解清空表、删除表等操作需谨慎？！

**表删除**操作将把表的定义和表中的数据一起删除，并且MySQL在执行删除操作时，不会有任何的确认信息提示，因此执行删除操时应当慎重。在删除表前，最好对表中的数据进行**备份**，这样当操作失误时可以对数据进行恢复，以免造成无法挽回的后果。

同样的，在使用 **ALTER TABLE** 进行表的基本修改操作时，在执行操作过程之前，也应该确保对数据进行完整的**备份**，因为数据库的改变是**无法撤销**的，如果添加了一个不需要的字段，可以将其删除；相同的，如果删除了一个需要的列，该列下面的所有数据都将会丢失。

### 拓展 3 ：MySQL 8 新特性—DDL的原子化

在MySQL 8.0版本中，InnoDB表的DDL支持事务完整性，即**DDL操作要么成功要么回滚**。DDL操作回滚日志写入到data dictionary数据字典表mysql.innodb_ddl_log（该表是隐藏的表，通过show tables无法看到）
中，用于回滚操作。通过设置参数，可将DDL操作日志打印输出到MySQL错误日志中。

分别在MySQL 5.7版本和MySQL 8.0版本中创建数据库和数据表，结果如下：

![image-20221001181713806](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001181713806.png)

（ 1 ）在MySQL 5.7版本中，测试步骤如下： 删除数据表book1和数据表book2，结果如下：

![image-20221001181724501](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001181724501.png)

再次查询数据库中的数据表名称，结果如下：

![image-20221001181736791](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001181736791.png)

从结果可以看出，虽然删除操作时报错了，但是仍然删除了数据表book1。

（ 2 ）在MySQL 8.0版本中，测试步骤如下： 删除数据表book1和数据表book2，结果如下：

![image-20221001181755553](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001181755553.png)

再次查询数据库中的数据表名称，结果如下：

![image-20221001181805497](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001181805497.png)

从结果可以看出，数据表book1并没有被删除。





------

# 第 11 章_数据处理之增删改

## 1. 插入数据

### 1. 1 实际问题

![image-20221001182406081](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001182406081.png)

解决方式：使用 INSERT 语句向表中插入数据。

### 1. 2 方式 1 ：VALUES的方式添加

使用这种语法一次只能向表中插入 **一条** 数据。

**情况 1 ：为表的所有字段按默认顺序插入数据**

```sql
INSERT INTO 表名
VALUES (value1,value2,....);
```

值列表中需要为表的每一个字段指定值，并且值的顺序必须和数据表中字段定义时的顺序相同。

举例：

```sql
INSERT INTO departments
VALUES ( 70 , 'Pub', 100 , 1700 );

INSERT INTO departments
VALUES ( 100 , 'Finance', NULL, NULL);
```

**情况 2 ：为表的指定字段插入数据**

```sql
INSERT INTO 表名(column1 [, column2, …, columnn])
VALUES (value1 [,value2, …, valuen]);
```

为表的指定字段插入数据，就是在INSERT语句中只向部分字段中插入值，而其他字段的值为表定义时的默认值。

在 INSERT 子句中随意列出列名，但是一旦列出，VALUES中要插入的value1,....valuen需要与column1,...columnn列一一对应。如果类型不同，将无法插入，并且MySQL会产生错误。

举例：

```sql
INSERT INTO departments(department_id, department_name)
VALUES (80, 'IT');
```

**情况 3 ：同时插入多条记录**

INSERT语句可以同时向数据表中插入多条记录，插入时指定多个值列表，每个值列表之间用逗号分隔开，基本语法格式如下：

```sql
INSERT INTO table_name
VALUES
(value1 [,value2, …, valuen]),
(value1 [,value2, …, valuen]),
……
(value1 [,value2, …, valuen]);
```

或者

```sql
INSERT INTO table_name(column1 [, column2, …, columnn])
VALUES
(value1 [,value2, …, valuen]),
(value1 [,value2, …, valuen]),
……
(value1 [,value2, …, valuen]);
```

举例：

```sql
mysql> INSERT INTO emp(emp_id,emp_name)
    -> VALUES (1001,'shkstart'),
    -> (1002,'atguigu'),
    -> (1003,'Tom');
Query OK, 3 rows affected (0.00 sec)
Records: 3 Duplicates: 0 Warnings: 0
```

使用INSERT同时插入多条记录时，MySQL会返回一些在执行单行插入时没有的额外信息，这些信息的含义如下： 

●　Records：表明插入的记录条数。

 ●　Duplicates：表明插入时被忽略的记录，原因可能是这些记录包含了重复的主键值。 

●　Warnings：表明有问题的数据值，例如发生数据类型转换。

​	一个同时插入多行记录的INSERT语句等同于多个单行插入的INSERT语句，但是多行的INSERT语句在处理过程中**效率更高**。因为MySQL执行单条INSERT语句插入多行数据比使用多条INSERT语句快，所以在插入多条记录时最好选择使用单条INSERT语句的方式插入。

**小结**：

- **VALUES**也可以写成**VALUE**，但是VALUES是标准写法。

- 字符和日期型数据应包含在单引号中。

### 1. 3 方式 2 ：将查询结果插入到表中

INSERT还可以将SELECT语句查询的结果插入到表中，此时不需要把每一条记录的值一个一个输入，只需要使用一条INSERT语句和一条SELECT语句组成的组合语句即可快速地从一个或多个表中向一个表中插入多行。

基本语法格式如下：

```sql
INSERT INTO 目标表名
(tar_column1 [, tar_column2, …, tar_columnn])
SELECT
(src_column1 [, src_column2, …, src_columnn])
FROM 源表名
[WHERE condition]
```

- 在 INSERT 语句中加入子查询。
- **不必书写 VALUES 子句**。
- 子查询中的值列表应与 INSERT 子句中的列名对应。

举例：

```sql
INSERT INTO emp2
SELECT *
FROM employees
WHERE department_id = 90;

INSERT INTO sales_reps(id, name, salary, commission_pct)
SELECT employee_id, last_name, salary, commission_pct
FROM employees
WHERE job_id LIKE '%REP%';
```

## 2. 更新数据

![image-20221001183106852](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001183106852.png)

- 使用 UPDATE 语句更新数据。语法如下：

```sql
UPDATE table_name
SET column1=value1, column2=value2, … , column=valuen
[WHERE condition]
```

- 可以一次更新 **多条** 数据。

- 如果需要回滚数据，需要保证在DML前，进行设置： **SET  AUTOCOMMIT = FALSE**;

- 使用 **WHERE** 子句指定需要更新的数据。

```sql
UPDATE employees
SET department_id = 70
WHERE employee_id = 113;
```

- 如果省略 WHERE 子句，则表中的所有数据都将被更新。

```sql
UPDATE copy_emp
SET department_id = 110;
```

- **更新中的数据完整性错误**

```sql
UPDATE employees
SET department_id = 55
WHERE department_id = 110;
```

![image-20221009164135863](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009164135863.png)

说明：不存在 55 号部门

## 3. 删除数据

![image-20221001183459161](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221001183459161.png)

- 使用 DELETE 语句从表中删除数据

![image-20221009170021070](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009170021070.png)

```SQL
DELETE FROM table_name [WHERE <condition>];
```

table_name指定要执行删除操作的表；“[WHERE ]”为可选参数，指定删除条件，如果没有WHERE子句，DELETE语句将删除表中的所有记录。

- 使用 WHERE 子句删除指定的记录。

```sql
DELETE FROM departments
WHERE department_name = 'Finance';
```

- 如果省略 WHERE 子句，则表中的全部数据将被删除

```sql
DELETE FROM copy_emp;
```

- **删除中的数据完整性错误**

```sql
DELETE FROM departments
WHERE department_id = 60;
```

![image-20221009164343211](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009164343211.png)

说明：You cannot delete a row that contains a primary key that is used as a foreign key in another  table.

## 4. MySQL 8 新特性：计算列

什么叫计算列呢？简单来说就是某一列的值是通过别的列计算得来的。例如，a列值为 1 、b列值为 2 ，c列不需要手动插入，定义a+b的结果为c的值，那么c就是计算列，是通过别的列计算得来的。

在MySQL 8.0中，CREATE TABLE 和 ALTER TABLE 中都支持增加计算列。下面以CREATE TABLE为例进行讲解。

举例：定义数据表tb1，然后定义字段id、字段a、字段b和字段c，其中字段c为计算列，用于计算a+b的值。 首先创建测试表tb1，语句如下：

```sql
CREATE TABLE tb1(
id INT,
a INT,
b INT,
c INT GENERATED ALWAYS AS (a + b) VIRTUAL
);
```

插入演示数据，语句如下：

```sql
INSERT INTO tb1(a,b) VALUES (100,200);
```

查询数据表tb1中的数据，结果如下：

```sql
mysql> SELECT * FROM tb1;
+------+------+------+------+
| id | a | b | c |
+------+------+------+------+
| NULL | 100 | 200 | 300 |
+------+------+------+------+
1 row in set (0.00 sec)
```

更新数据中的数据，语句如下：

```sql
mysql> UPDATE tb1 SET a = 500;
Query OK, 0 rows affected (0.00 sec)
Rows matched: 1 Changed: 0 Warnings: 0
```

## 5. 综合案例

```sql
# 1、创建数据库test01_library
# 2、创建表 books，表结构如下：


# 3、向books表中插入记录
    # 1）不指定字段名称，插入第一条记录
    # 2）指定所有字段名称，插入第二记录
    # 3）同时插入多条记录（剩下的所有记录）


# 4、将小说类型(novel)的书的价格都增加5。
# 5、将名称为EmmaT的书的价格改为40，并将说明改为drama。
# 6、删除库存为0的记录。
# 7、统计书名中包含a字母的书
# 8、统计书名中包含a字母的书的数量和库存总量
# 9、找出“novel”类型的书，按照价格降序排列
# 10、查询图书信息，按照库存量降序排列，如果库存量相同的按照note升序排列
# 11、按照note分类统计书的数量
# 12、按照note分类统计书的库存量，显示库存量超过30本的
# 13、查询所有图书，每页显示5本，显示第二页
# 14、按照note分类统计书的库存量，显示库存量最多的
# 15、查询书名达到10个字符的书，不包括里面的空格
# 16、查询书名和类型，其中note值为novel显示小说，law显示法律，medicine显示医药，cartoon显示卡通，joke显示笑话
# 17、查询书名、库存，其中num值超过30本的，显示滞销，大于0并低于10的，显示畅销，为0的显示需要无货
# 18、统计每一种note的库存量，并合计总量
# 19、统计每一种note的数量，并合计总量
# 20、统计库存量前三名的图书
# 21、找出最早出版的一本书
# 22、找出novel中价格最高的一本书
# 23、找出书名中字数最多的一本书，不含空格
```

![image-20221009165447560](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009165447560.png)

![image-20221009165500820](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009165500820.png)

**答案：**

![image-20221009165645996](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009165645996.png)

![image-20221009165659086](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009165659086.png)

![image-20221009165727951](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009165727951.png)

![image-20221009165743525](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221009165743525.png)





# 第 12 章_MySQL数据类型精讲

## 1. MySQL中的数据类型

![image-20221011150627020](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011150627020.png)

常见数据类型的属性，如下：

![image-20221011150647962](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011150647962.png)

## 2. 整数类型

### 2. 1 类型介绍

整数类型一共有 5 种，包括 TINYINT、SMALLINT、MEDIUMINT、INT（INTEGER）和 BIGINT。

它们的区别如下表所示：

![image-20221011150747141](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011150747141.png)

### 2. 2 可选属性

**整数类型的可选属性有三个：**

#### 2. 2. 1 M

**M**: 表示显示宽度，M的取值范围是( 0 , 255 )。例如，int( 5 )：当数据宽度小于 5 位的时候在数字前面需要用字符填满宽度。该项功能需要配合“**ZEROFILL**”使用，表示用“ 0 ”填满宽度，否则指定显示宽度无效。

如果设置了显示宽度，那么插入的数据宽度超过显示宽度限制，会不会截断或插入失败？

答案：不会对插入的数据有任何影响，还是按照类型的实际宽度进行保存，即**显示宽度与类型可以存储的值范围无关**。 **从MySQL 8. 0. 17 开始，整数数据类型不推荐使用显示宽度属性。**

整型数据类型可以在定义表结构时指定所需要的显示宽度，如果不指定，则系统为每一种类型指定默认的宽度值。

举例：

![image-20221011150927278](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011150927278.png)

查看表结构 （MySQL 5. 7 中显式如下，MySQL 8 中不再显式范围）

![image-20221011150940793](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011150940793.png)

TINYINT有符号数和无符号数的取值范围分别为- 128 ~ 127 和 0 ~ 255 ，由于负号占了一个数字位，因此TINYINT默认的显示宽度为 4 。同理，其他整数类型的默认显示宽度与其有符号数的最小值的宽度相同。

举例：

![image-20221011151006743](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011151006743.png)

#### 2. 2. 2 UNSIGNED

**UNSIGNED:** 无符号类型（非负），所有的整数类型都有一个可选的属性UNSIGNED（无符号属性），无符号整数类型的最小取值为 0 。所以，如果需要在MySQL数据库中保存非负整数值时，可以将整数类型设
置为无符号类型。

int类型默认显示宽度为int(11)，无符号int类型默认显示宽度为int(10)。

![image-20221011151049275](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011151049275.png)

#### 2. 2. 3 ZEROFILL

**ZEROFILL**: 0填充,（如果某列是ZEROFILL，那么MySQL会自动为当前列添加UNSIGNED属性），如果指定了ZEROFILL只是表示不够M位时，用 0 在左边填充，如果超过M位，只要不超过数据存储范围即可。

原来，在 int(M) 中，M 的值跟 int(M) 所占多少存储空间并无任何关系。 int(3)、int(4)、int(8) 在磁盘上都是占用 4 bytes 的存储空间。也就是说， **int(M)，必须和UNSIGNED ZEROFILL一起使用才有意义。** 如果整数值超过M位，就按照实际位数存储。只是无须再用字符 0 进行填充。

### 2. 3 适用场景

`TINYINT`：一般用于枚举数据，比如系统设定取值范围很小且固定的场景。

`SMALLINT`：可以用于较小范围的统计数据，比如统计工厂的固定资产库存数量等。

`MEDIUMINT`：用于较大整数的计算，比如车站每日的客流量等。

`INT、INTEGER`：取值范围足够大，一般情况下不用考虑超限问题，用得最多。比如商品编号。

`BIGINT`：只有当你处理特别巨大的整数时才会用到。比如双十一的交易量、大型门户网站点击量、证券公司衍生产品持仓等。

### 2. 4 如何选择？

在评估用哪种整数类型的时候，你需要考虑**存储空间**和**可靠性**的平衡问题：一方 面，用占用字节数少的整数类型可以节省存储空间；另一方面，要是为了节省存储空间， 使用的整数类型取值范围太小，一旦遇到超出取值范围的情况，就可能引起**系统错误**，影响可靠性。

举个例子，商品编号采用的数据类型是 INT。原因就在于，客户门店中流通的商品种类较多，而且，每天都有旧商品下架，新商品上架，这样不断迭代，日积月累。

如果使用 SMALLINT 类型，虽然占用字节数比 INT 类型的整数少，但是却不能保证数据不会超出范围65535 。相反，使用 INT，就能确保有足够大的取值范围，不用担心数据超出范围影响可靠性的问题。

你要注意的是，在实际工作中， **系统故障产生的成本远远超过增加几个字段存储空间所产生的成本** 。因此，我建议你首先确保数据不会超过取值范围，在这个前提之下，再去考虑如何节省存储空间。

## 3. 浮点类型

### 3. 1 类型介绍

浮点数和定点数类型的特点是可以**处理小数**，你可以把整数看成小数的一个特例。因此，浮点数和定点数的使用场景，比整数大多了。 MySQL支持的浮点数类型，分别是 FLOAT、DOUBLE、REAL。

- FLOAT 表示单精度浮点数；
- DOUBLE 表示双精度浮点数；

![image-20221011151421159](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011151421159.png)

- REAL默认就是 DOUBLE。如果你把 SQL 模式设定为启用“**REAL_AS_FLOAT**”，那 么，MySQL 就认为REAL 是 FLOAT。如果要启用“REAL_AS_FLOAT”，可以通过以下 SQL 语句实现：

![image-20221011151459901](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011151459901.png)

**问题 1** ： FLOAT 和 DOUBLE 这两种数据类型的区别是啥呢？

FLOAT 占用字节数少，取值范围小；DOUBLE 占用字节数多，取值范围也大。

**问题 2** ： 为什么浮点数类型的无符号数取值范围，只相当于有符号数取值范围的一半，也就是只相当于有符号数取值范围大于等于零的部分呢？

MySQL 存储浮点数的格式为：**符号(S)、尾数(M)和 阶码(E)**。因此，无论有没有符号，MySQL 的浮点数都会存储表示符号的部分。因此， 所谓的无符号数取值范围，其实就是有符号数取值范围大于等于零的部分。

### 3. 2 数据精度说明

对于浮点类型，在MySQL中**单精度值使用 4 个字节，双精度值使用 8 个字节**。

- MySQL允许使用**非标准语法**（其他数据库未必支持，因此如果涉及到数据迁移，则最好不要这么用）：**FLOAT(M,D)**或**DOUBLE(M,D)**。这里，M称为**精度**，D称为**标度**。(M,D)中 M=整数位+小数位，D=小数位。 D<=M<= 255 ， 0 <=D<= 30 。
  - 例如，定义为FLOAT( 5 , 2 )的一个列可以显示为- 999. 99 - 999. 99 。如果超过这个范围会报错。
- FLOAT和DOUBLE类型在不指定(M,D)时，默认会按照实际的精度（由实际的硬件和操作系统决定）来显示。
- 说明：浮点类型，也可以加UNSIGNED，但是不会改变数据范围，例如：FLOAT( 3 , 2 ) UNSIGNED仍然只能表示 0 - 9. 99 的范围。
- 不管是否显式设置了精度(M,D)，这里MySQL的处理方案如下：
  - 如果存储时，整数部分超出了范围，MySQL就会报错，不允许存这样的值
  - 如果存储时，小数点部分若超出范围，就分以下情况：
    - 若四舍五入后，整数部分没有超出范围，则只警告，但能成功操作并四舍五入删除多余的小数位后保存。例如在FLOAT( 5 , 2 )列内插入 999. 009 ，近似结果是 999. 01 。
    - 若四舍五入后，整数部分超出范围，则MySQL报错，并拒绝处理。如FLOAT( 5 , 2 )列内插入999. 995 和- 999. 995 都会报错。
- **从MySQL 8. 0. 17 开始，FLOAT(M,D) 和DOUBLE(M,D)用法在官方文档中已经明确不推荐使用** ，将来可能被移除。另外，关于浮点型FLOAT和DOUBLE的UNSIGNED也不推荐使用了，将来也可能被移除。
- 举例

![image-20221011151925019](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011151925019.png)

### 3. 3 精度误差说明

浮点数类型有个缺陷，就是不精准。下面我来重点解释一下为什么 MySQL 的浮点数不够精准。比如，我们设计一个表，有f 1 这个字段，插入值分别为 0. 47 , 0. 44 , 0. 19 ，我们期待的运行结果是： 0. 47 + 0. 44 + 0. 19 =1.1。而使用sum之后查询：

![image-20221011152014344](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011152014344.png)

查询结果是 1. 0999999999999999 。看到了吗？虽然误差很小，但确实有误差。 你也可以尝试把数据类型改成 FLOAT，然后运行求和查询，得到的是， 1. 0999999940395355 。显然，误差更大了。

那么，为什么会存在这样的误差呢？问题还是出在 MySQL 对浮点类型数据的存储方式上。

MySQL 用 4 个字节存储 FLOAT 类型数据，用 8 个字节来存储 DOUBLE 类型数据。无论哪个，都是采用二进制的方式来进行存储的。比如 9. 625 ，用二进制来表达，就是 1001. 101 ，或者表达成 1. 001101 × 2 ^ 3 。如果尾数不是 0 或 5 （比如 9. 624 ），你就无法用一个二进制数来精确表达。进而，就只好在取值允许的范围内进行四舍五入。

在编程中，如果用到浮点数，要特别注意误差问题， **因为浮点数是不准确的，所以我们要避免使用“=”来判断两个数是否相等。** 同时，在一些对精确度要求较高的项目中，千万不要使用浮点数，不然会导致结果错误，甚至是造成不可挽回的损失。那么，MySQL 有没有精准的数据类型呢？当然有，这就是定点数类型：**DECIMAL**。

## 4. 定点数类型

### 4. 1 类型介绍

- MySQL中的定点数类型只有 DECIMAL 一种类型。

![image-20221011185845336](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011185845336.png)

使用 DECIMAL(M,D) 的方式表示高精度小数。其中，M被称为精度，D被称为标度。0<=M<=65，0<=D<=30，D<M。例如，定义DECIMAL（5,2）的类型，表示该列取值范围是-999.99~999.99。

- **DECIMAL(M,D)的最大取值范围与DOUBLE类型一样** ，但是有效的数据范围是由M和D决定的。

  DECIMAL 的存储空间并不是固定的，由精度值M决定，总共占用的存储空间为M+2个字节。也就是说，在一些对精度要求不高的场景下，比起占用同样字节长度的定点数，浮点数表达的数值范围可以更大一些。

- 定点数在MySQL内部是以**字符串**的形式进行存储，这就决定了它一定是精准的。

- 当DECIMAL类型不指定精度和标度时，其默认为DECIMAL(10,0)。当数据的精度超出了定点数类型的精度范围时，则MySQL同样会进行四舍五入处理。

- **浮点数 vs 定点数**
  - 浮点数相对于定点数的优点是在长度一定的情况下，浮点类型取值范围大，但是不精准，适用于需要取值范围大，又可以容忍微小误差的科学计算场景（比如计算化学、分子建模、流体动力学等）
  - 定点数类型取值范围相对小，但是精准，没有误差，适合于对精度要求极高的场景 （比如涉及金额计算的场景）

- 举例

![image-20221011190028650](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190028650.png)

- 举例

我们运行下面的语句，把test_double2表中字段“f1”的数据类型修改为 DECIMAL(5,2)：

![image-20221011190053436](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190053436.png)

然后，我们再一次运行求和语句：

![image-20221011190114774](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190114774.png)

### 4. 2 开发中经验

“由于 DECIMAL 数据类型的精准性，在我们的项目中，除了极少数（比如商品编号）用到整数类型外，其他的数值都用的是 DECIMAL，原因就是这个项目所处的零售行业，要求精准，一分钱也不能差。 ” ——来自某项目经理

## 5. 位类型：BIT

BIT类型中存储的是二进制值，类似 010110 。

![image-20221011190230936](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190230936.png)

BIT类型，如果没有指定(M)，默认是 1 位。这个 1 位，表示只能存 1 位的二进制值。这里(M)是表示二进制的位数，位数最小值为 1 ，最大值为 64 。

![image-20221011190244939](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190244939.png)

注意：在向BIT类型的字段中插入数据时，一定要确保插入的数据在BIT类型支持的范围内。



使用SELECT命令查询位字段时，可以用**BIN()**或**HEX()**函数进行读取。

![image-20221011190325107](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190325107.png)

可以看到，使用b+ 0 查询数据时，可以直接查询出存储的十进制数据的值。

## 6. 日期与时间类型

日期与时间是重要的信息，在我们的系统中，几乎所有的数据表都用得到。原因是客户需要知道数据的时间标签，从而进行数据查询、统计和处理。

MySQL有多种表示日期和时间的数据类型，不同的版本可能有所差异，MySQL 8. 0 版本支持的日期和时间类型主要有：YEAR类型、TIME类型、DATE类型、DATETIME类型和TIMESTAMP类型。

- `YEAR`类型通常用来表示年
- `DATE`类型通常用来表示年、月、日
- `TIME`类型通常用来表示时、分、秒
- `DATETIME`类型通常用来表示年、月、日、时、分、秒
- `TIMESTAMP`类型通常用来表示带时区的年、月、日、时、分、秒

![image-20221011190449508](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190449508.png)

可以看到，不同数据类型表示的时间内容不同、取值范围不同，而且占用的字节数也不一样，你要根据实际需要灵活选取。

为什么时间类型 TIME 的取值范围不是 - 23 : 59 : 59 ～ 23 : 59 : 59 呢？原因是 MySQL 设计的 TIME 类型，不光表示一天之内的时间，而且可以用来表示一个时间间隔，这个时间间隔可以超过 24 小时。

### 6. 1 YEAR类型

YEAR类型用来表示年份，在所有的日期时间类型中所占用的存储空间最小，只需要 1 个字节的存储空间。

在MySQL中，YEAR有以下几种存储格式：

- 以 4 位字符串或数字格式表示YEAR类型，其格式为YYYY，最小值为 1901 ，最大值为 2155 。
- 以 2 位字符串格式表示YEAR类型，最小值为 00 ，最大值为 99 。
  - 当取值为 01 到 69 时，表示 2001 到 2069 ；
  - 当取值为 70 到 99 时，表示 1970 到 1999 ；
  - 当取值整数的 0 或 00 添加的话，那么是 0000 年；
  - 当取值是日期/字符串的' 0 '添加的话，是 2000 年。

**从MySQL 5. 5. 27 开始， 2 位格式的YEAR已经不推荐使用** 。YEAR默认格式就是“YYYY”，没必要写成YEAR( 4 )，从MySQL 8. 0. 19 开始，不推荐使用指定显示宽度的YEAR( 4 )数据类型。

![image-20221011190650567](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190650567.png)

![image-20221011190704596](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190704596.png)

### 6. 2 DATE类型

DATE类型表示日期，没有时间部分，格式为`YYYY-MM-DD`，其中，YYYY表示年份，MM表示月份，DD表示日期。需要 **3 个字节**的存储空间。在向DATE类型的字段插入数据时，同样需要满足一定的格式条件。

- 以`YYYY-MM-DD`格式或者`YYYYMMDD`格式表示的字符串日期，其最小取值为 1000 - 01 - 01 ，最大取值为9999 - 12 - 03 。YYYYMMDD格式会被转化为YYYY-MM-DD格式。

- 以`YY-MM-DD`格式或者`YYMMDD`格式表示的字符串日期，此格式中，年份为两位数值或字符串满足YEAR类型的格式条件为：当年份取值为 00 到 69 时，会被转化为 2000 到 2069 ；当年份取值为 70 到 99时，会被转化为 1970 到 1999 。

- 使用`CURRENT_DATE()`或者`NOW()`函数，会插入当前系统的日期。

**举例**：

创建数据表，表中只包含一个DATE类型的字段f 1 。

![image-20221011190809278](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190809278.png)

插入数据：

![image-20221011190856198](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190856198.png)

![image-20221011190904503](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011190904503.png)

### 6. 3 TIME类型

TIME类型用来表示时间，不包含日期部分。在MySQL中，需要 **3 个字节**的存储空间来存储TIME类型的数据，可以使用“HH:MM:SS”格式来表示TIME类型，其中，HH表示小时，MM表示分钟，SS表示秒。

在MySQL中，向TIME类型的字段插入数据时，也可以使用几种不同的格式。 

（ 1 ）可以使用带有冒号的字符串，比如'`D  HH:MM:SS`'、'`HH:MM:SS`'、'`HH:MM`'、'`D HH:MM`'、'`D HH`'或'`SS`'格式，都能被正确地插入TIME类型的字段中。其中D表示天，其最小值为 0 ，最大值为 34 。如果使用带有D格式的字符串插入TIME类型的字段时，D会被转化为小时，计算格式为D* 24 +HH。当使用带有冒号并且不带D的字符串表示时间时，表示当天的时间，比如 12 : 10 表示 12 : 10 : 00 ，而不是 00 : 12 : 10 。 

（ 2 ）可以使用不带有冒号的字符串或者数字，格式为'`HHMMSS`'或者`HHMMSS`。如果插入一个不合法的字符串或者数字，MySQL在存储数据时，会将其自动转化为 00 : 00 : 00 进行存储。比如 1210 ，MySQL会将最右边的两位解析成秒，表示00 : 12 : 10 ，而不是 12 : 10 : 00 。 

（ 3 ）使用`CURRENT_TIME()`或`NOW()`，会插入当前系统的时间。

**举例：**

创建数据表，表中包含一个TIME类型的字段f 1 。

![image-20221011191109431](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191109431.png)

### 6. 4 DATETIME类型

DATETIME类型在所有的日期时间类型中占用的存储空间最大，总共需要 **8** 个字节的存储空间。在格式上为DATE类型和TIME类型的组合，可以表示为`YYYY-MM-DD HH:MM:SS`，其中YYYY表示年份，MM表示月份，DD表示日期，HH表示小时，MM表示分钟，SS表示秒。

在向DATETIME类型的字段插入数据时，同样需要满足一定的格式条件。

- 以`YYYY-MM-DD HH:MM:SS`格式或者`YYYYMMDDHHMMSS`格式的字符串插入DATETIME类型的字段时，最小值为 1000 - 01 - 01 00 : 00 : 00 ，最大值为 9999 - 12 - 03 23 : 59 : 59 。
  - 以YYYYMMDDHHMMSS格式的数字插入DATETIME类型的字段时，会被转化为YYYY-MM-DD HH:MM:SS格式。

- 以`YY-MM-DD HH:MM:SS`格式或者`YYMMDDHHMMSS`格式的字符串插入DATETIME类型的字段时，两位数的年份规则符合YEAR类型的规则， 00 到 69 表示 2000 到 2069 ； 70 到 99 表示 1970 到 1999 。

- 使用函数`CURRENT_TIMESTAMP()`和`NOW()`，可以向DATETIME类型的字段插入系统的当前日期和时间。

**举例**：

创建数据表，表中包含一个DATETIME类型的字段dt。

![image-20221011191414825](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191414825.png)

插入数据：

![image-20221011191426159](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191426159.png)

### 6. 5 TIMESTAMP类型

TIMESTAMP类型也可以表示日期时间，其显示格式与DATETIME类型相同，都是`YYYY-MM-DDHH:MM:SS`，需要 4 个字节的存储空间。但是TIMESTAMP存储的时间范围比DATETIME要小很多，只能存储“ 1970 - 01 - 01 00 : 00 : 01 UTC”到“ 2038 - 01 - 19 03 : 14 : 07 UTC”之间的时间。其中，UTC表示世界统一时间，也叫作世界标准时间。

- **存储数据的时候需要对当前时间所在的时区进行转换，查询数据的时候再将时间转换回当前的时区。因此，使用TIMESTAMP存储的同一个时间值，在不同的时区查询时会显示不同的时间。**

向TIMESTAMP类型的字段插入数据时，当插入的数据格式满足YY-MM-DD HH:MM:SS和YYMMDDHHMMSS时，两位数值的年份同样符合YEAR类型的规则条件，只不过表示的时间范围要小很多。

如果向TIMESTAMP类型的字段插入的时间超出了TIMESTAMP类型的范围，则MySQL会抛出错误信息。

**举例：**

创建数据表，表中包含一个TIMESTAMP类型的字段ts。

![image-20221011191555032](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191555032.png)

插入数据：

![image-20221011191605229](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191605229.png)

**TIMESTAMP和DATETIME的区别**：

- TIMESTAMP存储空间比较小，表示的日期时间范围也比较小

- 底层存储方式不同，TIMESTAMP底层存储的是毫秒值，距离 1970 - 1 - 1 0 : 0 : 0 0 毫秒的毫秒值。

- 两个日期比较大小或日期计算时，TIMESTAMP更方便、更快。

- TIMESTAMP和时区有关。TIMESTAMP会根据用户的时区不同，显示不同的结果。而DATETIME则只能反映出插入时当地的时区，其他时区的人查看数据必然会有误差的。

![image-20221011191643533](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191643533.png)

### 6. 6 开发中经验

用得最多的日期时间类型，就是 **DATETIME**。虽然 MySQL 也支持 YEAR（年）、 TIME（时间）、DATE（日期），以及 TIMESTAMP 类型，但是在实际项目中，尽量用 DATETIME 类型。因为这个数据类型包括了完整的日期和时间信息，取值范围也最大，使用起来比较方便。毕竟，如果日期时间信息分散在好几个字段，很不容易记，而且查询的时候，SQL 语句也会更加复杂。

此外，一般存注册时间、商品发布时间等，不建议使用DATETIME存储，而是使用**时间戳**，因为DATETIME虽然直观，但不便于计算。

![image-20221011191739913](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191739913.png)

## 7. 文本字符串类型

在实际的项目中，我们还经常遇到一种数据，就是字符串数据。

MySQL中，文本字符串总体上分为`CHAR`、`VARCHAR`、`TINYTEXT`、`TEXT`、`MEDIUMTEXT`、`LONGTEXT`、`ENUM`、`SET`等类型。

![image-20221011191848963](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191848963.png)

### 7. 1 CHAR与VARCHAR类型

CHAR和VARCHAR类型都可以存储比较短的字符串。

![image-20221011191923881](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011191923881.png)

**CHAR类型**：

- CHAR(M) 类型一般需要预先定义字符串长度。如果不指定(M)，则表示长度默认是 1 个字符。

- 如果保存时，数据的实际长度比CHAR类型声明的长度小，则会在**右侧填充**空格以达到指定的长度。当MySQL检索CHAR类型的数据时，CHAR类型的字段会去除尾部的空格。
- 定义CHAR类型字段时，声明的字段长度即为CHAR类型字段所占的存储空间的字节数。

![image-20221011192027825](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192027825.png)

**VARCHAR类型**：

- VARCHAR(M) 定义时，**必须指定长度M**，否则报错。
- MySQL4.0版本以下，varchar(20)：指的是 20 字节，如果存放UTF8汉字时，只能存 6 个（每个汉字 3 字节） ；MySQL5.0版本以上，varchar(20)：指的是 20 字符。
- 检索VARCHAR类型的字段数据时，会保留数据尾部的空格。VARCHAR类型的字段所占用的存储空间为字符串实际长度加 1 个字节。

![image-20221011192135112](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192135112.png)

**哪些情况使用 CHAR 或 VARCHAR 更好**

![image-20221011192150645](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192150645.png)

情况 1 ：存储很短的信息。比如门牌号码 101 ，201......这样很短的信息应该用char，因为varchar还要占个byte用于存储信息长度，本来打算节约存储的，结果得不偿失。

情况 2 ：固定长度的。比如使用uuid作为主键，那用char应该更合适。因为他固定长度，varchar动态根据长度的特性就消失了，而且还要占个长度信息。

情况 3 ：十分频繁改变的column。因为varchar每次存储都要有额外的计算，得到长度等工作，如果一个非常频繁改变的，那就要有很多的精力用于计算，而这些对于char来说是不需要的。

情况 4 ：具体存储引擎中的情况：

- `MyISAM `数据存储引擎和数据列：MyISAM数据表，最好使用固定长度(CHAR)的数据列代替可变长度(VARCHAR)的数据列。这样使得整个表静态化，从而使**数据检索更快**，用空间换时间。
- `MEMORY` 存储引擎和数据列：MEMORY数据表目前都使用固定长度的数据行存储，因此无论使用CHAR或VARCHAR列都没有关系，两者都是作为CHAR类型处理的。
- `InnoDB`存储引擎，建议使用VARCHAR类型。因为对于InnoDB数据表，内部的行存储格式并没有区分固定长度和可变长度列（所有数据行都使用指向数据列值的头指针），而且 主**要影响性能的因素是数据行使用的存储总量** ，由于char平均占用的空间多于varchar，所以除了简短并且固定长度的，其他考虑varchar。这样节省空间，对磁盘I/O和数据存储总量比较好。

### 7. 2 TEXT类型

在MySQL中，TEXT用来保存文本类型的字符串，总共包含 4 种类型，分别为TINYTEXT、TEXT、MEDIUMTEXT 和 LONGTEXT 类型。

在向TEXT类型的字段保存和查询数据时，系统自动按照实际长度存储，不需要预先定义长度。这一点和VARCHAR类型相同。

每种TEXT类型保存的数据长度和所占用的存储空间不同，如下：

![image-20221011192358765](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192358765.png)

**由于实际存储的长度不确定，MySQL 不允许 TEXT 类型的字段做主键** 。遇到这种情况，你只能采用CHAR(M)，或者 VARCHAR(M)。

**举例：**

创建数据表：

![image-20221011192421144](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192421144.png)

**开发中经验**：

TEXT文本类型，可以存比较大的文本段，搜索速度稍慢，因此如果不是特别大的内容，建议使用CHAR，VARCHAR来代替。还有TEXT类型不用加默认值，加了也没用。而且text和blob类型的数据删除后容易导致
“空洞”，使得文件碎片比较多，所以频繁使用的表不建议包含TEXT类型字段，建议单独分出去，单独用一个表。

## 8. ENUM类型

ENUM类型也叫作枚举类型，ENUM类型的取值范围需要在定义字段时进行指定。设置字段值时，ENUM类型只允许从成员中选取单个值，不能一次选取多个值。

其所需要的存储空间由定义ENUM类型时指定的成员个数决定。

![image-20221011192519118](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192519118.png)

- 当ENUM类型包含 1 ～ 255 个成员时，需要 1 个字节的存储空间；

- 当ENUM类型包含 256 ～ 65535 个成员时，需要 2 个字节的存储空间。

- ENUM类型的成员个数的上限为 65535 个。

举例：

创建表如下：

![image-20221011192548731](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192548731.png)

添加数据：

![image-20221011192556372](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192556372.png)

## 9. SET类型

SET表示一个字符串对象，可以包含 0 个或多个成员，但成员个数的上限为 **64** 。设置字段值时，可以取取值范围内的 0 个或多个值。

当SET类型包含的成员个数不同时，其所占用的存储空间也是不同的，具体如下：

![image-20221011192628377](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192628377.png)

SET类型在存储数据时成员个数越多，其占用的存储空间越大。注意：SET类型在选取成员时，可以一次选择多个成员，这一点与ENUM类型不同。

举例：

创建表：

![image-20221011192653270](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192653270.png)

向表中插入数据：

![image-20221011192702744](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192702744.png)

举例：

![image-20221011192717442](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192717442.png)

## 10. 二进制字符串类型

MySQL中的二进制字符串类型主要存储一些二进制数据，比如可以存储图片、音频和视频等二进制数据。

MySQL中支持的二进制字符串类型主要包括BINARY、VARBINARY、TINYBLOB、BLOB、MEDIUMBLOB 和LONGBLOB类型。

#### BINARY与VARBINARY类型

BINARY和VARBINARY类似于CHAR和VARCHAR，只是它们存储的是二进制字符串。

BINARY (M)为固定长度的二进制字符串，M表示最多能存储的字节数，取值范围是 0 ~ 255 个字符。如果未指定(M)，表示只能存储 **1 个字节**。例如BINARY ( 8 )，表示最多能存储 8 个字节，如果字段值不足(M)个字节，将在右边填充'\ 0 '以补齐指定长度。

VARBINARY (M)为可变长度的二进制字符串，M表示最多能存储的字节数，总字节数不能超过行的字节长度限制 65535 ，另外还要考虑额外字节开销，VARBINARY类型的数据除了存储数据本身外，还需要 1 或 2 个字节来存储数据的字节数。VARBINARY类型**必须指定(M)**，否则报错。

![image-20221011192920879](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192920879.png)

举例：

创建表：

![image-20221011192940408](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192940408.png)

添加数据：

![image-20221011192949901](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011192949901.png)

#### BLOB类型

BLOB是一个**二进制大对象**，可以容纳可变数量的数据。

MySQL中的BLOB类型包括TINYBLOB、BLOB、MEDIUMBLOB和LONGBLOB 4种类型，它们可容纳值的最大长度不同。可以存储一个二进制的大对象，比如**图片、音频和视频**等。

需要注意的是，在实际工作中，往往不会在MySQL数据库中使用BLOB类型存储大对象数据，通常会将图片、音频和视频文件存储到**服务器的磁盘上**，并将图片、音频和视频的访问路径存储到MySQL中。

![image-20221011193033093](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011193033093.png)

举例：

![image-20221011193042038](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011193042038.png)

**TEXT和BLOB的使用注意事项**：

在使用text和blob字段类型时要注意以下几点，以便更好的发挥数据库的性能。

① BLOB和TEXT值也会引起自己的一些问题，特别是执行了大量的删除或更新操作的时候。删除这种值会在数据表中留下很大的"**空洞**"，以后填入这些"空洞"的记录可能长度不同。为了提高性能，建议定期使用 OPTIMIZE TABLE 功能对这类表进行**碎片整理**。

② 如果需要对大文本字段进行模糊查询，MySQL 提供了**前缀索引**。但是仍然要在不必要的时候避免检索大型的BLOB或TEXT值。例如，SELECT * 查询就不是很好的想法，除非你能够确定作为约束条件的
WHERE子句只会找到所需要的数据行。否则，你可能毫无目的地在网络上传输大量的值。

③ 把BLOB或TEXT列**分离到单独的表**中。在某些环境中，如果把这些数据列移动到第二张数据表中，可以让你把原数据表中的数据列转换为固定长度的数据行格式，那么它就是有意义的。这会**减少主表中的碎片**，使你得到固定长度数据行的性能优势。它还使你在主数据表上运行 SELECT * 查询的时候不会通过网络传输大量的BLOB或TEXT值。

## 11. JSON 类型

JSON（JavaScript Object Notation）是一种轻量级的**数据交换格式**。简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言。它易于人阅读和编写，同时也易于机器解析和生成，并有效地提升网络传输效率。**JSON 可以将 JavaScript 对象中表示的一组数据转换为字符串，然后就可以在网络或者程序之间轻松地传递这个字符串，并在需要的时候将它还原为各编程语言所支持的数据格式。**

在MySQL 5.7中，就已经支持JSON数据类型。在MySQL 8.x版本中，JSON类型提供了可以进行自动验证的JSON文档和优化的存储结构，使得在MySQL中存储和读取JSON类型的数据更加方便和高效。 创建数据表，表中包含一个JSON类型的字段 js 。

![image-20221011210208679](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011210208679.png)

向表中插入JSON数据。

![image-20221011210221071](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011210221071.png)

查询t19表中的数据。

![image-20221011210236833](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011210236833.png)

当需要检索JSON类型的字段中数据的某个具体值时，可以使用“->”和“->>”符号。

![image-20221011210246451](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011210246451.png)

通过“->”和“->>”符号，从JSON字段中正确查询出了指定的JSON数据的值。

## 12. 空间类型

MySQL 空间类型扩展支持地理特征的生成、存储和分析。这里的地理特征表示世界上具有位置的任何东西，可以是一个实体，例如一座山；可以是空间，例如一座办公楼；也可以是一个可定义的位置，例如:一个十字路口等等。MySQL中使用**Geometry（几何）**来表示所有地理特征。Geometry指一个点或点的集合，代表世界上任何具有位置的事物。

MySQL的空间数据类型（Spatial Data Type）对应于OpenGIS类，包括单值类型：GEOMETRY、POINT、LINESTRING、POLYGON以及集合类型：MULTIPOINT、MULTILINESTRING、MULTIPOLYGON、
GEOMETRYCOLLECTION 。

- Geometry是所有空间集合类型的基类，其他类型如POINT、LINESTRING、POLYGON都是Geometry的子类。
  - Point，顾名思义就是点，有一个坐标值。例如POINT(121.213342 31.234532)，POINT(30 10)，坐标值支持DECIMAL类型，经度（longitude）在前，维度（latitude）在后，用空格分隔。
  - LineString，线，由一系列点连接而成。如果线从头至尾没有交叉，那就是简单的（simple）；如果起点和终点重叠，那就是封闭的（closed）。例如LINESTRING(30 10,10 30,4040)，点与点之间用逗号分隔，一个点中的经纬度用空格分隔，与POINT格式一致。
  - Polygon，多边形。可以是一个实心平面形，即没有内部边界，也可以有空洞，类似纽扣。最简单的就是只有一个外边界的情况，例如POLYGON((0 0,10 0,10 10, 0 10))。

下面展示几种常见的几何图形元素：

![image-20221011210544799](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011210544799.png)

- MultiPoint、MultiLineString、MultiPolygon、GeometryCollection 这 4 种类型都是集合类，是多个
  Point、LineString或Polygon组合而成。

下面展示的是多个同类或异类几何图形元素的组合：

![image-20221011210611467](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011210611467.png)

## 13. 小结及选择建议

在定义数据类型时，如果确定是**整数**，就用**INT**； 如果是**小数**，一定用定点数类型**DECIMAL(M,D)**； 如果是日期与时间，就用 **DATETIME**。

这样做的好处是，首先确保你的系统不会因为数据类型定义出错。不过，凡事都是有两面的，可靠性好，并不意味着高效。比如，TEXT 虽然使用方便，但是效率不如 CHAR(M) 和 VARCHAR(M)。

关于字符串的选择，建议参考如下阿里巴巴的《Java开发手册》规范：

**阿里巴巴《Java开发手册》之MySQL数据库：**

- 任何字段如果为非负数，必须是 UNSIGNED
- 【**强制**】小数类型为 DECIMAL，禁止使用 FLOAT 和 DOUBLE。
  - 说明：在存储的时候，FLOAT 和 DOUBLE 都存在精度损失的问题，很可能在比较值的时候，得到不正确的结果。如果存储的数据范围超过 DECIMAL 的范围，建议将数据拆成整数和小数并分开存储。
- 【**强制**】如果存储的字符串长度几乎相等，使用 CHAR 定长字符串类型。
- 【**强制**】VARCHAR 是可变长字符串，不预先分配存储空间，长度不要超过 5000 。如果存储长度大于此值，定义字段类型为 TEXT，独立出来一张表，用主键来对应，避免影响其它字段索引效率。





------

# 第 13 章_约束

## 1. 约束(constraint)概述

### 1. 1 为什么需要约束

数据完整性（Data Integrity）是指数据的精确性（Accuracy）和可靠性（Reliability）。它是防止数据库中存在不符合语义规定的数据和防止因错误信息的输入输出造成无效操作或错误信息而提出的。

为了保证数据的完整性，SQL规范以约束的方式对 **表数据进行额外的条件限制** 。从以下四个方面考虑：

- `实体完整性（Entity Integrity）`：例如，同一个表中，不能存在两条完全相同无法区分的记录

- `域完整性（Domain Integrity）`：例如：年龄范围0-120，性别范围“男/女”

- `引用完整性（Referential Integrity）`：例如：员工所在部门，在部门表中要能找到这个部门

- `用户自定义完整性（User-defined Integrity）`：例如：用户名唯一、密码不能为空等，本部门经理的工资不得高于本部门职工的平均工资的 5 倍。

### 1. 2 什么是约束

![image-20221014145702636](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221014145702636.png)

约束是表级的强制规定。

可以在 **创建表时规定约束（通过 CREATE TABLE 语句）** ，或者在 **表创建之后通过 ALTER TABLE 语句规定约束** 。

### 1. 3 约束的分类

- **根据约束数据列的限制**， 约束可分为：
  - **单列约束** ：每个约束只约束一列
  - **多列约束** ：每个约束可约束多列数据

- **根据约束的作用范围** ，约束可分为：
  - **列级约束** ：只能作用在一个列上，跟在列的定义后面
  - **表级约束** ：可以作用在多个列上，不与列一起，而是单独定义

![image-20221011212109098](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212109098.png)

- **根据约束起的作用** ，约束可分为：
  - **NOT NULL 非空约束，规定某个字段不能为空**
  - **UNIQUE 唯一约束 ， 规定某个字段在整个表中是唯一的**
  - **PRIMARY KEY 主键(非空且唯一)约束**
  - **FOREIGN KEY 外键约束**
  - **CHECK 检查约束**
  - **DEFAULT 默认值约束**

注意： MySQL不支持check约束，但可以使用check约束，而没有任何效果

- 查看某个表已有的约束

![image-20221011212218519](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212218519.png)

## 2. 非空约束

### 2. 1 作用

限定某个字段/某列的值不允许为空

![image-20221011212246572](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212246572.png)

### 2. 2 关键字

NOT NULL

### 2. 3 特点

- 默认，所有的类型的值都可以是NULL，包括INT、FLOAT等数据类型

- 非空约束只能出现在表对象的列上，只能某个列单独限定非空，不能组合非空

- 一个表可以有很多列都分别限定了非空

- 空字符串''不等于NULL， 0 也不等于NULL

### 2. 4 添加非空约束

（ 1 ）建表时

![image-20221011212330954](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212330954.png)

举例：

![image-20221011212346606](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212346606.png)

（ 2 ）建表后

![image-20221011212411924](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212411924.png)

举例：

![image-20221011212420860](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212420860.png)

### 2. 5 删除非空约束

![image-20221011212623008](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212623008.png)

举例：

![image-20221011212633082](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011212633082.png)

## 3. 唯一性约束

### 3. 1 作用

用来限制某个字段/某列的值不能重复。

![image-20221011213002546](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213002546.png)

### 3. 2 关键字

UNIQUE

### 3. 3 特点

- 同一个表可以有多个唯一约束。

- 唯一约束可以是某一个列的值唯一，也可以多个列组合的值唯一。

- 唯一性约束允许列值为空。

- 在创建唯一约束的时候，如果不给唯一约束命名，就默认和列名相同。

- **MySQL会给唯一约束的列上默认创建一个唯一索引。**

### 3. 4 添加唯一约束

（ 1 ）建表时

![image-20221011213106193](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213106193.png)

举例：

![image-20221011213121088](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213121088.png)

表示用户名和密码组合不能重复

![image-20221011213246017](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213246017.png)

（ 2 ）建表后指定唯一键约束

![image-20221011213306363](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213306363.png)

举例：

![image-20221011213346728](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213346728.png)

![image-20221011213355539](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213355539.png)

举例：

![image-20221011213426585](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213426585.png)

### 3. 5 关于复合唯一约束

![image-20221011213510507](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213510507.png)

![image-20221011213522493](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213522493.png)

### 3. 6 删除唯一约束

- 添加唯一性约束的列上也会自动创建唯一索引。

- 删除唯一约束只能通过删除唯一索引的方式删除。

- 删除时需要指定唯一索引名，唯一索引名就和唯一约束名一样。

- 如果创建唯一约束时未指定名称，如果是单列，就默认和列名相同；如果是组合列，那么默认和()中排在第一个的列名相同。也可以自定义唯一性约束名。

![image-20221011213628042](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213628042.png)

注意：可以通过 **show index from** 表名称;查看表的索引

## 4. PRIMARY KEY 约束

### 4. 1 作用

用来唯一标识表中的一行记录。

### 4. 2 关键字

primary key

### 4. 3 特点

- 主键约束相当于 **唯一约束+非空约束的组合** ，主键约束列不允许重复，也不允许出现空值。

![image-20221011213929332](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011213929332.png)

- 一个表最多只能有一个主键约束，建立主键约束可以在列级别创建，也可以在表级别上创建。

- 主键约束对应着表中的一列或者多列（复合主键）

- 如果是多列组合的复合主键约束，那么这些列都不允许为空值，并且组合的值不允许重复。

- **MySQL的主键名总是PRIMARY** ，就算自己命名了主键约束名也没用。

- 当创建主键约束时，系统默认会在所在的列或列组合上建立对应的 主键索引 （能够根据主键查询的，就根据主键查询，效率更高）。如果删除主键约束了，主键约束对应的索引就自动删除了。

- 需要注意的一点是，不要修改主键字段的值。因为主键是数据记录的唯一标识，如果修改了主键的值，就有可能会破坏数据的完整性。

### 4. 4 添加主键约束

（ 1 ）建表时指定主键约束

![image-20221011214023287](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214023287.png)

举例：

![image-20221011214045543](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214045543.png)

![image-20221011214101009](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214101009.png)

再举例：

- 列级约束

![image-20221011214120849](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214120849.png)

- 表级约束

![image-20221011214132560](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214132560.png)

（ 2 ）建表后增加主键约束

![image-20221011214151371](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214151371.png)

![image-20221011214158277](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011214158277.png)

### 4. 5 关于复合主键

![image-20221011221829631](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011221829631.png)

![image-20221011221844175](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011221844175.png)

![image-20221011221855767](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011221855767.png)

- 再举例

![image-20221011221915871](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011221915871.png)

### 4. 6 删除主键约束

![image-20221011221937689](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011221937689.png)

举例：

![image-20221011221947099](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011221947099.png)

说明：删除主键约束，不需要指定主键名，因为一个表只有一个主键，删除主键约束后，非空还在。

## 5. 自增列：AUTO_INCREMENT

### 5. 1 作用

某个字段的值自增

### 5. 2 关键字

auto_increment

### 5. 3 特点和要求

（ 1 ）一个表最多只能有一个自增长列

（ 2 ）当需要产生唯一标识符或顺序值时，可设置自增长

（ 3 ）自增长列约束的列必须是键列（主键列，唯一键列）

（ 4 ）自增约束的列的数据类型必须是整数类型

（ 5 ）如果自增列指定了 0 和 null，会在当前最大值的基础上自增；如果自增列手动指定了具体值，直接赋值为具体值。

错误演示：

![image-20221011222039578](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222039578.png)

### 5. 4 如何指定自增约束

**（ 1 ）建表时**

![image-20221011222103488](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222103488.png)

![image-20221011222111976](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222111976.png)

**（ 2 ）建表后**

![image-20221011222135354](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222135354.png)

例如：

![image-20221011222144990](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222144990.png)

### 5. 5 如何删除自增约束

![image-20221011222203656](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222203656.png)

### 5. 6 MySQL 8. 0 新特性—自增变量的持久化

在MySQL 8.0之前，自增主键AUTO_INCREMENT的值如果大于max(primary key)+1，在MySQL重启后，会重置AUTO_INCREMENT=max(primary key)+1，这种现象在某些情况下会导致业务主键冲突或者其他难以发现的问题。 下面通过案例来对比不同的版本中自增变量是否持久化。 在MySQL 5.7版本中，测试步骤如下： 创建的数据表中包含自增主键的id字段，语句如下：

![image-20221011222242537](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222242537.png)

插入 4 个空值，执行如下：

![image-20221011222256308](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222256308.png)

查询数据表test1中的数据，结果如下：

![image-20221011222309379](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222309379.png)

删除id为 4 的记录，语句如下：

![image-20221011222320634](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222320634.png)

再次插入一个空值，语句如下：

![image-20221011222332568](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222332568.png)

查询此时数据表test1中的数据，结果如下：

![image-20221011222345648](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222345648.png)

从结果可以看出，虽然删除了id为 4 的记录，但是再次插入空值时，并没有重用被删除的 4 ，而是分配了5 。 删除id为 5 的记录，结果如下：

![image-20221011222408217](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222408217.png)

**重启数据库** ，重新插入一个空值。

![image-20221011222418172](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222418172.png)

再次查询数据表test1中的数据，结果如下：

![image-20221011222438787](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222438787.png)

从结果可以看出，新插入的 0 值分配的是 4 ，按照重启前的操作逻辑，此处应该分配 6 。出现上述结果的主要原因是自增主键没有持久化。 在MySQL 5. 7 系统中，对于自增主键的分配规则，是由InnoDB数据字典内部一个**计数器**来决定的，而该计数器只在**内存中维护**，并不会持久化到磁盘中。当数据库重启时，该计数器会被初始化。

在MySQL 8. 0 版本中，上述测试步骤最后一步的结果如下：

![image-20221011222607010](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011222607010.png)

从结果可以看出，自增变量已经持久化了。

MySQL 8. 0 将自增主键的计数器持久化到**重做日志**中。每次计数器发生改变，都会将其写入重做日志中。如果数据库重启，InnoDB会根据重做日志中的信息来初始化计数器的内存值。

## 6. FOREIGN KEY 约束

### 6. 1 作用

限定某个表的某个字段的引用完整性。

比如：员工表的员工所在部门的选择，必须在部门表能找到对应的部分。

![image-20221011223107575](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223107575.png)

### 6. 2 关键字

FOREIGN KEY

### 6. 3 主表和从表/父表和子表

主表（父表）：被引用的表，被参考的表

从表（子表）：引用别人的表，参考别人的表

例如：员工表的员工所在部门这个字段的值要参考部门表：部门表是主表，员工表是从表。

例如：学生表、课程表、选课表：选课表的学生和课程要分别参考学生表和课程表，学生表和课程表是主表，选课表是从表。

### 6. 4 特点

（ 1 ）从表的外键列，必须引用/参考主表的主键或唯一约束的列为什么？因为被依赖/被参考的值必须是唯一的

（ 2 ）在创建外键约束时，如果不给外键约束命名， **默认名不是列名，而是自动产生一个外键名** （例如student_ibfk_1;），也可以指定外键约束名。

（ 3 ）创建(CREATE)表时就指定外键约束的话，先创建主表，再创建从表

（ 4 ）删表时，先删从表（或先删除外键约束），再删除主表

（ 5 ）当主表的记录被从表参照时，主表的记录将不允许删除，如果要删除数据，需要先删除从表中依赖该记录的数据，然后才可以删除主表的数据

（ 6 ）在“从表”中指定外键约束，并且一个表可以建立多个外键约束

（ 7 ）从表的外键列与主表被参照的列名字可以不相同，但是数据类型必须一样，逻辑意义一致。如果类型不一样，创建子表时，就会出现错误“ERROR 1005 (HY000): Can't create

table'database.tablename'(errno: 150)”。

例如：都是表示部门编号，都是int类型。

（ 8 ） **当创建外键约束时，系统默认会在所在的列上建立对应的普通索引 。**但是索引名是外键的约束名。（根据外键查询效率很高）

（ 9 ）删除外键约束后，必须**手动**删除对应的索引

### 6. 5 添加外键约束

（ 1 ）建表时

![image-20221011223340182](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223340182.png)

（ 2 ）建表后

一般情况下，表与表的关联都是提前设计好了的，因此，会在创建表的时候就把外键约束定义好。不过，如果需要修改表的设计（比如添加新的字段，增加新的关联关系），但没有预先定义外键约束，那么，就要用修改表的方式来补充定义。

格式：

![image-20221011223355768](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223355768.png)

举例：

![image-20221011223410154](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223410154.png)

举例：

![image-20221011223445149](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223445149.png)

### 6. 6 演示问题

（ 1 ）失败：不是键列

![image-20221011223510408](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223510408.png)

（ 2 ）失败：数据类型不一致

![image-20221011223518033](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223518033.png)

（ 3 ）成功，两个表字段名一样

![image-20221011223530814](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223530814.png)

（ 4 ）添加、删除、修改问题

![image-20221011223559974](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223559974.png)

![image-20221011223623781](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011223623781.png)

总结：约束关系是针对双方的

- 添加了外键约束后，主表的修改和删除数据受约束

- 添加了外键约束后，从表的添加和修改数据受约束

- 在从表上建立外键，要求主表必须存在

- 删除主表时，要求从表从表先删除，或将从表中外键引用该主表的关系先删除

### 6. 7 约束等级

- `Cascade方式`：在父表上update/delete记录时，同步update/delete掉子表的匹配记录

- `Set null方式`：在父表上update/delete记录时，将子表上匹配记录的列设为null，但是要注意子表的外键列不能为not null

- `No action方式`：如果子表中有匹配的记录，则不允许对父表对应候选键进行update/delete操作

- `Restrict方式`：同no action， 都是立即检查外键约束

- `Set default方式`（在可视化工具SQLyog中可能显示空白）：父表有变更时，子表将外键列设置成一个默认的值，但Innodb不能识别

如果没有指定等级，就相当于Restrict方式。

对于外键约束，最好是采用: **ON UPDATE CASCADE ON DELETE RESTRICT** 的方式。

（ 1 ）演示 1 ：on update cascade on delete set null

![image-20221011224154848](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224154848.png)

![image-20221011224206554](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224206554.png)

![image-20221011224219683](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224219683.png)

![image-20221011224231791](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224231791.png)

（ 2 ）演示 2 ：on update set null on delete cascade

![image-20221011224327556](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224327556.png)

![image-20221011224354101](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224354101.png)

![image-20221011224404696](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224404696.png)

（ 3 ）演示：on update cascade on delete cascade

![image-20221011224430209](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224430209.png)

![image-20221011224443176](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224443176.png)

![image-20221011224455388](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224455388.png)

![image-20221011224506604](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224506604.png)

### 6. 8 删除外键约束

流程如下：

![image-20221011224540122](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224540122.png)

举例：

![image-20221011224550248](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224550248.png)

### 6. 9 开发场景

- 问题 1 ：如果两个表之间有关系（一对一、一对多），比如：员工表和部门表（一对多），它们之间是否一定要建外键约束？

- - 答：不是的

- 问题 2 ：建和不建外键约束有什么区别？

- - 答：建外键约束，你的操作（创建表、删除表、添加、修改、删除）会受到限制，从语法层面受到限制。例如：在员工表中不可能添加一个员工信息，它的部门的值在部门表中找不到。

不建外键约束，你的操作（创建表、删除表、添加、修改、删除）不受限制，要保证数据的**引用完整性**，只能依靠**程序员的自觉**，或者是**在Java程序中进行限定**。例如：在员工表中，可以添加一个员工的信息，它的部门指定为一个完全不存在的部门。

- 问题 3 ：那么建和不建外键约束和查询有没有关系？

- - 答：没有

在 MySQL 里，外键约束是有成本的，需要消耗系统资源。对于大并发的 SQL 操作，有可能会不适合。比如大型网站的中央数据库，可能会**因为外键约束的系统开销而变得非常慢**。所以， MySQL 允许你不使用系统自带的外键约束，在**应用层面**完成检查数据一致性的逻辑。也就是说，即使你不用外键约束，也要想办法通过应用层面的附加逻辑，来实现外键约束的功能，确保数据的一致性。

### 6. 10 阿里开发规范

【**强制**】不得使用外键与级联，一切外键概念必须在应用层解决。

说明：（概念解释）学生表中的 student_id 是主键，那么成绩表中的 student_id 则为外键。如果更新学生表中的 student_id，同时触发成绩表中的 student_id 更新，即为级联更新。外键与级联更新适用于**单机低并发**，不适合**分布式、高并发集群**；级联更新是强阻塞，存在数据库**更新风暴**的风险；外键影响数据库的插入速度。

## 7. CHECK 约束

### 7. 1 作用

检查某个字段的值是否符号xx要求，一般指的是值的范围

### 2 、关键字

CHECK

### 3 、说明：MySQL 5. 7 不支持

MySQL5.7 可以使用check约束，但check约束对数据验证没有任何作用。添加数据时，没有任何错误或警告

但是 **MySQL 8.0中可以使用check约束了** 。

![image-20221011224931410](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224931410.png)

- 再举例

![image-20221011224945706](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224945706.png)

- 再举例

![image-20221011224957741](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011224957741.png)

- 再举例

![image-20221011225010423](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225010423.png)

## 8. DEFAULT约束

### 8. 1 作用

给某个字段/某列指定默认值，一旦设置默认值，在插入数据时，如果此字段没有显式赋值，则赋值为默认值。

### 8. 2 关键字

DEFAULT

### 8. 3 如何给字段加默认值

（ 1 ）建表时

![image-20221011225057483](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225057483.png)

![image-20221011225121762](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225121762.png)

![image-20221011225131573](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225131573.png)

再举例：

![image-20221011225146288](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225146288.png)

（ 2 ）建表后

![image-20221011225307691](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225307691.png)

![image-20221011225319536](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225319536.png)

### 8. 4 如何删除默认值约束

![image-20221011225334251](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225334251.png)

## 9. 面试

- 面试 1 、为什么建表时，加 not null default '' 或 default 0

- - 答：不想让表中出现null值。

- 面试 2 、为什么不想要 null 的值

- - 答:（ 1 ）不好比较。null是一种特殊值，比较时只能用专门的is null 和 is not null来比较。碰到运算符，通常返回null。
  - （ 2 ）效率不高。影响提高索引效果。因此，我们往往在建表时 not null default '' 或 default 0

- 面试 3 、带AUTO_INCREMENT约束的字段值是从 1 开始的吗？ 
- - 在MySQL中，默认AUTO_INCREMENT的初始值是 1 ，每新增一条记录，字段值自动加 1 。设置自增属性（AUTO_INCREMENT）的时候，还可以指定第一条插入记录的自增字段的值，这样新插入的记录的自增字段值从初始值开始递增，如在表中插入第一条记录，同时指定id值为 5 ，则以后插入的记录的id值就会从 6 开始往上增加。添加主键约束时，往往需要设置字段自动增加属性。

- 面试 4 、并不是每个表都可以任意选择存储引擎？ 
- - 外键约束（FOREIGN KEY）不能跨引擎使用。MySQL支持多种存储引擎，每一个表都可以指定一个不同的存储引擎，需要注意的是：外键约束是用来保证数据的参照完整性的，如果表之间需要关联外键，却指定了不同的存储引擎，那么这些表之间是不能创建外键约束的。所以说，存储引擎的选择也不完全是随意的。





# 第 14 章_视图

## 1. 常见的数据库对象

![image-20221011225750890](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225750890.png)

## 2. 视图概述

![image-20221011225809437](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011225809437.png)

### 2. 1 为什么使用视图？

视图一方面可以帮我们使用表的一部分而不是所有的表，另一方面也可以针对不同的用户制定不同的查询视图。比如，针对一个公司的销售人员，我们只想给他看部分数据，而某些特殊的数据，比如采购的价格，则不会提供给他。再比如，人员薪酬是个敏感的字段，那么只给某个级别以上的人员开放，其他人的查询视图中则不提供这个字段。

刚才讲的只是视图的一个使用场景，实际上视图还有很多作用。最后，我们总结视图的优点。

### 2. 2 视图的理解

- 视图是一种**虚拟表**，本身是**不具有数据**的，占用很少的内存空间，它是 SQL 中的一个重要概念。
- **视图建立在已有表的基础上** , 视图赖以建立的这些表称为 **基表** 。

![image-20221011230107446](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221011230107446.png)

- 视图的创建和删除只影响视图本身，不影响对应的基表。但是当对视图中的数据进行增加、删除和修改操作时，数据表中的数据会相应地发生变化，反之亦然。

- 向视图提供数据内容的语句为 SELECT 语句, 可以将视图理解为 **存储起来的 SELECT 语句**
  - 在数据库中，视图不会保存数据，数据真正保存在数据表中。当对视图中的数据进行增加、删除和修改操作时，数据表中的数据会相应地发生变化；反之亦然。

- 视图，是向用户提供基表数据的另一种表现形式。通常情况下，小型项目的数据库可以不使用视图，但是在大型项目中，以及数据表比较复杂的情况下，视图的价值就凸显出来了，它可以帮助我们把经常查询的结果集放到虚拟表中，提升使用效率。理解和使用起来都非常方便。

## 3. 创建视图

- **在 CREATE VIEW 语句中嵌入子查询**

![image-20221012115939888](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012115939888.png)

- 精简版

![image-20221012115954140](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012115954140.png)

### 3. 1 创建单表视图

举例：

![image-20221012120019152](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120019152.png)

查询视图：

![image-20221012120036730](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120036730.png)

举例：

![image-20221012120048112](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120048112.png)

举例：

![image-20221012120100775](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120100775.png)

说明 1 ：实际上就是我们在 SQL 查询语句的基础上封装了视图 VIEW，这样就会基于 SQL 语句的结果集形成一张虚拟表。

说明 2 ：在创建视图时，没有在视图名后面指定字段列表，则视图中字段列表默认和SELECT语句中的字段列表一致。如果SELECT语句中给字段取了别名，那么视图中的字段名和别名相同。

### 3. 2 创建多表联合视图

举例：

![image-20221012120125261](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120125261.png)

- **利用视图对数据进行格式化**

我们经常需要输出某个格式的内容，比如我们想输出员工姓名和对应的部门名，对应格式为emp_name(department_name)，就可以使用视图来完成数据格式化的操作：

![image-20221012120155482](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120155482.png)

### 3. 3 基于视图创建视图

当我们创建好一张视图之后，还可以在它的基础上继续创建视图。

举例：联合“emp_dept”视图和“emp_year_salary”视图查询员工姓名、部门名称、年薪信息创建“emp_dept_ysalary”视图。

![image-20221012120222927](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120222927.png)

## 4. 查看视图

语法 1 ：查看数据库的表对象、视图对象

![image-20221012120241513](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120241513.png)

语法 2 ：查看视图的结构

![image-20221012120249642](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120249642.png)

语法 3 ：查看视图的属性信息

![image-20221012120301299](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120301299.png)

执行结果显示，注释Comment为VIEW，说明该表为视图，其他的信息为NULL，说明这是一个虚表。

语法 4 ：查看视图的详细定义信息

![image-20221012120312929](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120312929.png)

## 5. 更新视图的数据

### 5. 1 一般情况

MySQL支持使用INSERT、UPDATE和DELETE语句对视图中的数据进行插入、更新和删除操作。当视图中的数据发生变化时，数据表中的数据也会发生变化，反之亦然。

举例：UPDATE操作

![image-20221012120348063](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120348063.png)

![image-20221012120355813](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120355813.png)

举例：DELETE操作

![image-20221012120407583](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120407583.png)

### 5. 2 不可更新的视图

要使视图可更新，视图中的行和底层基本表中的行之间必须存在**一对一**的关系。另外当视图定义出现如下情况时，视图不支持更新操作：

- 在定义视图的时候指定了“ALGORITHM = TEMPTABLE”，视图将不支持INSERT和DELETE操作；

- 视图中不包含基表中所有被定义为非空又未指定默认值的列，视图将不支持INSERT操作；

- 在定义视图的SELECT语句中使用了**JOIN联合查询**，视图将不支持INSERT和DELETE操作；

- 在定义视图的SELECT语句后的字段列表中使用了**数学表达式**或**子查询**，视图将不支持INSERT，也不支持UPDATE使用了数学表达式、子查询的字段值；

- 在定义视图的SELECT语句后的字段列表中使用**DISTINCT、聚合函数、GROUP BY、HAVING、UNION**等，视图将不支持INSERT、UPDATE、DELETE；

- 在定义视图的SELECT语句中包含了子查询，而子查询中引用了FROM后面的表，视图将不支持INSERT、UPDATE、DELETE；

- 视图定义基于一个**不可更新视图**；

- 常量视图。

举例：

![image-20221012120540652](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120540652.png)

从上面的SQL执行结果可以看出，在定义视图的SELECT语句中使用了JOIN联合查询，视图将不支持更新操作。

虽然可以更新视图数据，但总的来说，视图作为虚拟表，主要用于方便查询，不建议更新视图的数据。 对视图数据的更改，都是通过对实际数据表里数据的操作来完成的。

## 6. 修改、删除视图

### 6. 1 修改视图

方式 1 ：使用CREATE OR REPLACE VIEW 子句 修改视图

![image-20221012120608705](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120608705.png)

说明：CREATE VIEW 子句中各列的别名应和子查询中各列相对应。

方式 2 ：ALTER VIEW

修改视图的语法是：

![image-20221012120622887](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120622887.png)

### 6. 2 删除视图

- 删除视图只是删除视图的定义，并不会删除基表的数据。

- 删除视图的语法是：

![image-20221012120645226](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120645226.png)

![image-20221012120653781](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120653781.png)

- 举例：

![image-20221012120708812](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120708812.png)

- 说明：基于视图a、b创建了新的视图c，如果将视图a或者视图b删除，会导致视图c的查询失败。这样的视图c需要手动删除或修改，否则影响使用。

## 7. 总结

### 7. 1 视图优点

1. **操作简单**

将经常使用的查询操作定义为视图，可以使开发人员不需要关心视图对应的数据表的结构、表与表之间的关联关系，也不需要关心数据表之间的业务逻辑和查询条件，而只需要简单地操作视图即可，极大简化了开发人员对数据库的操作。

2. **减少数据冗余**

视图跟实际数据表不一样，它存储的是查询语句。所以，在使用的时候，我们要通过定义视图的查询语句来获取结果集。而视图本身不存储数据，不占用数据存储的资源，减少了数据冗余。

3. **数据安全**

MySQL将用户对数据的**访问限制**在某些数据的结果集上，而这些数据的结果集可以使用视图来实现。用户不必直接查询或操作数据表。这也可以理解为视图具有**隔离性**。视图相当于在用户和实际的数据表之间加了一层虚拟表。

![image-20221012120911191](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012120911191.png)

同时，MySQL可以根据权限将用户对数据的访问限制在某些视图上， **用户不需要查询数据表，可以直接通过视图获取数据表中的信息** 。这在一定程度上保障了数据表中数据的安全性。

**4. 适应灵活多变的需求** 当业务系统的需求发生变化后，如果需要改动数据表的结构，则工作量相对较大，可以使用视图来减少改动的工作量。这种方式在实际工作中使用得比较多。

**5. 能够分解复杂的查询逻辑** 数据库中如果存在复杂的查询逻辑，则可以将问题进行分解，创建多个视图获取数据，再将创建的多个视图结合起来，完成复杂的查询逻辑。

### 7. 2 视图不足

如果我们在实际数据表的基础上创建了视图，那么， **如果实际数据表的结构变更了，我们就需要及时对相关的视图进行相应的维护** 。特别是嵌套的视图（就是在视图的基础上创建视图），维护会变得比较复杂，可**读性不好**，容易变成系统的潜在隐患。因为创建视图的 SQL 查询可能会对字段重命名，也可能包含复杂的逻辑，这些都会增加维护的成本。

实际项目中，如果视图过多，会导致数据库维护成本的问题。

所以，在创建视图的时候，你要结合实际项目需求，综合考虑视图的优点和不足，这样才能正确使用视图，使系统整体达到最优。





------

# 第 15 章_存储过程与函数

MySQL从 5. 0 版本开始支持存储过程和函数。存储过程和函数能够将复杂的SQL逻辑封装在一起，应用程序无须关注存储过程和函数内部复杂的SQL逻辑，而只需要简单地调用存储过程和函数即可。

## 1. 存储过程概述

### 1. 1 理解

**含义** ：存储过程的英文是 **Stored Procedure**。它的思想很简单，就是一组经过**预先编译**的 SQL 语句的封装。

执行过程：存储过程预先存储在 MySQL 服务器上，需要执行的时候，客户端只需要向服务器端发出调用存储过程的命令，服务器端就可以把预先存储好的这一系列 SQL 语句全部执行。

**好处** ：

1 、简化操作，提高了sql语句的重用性，减少了开发程序员的压力

2 、减少操作过程中的失误，提高效率

3 、减少网络传输量（客户端不需要把所有的 SQL 语句通过网络发给服务器）

 4 、减少了 SQL 语句暴露在网上的风险，也提高了数据查询的安全性

**和视图、函数的对比** ：

它和视图有着同样的优点，清晰、安全，还可以减少网络传输量。不过它和视图不同，视图是**虚拟表**，通常不对底层数据表直接操作，而存储过程是程序化的 SQL，可以**直接操作底层数据表**，相比于面向集合的操作方式，能够实现一些更复杂的数据处理。

一旦存储过程被创建出来，使用它就像使用函数一样简单，我们直接通过调用存储过程名即可。相较于函数，存储过程是**没有返回值**的。

### 1. 2 分类

存储过程的参数类型可以是IN、OUT和INOUT。根据这点分类如下：

1 、没有参数（无参数无返回） 

2 、仅仅带 IN 类型（有参数无返回） 

3 、仅仅带 OUT 类型（无参数有返回）

4 、既带 IN 又带 OUT（有参数有返回） 

5 、带 INOUT（有参数有返回）

注意：IN、OUT、INOUT 都可以在一个存储过程中带多个。

## 2. 创建存储过程

### 2. 1 语法分析

语法：

![image-20221012121418225](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121418225.png)

类似于Java中的方法：

![image-20221012121426988](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121426988.png)

说明：

1 、参数前面的符号的意思

- `IN`：当前参数为输入参数，也就是表示入参；

  存储过程只是读取这个参数的值。如果没有定义参数种类，**默认就是 IN**，表示输入参数。

- `OUT`：当前参数为输出参数，也就是表示出参；

  执行完成之后，调用这个存储过程的客户端或者应用程序就可以读取这个参数返回的值了。

- `INOUT`：当前参数既可以为输入参数，也可以为输出参数。

2 、形参类型可以是 MySQL数据库中的任意类型。

3 、`characteristics `表示创建存储过程时指定的对存储过程的约束条件，其取值信息如下：

![image-20221012121505546](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121505546.png)

- `LANGUAGE SQL`：说明存储过程执行体是由SQL语句组成的，当前系统支持的语言为SQL。

- `[NOT] DETERMINISTIC`：指明存储过程执行的结果是否确定。DETERMINISTIC表示结果是确定的。每次执行存储过程时，相同的输入会得到相同的输出。NOT DETERMINISTIC表示结果是不确定的，相同的输入可能得到不同的输出。如果没有指定任意一个值，默认为NOT DETERMINISTIC。

- `{ CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }`：指明子程序使用SQL语句的限制。
  - CONTAINS SQL表示当前存储过程的子程序包含SQL语句，但是并不包含读写数据的SQL语句；
  - NO SQL表示当前存储过程的子程序中不包含任何SQL语句；
  - READS SQL DATA表示当前存储过程的子程序中包含读数据的SQL语句；
  - MODIFIES SQL DATA表示当前存储过程的子程序中包含写数据的SQL语句。
  - 默认情况下，系统会指定为CONTAINS SQL。

- `SQL SECURITY { DEFINER | INVOKER }`：执行当前存储过程的权限，即指明哪些用户能够执行当前存储过程。
  - `DEFINER`表示只有当前存储过程的创建者或者定义者才能执行当前存储过程；
  - `INVOKER`表示拥有当前存储过程的访问权限的用户能够执行当前存储过程。
  - 如果没有设置相关的值，则MySQL默认指定值为DEFINER。
  - `COMMENT 'string'`：注释信息，可以用来描述存储过程。

4 、存储过程体中可以有多条 SQL 语句，如果仅仅一条SQL 语句，则可以省略 BEGIN 和 END编写存储过程并不是一件简单的事情，可能存储过程中需要复杂的 SQL 语句。

![image-20221012121658209](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121658209.png)

5 、需要设置新的结束标记

因为MySQL默认的语句结束符号为分号‘;’。为了避免与存储过程中SQL语句结束符相冲突，需要使用DELIMITER改变存储过程的结束符。

比如：“DELIMITER //”语句的作用是将MySQL的结束符设置为//，并以“END //”结束存储过程。存储过程定义完毕之后再使用“DELIMITER ;”恢复默认结束符。DELIMITER也可以指定其他符号作为结束符。

当使用DELIMITER命令时，应该避免使用反斜杠（‘\’）字符，因为反斜线是MySQL的转义字符。

示例：

![image-20221012121717905](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121717905.png)

### 2. 2 代码举例

举例 1 ：创建存储过程select_all_data()，查看 emps 表的所有数据

![image-20221012121839471](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121839471.png)

举例 2 ：创建存储过程avg_employee_salary()，返回所有员工的平均工资

![image-20221012121856916](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121856916.png)

举例 3 ：创建存储过程show_max_salary()，用来查看“emps”表的最高薪资值。

![image-20221012121923644](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121923644.png)

举例 4 ：创建存储过程show_min_salary()，查看“emps”表的最低薪资值。并将最低薪资通过OUT参数“ms”输出

![image-20221012121938575](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121938575.png)

举例 5 ：创建存储过程show_someone_salary()，查看“emps”表的某个员工的薪资，并用IN参数empname输入员工姓名。

![image-20221012121956981](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012121956981.png)

举例 6 ：创建存储过程show_someone_salary2()，查看“emps”表的某个员工的薪资，并用IN参数empname输入员工姓名，用OUT参数empsalary输出员工薪资。

![image-20221012122016319](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122016319.png)

举例 7 ：创建存储过程show_mgr_name()，查询某个员工领导的姓名，并用INOUT参数“empname”输入员工姓名，输出领导的姓名。

![image-20221012122039662](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122039662.png)

## 3. 调用存储过程

### 3. 1 调用格式

存储过程有多种调用方法。存储过程必须使用CALL语句调用，并且存储过程和数据库相关，如果要执行其他数据库中的存储过程，需要指定数据库名称，例如CALL dbname.procname。

**格式**：

1 、调用in模式的参数：

![image-20221012122110166](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122110166.png)

2 、调用out模式的参数：

![image-20221012122118568](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122118568.png)

3 、调用inout模式的参数：

![image-20221012122128414](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122128414.png)

### 3. 2 代码举例

**举例 1** ：

![image-20221012122203536](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122203536.png)

调用存储过程：

![image-20221012122213411](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122213411.png)

查看返回结果：

![image-20221012122223227](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122223227.png)

该存储过程返回了指定 s_id=101 的水果商提供的水果种类，返回值存储在num变量中，使用SELECT查看，返回结果为 3 。

**举例 2 ：** 创建存储过程，实现累加运算，计算 1+2+...+n 等于多少。具体的代码如下：

![image-20221012122245502](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122245502.png)

如果你用的是 Navicat 工具，那么在编写存储过程的时候，Navicat 会自动设置 DELIMITER 为其他符号，我们不需要再进行 DELIMITER 的操作。

直接使用 **CALL add_num(50);**即可。这里我传入的参数为 50 ，也就是统计 1+2+...+50 的积累之和。

### 3. 3 如何调试

在 MySQL 中，存储过程不像普通的编程语言（比如 VC++、Java 等）那样有专门的集成开发环境。因此，你可以通过 SELECT 语句，把程序执行的中间结果查询出来，来调试一个 SQL 语句的正确性。调试成功之后，把 SELECT 语句后移到下一个 SQL 语句之后，再调试下一个 SQL 语句。这样**逐步推进**，就可以完成对存储过程中所有操作的调试了。当然，你也可以把存储过程中的 SQL 语句复制出来，逐段单独调试。

## 4. 存储函数的使用

前面学习了很多函数，使用这些函数可以对数据进行的各种处理操作，极大地提高用户对数据库的管理效率。MySQL支持自定义函数，定义好之后，调用方式与调用MySQL预定义的系统函数一样。

### 4. 1 语法分析

学过的函数：LENGTH、SUBSTR、CONCAT等

语法格式：

![image-20221012122406919](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122406919.png)

说明：

1 、参数列表：指定参数为IN、OUT或INOUT只对PROCEDURE是合法的，FUNCTION中总是默认为IN参数。

2 、RETURNS type 语句表示函数返回数据的类型；

RETURNS子句只能对FUNCTION做指定，对函数而言这是**强制**的。它用来指定函数的返回类型，而且函数体必须包含一个**RETURN value**句。

3 、characteristic 创建函数时指定的对函数的约束。取值与创建存储过程时相同，这里不再赘述。

4 、函数体也可以用BEGIN...END来表示SQL代码的开始和结束。如果函数体只有一条语句，也可以省略BEGIN...END。

### 4. 2 调用存储函数

在MySQL中，存储函数的使用方法与MySQL内部函数的使用方法是一样的。换言之，用户自己定义的存储函数与MySQL内部函数是一个性质的。区别在于，存储函数是**用户自己定义**的，而内部函数是MySQL的**开发者定义**的。

![image-20221012122518510](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122518510.png)

### 4. 3 代码举例

**举例 1** ：

创建存储函数，名称为email_by_name()，参数定义为空，该函数查询Abel的email，并返回，数据类型为字符串型。

![image-20221012122549601](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122549601.png)

调用：

![image-20221012122601177](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122601177.png)

**举例 2** ：

创建存储函数，名称为email_by_id()，参数传入emp_id，该函数查询emp_id的email，并返回，数据类型为字符串型。

![image-20221012122620452](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122620452.png)

调用：

![image-20221012122633956](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122633956.png)

**举例 3 **：

创建存储函数count_by_id()，参数传入dept_id，该函数查询dept_id部门的员工人数，并返回，数据类型为整型。

![image-20221012122711726](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122711726.png)

调用：

![image-20221012122728241](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122728241.png)

**注意**：

若在创建存储函数中报错“`you might want to use the less safe
log_bin_trust_function_creators variable`”，有两种处理方法：

- 方式 1 ：加上必要的函数特性“[NOT]  DETERMINISTIC”和“{CONTAINS SQL | NO SQL | READS SQL DATA |MODIFIES SQL DATA}”
- 方式 2 ：

![image-20221012122822600](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122822600.png)

### 4. 4 对比存储函数和存储过程

![image-20221012122846438](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122846438.png)

此外， **存储函数可以放在查询语句中使用，存储过程不行** 。反之，存储过程的功能更加强大，包括能够执行对表的操作（比如创建表，删除表等）和事务操作，这些功能是存储函数不具备的。

## 5. 存储过程和函数的查看、修改、删除

### 5. 1 查看

创建完之后，怎么知道我们创建的存储过程、存储函数是否成功了呢？

MySQL存储了存储过程和函数的状态信息，用户可以使用SHOW STATUS语句或SHOW CREATE语句来查看，也可直接从系统的information_schema数据库中查询。这里介绍 3 种方法。

**1. 使用SHOW CREATE语句查看存储过程和函数的创建信息**

基本语法结构如下：

![image-20221012122932272](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122932272.png)

举例：

![image-20221012122946661](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012122946661.png)

**2. 使用SHOW STATUS语句查看存储过程和函数的状态信息**

基本语法结构如下：

![image-20221012123006050](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123006050.png)

这个语句返回子程序的特征，如数据库、名字、类型、创建者及创建和修改日期。

[LIKE 'pattern']：匹配存储过程或函数的名称，可以省略。当省略不写时，会列出MySQL数据库中存在的所有存储过程或函数的信息。 举例：SHOW STATUS语句示例，代码如下：

![image-20221012123034142](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123034142.png)

**3. 从information_schema.Routines表中查看存储过程和函数的信息**

MySQL中存储过程和函数的信息存储在information_schema数据库下的Routines表中。可以通过查询该表的记录来查询存储过程和函数的信息。其基本语法形式如下：

![image-20221012123057045](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123057045.png)

说明：如果在MySQL数据库中存在存储过程和函数名称相同的情况，最好指定ROUTINE_TYPE查询条件来指明查询的是存储过程还是函数。

举例：从Routines表中查询名称为CountProc的存储函数的信息，代码如下：

![image-20221012123108320](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123108320.png)

### 5. 2 修改

修改存储过程或函数，不影响存储过程或函数功能，只是修改相关特性。使用ALTER语句实现。

![image-20221012123126198](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123126198.png)

其中，characteristic指定存储过程或函数的特性，其取值信息与创建存储过程、函数时的取值信息略有不同。

![image-20221012123137843](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123137843.png)

- `CONTAINS SQL`，表示子程序包含SQL语句，但不包含读或写数据的语句。

- `NO SQL`，表示子程序中不包含SQL语句。

- `READS SQL DATA`，表示子程序中包含读数据的语句。

- `MODIFIES SQL DATA`，表示子程序中包含写数据的语句。

- `SQL SECURITY { DEFINER | INVOKER }`，指明谁有权限来执行。
  - `DEFINER`，表示只有定义者自己才能够执行。
  - `INVOKER`，表示调用者可以执行。
- `COMMENT 'string'`，表示注释信息。

修改存储过程使用ALTER PROCEDURE语句，修改存储函数使用ALTER FUNCTION语句。但是，这两个语句的结构是一样的，语句中的所有参数也是一样的。

**举例 1** ：

修改存储过程CountProc的定义。将读写权限改为MODIFIES SQL DATA，并指明调用者可以执行，代码如下：

![image-20221012123404592](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123404592.png)

查询修改后的信息：

![image-20221012123415388](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123415388.png)

结果显示，存储过程修改成功。从查询的结果可以看出，访问数据的权限（SQL_DATA_ ACCESS）已经变成MODIFIES SQL DATA，安全类型（SECURITY_TYPE）已经变成INVOKER。

**举例 2** ：

修改存储函数CountProc的定义。将读写权限改为READS SQL DATA，并加上注释信息“FIND NAME”，代码如下：

![image-20221012123442653](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123442653.png)

存储函数修改成功。从查询的结果可以看出，访问数据的权限（SQL_DATA_ACCESS）已经变成READSSQL DATA，函数注释（ROUTINE_COMMENT）已经变成FIND NAME。

### 5. 3 删除

删除存储过程和函数，可以使用DROP语句，其语法结构如下：

![image-20221012123504375](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123504375.png)

IF EXISTS：如果程序或函数不存储，它可以防止发生错误，产生一个用SHOW WARNINGS查看的警告。

举例：

![image-20221012123517130](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221012123517130.png)

## 6. 关于存储过程使用的争议

尽管存储过程有诸多优点，但是对于存储过程的使用， **一直都存在着很多争议** ，比如有些公司对于大型项目要求使用存储过程，而有些公司在手册中明确禁止使用存储过程，为什么这些公司对存储过程的使用需求差别这么大呢？

### 6. 1 优点

**1 、存储过程可以一次编译多次使用。** 存储过程只在创建时进行编译，之后的使用都不需要重新编译，这就提升了 SQL 的执行效率。

**2 、可以减少开发工作量。** 将代码**封装**成模块，实际上是编程的核心思想之一，这样可以把复杂的问题拆解成不同的模块，然后模块之间可以**重复使用**，在减少开发工作量的同时，还能保证代码的结构清晰。

**3 、存储过程的安全性强。** 我们在设定存储过程的时候可以**设置对用户的使用权限**，这样就和视图一样具有较强的安全性。

**4 、可以减少网络传输量。** 因为代码封装到存储过程中，每次使用只需要调用存储过程即可，这样就减少了网络传输量。

**5 、良好的封装性。** 在进行相对复杂的数据库操作时，原本需要使用一条一条的 SQL 语句，可能要连接多次数据库才能完成的操作，现在变成了一次存储过程，只需要**连接一次即可**。

### 6. 2 缺点

基于上面这些优点，不少大公司都要求大型项目使用存储过程，比如微软、IBM 等公司。但是国内的阿里并不推荐开发人员使用存储过程，这是为什么呢？

**阿里开发规范**

【强制】禁止使用存储过程，存储过程难以调试和扩展，更没有移植性。

存储过程虽然有诸如上面的好处，但缺点也是很明显的。

**1 、可移植性差。** 存储过程不能跨数据库移植，比如在 MySQL、Oracle 和 SQL Server 里编写的存储过程，在换成其他数据库时都需要重新编写。

**2 、调试困难。** 只有少数 DBMS 支持存储过程的调试。对于复杂的存储过程来说，开发和维护都不容易。虽然也有一些第三方工具可以对存储过程进行调试，但要收费。

**3 、存储过程的版本管理很困难。** 比如数据表索引发生变化了，可能会导致存储过程失效。我们在开发软件的时候往往需要进行版本管理，但是存储过程本身没有版本控制，版本迭代更新的时候很麻烦。

**4 、它不适合高并发的场景。** 高并发的场景需要减少数据库的压力，有时数据库会采用分库分表的方式，而且对可扩展性要求很高，在这种情况下，存储过程会变得难以维护，**增加数据库的压力**，显然就不适用了。

**小结：**

存储过程既方便，又有局限性。尽管不同的公司对存储过程的态度不一，但是对于我们开发人员来说，不论怎样，掌握存储过程都是必备的技能之一。





------

# 第 16 章_变量、流程控制与游标

## 1. 变量

在MySQL数据库的存储过程和函数中，可以使用变量来存储查询或计算的中间结果数据，或者输出最终的结果数据。

在 MySQL 数据库中，变量分为**系统变量**以及**用户自定义变量**。

### 1. 1 系统变量

#### 1. 1. 1 系统变量分类

变量由系统定义，不是用户定义，属于**服务器**层面。启动MySQL服务，生成MySQL服务实例期间，MySQL将为MySQL服务器内存中的系统变量赋值，这些系统变量定义了当前MySQL服务实例的属性、特征。这些系统变量的值要么是**编译MySQL时参数**的默认值，要么是**配置文件**（例如my.ini等）中的参数值。大家可以通过网址 https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html 查看MySQL文档的系统变量。

系统变量分为全局系统变量（需要添加**global** 关键字）以及会话系统变量（需要添加 **session** 关键字），有时也把全局系统变量简称为全局变量，有时也把会话系统变量称为local变量。 **如果不写，默认会话级别**。 静态变量（在 MySQL 服务实例运行期间它们的值不能使用 set 动态修改）属于特殊的全局系统变量。

每一个MySQL客户机成功连接MySQL服务器后，都会产生与之对应的会话。会话期间，MySQL服务实例会在MySQL服务器内存中生成与该会话对应的会话系统变量，这些会话系统变量的初始值是全局系统变量值的复制。如下图：

![image-20221026194644829](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026194644829.png)

- 全局系统变量针对于所有会话（连接）有效，但**不能跨重启**

- 会话系统变量仅针对于当前会话（连接）有效。会话期间，当前会话对某个会话系统变量值的修改，不会影响其他会话同一个会话系统变量的值。

- 会话 1 对某个全局系统变量值的修改会导致会话 2 中同一个全局系统变量值的修改。

在MySQL中有些系统变量只能是全局的，例如 max_connections 用于限制服务器的最大连接数；有些系统变量作用域既可以是全局又可以是会话，例如 character_set_client 用于设置客户端的字符集；有些系统变量的作用域只能是当前会话，例如 pseudo_thread_id 用于标记当前会话的 MySQL 连接 ID。

#### 1. 1. 2 查看系统变量

- **查看所有或部分系统变量**

```sql
#查看所有全局变量
SHOW GLOBAL VARIABLES;
#查看所有会话变量
SHOW SESSION VARIABLES;
或
SHOW VARIABLES;
```

```sql
#查看满足条件的部分系统变量。
SHOW GLOBAL VARIABLES LIKE '%标识符%';
#查看满足条件的部分会话变量
SHOW SESSION VARIABLES LIKE '%标识符%';
```

举例：

```sql
SHOW GLOBAL VARIABLES LIKE 'admin_%';
```

- **查看指定系统变量**

作为 MySQL 编码规范，MySQL 中的系统变量以**两个“@”**开头，其中“@@global”仅用于标记全局系统变量，“@@session”仅用于标记会话系统变量。“@@”首先标记会话系统变量，如果会话系统变量不存在，则标记全局系统变量。

```sql
#查看指定的系统变量的值
SELECT @@global.变量名;

#查看指定的会话变量的值
SELECT @@session.变量名;
#或者
SELECT @@变量名;
```

- **修改系统变量的值**

有些时候，数据库管理员需要修改系统变量的默认值，以便修改当前会话或者MySQL服务实例的属性、特征。具体方法：

方式 1 ：修改MySQL**配置文件**，继而修改MySQL系统变量的值（该方法需要重启MySQL服务）

方式 2 ：在MySQL服务运行期间，使用“set”命令重新设置系统变量的值

```sql
#为某个系统变量赋值
#方式1：
SET @@global.变量名=变量值;
#方式2：
SET GLOBAL 变量名=变量值;

#为某个会话变量赋值
#方式1：
SET @@session.变量名=变量值;
#方式2：
SET SESSION 变量名=变量值;
```

举例：

```sql
SELECT @@global.autocommit;
SET GLOBAL autocommit=0;
```

```sql
SELECT @@session.tx_isolation;
SET @@session.tx_isolation='read-uncommitted';
```

```sql
SET GLOBAL max_connections = 1000;
SELECT @@global.max_connections;
```

### 1. 2 用户变量

#### 1. 2. 1 用户变量分类

用户变量是用户自己定义的，作为 MySQL 编码规范，MySQL 中的用户变量以**一个“@”**开头。根据作用范围不同，又分为**会话用户变量**和**局部变量**。

- 会话用户变量：作用域和会话变量一样，只对**当前连接**会话有效。
- 局部变量：只在 BEGIN 和 END 语句块中有效。局部变量只能在**存储过程和函数**中使用。

#### 1. 2. 2 会话用户变量

- **变量的定义**

```sql
#方式1：“=”或“:=”
SET @用户变量 = 值;
SET @用户变量 := 值;

#方式2：“:=” 或 INTO关键字
SELECT @用户变量 := 表达式 [FROM 等子句];
SELECT 表达式 INTO @用户变量 [FROM 等子句];
```

- **查看用户变量的值 （查看、比较、运算等）**

```sql
SELECT @用户变量
```

- 举例

```sql
SET @a = 1;
SELECT @a;
```

```sql
SELECT @num := COUNT(*) FROM employees;
SELECT @num;
```

```sql
SELECT AVG(salary) INTO @avgsalary FROM employees;
SELECT @avgsalary;
```

```sql
SELECT @big; #查看某个未声明的变量时，将得到NULL值
```

#### 1. 2. 3 局部变量

定义：可以使用**DECLARE**语句定义一个局部变量

作用域：仅仅在定义它的 BEGIN ... END 中有效

位置：只能放在 BEGIN ... END 中，而且只能放在第一句

```sql
BEGIN
    #声明局部变量
    DECLARE 变量名1 变量数据类型 [DEFAULT 变量默认值];
    DECLARE 变量名2,变量名3,... 变量数据类型 [DEFAULT 变量默认值];
    #为局部变量赋值
    SET 变量名1 = 值;
    SELECT 值 INTO 变量名2 [FROM 子句];
    #查看局部变量的值
    SELECT 变量1,变量2,变量3;
END
```

**1 .定义变量**

```sql
DECLARE 变量名 类型 [default 值]; # 如果没有DEFAULT子句，初始值为NULL
```

举例：

```sql
DECLARE　myparam　INT　DEFAULT 100;
```

**2 .变量赋值**

方式 1 ：一般用于赋简单的值

```sql
SET 变量名=值;
SET 变量名:=值;
```

方式 2 ：一般用于赋表中的字段值

```sql
SELECT 字段名或表达式 INTO 变量名 FROM 表;
```

**3 .使用变量** （查看、比较、运算等）

```sql
SELECT 局部变量名;
```

```sql
DELIMITER //
CREATE PROCEDURE set_value()
BEGIN
DECLARE emp_name VARCHAR(25);
DECLARE sal DOUBLE(10,2);
SELECT last_name,salary INTO emp_name,sal
FROM employees
WHERE employee_id = 102;
SELECT emp_name,sal;
END //
DELIMITER ;
```

举例 2 ：声明两个变量，求和并打印 （分别使用会话用户变量、局部变量的方式实现）

```sql
#方式1：使用用户变量
SET @m=1;
SET @n=1;
SET @sum=@m+@n;
SELECT @sum;
```

```sql
#方式2：使用局部变量
DELIMITER //
CREATE PROCEDURE add_value()
BEGIN
#局部变量
DECLARE m INT DEFAULT 1;
DECLARE n INT DEFAULT 3;
DECLARE SUM INT;
SET SUM = m+n;
SELECT SUM;
END //
DELIMITER ;
```

举例 3 ：创建存储过程“different_salary”查询某员工和他领导的薪资差距，并用IN参数emp_id接收员工id，用OUT参数dif_salary输出薪资差距结果。

```sql
#声明
DELIMITER //
CREATE PROCEDURE different_salary(IN emp_id INT,OUT dif_salary DOUBLE)
BEGIN
#声明局部变量
DECLARE emp_sal,mgr_sal DOUBLE DEFAULT 0.0;
DECLARE mgr_id INT;

SELECT salary INTO emp_sal FROM employees WHERE employee_id = emp_id;
SELECT manager_id INTO mgr_id FROM employees WHERE employee_id = emp_id;
SELECT salary INTO mgr_sal FROM employees WHERE employee_id = mgr_id;
SET dif_salary = mgr_sal - emp_sal;
END //

DELIMITER ;

#调用
SET @emp_id = 102;
CALL different_salary(@emp_id,@diff_sal);

#查看
SELECT @diff_sal;
```

#### 1. 2. 4 对比会话用户变量与局部变量

![image-20221026194909912](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026194909912.png)

## 2. 定义条件与处理程序

**定义条件**是事先定义程序执行过程中可能遇到的问题，**处理程序**定义了在遇到问题时应当采取的处理方式，并且保证存储过程或函数在遇到警告或错误时能继续执行。这样可以增强存储程序处理问题的能力，避免程序异常停止运行。

说明：定义条件和处理程序在存储过程、存储函数中都是支持的。

### 2. 1 案例分析

**案例分析**： 创建一个名称为“UpdateDataNoCondition”的存储过程。代码如下：

```sql
DELIMITER //
CREATE PROCEDURE UpdateDataNoCondition()
BEGIN
SET @x = 1;
UPDATE employees SET email = NULL WHERE last_name = 'Abel';
SET @x = 2;
UPDATE employees SET email = 'aabbel' WHERE last_name = 'Abel';
SET @x = 3;
END //
DELIMITER ;
```

调用存储过程：

```sql
mysql> CALL UpdateDataNoCondition();
ERROR 1048 (23000): Column 'email' cannot be null
mysql> SELECT @x;
+------+
| @x |
+------+
| 1 |
+------+
1 row in set (0.00 sec)
```

可以看到，此时@x变量的值为 1 。结合创建存储过程的SQL语句代码可以得出：在存储过程中未定义条件和处理程序，且当存储过程中执行的SQL语句报错时，MySQL数据库会抛出错误，并退出当前SQL逻辑，不再向下继续执行。

### 2. 2 定义条件

定义条件就是给MySQL中的错误码命名，这有助于存储的程序代码更清晰。它将一个**错误名字**和**指定的错误条件**关联起来。这个名字可以随后被用在定义处理程序的**DECLARE HANDLER**语句中。

定义条件使用DECLARE语句，语法格式如下：

```sql
DECLARE 错误名称 CONDITION FOR 错误码（或错误条件）
```

错误码的说明：

- **MySQL_error_code**和**sqlstate_value**都可以表示MySQL的错误。
  - MySQL_error_code是数值类型错误代码。
  - sqlstate_value是长度为 5 的字符串类型错误代码。

- 例如，在ERROR 1418 (HY000)中， 1418 是MySQL_error_code，'HY000'是sqlstate_value。

- 例如，在ERROR 1142（ 42000 ）中， 1142 是MySQL_error_code，'42000'是sqlstate_value。

**举例 1** ： 定义“Field_Not_Be_NULL”错误名与MySQL中违反非空约束的错误类型是“ERROR 1048 (23000)”对应。

```sql
#使用MySQL_error_code
DECLARE Field_Not_Be_NULL CONDITION FOR 1048;
#使用sqlstate_value
DECLARE Field_Not_Be_NULL CONDITION FOR SQLSTATE '23000';
```

**举例 2** ： 定义"ERROR 1148(42000)"错误，名称为command_not_allowed。

```sql
#使用MySQL_error_code
DECLARE command_not_allowed CONDITION FOR 1148;
#使用sqlstate_value
DECLARE command_not_allowed CONDITION FOR SQLSTATE '42000';
```

### 2. 3 定义处理程序

可以为SQL执行过程中发生的某种类型的错误定义特殊的处理程序。定义处理程序时，使用DECLARE语句的语法如下：

```sql
DECLARE 处理方式 HANDLER FOR 错误类型 处理语句
```

- **处理方式** ：处理方式有 3 个取值：CONTINUE、EXIT、UNDO。
  - `CONTINUE`：表示遇到错误不处理，继续执行。
  - `EXIT`：表示遇到错误马上退出。
  - `UNDO`：表示遇到错误后撤回之前的操作。MySQL中暂时不支持这样的操作。

- **错误类型** （即条件）可以有如下取值：
  - `SQLSTATE '字符串错误码'`：表示长度为 5 的sqlstate_value类型的错误代码；
  - `MySQL_error_code`：匹配数值类型错误代码；
  - `错误名称`：表示DECLARE ... CONDITION定义的错误条件名称。
  - `SQLWARNING`：匹配所有以 01 开头的SQLSTATE错误代码；
  - NOT FOUND`：匹配所有以 02 开头的SQLSTATE错误代码；
  - `SQLEXCEPTION`：匹配所有没有被SQLWARNING或NOT FOUND捕获的SQLSTATE错误代码；

- **处理语句** ：如果出现上述条件之一，则采用对应的处理方式，并执行指定的处理语句。语句可以是像“**SET 变量 = 值**”这样的简单语句，也可以是使用**BEGIN ... END**编写的复合语句。

定义处理程序的几种方式，代码如下：

```sql
#方法1：捕获sqlstate_value
DECLARE CONTINUE HANDLER FOR SQLSTATE '42S02' SET @info = 'NO_SUCH_TABLE';
#方法2：捕获mysql_error_value
DECLARE CONTINUE HANDLER FOR 1146 SET @info = 'NO_SUCH_TABLE';
#方法3：先定义条件，再调用
DECLARE no_such_table CONDITION FOR 1146;
DECLARE CONTINUE HANDLER FOR NO_SUCH_TABLE SET @info = 'NO_SUCH_TABLE';
#方法4：使用SQLWARNING
DECLARE EXIT HANDLER FOR SQLWARNING SET @info = 'ERROR';
#方法5：使用NOT FOUND
DECLARE EXIT HANDLER FOR NOT FOUND SET @info = 'NO_SUCH_TABLE';
#方法6：使用SQLEXCEPTION
DECLARE EXIT HANDLER FOR SQLEXCEPTION SET @info = 'ERROR';
```

### 2. 4 案例解决

在存储过程中，定义处理程序，捕获sqlstate_value值，当遇到MySQL_error_code值为 1048 时，执行CONTINUE操作，并且将@proc_value的值设置为-1。

```sql
DELIMITER //
CREATE PROCEDURE UpdateDataNoCondition()
BEGIN
#定义处理程序
DECLARE CONTINUE HANDLER FOR 1048 SET @proc_value = -1;
SET @x = 1;
UPDATE employees SET email = NULL WHERE last_name = 'Abel';
SET @x = 2;
UPDATE employees SET email = 'aabbel' WHERE last_name = 'Abel';
SET @x = 3;
END //
DELIMITER ;
```

调用过程：

```sql
mysql> CALL UpdateDataWithCondition();
Query OK, 0 rows affected (0.01 sec)
mysql> SELECT @x,@proc_value;
+------+-------------+
| @x | @proc_value |
+------+-------------+
| 3 | -1 |
+------+-------------+
1 row in set (0.00 sec)
```

**举例**：

创建一个名称为“InsertDataWithCondition”的存储过程，代码如下。

在存储过程中，定义处理程序，捕获sqlstate_value值，当遇到sqlstate_value值为 23000 时，执行EXIT操作，并且将@proc_value的值设置为-1。

```sql
#准备工作
CREATE TABLE departments
AS
SELECT * FROM atguigudb.`departments`;
ALTER TABLE departments
ADD CONSTRAINT uk_dept_name UNIQUE(department_id);
```

```sql
DELIMITER //
CREATE PROCEDURE InsertDataWithCondition()
BEGIN
DECLARE duplicate_entry CONDITION FOR SQLSTATE '23000' ;
DECLARE EXIT HANDLER FOR duplicate_entry SET @proc_value = -1;
SET @x = 1;
INSERT INTO departments(department_name) VALUES('测试');
SET @x = 2;
INSERT INTO departments(department_name) VALUES('测试');
SET @x = 3;
END //
DELIMITER ;
```

调用存储过程：

```sql
mysql> CALL InsertDataWithCondition();
Query OK, 0 rows affected (0.01 sec)
mysql> SELECT @x,@proc_value;
+------+-------------+
| @x | @proc_value |
+------+-------------+
| 2 | -1 |
+------+-------------+
1 row in set (0.00 sec)
```

## 3. 流程控制

解决复杂问题不可能通过一个 SQL 语句完成，我们需要执行多个 SQL 操作。流程控制语句的作用就是控制存储过程中 SQL 语句的执行顺序，是我们完成复杂操作必不可少的一部分。只要是执行的程序，流程就分为三大类：

- **顺序结构**：程序从上往下依次执行
- **分支结构**：程序按条件进行选择执行，从两条或多条路径中选择一条执行
- **循环结构**：程序满足一定条件下，重复执行一组语句

针对于MySQL 的流程控制语句主要有 3 类。注意：只能用于存储程序。

- **条件判断语句**：IF 语句和 CASE 语句
- **循环语句**：LOOP、WHILE 和 REPEAT 语句
- **跳转语句**：ITERATE 和 LEAVE 语句

### 3. 1 分支结构之 IF

- IF 语句的语法结构是：

```sql
IF 表达式1 THEN 操作1
[ELSEIF 表达式2 THEN 操作2]……
[ELSE 操作N]
END IF
```

根据表达式的结果为TRUE或FALSE执行相应的语句。这里“[]”中的内容是可选的。

- 特点：① 不同的表达式对应不同的操作 ② 使用在begin end中

- **举例 1** ：

```sql
IF val IS NULL
THEN SELECT 'val is null';
ELSE SELECT 'val is not null';
END IF;
```

- **举例 2** ： 声明存储过程“update_salary_by_eid1”，定义IN参数emp_id，输入员工编号。判断该员工薪资如果低于 8000 元并且入职时间超过 5 年，就涨薪 500 元；否则就不变。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_by_eid1(IN emp_id INT)
BEGIN
DECLARE emp_salary DOUBLE;
DECLARE hire_year DOUBLE;
SELECT salary INTO emp_salary FROM employees WHERE employee_id = emp_id;
SELECT DATEDIFF(CURDATE(),hire_date)/365 INTO hire_year
FROM employees WHERE employee_id = emp_id;
IF emp_salary < 8000 AND hire_year > 5
THEN UPDATE employees SET salary = salary + 500 WHERE employee_id = emp_id;
END IF;
END //
DELIMITER ;
```

- **举例 3** ： 声明存储过程“update_salary_by_eid2”，定义IN参数emp_id，输入员工编号。判断该员工薪资如果低于 9000 元并且入职时间超过 5 年，就涨薪 500 元；否则就涨薪 100 元。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_by_eid2(IN emp_id INT)
BEGIN
DECLARE emp_salary DOUBLE;
DECLARE hire_year DOUBLE;
SELECT salary INTO emp_salary FROM employees WHERE employee_id = emp_id;
SELECT DATEDIFF(CURDATE(),hire_date)/365 INTO hire_year
FROM employees WHERE employee_id = emp_id;
IF emp_salary < 8000 AND hire_year > 5
THEN UPDATE employees SET salary = salary + 500 WHERE employee_id =
emp_id;
ELSE
UPDATE employees SET salary = salary + 100 WHERE employee_id = emp_id;
END IF;
END //
DELIMITER ;
```

- **举例 4** ： 声明存储过程“update_salary_by_eid3”，定义IN参数emp_id，输入员工编号。判断该员工薪资如果低于 9000 元，就更新薪资为 9000 元；薪资如果大于等于 9000 元且低于 10000 的，但是奖金比例为NULL的，就更新奖金比例为0.01；其他的涨薪 100 元。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_by_eid3(IN emp_id INT)
BEGIN
DECLARE emp_salary DOUBLE;
DECLARE bonus DECIMAL(3,2);
SELECT salary INTO emp_salary FROM employees WHERE employee_id = emp_id;
SELECT commission_pct INTO bonus FROM employees WHERE employee_id = emp_id;
IF emp_salary < 9000
THEN UPDATE employees SET salary = 9000 WHERE employee_id = emp_id;
ELSEIF emp_salary < 10000 AND bonus IS NULL
THEN UPDATE employees SET commission_pct = 0.01 WHERE employee_id =
emp_id;
ELSE
UPDATE employees SET salary = salary + 100 WHERE employee_id = emp_id;
END IF;
END //
DELIMITER ;
```

### 3. 2 分支结构之 CASE

CASE 语句的语法结构 1 ：

```sql
#情况一：类似于switch
CASE 表达式
WHEN 值1 THEN 结果1或语句1(如果是语句，需要加分号)
WHEN 值2 THEN 结果2或语句2(如果是语句，需要加分号)
...
ELSE 结果n或语句n(如果是语句，需要加分号)
END [case]（如果是放在begin end中需要加上case，如果放在select后面不需要）
```

CASE 语句的语法结构 2 ：

```sql
#情况二：类似于多重if
CASE
WHEN 条件1 THEN 结果1或语句1(如果是语句，需要加分号)
WHEN 条件2 THEN 结果2或语句2(如果是语句，需要加分号)
...
ELSE 结果n或语句n(如果是语句，需要加分号)
END [case]（如果是放在begin end中需要加上case，如果放在select后面不需要）
```

- **举例 1** ：

使用CASE流程控制语句的第 1 种格式，判断val值等于 1 、等于 2 ，或者两者都不等。

```sql
CASE val
　　　WHEN 1 THEN SELECT 'val is 1';
　　　WHEN 2 THEN SELECT 'val is 2';
　　　ELSE SELECT 'val is not 1 or 2';
END CASE;
```

- **举例 2** ：

使用CASE流程控制语句的第 2 种格式，判断val是否为空、小于 0 、大于 0 或者等于 0 。

```sql
CASE
WHEN val IS NULL THEN SELECT 'val is null';
WHEN val < 0 THEN SELECT 'val is less than 0';
WHEN val > 0 THEN SELECT 'val is greater than 0';
ELSE SELECT 'val is 0';
END CASE;
```

- **举例 3** ： 声明存储过程“update_salary_by_eid4”，定义IN参数emp_id，输入员工编号。判断该员工薪资如果低于 9000 元，就更新薪资为 9000 元；薪资大于等于 9000 元且低于 10000 的，但是奖金比例为NULL的，就更新奖金比例为0.01；其他的涨薪 100 元。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_by_eid4(IN emp_id INT)
BEGIN
DECLARE emp_sal DOUBLE;
DECLARE bonus DECIMAL(3,2);
SELECT salary INTO emp_sal FROM employees WHERE employee_id = emp_id;
SELECT commission_pct INTO bonus FROM employees WHERE employee_id = emp_id;
CASE
WHEN emp_sal<9000
THEN UPDATE employees SET salary=9000 WHERE employee_id = emp_id;
WHEN emp_sal<10000 AND bonus IS NULL
THEN UPDATE employees SET commission_pct=0.01 WHERE employee_id = emp_id;
ELSE
UPDATE employees SET salary=salary+100 WHERE employee_id = emp_id;
END CASE;
END //
DELIMITER ;
```

- **举例 4** ：声明存储过程update_salary_by_eid5，定义IN参数emp_id，输入员工编号。判断该员工的入职年限，如果是 0 年，薪资涨 50 ；如果是 1 年，薪资涨 100 ；如果是 2 年，薪资涨 200 ；如果是 3 年，薪资涨 300 ；如果是 4 年，薪资涨 400 ；其他的涨薪 500 。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_by_eid5(IN emp_id INT)
BEGIN
DECLARE emp_sal DOUBLE;
DECLARE hire_year DOUBLE;
SELECT salary INTO emp_sal FROM employees WHERE employee_id = emp_id;
SELECT ROUND(DATEDIFF(CURDATE(),hire_date)/365) INTO hire_year FROM employees
WHERE employee_id = emp_id;
CASE hire_year
WHEN 0 THEN UPDATE employees SET salary=salary+50 WHERE employee_id = emp_id;
WHEN 1 THEN UPDATE employees SET salary=salary+100 WHERE employee_id = emp_id;
WHEN 2 THEN UPDATE employees SET salary=salary+200 WHERE employee_id = emp_id;
WHEN 3 THEN UPDATE employees SET salary=salary+300 WHERE employee_id = emp_id;
WHEN 4 THEN UPDATE employees SET salary=salary+400 WHERE employee_id = emp_id;
ELSE UPDATE employees SET salary=salary+500 WHERE employee_id = emp_id;
END CASE;
END //
DELIMITER ;
```

### 3. 3 循环结构之LOOP

LOOP循环语句用来重复执行某些语句。LOOP内的语句一直重复执行直到循环被退出（使用LEAVE子句），跳出循环过程。

LOOP语句的基本格式如下：

```sql
[loop_label:] LOOP
循环执行的语句
END LOOP [loop_label]
```

其中，loop_label表示LOOP语句的标注名称，该参数可以省略。

**举例 1** ：

使用LOOP语句进行循环操作，id值小于 10 时将重复执行循环过程。

```sql
DECLARE id INT DEFAULT 0;
add_loop:LOOP
SET id = id +1;
IF id >= 10 THEN LEAVE add_loop;
END IF;
END LOOP add_loop;
```

**举例 2** ： 当市场环境变好时，公司为了奖励大家，决定给大家涨工资。声明存储过程“update_salary_loop()”，声明OUT参数num，输出循环次数。存储过程中实现循环给大家涨薪，薪资涨为原来的1.1倍。直到全公司的平均薪资达到 12000 结束。并统计循环次数。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_loop(OUT num INT)
BEGIN
DECLARE avg_salary DOUBLE;
DECLARE loop_count INT DEFAULT 0;
SELECT AVG(salary) INTO avg_salary FROM employees;
label_loop:LOOP
IF avg_salary >= 12000 THEN LEAVE label_loop;
END IF;
UPDATE employees SET salary = salary * 1.1;
SET loop_count = loop_count + 1;
SELECT AVG(salary) INTO avg_salary FROM employees;
END LOOP label_loop;
SET num = loop_count;
END //
DELIMITER ;
```

### 3. 4 循环结构之WHILE

WHILE语句创建一个带条件判断的循环过程。WHILE在执行语句执行时，先对指定的表达式进行判断，如果为真，就执行循环内的语句，否则退出循环。WHILE语句的基本格式如下：

```sql
[while_label:] WHILE 循环条件 DO
循环体
END WHILE [while_label];
```

while_label为WHILE语句的标注名称；如果循环条件结果为真，WHILE语句内的语句或语句群被执行，直至循环条件为假，退出循环。

**举例 1** ：

WHILE语句示例，i值小于 10 时，将重复执行循环过程，代码如下：

```sql
DELIMITER //
CREATE PROCEDURE test_while()
BEGIN
DECLARE i INT DEFAULT 0;
WHILE i < 10 DO
SET i = i + 1;
END WHILE;
SELECT i;
END //
DELIMITER ;
#调用
CALL test_while();
```

**举例 2** ： 市场环境不好时，公司为了渡过难关，决定暂时降低大家的薪资。声明存储过程“update_salary_while()”，声明OUT参数num，输出循环次数。存储过程中实现循环给大家降薪，薪资降为原来的90%。直到全公司的平均薪资达到 5000 结束。并统计循环次数。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_while(OUT num INT)
BEGIN
DECLARE avg_sal DOUBLE ;
DECLARE while_count INT DEFAULT 0;
SELECT AVG(salary) INTO avg_sal FROM employees;
WHILE avg_sal > 5000 DO
UPDATE employees SET salary = salary * 0.9;
SET while_count = while_count + 1;
SELECT AVG(salary) INTO avg_sal FROM employees;
END WHILE;
SET num = while_count;
END //
DELIMITER ;
```

### 3. 5 循环结构之REPEAT

REPEAT语句创建一个带条件判断的循环过程。与WHILE循环不同的是，REPEAT 循环首先会执行一次循环，然后在 UNTIL 中进行表达式的判断，如果满足条件就退出，即 END REPEAT；如果条件不满足，则会就继续执行循环，直到满足退出条件为止。

REPEAT语句的基本格式如下：

```sql
[repeat_label:] REPEAT
　　　　循环体的语句
UNTIL 结束循环的条件表达式
END REPEAT [repeat_label]
```

repeat_label为REPEAT语句的标注名称，该参数可以省略；REPEAT语句内的语句或语句群被重复，直至expr_condition为真。

**举例 1** ：

```sql
DELIMITER //
CREATE PROCEDURE test_repeat()
BEGIN
DECLARE i INT DEFAULT 0;
REPEAT
SET i = i + 1;
UNTIL i >= 10
END REPEAT;
SELECT i;
END //
DELIMITER ;
```

**举例 2** ： 当市场环境变好时，公司为了奖励大家，决定给大家涨工资。声明存储过程“update_salary_repeat()”，声明OUT参数num，输出循环次数。存储过程中实现循环给大家涨薪，薪资涨为原来的1.15倍。直到全公司的平均薪资达到 13000 结束。并统计循环次数。

```sql
DELIMITER //
CREATE PROCEDURE update_salary_repeat(OUT num INT)
BEGIN
DECLARE avg_sal DOUBLE ;
DECLARE repeat_count INT DEFAULT 0;
SELECT AVG(salary) INTO avg_sal FROM employees;
REPEAT
UPDATE employees SET salary = salary * 1.15;
SET repeat_count = repeat_count + 1;
SELECT AVG(salary) INTO avg_sal FROM employees;
UNTIL avg_sal >= 13000
END REPEAT;
SET num = repeat_count;
END //
DELIMITER ;
```

**对比三种循环结构**：

1 、这三种循环都可以省略名称，但如果循环中添加了循环控制语句（LEAVE或ITERATE）则必须添加名称。

 2 、 LOOP：一般用于实现简单的"死"循环 

​		WHILE：先判断后执行 

​		REPEAT：先执行后判断，无条件至少执行一次

### 3. 6 跳转语句之LEAVE语句

LEAVE语句：可以用在循环语句内，或者以 BEGIN 和 END 包裹起来的程序体内，表示跳出循环或者跳出程序体的操作。如果你有面向过程的编程语言的使用经验，你可以把 LEAVE 理解为 break。

基本格式如下：

```sql
LEAVE 标记名
```

其中，label参数表示循环的标志。LEAVE和BEGIN ... END或循环一起被使用。

**举例 1** ： 创建存储过程 “leave_begin()”，声明INT类型的IN参数num。给BEGIN...END加标记名，并在BEGIN...END中使用IF语句判断num参数的值。

- 如果num<=0，则使用LEAVE语句退出BEGIN...END；
- 如果num=1，则查询“employees”表的平均薪资；
- 如果num=2，则查询“employees”表的最低薪资；
- 如果num>2，则查询“employees”表的最高薪资。

IF语句结束后查询“employees”表的总人数。

```sql
DELIMITER //
CREATE PROCEDURE leave_begin(IN num INT)
begin_label: BEGIN
IF num<=0
THEN LEAVE begin_label;
ELSEIF num=1
THEN SELECT AVG(salary) FROM employees;
ELSEIF num=2
THEN SELECT MIN(salary) FROM employees;
ELSE
SELECT MAX(salary) FROM employees;
END IF;
SELECT COUNT(*) FROM employees;
END //
DELIMITER ;
```

**举例 2** ：

当市场环境不好时，公司为了渡过难关，决定暂时降低大家的薪资。声明存储过程“leave_while()”，声明OUT参数num，输出循环次数，存储过程中使用WHILE循环给大家降低薪资为原来薪资的90%，直到全公司的平均薪资小于等于 10000 ，并统计循环次数。

```sql
DELIMITER //
CREATE PROCEDURE leave_while(OUT num INT)
BEGIN
#
DECLARE avg_sal DOUBLE;#记录平均工资
DECLARE while_count INT DEFAULT 0; #记录循环次数
SELECT AVG(salary) INTO avg_sal FROM employees; #① 初始化条件
while_label:WHILE TRUE DO #② 循环条件
#③ 循环体
IF avg_sal <= 10000 THEN
LEAVE while_label;
END IF;
UPDATE employees SET salary = salary * 0.9;
SET while_count = while_count + 1;
#④ 迭代条件
SELECT AVG(salary) INTO avg_sal FROM employees;
END WHILE;
#赋值
SET num = while_count;
END //
DELIMITER ;
```

### 3. 7 跳转语句之ITERATE语句

ITERATE语句：只能用在循环语句（LOOP、REPEAT和WHILE语句）内，表示重新开始循环，将执行顺序转到语句段开头处。如果你有面向过程的编程语言的使用经验，你可以把 ITERATE 理解为 continue，意思为“再次循环”。

语句基本格式如下：

```sql
ITERATE label
```

label参数表示循环的标志。ITERATE语句必须跟在循环标志前面。

**举例**： 定义局部变量num，初始值为 0 。循环结构中执行num + 1操作。

- 如果num < 10，则继续执行循环；

- 如果num > 15，则退出循环结构；

```sql
DELIMITER //
CREATE PROCEDURE test_iterate()
BEGIN
DECLARE num INT DEFAULT 0;
my_loop:LOOP
SET num = num + 1;
IF num < 10
THEN ITERATE my_loop;
ELSEIF num > 15
THEN LEAVE my_loop;
END IF;
SELECT '尚硅谷：让天下没有难学的技术';
END LOOP my_loop;
END //
DELIMITER ;
```

## 4. 游标

### 4. 1 什么是游标（或光标）

虽然我们也可以通过筛选条件 WHERE 和 HAVING，或者是限定返回记录的关键字 LIMIT 返回一条记录，但是，却无法在结果集中像指针一样，向前定位一条记录、向后定位一条记录，或者是**随意定位到某一条记录**，并对记录的数据进行处理。

这个时候，就可以用到游标。游标，提供了一种灵活的操作方式，让我们能够对结果集中的每一条记录进行定位，并对指向的记录中的数据进行操作的数据结构。 **游标让 SQL 这种面向集合的语言有了面向过程开发的能力**。

在 SQL 中，游标是一种临时的数据库对象，可以指向存储在数据库表中的数据行指针。这里游标**充当了指针的作用**，我们可以通过操作游标来对数据行进行操作。

MySQL中游标可以在存储过程和函数中使用。

比如，我们查询了 employees 数据表中工资高于 15000 的员工都有哪些：

```sql
SELECT employee_id,last_name,salary FROM employees
WHERE salary > 15000;
```

![image-20221026195825863](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026195825863.png)

这里我们就可以通过游标来操作数据行，如图所示此时游标所在的行是“108”的记录，我们也可以在结果集上滚动游标，指向结果集中的任意一行。

### 4. 2 使用游标步骤

游标必须在声明处理程序之前被声明，并且变量和条件还必须在声明游标或处理程序之前被声明。

如果我们想要使用游标，一般需要经历四个步骤。不同的 DBMS 中，使用游标的语法可能略有不同。

**第一步，声明游标**

在MySQL中，使用DECLARE关键字来声明游标，其语法的基本形式如下：

```sql
DECLARE cursor_name CURSOR FOR select_statement;
```

这个语法适用于 MySQL，SQL Server，DB2 和 MariaDB。如果是用 Oracle 或者 PostgreSQL，需要写成：

```sql
DECLARE cursor_name CURSOR IS select_statement;
```

要使用 SELECT 语句来获取数据结果集，而此时还没有开始遍历数据，这里 select_statement 代表的是SELECT 语句，返回一个用于创建游标的结果集。

比如：

```sql
DECLARE cur_emp CURSOR FOR
SELECT employee_id,salary FROM employees;
```

```sql
DECLARE cursor_fruit CURSOR FOR
SELECT f_name, f_price FROM fruits ;
```

**第二步，打开游标**

打开游标的语法如下：

```sql
OPEN cursor_name
```

当我们定义好游标之后，如果想要使用游标，必须先打开游标。打开游标的时候 SELECT 语句的查询结果集就会送到游标工作区，为后面游标的**逐条读取**结果集中的记录做准备。

```sql
OPEN cur_emp ;
```

**第三步，使用游标（从游标中取得数据）**

语法如下：

```sql
FETCH cursor_name INTO var_name [, var_name] ...
```

这句的作用是使用 cursor_name 这个游标来读取当前行，并且将数据保存到 var_name 这个变量中，游标指针指到下一行。如果游标读取的数据行有多个列名，则在 INTO 关键字后面赋值给多个变量名即可。

注意：var_name必须在声明游标之前就定义好。

```sql
FETCH cur_emp INTO emp_id, emp_sal ;
```

注意： **游标的查询结果集中的字段数，必须跟 INTO 后面的变量数一致** ，否则，在存储过程执行的时候，MySQL 会提示错误。

**第四步，关闭游标**

```sql
CLOSE cursor_name
```

有 OPEN 就会有 CLOSE，也就是打开和关闭游标。当我们使用完游标后需要关闭掉该游标。因为游标会**占用系统资源**，如果不及时关闭， **游标会一直保持到存储过程结束** ，影响系统运行的效率。而关闭游标的操作，会释放游标占用的系统资源。

关闭游标之后，我们就不能再检索查询结果中的数据行，如果需要检索只能再次打开游标。

```sql
CLOSE cur_emp;
```

### 4. 3 举例

创建存储过程“get_count_by_limit_total_salary()”，声明IN参数 limit_total_salary，DOUBLE类型；声明OUT参数total_count，INT类型。函数的功能可以实现累加薪资最高的几个员工的薪资值，直到薪资总和达到limit_total_salary参数的值，返回累加的人数给total_count。

```sql
DELIMITER //
CREATE PROCEDURE get_count_by_limit_total_salary(IN limit_total_salary DOUBLE,OUT
total_count INT)
BEGIN
DECLARE sum_salary DOUBLE DEFAULT 0; #记录累加的总工资
DECLARE cursor_salary DOUBLE DEFAULT 0; #记录某一个工资值
DECLARE emp_count INT DEFAULT 0; #记录循环个数
#定义游标
DECLARE emp_cursor CURSOR FOR SELECT salary FROM employees ORDER BY salary DESC;
#打开游标
OPEN emp_cursor;
REPEAT
#使用游标（从游标中获取数据）
FETCH emp_cursor INTO cursor_salary;
SET sum_salary = sum_salary + cursor_salary;
SET emp_count = emp_count + 1;
UNTIL sum_salary >= limit_total_salary
END REPEAT;
SET total_count = emp_count;
#关闭游标
CLOSE emp_cursor;
END //
DELIMITER ;
```

### 4. 5 小结

游标是 MySQL 的一个重要的功能，为**逐条读取**结果集中的数据，提供了完美的解决方案。跟在应用层面实现相同的功能相比，游标可以在存储程序中使用，效率高，程序也更加简洁。

但同时也会带来一些性能问题，比如在使用游标的过程中，会对数据行进行**加锁**，这样在业务并发量大的时候，不仅会影响业务之间的效率，还会**消耗系统资源**，造成内存不足，这是因为游标是在内存中进行的处理。

建议：养成用完之后就关闭的习惯，这样才能提高系统的整体效率。

## 补充：MySQL 8. 0 的新特性—全局变量的持久化

在MySQL数据库中，全局变量可以通过SET GLOBAL语句来设置。例如，设置服务器语句超时的限制，可以通过设置系统变量max_execution_time来实现：

```sql
SET GLOBAL MAX_EXECUTION_TIME=2000;
```

使用SET GLOBAL语句设置的变量值只会**临时生效**。**数据库重启**后，服务器又会从MySQL配置文件中读取变量的默认值。 MySQL 8.0版本新增了**SET PERSIST**命令。例如，设置服务器的最大连接数为 1000 ：

```sql
SET PERSIST global max_connections = 1000;
```

MySQL会将该命令的配置保存到数据目录下的**mysqld-auto.cnf**文件中，下次启动时会读取该文件，用其中的配置来覆盖默认的配置文件。

举例：

查看全局变量max_connections的值，结果如下：

```sql
mysql> show variables like '%max_connections%';
+------------------------+-------+
| Variable_name | Value |
+------------------------+-------+
| max_connections | 151 |
| mysqlx_max_connections | 100 |
+------------------------+-------+
2 rows in set, 1 warning (0.00 sec)
```

设置全局变量max_connections的值：

```sql
mysql> set persist max_connections=1000;
Query OK, 0 rows affected (0.00 sec)
```

**重启MySQL服务器**，再次查询max_connections的值：

```sql
mysql> show variables like '%max_connections%';
+------------------------+-------+
| Variable_name | Value |
+------------------------+-------+
| max_connections | 1000 |
| mysqlx_max_connections | 100 |
+------------------------+-------+
2 rows in set, 1 warning (0.00 sec)
```





------

# 第 17 章_触发器

在实际开发中，我们经常会遇到这样的情况：有 2 个或者多个相互关联的表，如**商品信息**和**库存信息**分别存放在 2 个不同的数据表中，我们在添加一条新商品记录的时候，为了保证数据的完整性，必须同时在库存表中添加一条库存记录。

这样一来，我们就必须把这两个关联的操作步骤写到程序里面，而且要用**事务**包裹起来，确保这两个操作成为一个**原子操作**，要么全部执行，要么全部不执行。要是遇到特殊情况，可能还需要对数据进行手动维护，这样就**很容易忘记其中的一步**，导致数据缺失。

这个时候，咱们可以使用触发器。 **你可以创建一个触发器，让商品信息数据的插入操作自动触发库存数据的插入操作。** 这样一来，就不用担心因为忘记添加库存数据而导致的数据缺失了。

## 1. 触发器概述

MySQL从**5.0.2**版本开始支持触发器。MySQL的触发器和存储过程一样，都是嵌入到MySQL服务器的一段程序。

触发器是由**事件来触发**某个操作，这些事件包括**INSERT、UPDATE、DELETE**事件。所谓事件就是指用户的动作或者触发某项行为。如果定义了触发程序，当数据库执行这些语句时候，就相当于事件发生了，就会**自动**激发触发器执行相应的操作。

当对数据表中的数据执行插入、更新和删除操作，需要自动执行一些数据库逻辑时，可以使用触发器来实现。

## 2. 触发器的创建

### 2. 1 创建触发器语法

创建触发器的语法结构是：

![image-20221026202258345](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202258345.png)

说明：

- `表名`：表示触发器监控的对象。
- `BEFORE|AFTER`：表示触发的时间。BEFORE 表示在事件之前触发；AFTER 表示在事件之后触发。
- `INSERT|UPDATE|DELETE`：表示触发的事件。
  - INSERT 表示插入记录时触发；
  - UPDATE 表示更新记录时触发；
  - DELETE 表示删除记录时触发。

- `触发器执行的语句块`：可以是单条SQL语句，也可以是由BEGIN...END结构组成的复合语句块。

### 2. 2 代码举例

**举例 1** ：

1 、创建数据表：

![image-20221026202351761](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202351761.png)

2 、创建触发器：创建名称为before_insert的触发器，向test_trigger数据表插入数据之前，向test_trigger_log数据表中插入before_insert的日志信息。

![image-20221026202412638](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202412638.png)

3 、向test_trigger数据表中插入数据

![image-20221026202427613](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202427613.png)

4 、查看test_trigger_log数据表中的数据

![image-20221026202438551](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202438551.png)

**举例 2** ：

1 、创建名称为after_insert的触发器，向test_trigger数据表插入数据之后，向test_trigger_log数据表中插入after_insert的日志信息。

![image-20221026202500365](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202500365.png)

2 、向test_trigger数据表中插入数据。

![image-20221026202515513](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202515513.png)

3 、查看test_trigger_log数据表中的数据

![image-20221026202528716](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202528716.png)

**举例 3 ：** 定义触发器“salary_check_trigger”，基于员表“employees”的INSERT事件，在INSERT之前检查将要添加的新员工薪资是否大于他领导的薪资，如果大于领导薪资，则报sqlstate_value为'HY000'的错误，从而使得添加失败。

![image-20221026202549188](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202549188.png)

上面触发器声明过程中的NEW关键字代表INSERT添加语句的新记录。

## 3. 查看、删除触发器

### 3. 1 查看触发器

查看触发器是查看数据库中已经存在的触发器的定义、状态和语法信息等。

方式 1 ：查看当前数据库的所有触发器的定义

```sql
SHOW TRIGGERS\G
```

方式 2 ：查看当前数据库中某个触发器的定义

```sql
SHOW CREATE TRIGGER 触发器名
```

方式 3 ：从系统库information_schema的TRIGGERS表中询“salary_check_trigger”触发器的信息。

```sql
SELECT * FROM information_schema.TRIGGERS;
```

### 3. 2 删除触发器

触发器也是数据库对象，删除触发器也用DROP语句，语法格式如下：

```sql
DROP TRIGGER IF EXISTS 触发器名称;
```

## 4. 触发器的优缺点

### 4. 1 优点

**1 、触发器可以确保数据的完整性** 。

假设我们用**进货单头表**（demo.importhead）来保存进货单的总体信息，包括进货单编号、供货商编号、仓库编号、总计进货数量、总计进货金额和验收日期。

![image-20221026202744728](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202744728.png)

用**进货单明细表**（demo.importdetails）来保存进货商品的明细，包括进货单编号、商品编号、进货数量、进货价格和进货金额。

![image-20221026202804843](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202804843.png)

每当我们录入、删除和修改一条进货单明细数据的时候，进货单明细表里的数据就会发生变动。这个时候，在进货单头表中的总计数量和总计金额就必须重新计算，否则，进货单头表中的总计数量和总计金额就不等于进货单明细表中数量合计和金额合计了，这就是数据不一致。

为了解决这个问题，我们就可以使用触发器， **规定每当进货单明细表有数据插入、修改和删除的操作时，自动触发 2 步操作**：

1 ）重新计算进货单明细表中的数量合计和金额合计；

2 ）用第一步中计算出来的值更新进货单头表中的合计数量与合计金额。

这样一来，进货单头表中的合计数量与合计金额的值，就始终与进货单明细表中计算出来的合计数量与合计金额的值相同，数据就是一致的，不会互相矛盾。

**2 、触发器可以帮助我们记录操作日志**。

利用触发器，可以具体记录什么时间发生了什么。比如，记录修改会员储值金额的触发器，就是一个很好的例子。这对我们还原操作执行时的具体场景，更好地定位问题原因很有帮助。

**3 、触发器还可以用在操作数据前，对数据进行合法性检查**。

比如，超市进货的时候，需要库管录入进货价格。但是，人为操作很容易犯错误，比如说在录入数量的时候，把条形码扫进去了；录入金额的时候，看串了行，录入的价格远超售价，导致账面上的巨亏......这些都可以通过触发器，在实际插入或者更新操作之前，对相应的数据进行检查，及时提示错误，防止错误数据进入系统。

### 4. 2 缺点

**1 、触发器最大的一个问题就是可读性差**。

因为触发器存储在数据库中，并且由事件驱动，这就意味着触发器有可能不受应用层的控制。这对系统维护是非常有挑战的。

比如，创建触发器用于修改会员储值操作。如果触发器中的操作出了问题，会导致会员储值金额更新失败。我用下面的代码演示一下：

![image-20221026202938685](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026202938685.png)

结果显示，系统提示错误，字段“aa”不存在。

这是因为，触发器中的数据插入操作多了一个字段，系统提示错误。可是，如果你不了解这个触发器，很可能会认为是更新语句本身的问题，或者是会员信息表的结构出了问题。说不定你还会给会员信息表添加一个叫“aa”的字段，试图解决这个问题，结果只能是白费力。

**2 、相关数据的变更，可能会导致触发器出错。**

特别是数据表结构的变更，都可能会导致触发器出错，进而影响数据操作的正常运行。这些都会由于触发器本身的隐蔽性，影响到应用中错误原因排查的效率。

### 4. 3 注意点

注意，如果在子表中定义了外键约束，并且外键指定了ON UPDATE/DELETE CASCADE/SET NULL子句，此时修改父表被引用的键值或删除父表被引用的记录行时，也会引起子表的修改和删除操作，此时基于子表的UPDATE和DELETE语句定义的触发器并不会被激活。

例如：基于子表员工表（t_employee）的DELETE语句定义了触发器t1，而子表的部门编号（did）字段定义了外键约束引用了父表部门表（t_department）的主键列部门编号（did），并且该外键加了“ON
DELETE SET NULL”子句，那么如果此时删除父表部门表（t_department）在子表员工表（t_employee）有匹配记录的部门记录时，会引起子表员工表（t_employee）匹配记录的部门编号（did）修改为NULL，

但是此时不会激活触发器t1。只有直接对子表员工表（t_employee）执行DELETE语句时才会激活触发器t1。





------

# 第 18 章_MySQL 8 其它新特性

## 1. MySQL 8 新特性概述

**MySQL从5.7版本直接跳跃发布了8.0版本**，可见这是一个令人兴奋的里程碑版本。MySQL 8版本在功能上做了显著的改进与增强，开发者对MySQL的源代码进行了重构，最突出的一点是多MySQL Optimizer优化器进行了改进。不仅在速度上得到了改善，还为用户带来了更好的性能和更棒的体验。

### 1. 1 MySQL 8. 0 新增特性

**1. 更简便的NoSQL支持** NoSQL泛指非关系型数据库和数据存储。随着互联网平台的规模飞速发展，传统的关系型数据库已经越来越不能满足需求。从5.6版本开始，MySQL就开始支持简单的NoSQL存储功能。MySQL 8对这一功能做了优化，以更灵活的方式实现NoSQL功能，不再依赖模式（schema）。

**2. 更好的索引** 在查询中，正确地使用索引可以提高查询的效率。MySQL 8中新增了**隐藏索引**和**降序索引**。隐藏索引可以用来测试去掉索引对查询性能的影响。在查询中混合存在多列索引时，使用降序索引可以提高查询的性能。

**3 .更完善的JSON支持** MySQL从5.7开始支持原生JSON数据的存储，MySQL 8对这一功能做了优化，增加了聚合函数**JSON_ARRAYAGG()**和**JSON_OBJECTAGG()**，将参数聚合为JSON数组或对象，新增了行内操作符 ->>，是列路径运算符 ->的增强，对JSON排序做了提升，并优化了JSON的更新操作。

**4 .安全和账户管理** MySQL 8中新增了**caching_sha2_password** 授权插件、角色、密码历史记录和FIPS模式支持，这些特性提高了数据库的安全性和性能，使数据库管理员能够更灵活地进行账户管理工作。

**5 .InnoDB的变化** **InnoDB是MySQL默认的存储引擎**，是事务型数据库的首选引擎，支持事务安全表（ACID），支持行锁定和外键。在MySQL 8 版本中，InnoDB在自增、索引、加密、死锁、共享锁等方面做了大量的**改进和优化**，并且支持原子数据定义语言（DDL），提高了数据安全性，对事务提供更好的支持。

**6 .数据字典** 在之前的MySQL版本中，字典数据都存储在元数据文件和非事务表中。从MySQL 8开始新增了事务数据字典，在这个字典里存储着数据库对象信息，这些数据字典存储在内部事务表中。

**7. 原子数据定义语句** MySQL 8开始支持原子数据定义语句（Automic DDL），即原子DDL。目前，只有InnoDB存储引擎支持**原子DDL**。原子数据定义语句（DDL）将与DDL操作相关的数据字典更新、存储引擎操作、二进制日志写入结合到一个单独的原子事务中，这使得即使服务器崩溃，事务也会提交或回滚。使用支持原子操作的存储引擎所创建的表，在执行DROP TABLE、CREATE TABLE、ALTER TABLE、RENAME TABLE、TRUNCATE TABLE、CREATE TABLESPACE、DROP TABLESPACE等操作时，都支持原子操作，即事务要么完全操作成功，要么失败后回滚，不再进行部分提交。 对于从MySQL 5.7复制到MySQL 8版本中的语句，可以添加**IF EXISTS**或**IF NOT EXISTS**语句来避免发生错误。

**8 .资源管理** MySQL 8开始支持创建和管理资源组，允许将服务器内运行的线程分配给特定的分组，以便线程根据组内可用资源执行。组属性能够控制组内资源，启用或限制组内资源消耗。数据库管理员能够根据不同的工作负载适当地更改这些属性。 目前，CPU时间是可控资源，由“虚拟CPU”这个概念来表示，此术语包含CPU的核心数，超线程，硬件线程等等。服务器在启动时确定可用的虚拟CPU数量。拥有对应权限的数据库管理员可以将这些CPU与资源组关联，并为资源组分配线程。 资源组组件为MySQL中的资源组管理提供了SQL接口。资源组的属性用于定义资源组。MySQL中存在两个默认组，系统组和用户组，默认的组不能被删除，其属性也不能被更改。对于用户自定义的组，资源组创建时可初始化所有的属性，除去名字和类型，其他属性都可在创建之后进行更改。 在一些平台下，或进行了某些MySQL的配置时，资源管理的功能将受到限制，甚至不可用。例如，如果安装了线程池插件，或者使用的是macOS系统，资源管理将处于不可用状态。在FreeBSD和Solaris系统中，资源线程优先级将失效。在Linux系统中，只有配置了CAP_SYS_NICE属性，资源管理优先级才能发挥作用。

**9 .字符集支持** MySQL 8中默认的字符集由**latin1**更改为**utf8mb4**，并首次增加了日语所特定使用的集合，utf8mb4_ja_0900_as_cs。

**10 .优化器增强** MySQL优化器开始支持隐藏索引和降序索引。隐藏索引不会被优化器使用，验证索引的必要性时不需要删除索引，先将索引隐藏，如果优化器性能无影响就可以真正地删除索引。降序索引允许优化器对多个列进行排序，并且允许排序顺序不一致。

**11 .公用表表达式** 公用表表达式（Common Table Expressions）简称为CTE，MySQL现在支持递归和非递归两种形式的CTE。CTE通过在SELECT语句或其他特定语句前**使用WITH语句对临时结果集**进行命名。

基础语法如下：

```sql
WITH cte_name (col_name1,col_name2 ...) AS (Subquery)
SELECT * FROM cte_name;
```

Subquery代表子查询，子查询前使用WITH语句将结果集命名为cte_name，在后续的查询中即可使用cte_name进行查询。

**12 .窗口函数** MySQL 8开始支持窗口函数。在之前的版本中已存在的大部分**聚合函数**在MySQL 8中也可以作为窗口函数来使用。

![image-20221026203453730](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026203453730.png)

**13 .正则表达式支持** MySQL在8.0.4以后的版本中采用支持Unicode的国际化组件库实现正则表达式操作，这种方式不仅能提供完全的Unicode支持，而且是多字节安全编码。MySQL增加了REGEXP_LIKE()、EGEXP_INSTR()、REGEXP_REPLACE()和 REGEXP_SUBSTR()等函数来提升性能。另外，regexp_stack_limit和regexp_time_limit 系统变量能够通过匹配引擎来控制资源消耗。

**14 .内部临时表**   **TempTable存储引擎取代MEMORY存储引擎成为内部临时表的默认存储引擎**。TempTable存储引擎为VARCHAR和VARBINARY列提供高效存储。internal_tmp_mem_storage_engine会话变量定义了内部临时表的存储引擎，可选的值有两个，TempTable和MEMORY，其中TempTable为默认的存储引擎。temptable_max_ram系统配置项定义了TempTable存储引擎可使用的最大内存数量。

**15 .日志记录** 在MySQL 8中错误日志子系统由一系列MySQL组件构成。这些组件的构成由系统变量log_error_services来配置，能够实现日志事件的过滤和写入。

**16 .备份锁** 新的备份锁允许在线备份期间执行数据操作语句，同时阻止可能造成快照不一致的操作。新备份锁由 LOCK INSTANCE FOR BACKUP 和 UNLOCK INSTANCE 语法提供支持，执行这些操作需要备份管理员特权。

**17 .增强的MySQL复制** MySQL 8复制支持对**JSON文档**进行部分更新的**二进制日志记录**，该记录**使用紧凑的二进制格式**，从而节省记录完整JSON文档的空间。当使用基于语句的日志记录时，这种紧凑的日志记录会自动完成，并且可以通过将新的binlog_row_value_options系统变量值设置为PARTIAL_JSON来启用。

### 1. 2 MySQL 8. 0 移除的旧特性

在MySQL 5.7版本上开发的应用程序如果使用了MySQL8.0 移除的特性，语句可能会失败，或者产生不同的执行结果。为了避免这些问题，对于使用了移除特性的应用，应当尽力修正避免使用这些特性，并尽可能使用替代方法。

**1. 查询缓存**    **查询缓存已被移除**，删除的项有： 

**（ 1 ）语句：** FLUSH QUERY CACHE和RESET QUERYCACHE。 

**（ 2 ）系统变量：** query_cache_limit、query_cache_min_res_unit、query_cache_size、query_cache_type、query_cache_wlock_invalidate。 

**（ 3 ）状态变量：** Qcache_free_blocks、Qcache_free_memory、Qcache_hits、Qcache_inserts、Qcache_lowmem_prunes、Qcache_not_cached、Qcache_queries_in_cache、Qcache_total_blocks。 

**（ 4 ）线程状态：** checking privileges on cached  query、checking query cache for query、invalidating query cache entries、sending cached result to client、storing result in query cache、waiting for query cache lock。

**2 .加密相关** 删除的加密相关的内容有：ENCODE()、DECODE()、ENCRYPT()、DES_ENCRYPT()和DES_DECRYPT()函数，配置项des-key-file，系统变量have_crypt，FLUSH语句的DES_KEY_FILE选项，HAVE_CRYPT CMake选项。 对于移除的ENCRYPT()函数，考虑使用SHA2()替代，对于其他移除的函数，使用AES_ENCRYPT()和AES_DECRYPT()替代。

**3 .空间函数相关** 在MySQL 5.7版本中，多个空间函数已被标记为过时。这些过时函数在MySQL 8中都已被移除，只保留了对应的ST_和MBR函数。

**4 .\N和NULL** 在SQL语句中，解析器不再将\N视为NULL，所以在SQL语句中应使用NULL代替\N。这项变化不会影响使用LOAD DATA INFILE或者SELECT...INTO OUTFILE操作文件的导入和导出。在这类操作中，NULL仍等同于\N。

**5. mysql_install_db** 在MySQL分布中，已移除了mysql_install_db程序，数据字典初始化需要调用带着--initialize或者--initialize-insecure选项的mysqld来代替实现。另外，--bootstrap和INSTALL_SCRIPTDIR CMake也已被删除。

**6 .通用分区处理程序** 通用分区处理程序已从MySQL服务中被移除。为了实现给定表分区，表所使用的存储引擎需要自有的分区处理程序。 提供本地分区支持的MySQL存储引擎有两个，即InnoDB和NDB，而在MySQL 8中只支持InnoDB。

**7 .系统和状态变量信息** 在INFORMATION_SCHEMA数据库中，对系统和状态变量信息不再进行维护。GLOBAL_VARIABLES、SESSION_VARIABLES、GLOBAL_STATUS、SESSION_STATUS表都已被删除。另外，系统变量show_compatibility_56也已被删除。被删除的状态变量有Slave_heartbeat_period、Slave_last_heartbeat,Slave_received_heartbeats、Slave_retried_transactions、Slave_running。以上被删除的内容都可使用性能模式中对应的内容进行替代。

**8 .mysql_plugin工具** mysql_plugin工具用来配置MySQL服务器插件，现已被删除，可使用--plugin-load或--plugin-load-add选项在服务器启动时加载插件或者在运行时使用INSTALL PLUGIN语句加载插件来替代该工具。

## 2. 新特性 1 ：窗口函数

### 2. 1 使用窗口函数前后对比

假设我现在有这样一个数据表，它显示了某购物网站在每个城市每个区的销售额：

![image-20221026203944231](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026203944231.png)

查询：

![image-20221026203954685](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026203954685.png)

**需求**： 现在计算这个网站在每个城市的销售总额、在全国的销售总额、每个区的销售额占所在城市销售额中的比率，以及占总销售额中的比率。

如果用分组和聚合函数，就需要分好几步来计算。

第一步，计算总销售金额，并存入临时表 a：

![image-20221026204016015](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204016015.png)

查看一下临时表 a ：

![image-20221026204059575](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204059575.png)

第二步，计算每个城市的销售总额并存入临时表 b：

![image-20221026204043050](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204043050.png)

查看临时表 b ：

![image-20221026204112468](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204112468.png)

第三步，计算各区的销售占所在城市的总计金额的比例，和占全部销售总计金额的比例。我们可以通过下面的连接查询获得需要的结果：

![image-20221026204128043](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204128043.png)

结果显示：市销售金额、市销售占比、总销售金额、总销售占比都计算出来了。

同样的查询，如果用窗口函数，就简单多了。我们可以用下面的代码来实现：

![image-20221026204143735](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204143735.png)

结果显示，我们得到了与上面那种查询同样的结果。

使用窗口函数，只用了一步就完成了查询。而且，由于没有用到临时表，执行的效率也更高了。很显然， **在这种需要用到分组统计的结果对每一条记录进行计算的场景下，使用窗口函数更好** 。

### 2. 2 窗口函数分类

MySQL从 8. 0 版本开始支持窗口函数。窗口函数的作用类似于在查询中对数据进行分组，不同的是，分组操作会把分组的结果聚合成一条记录，而窗口函数是将结果置于每一条数据记录中。

窗口函数可以分为**静态窗口函数**和**动态窗口函数**。

- 静态窗口函数的窗口大小是固定的，不会因为记录的不同而不同；

- 动态窗口函数的窗口大小会随着记录的不同而变化。

MySQL官方网站窗口函数的网址为 https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_row-number 。

窗口函数总体上可以分为序号函数、分布函数、前后函数、首尾函数和其他函数，如下表：

![image-20221026204256339](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204256339.png)

### 2. 3 语法结构

窗口函数的语法结构是：

```sql
函数 OVER（[PARTITION BY 字段名 ORDER BY 字段名 ASC|DESC]）
```

或者是：

```sql
函数 OVER 窗口名 … WINDOW 窗口名 AS （[PARTITION BY 字段名 ORDER BY 字段名 ASC|DESC]）
```

- OVER 关键字指定函数窗口的范围。
  - 如果省略后面括号中的内容，则窗口会包含满足WHERE条件的所有记录，窗口函数会基于所有满足WHERE条件的记录进行计算。
  - 如果OVER关键字后面的括号不为空，则可以使用如下语法设置窗口。

- 窗口名：为窗口设置一个别名，用来标识窗口。

- PARTITION BY子句：指定窗口函数按照哪些字段进行分组。分组后，窗口函数可以在每个分组中分别执行。

- ORDER BY子句：指定窗口函数按照哪些字段进行排序。执行排序操作使窗口函数按照排序后的数据记录的顺序进行编号。

- FRAME子句：为分区中的某个子集定义规则，可以用来作为滑动窗口使用。

### 2. 4 分类讲解

创建表：

```sql
CREATE TABLE goods(
id INT PRIMARY KEY AUTO_INCREMENT,
category_id INT,
category VARCHAR(15),
NAME VARCHAR(30),
price DECIMAL(10,2),
stock INT,
upper_time DATETIME
);
```

添加数据：

```sql
INSERT INTO goods(category_id,category,NAME,price,stock,upper_time)
VALUES
(1, '女装/女士精品', 'T恤', 39.90, 1000, '2020-11-10 00:00:00'),
(1, '女装/女士精品', '连衣裙', 79.90, 2500, '2020-11-10 00:00:00'),
(1, '女装/女士精品', '卫衣', 89.90, 1500, '2020-11-10 00:00:00'),
(1, '女装/女士精品', '牛仔裤', 89.90, 3500, '2020-11-10 00:00:00'),
(1, '女装/女士精品', '百褶裙', 29.90, 500, '2020-11-10 00:00:00'),
(1, '女装/女士精品', '呢绒外套', 399.90, 1200, '2020-11-10 00:00:00'),
(2, '户外运动', '自行车', 399.90, 1000, '2020-11-10 00:00:00'),
(2, '户外运动', '山地自行车', 1399.90, 2500, '2020-11-10 00:00:00'),
(2, '户外运动', '登山杖', 59.90, 1500, '2020-11-10 00:00:00'),
(2, '户外运动', '骑行装备', 399.90, 3500, '2020-11-10 00:00:00'),
(2, '户外运动', '运动外套', 799.90, 500, '2020-11-10 00:00:00'),
(2, '户外运动', '滑板', 499.90, 1200, '2020-11-10 00:00:00');
```

下面针对goods表中的数据来验证每个窗口函数的功能。

#### 1. 序号函数

**1 ．ROW_NUMBER()函数**

ROW_NUMBER()函数能够对数据中的序号进行顺序显示。

举例：查询 goods 数据表中每个商品分类下价格降序排列的各个商品信息。

```sql
mysql> SELECT ROW_NUMBER() OVER(PARTITION BY category_id ORDER BY price DESC) AS
row_num,
-> id, category_id, category, NAME, price, stock
-> FROM goods;
+---------+----+-------------+---------------+------------+---------+-------+
| row_num | id | category_id | category | NAME | price | stock |
+---------+----+-------------+---------------+------------+---------+-------+
| 1 | 6 | 1 | 女装/女士精品 | 呢绒外套 | 399.90 | 1200 |
| 2 | 3 | 1 | 女装/女士精品 | 卫衣 | 89.90 | 1500 |
| 3 | 4 | 1 | 女装/女士精品 | 牛仔裤 | 89.90 | 3500 |
| 4 | 2 | 1 | 女装/女士精品 | 连衣裙 | 79.90 | 2500 |
| 5 | 1 | 1 | 女装/女士精品 | T恤 | 39.90 | 1000 |
| 6 | 5 | 1 | 女装/女士精品 | 百褶裙 | 29.90 | 500 |
| 1 | 8 | 2 | 户外运动 | 山地自行车 | 1399.90 | 2500 |
| 2 | 11 | 2 | 户外运动 | 运动外套 | 799.90 | 500 |
| 3 | 12 | 2 | 户外运动 | 滑板 | 499.90 | 1200 |
| 4 | 7 | 2 | 户外运动 | 自行车 | 399.90 | 1000 |
| 5 | 10 | 2 | 户外运动 | 骑行装备 | 399.90 | 3500 |
| 6 | 9 | 2 | 户外运动 | 登山杖 | 59.90 | 1500 |
+---------+----+-------------+---------------+------------+---------+-------+
12 rows in set (0.00 sec)
```

举例：查询 goods 数据表中每个商品分类下价格最高的 3 种商品信息。

![image-20221026204550689](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204550689.png)

在名称为“女装/女士精品”的商品类别中，有两款商品的价格为 89. 90 元，分别是卫衣和牛仔裤。两款商品的序号都应该为 2 ，而不是一个为 2 ，另一个为 3 。此时，可以使用RANK()函数和DENSE_RANK()函数解决。

**2 ．RANK()函数**

使用RANK()函数能够对序号进行并列排序，并且会跳过重复的序号，比如序号为 1 、 1 、 3 。

举例：使用RANK()函数获取 goods 数据表中各类别的价格从高到低排序的各商品信息。

![image-20221026204622072](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204622072.png)

举例：使用RANK()函数获取 goods 数据表中类别为“女装/女士精品”的价格最高的 4 款商品信息。

![image-20221026204645292](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204645292.png)

可以看到，使用RANK()函数得出的序号为 1 、 2 、 2 、 4 ，相同价格的商品序号相同，后面的商品序号是不连续的，跳过了重复的序号。

**3 ．DENSE_RANK()函数**

DENSE_RANK()函数对序号进行并列排序，并且不会跳过重复的序号，比如序号为 1 、 1 、 2 。

举例：使用DENSE_RANK()函数获取 goods 数据表中各类别的价格从高到低排序的各商品信息。

![image-20221026204709419](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204709419.png)

举例：使用DENSE_RANK()函数获取 goods 数据表中类别为“女装/女士精品”的价格最高的 4 款商品信息。

```sql
mysql> SELECT *
-> FROM(
-> SELECT DENSE_RANK() OVER(PARTITION BY category_id ORDER BY price DESC) AS
row_num,
-> id, category_id, category, NAME, price, stock
-> FROM goods) t
-> WHERE category_id = 1 AND row_num <= 3;
+---------+----+-------------+---------------+----------+--------+-------+
| row_num | id | category_id | category | NAME | price | stock |
+---------+----+-------------+---------------+----------+--------+-------+
| 1 | 6 | 1 | 女装/女士精品 | 呢绒外套 | 399.90 | 1200 |
| 2 | 3 | 1 | 女装/女士精品 | 卫衣 | 89.90 | 1500 |
| 2 | 4 | 1 | 女装/女士精品 | 牛仔裤 | 89.90 | 3500 |
| 3 | 2 | 1 | 女装/女士精品 | 连衣裙 | 79.90 | 2500 |
+---------+----+-------------+---------------+----------+--------+-------+
4 rows in set (0.00 sec)
```

可以看到，使用DENSE_RANK()函数得出的行号为 1 、 2 、 2 、 3 ，相同价格的商品序号相同，后面的商品序号是连续的，并且没有跳过重复的序号。

#### 2. 分布函数

**1 ．PERCENT_RANK()函数**

PERCENT_RANK()函数是等级值百分比函数。按照如下方式进行计算。

```sql
(rank - 1) / (rows - 1)
```

其中，rank的值为使用RANK()函数产生的序号，rows的值为当前窗口的总记录数。

举例：计算 goods 数据表中名称为“女装/女士精品”的类别下的商品的PERCENT_RANK值。

![image-20221026204855744](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204855744.png)

**2 ．CUME_DIST()函数**

CUME_DIST()函数主要用于查询小于或等于某个值的比例。

举sq例：查询goods数据表中小于或等于当前价格的比例。

```sql
mysql> SELECT CUME_DIST() OVER(PARTITION BY category_id ORDER BY price ASC) AS cd,
-> id, category, NAME, price
-> FROM goods;
+---------------------+----+---------------+------------+---------+
| cd | id | category | NAME | price |
+---------------------+----+---------------+------------+---------+
| 0.16666666666666666 | 5 | 女装/女士精品 | 百褶裙 | 29.90 |
| 0.3333333333333333 | 1 | 女装/女士精品 | T恤 | 39.90 |
| 0.5 | 2 | 女装/女士精品 | 连衣裙 | 79.90 |
| 0.8333333333333334 | 3 | 女装/女士精品 | 卫衣 | 89.90 |
| 0.8333333333333334 | 4 | 女装/女士精品 | 牛仔裤 | 89.90 |
| 1 | 6 | 女装/女士精品 | 呢绒外套 | 399.90 |
| 0.16666666666666666 | 9 | 户外运动 | 登山杖 | 59.90 |
| 0.5 | 7 | 户外运动 | 自行车 | 399.90 |
| 0.5 | 10 | 户外运动 | 骑行装备 | 399.90 |
| 0.6666666666666666 | 12 | 户外运动 | 滑板 | 499.90 |
| 0.8333333333333334 | 11 | 户外运动 | 运动外套 | 799.90 |
| 1 | 8 | 户外运动 | 山地自行车 | 1399.90 |
+---------------------+----+---------------+------------+---------+
12 rows in set (0.00 sec)
```

#### 3. 前后函数

**1 ．LAG(expr,n)函数**

LAG(expr,n)函数返回当前行的前n行的expr的值。

举例：查询goods数据表中前一个商品价格与当前商品价格的差值。

![image-20221026204954506](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026204954506.png)

**2 ．LEAD(expr,n)函数**

LEAD(expr,n)函数返回当前行的后n行的expr的值。

举例：查询goods数据表中后一个商品价格与当前商品价格的差值。

```sql
mysql> SELECT id, category, NAME, behind_price, price,behind_price - price AS
diff_price
-> FROM(
-> SELECT id, category, NAME, price,LEAD(price, 1) OVER w AS behind_price
-> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price)) t;
+----+---------------+------------+--------------+---------+------------+
| id | category | NAME | behind_price | price | diff_price |
+----+---------------+------------+--------------+---------+------------+
| 5 | 女装/女士精品 | 百褶裙 | 39.90 | 29.90 | 10.00 |
| 1 | 女装/女士精品 | T恤 | 79.90 | 39.90 | 40.00 |
| 2 | 女装/女士精品 | 连衣裙 | 89.90 | 79.90 | 10.00 |
| 3 | 女装/女士精品 | 卫衣 | 89.90 | 89.90 | 0.00 |
| 4 | 女装/女士精品 | 牛仔裤 | 399.90 | 89.90 | 310.00 |
| 6 | 女装/女士精品 | 呢绒外套 | NULL | 399.90 | NULL |
| 9 | 户外运动 | 登山杖 | 399.90 | 59.90 | 340.00 |
| 7 | 户外运动 | 自行车 | 399.90 | 399.90 | 0.00 |
| 10 | 户外运动 | 骑行装备 | 499.90 | 399.90 | 100.00 |
| 12 | 户外运动 | 滑板 | 799.90 | 499.90 | 300.00 |
| 11 | 户外运动 | 运动外套 | 1399.90 | 799.90 | 600.00 |
| 8 | 户外运动 | 山地自行车 | NULL | 1399.90 | NULL |
+----+---------------+------------+--------------+---------+------------+
12 rows in set (0.00 sec)
```

#### 4. 首尾函数

**1 ．FIRST_VALUE(expr)函数**

FIRST_VALUE(expr)函数返回第一个expr的值。

举例：按照价格排序，查询第 1 个商品的价格信息。

![image-20221026205100197](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026205100197.png)

**2 ．LAST_VALUE(expr)函数**

LAST_VALUE(expr)函数返回最后一个expr的值。

举例：按照价格排序，查询最后一个商品的价格信息。

```sql
mysql> SELECT id, category, NAME, price, stock,LAST_VALUE(price) OVER w AS last_price
-> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price);
+----+---------------+------------+---------+-------+------------+
| id | category | NAME | price | stock | last_price |
+----+---------------+------------+---------+-------+------------+
| 5 | 女装/女士精品 | 百褶裙 | 29.90 | 500 | 29.90 |
| 1 | 女装/女士精品 | T恤 | 39.90 | 1000 | 39.90 |
| 2 | 女装/女士精品 | 连衣裙 | 79.90 | 2500 | 79.90 |
| 3 | 女装/女士精品 | 卫衣 | 89.90 | 1500 | 89.90 |
| 4 | 女装/女士精品 | 牛仔裤 | 89.90 | 3500 | 89.90 |
| 6 | 女装/女士精品 | 呢绒外套 | 399.90 | 1200 | 399.90 |
| 9 | 户外运动 | 登山杖 | 59.90 | 1500 | 59.90 |
| 7 | 户外运动 | 自行车 | 399.90 | 1000 | 399.90 |
| 10 | 户外运动 | 骑行装备 | 399.90 | 3500 | 399.90 |
| 12 | 户外运动 | 滑板 | 499.90 | 1200 | 499.90 |
| 11 | 户外运动 | 运动外套 | 799.90 | 500 | 799.90 |
| 8 | 户外运动 | 山地自行车 | 1399.90 | 2500 | 1399.90 |
+----+---------------+------------+---------+-------+------------+
12 rows in set (0.00 sec)
```

#### 5. 其他函数

**1 ．NTH_VALUE(expr,n)函数**

NTH_VALUE(expr,n)函数返回第n个expr的值。

举例：查询goods数据表中排名第 2 和第 3 的价格信息。

![image-20221026205200127](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026205200127.png)

**2 ．NTILE(n)函数**

NTILE(n)函数将分区中的有序数据分为n个桶，记录桶编号。

举例：将goods表中的商品按照价格分为 3 组。

```sql
mysql> SELECT NTILE(3) OVER w AS nt,id, category, NAME, price
-> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price);
+----+----+---------------+------------+---------+
| nt | id | category | NAME | price |
+----+----+---------------+------------+---------+
| 1 | 5 | 女装/女士精品 | 百褶裙 | 29.90 |
| 1 | 1 | 女装/女士精品 | T恤 | 39.90 |
| 2 | 2 | 女装/女士精品 | 连衣裙 | 79.90 |
| 2 | 3 | 女装/女士精品 | 卫衣 | 89.90 |
| 3 | 4 | 女装/女士精品 | 牛仔裤 | 89.90 |
| 3 | 6 | 女装/女士精品 | 呢绒外套 | 399.90 |
| 1 | 9 | 户外运动 | 登山杖 | 59.90 |
| 1 | 7 | 户外运动 | 自行车 | 399.90 |
| 2 | 10 | 户外运动 | 骑行装备 | 399.90 |
| 2 | 12 | 户外运动 | 滑板 | 499.90 |
| 3 | 11 | 户外运动 | 运动外套 | 799.90 |
| 3 | 8 | 户外运动 | 山地自行车 | 1399.90 |
+----+----+---------------+------------+---------+
12 rows in set (0.00 sec)
```

### 2. 5 小 结

窗口函数的特点是可以分组，而且可以在分组内排序。另外，窗口函数不会因为分组而减少原表中的行数，这对我们在原表数据的基础上进行统计和排序非常有用。

## 3. 新特性 2 ：公用表表达式

公用表表达式（或通用表表达式）简称为CTE（Common Table Expressions）。CTE是一个命名的临时结果集，作用范围是当前语句。CTE可以理解成一个可以复用的子查询，当然跟子查询还是有点区别的，CTE可以引用其他CTE，但子查询不能引用其他子查询。所以，可以考虑代替子查询。

依据语法结构和执行方式的不同，公用表表达式分为**普通公用表表达式**和**递归公用表表达式** 2 种。

### 3. 1 普通公用表表达式

普通公用表表达式的语法结构是：

```sql
WITH CTE名称
AS （子查询）
SELECT|DELETE|UPDATE 语句;
```

普通公用表表达式类似于子查询，不过，跟子查询不同的是，它可以被多次引用，而且可以被其他的普通公用表表达式所引用。

举例：查询员工所在的部门的详细信息。

![image-20221026205352689](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026205352689.png)

这个查询也可以用普通公用表表达式的方式完成：

![image-20221026205415899](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026205415899.png)

例子说明，公用表表达式可以起到子查询的作用。以后如果遇到需要使用子查询的场景，你可以在查询之前，先定义公用表表达式，然后在查询中用它来代替子查询。而且，跟子查询相比，公用表表达式有一个优点，就是定义过公用表表达式之后的查询，可以像一个表一样多次引用公用表表达式，而子查询则不能。

### 3. 2 递归公用表表达式

递归公用表表达式也是一种公用表表达式，只不过，除了普通公用表表达式的特点以外，它还有自己的特点，就是 **可以调用自己** 。它的语法结构是：

```sql
WITH RECURSIVE
CTE名称 AS （子查询）
SELECT|DELETE|UPDATE 语句;
```

递归公用表表达式由 2 部分组成，分别是种子查询和递归查询，中间通过关键字 UNION [ALL]进行连接。

这里的 **种子查询，意思就是获得递归的初始值** 。这个查询只会运行一次，以创建初始数据集，之后递归查询会一直执行，直到没有任何新的查询数据产生，递归返回。

**案例**： 针对于我们常用的employees表，包含employee_id，last_name和manager_id三个字段。如果a是b的管理者，那么，我们可以把b叫做a的下属，如果同时b又是c的管理者，那么c就是b的下属，是a的下下属。

下面我们尝试用查询语句列出所有具有下下属身份的人员信息。

如果用我们之前学过的知识来解决，会比较复杂，至少要进行 4 次查询才能搞定：

- 第一步，先找出初代管理者，就是不以任何别人为管理者的人，把结果存入临时表；
- 第二步，找出所有以初代管理者为管理者的人，得到一个下属集，把结果存入临时表；
- 第三步，找出所有以下属为管理者的人，得到一个下下属集，把结果存入临时表。
- 第四步，找出所有以下下属为管理者的人，得到一个结果集。

如果第四步的结果集为空，则计算结束，第三步的结果集就是我们需要的下下属集了，否则就必须继续进行第四步，一直到结果集为空为止。比如上面的这个数据表，就需要到第五步，才能得到空结果集。而且，最后还要进行第六步：把第三步和第四步的结果集合并，这样才能最终获得我们需要的结果集。

如果用递归公用表表达式，就非常简单了。我介绍下具体的思路。

- 用递归公用表表达式中的种子查询，找出初代管理者。字段 n 表示代次，初始值为 1 ，表示是第一代管理者。
- 用递归公用表表达式中的递归查询，查出以这个递归公用表表达式中的人为管理者的人，并且代次的值加 1 。直到没有人以这个递归公用表表达式中的人为管理者了，递归返回。

- 在最后的查询中，选出所有代次大于等于 3 的人，他们肯定是第三代及以上代次的下属了，也就是下下属了。这样就得到了我们需要的结果集。

这里看似也是 3 步，实际上是一个查询的 3 个部分，只需要执行一次就可以了。而且也不需要用临时表保存中间结果，比刚刚的方法简单多了。

**代码实现**：

![image-20221026205636887](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026205636887.png)

总之，递归公用表表达式对于查询一个有共同的根节点的树形结构数据，非常有用。它可以不受层级的限制，轻松查出所有节点的数据。如果用其他的查询方式，就比较复杂了。

### 3. 3 小 结

公用表表达式的作用是可以替代子查询，而且可以被多次引用。递归公用表表达式对查询有一个共同根节点的树形结构数据非常高效，可以轻松搞定其他查询方式难以处理的查询。





------

# 第 19 章 _ 写在最后

**分享 1**

![image-20221026205815912](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20221026205815912.png)

**分享 2**
如何看待生活上、工作上的冗余、反冗余？
又如何看待社会的脆弱性？反脆弱性？
个人如何应对？


