## 1. 数据存储

- 以前是这样记录的：结绳记事

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135237.png)

- 也有这样记录的：甲骨

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135243.png)

- 后来开始这样记录：图书

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135251.png)

**传统记录数据的缺点:**

- 不易保存
- 备份困难
- 查找不便

**现代化手段----文件**

- 使用简单，例如python中的open可以打开文件，用read/write对文件进行读写，close关闭文件
- 对于数据容量较大的数据，不能够很好的满足，而且性能较差
- 不易扩展

**现代化手段----数据库**

- 持久化存储
- 读写速度极高
- 保证数据的有效性
- 对程序支持性非常好，容易扩展

**真实的仓库是这样的:**

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135324.png)

**我们看到的是这个样子的**

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135337.png)

**顾客看到的是这个样子的:**

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135344.png)

## 2. 数据库

数据库就是一种特殊的文件，其中存储着需要的数据

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135359.png)

关系型数据库核心元素

- 数据行(记录)
- 数据列(字段)
- 数据表(数据行的集合)
- 数据库(数据表的集合)

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135407.png)

## 3. RDBMS

> Relational Database Management System
>
> 通过表来表示关系型

- 当前主要使用两种类型的数据库：关系型数据库、非关系型数据库，本部分主要讨论关系型数据库，对于非关系型数据库会在后面学习
- 所谓的关系型数据库RDBMS，是建立在关系模型基础上的数据库，借助于集合代数等数学概念和方法来处理数据库中的数据
- 查看数据库排名:https://db-engines.com/en/ranking
- 关系型数据库的主要产品：
  - oracle：在以前的大型项目中使用,银行,电信等项目
  - mysql：web时代使用最广泛的关系型数据库
  - ms sql server：在微软的项目中使用
  - sqlite：轻量级数据库，主要应用在移动平台

## 4. RDBMS和数据库的关系

![image-20210218135520598](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218135520.png)

## 5. SQL

> Structured Query Language

SQL是结构化查询语言，是一种用来操作RDBMS的数据库语言，当前关系型数据库都支持使用SQL语言进行操作,也就是说可以通过 SQL 操作 oracle,sql server,mysql,sqlite 等等所有的关系型的数据库

- SQL语句主要分为：
  - **DQL：数据查询语言，用于对数据进行查询，如select**
  - **DML：数据操作语言，对数据进行增加、修改、删除，如insert、udpate、delete**
  - TPL：事务处理语言，对事务进行处理，包括begin transaction、commit、rollback
  - DCL：数据控制语言，进行授权与权限回收，如grant、revoke
  - DDL：数据定义语言，进行数据库、表的管理等，如create、drop
  - CCL：指针控制语言，通过控制指针完成表的操作，如declare cursor
- 对于web程序员来讲，重点是数据的crud（增删改查），必须熟练编写DQL、DML，能够编写DDL完成数据库、表的操作，其它语言如TPL、DCL、CCL了解即可
- SQL 是一门特殊的语言,专门用来操作关系数据库
- 不区分大小写

学习要求

- 熟练掌握数据增删改查相关的 SQL 语句编写
- 在 Python代码中操作数据就是通过 SQL 语句来操作数据

```python
# 创建Connection连接
conn = connect(host='localhost', port=3306, user='root', password='mysql', database='python1', charset='utf8')
# 得Cursor对象
cs = conn.cursor()
# 更新
# sql = 'update students set name="刘邦" where id=6'
# 删除
# sql = 'delete from students where id=6'
# 执行select语句，并返回受影响的行数：查询一条学生数据
sql = 'select id,name from students where id = 7'
# sql = 'SELECT id,name FROM students WHERE id = 7'
count=cs.execute(sql)
# 打印受影响的行数
print(count)
```

## 6. MySQL 简介

- 点击查看[MySQL官方网站](http://www.mysql.com/)
- MySQL是一个关系型数据库管理系统，由瑞典MySQL AB公司开发，后来被Sun公司收购，Sun公司后来又被Oracle公司收购，目前属于Oracle旗下产品

**特点**

- 使用C和C++编写，并使用了多种编译器进行测试，保证源代码的可移植性
- 支持多种操作系统，如Linux、Windows、AIX、FreeBSD、HP-UX、MacOS、NovellNetware、OpenBSD、OS/2 Wrap、Solaris等
- 为多种编程语言提供了API，如C、C++、Python、Java、Perl、PHP、Eiffel、Ruby等
- 支持多线程，充分利用CPU资源
- 优化的SQL查询算法，有效地提高查询速度
- 提供多语言支持，常见的编码如GB2312、BIG5、UTF8
- 提供TCP/IP、ODBC和JDBC等多种数据库连接途径
- 提供用于管理、检查、优化数据库操作的管理工具
- 大型的数据库。可以处理拥有上千万条记录的大型数据库
- 支持多种存储引擎
- MySQL 软件采用了双授权政策，它分为社区版和商业版，由于其体积小、速度快、总体拥有成本低，尤其是开放源码这一特点，一般中小型网站的开发都选择MySQL作为网站数据库
- MySQL使用标准的SQL数据语言形式
- Mysql是可以定制的，采用了GPL协议，你可以修改源码来开发自己的Mysql系统
- 在线DDL更改功能
- 复制全局事务标识
- 复制无崩溃从机
- 复制多线程从机

> 开源 免费 不要钱 使用范围广,跨平台支持性好,提供了多种语言调用的 API
>
> 是学习数据库开发的首选

## 7. 数据完整性

- 一个数据库就是一个完整的业务单元，可以包含多张表，数据被存储在表中
- 在表中为了更加准确的存储数据，保证数据的正确有效，可以在创建表的时候，为表添加一些强制性的验证，包括数据字段的类型、约束

**数据类型**

- 可以通过查看帮助文档查阅所有支持的数据类型
- 使用数据类型的原则是：够用就行，尽量使用取值范围小的，而不用大的，这样可以更多的节省存储空间
- 常用数据类型如下：
  - 整数：int，bit
  - 小数：decimal
  - 字符串：varchar,char
  - 日期时间: date, time, datetime
  - 枚举类型(enum)
- 特别说明的类型如下：
  - decimal表示浮点数，如decimal(5,2)表示共存5位数，小数占2位
  - char表示固定长度的字符串，如char(3)，如果填充'ab'时会补一个空格为`'ab '`
  - varchar表示可变长度的字符串，如varchar(3)，填充'ab'时就会存储'ab'
  - 字符串text表示存储大文本，当字符大于4000时推荐使用
  - 对于图片、音频、视频等文件，不存储在数据库中，而是上传到某个服务器上，然后在表中存储这个文件的保存路径
- 更全的数据类型可以参考http://blog.csdn.net/anxpp/article/details/51284106

**约束**

- 主键primary key：物理上存储的顺序
- 非空not null：此字段不允许填写空值
- 惟一unique：此字段的值不允许重复
- 默认default：当不填写此值时会使用默认值，如果填写时以填写为准
- 外键foreign key：对关系字段进行约束，当为关系字段填写值时，会到关联的表中查询此值是否存在，如果存在则填写成功，如果不存在则填写失败并抛出异常
- 说明：虽然外键约束可以保证数据的有效性，但是在进行数据的crud（增加、修改、删除、查询）时，都会降低数据库的性能，所以不推荐使用，那么数据的有效性怎么保证呢？答：可以在逻辑层进行控制

> 数值类型(常用)

| 类型        | 字节大小 | 有符号范围(Signed)                         | 无符号范围(Unsigned)     |
| :---------- | :------- | :----------------------------------------- | :----------------------- |
| TINYINT     | 1        | -128 ~ 127                                 | 0 ~ 255                  |
| SMALLINT    | 2        | -32768 ~ 32767                             | 0 ~ 65535                |
| MEDIUMINT   | 3        | -8388608 ~ 8388607                         | 0 ~ 16777215             |
| INT/INTEGER | 4        | -2147483648 ~2147483647                    | 0 ~ 4294967295           |
| BIGINT      | 8        | -9223372036854775808 ~ 9223372036854775807 | 0 ~ 18446744073709551615 |

> 字符串

| 类型    | 字节大小 | 示例                                                         |
| :------ | :------- | :----------------------------------------------------------- |
| CHAR    | 0-255    | 类型:char(3) 输入 'ab', 实际存储为'ab ', 输入'abcd' 实际存储为 'abc' |
| VARCHAR | 0-255    | 类型:varchar(3) 输 'ab',实际存储为'ab', 输入'abcd',实际存储为'abc' |
| TEXT    | 0-65535  | 大文本                                                       |

> 日期时间类型

| 类型      | 字节大小 | 示例                                                  |
| :-------- | :------- | :---------------------------------------------------- |
| DATE      | 4        | '2020-01-01'                                          |
| TIME      | 3        | '12:29:59'                                            |
| DATETIME  | 8        | '2020-01-01 12:29:59'                                 |
| YEAR      | 1        | '2017'                                                |
| TIMESTAMP | 4        | '1970-01-01 00:00:01' UTC ~ '2038-01-01 00:00:01' UTC |

## 8. 命令行连接

- 在工作中主要使用命令操作方式，要求熟练编写
- 打开终端，运行命令

```
mysql -uroot -p
回车后输入密码，当前设置的密码为mysql
```

- 连接成功后如下图

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140137.png)

- 退出登录

```
quit 和 exit
或
ctrl+d
```

- 登录成功后，输入如下命令查看效果

```
查看版本：select version();
显示当前时间：select now();
```

**修改输入提示符**

```
prompt python>
```

- \D 完整日期
- \U 使用用户

### 8.1 数据库

- 查看所有数据库

```sql
show databases;
```

- 使用数据库

```sql
use 数据库名;
```

- 查看当前使用的数据库

```sql
select database();
```

- 创建数据库

```sql
create database 数据库名 charset=utf8;
例：
create database python charset=utf8;
```

- 删除数据库

```sql
drop database 数据库名;
例：
drop database python;
```

### 8.2 数据表

- 查看当前数据库中所有表

```sql
show tables;
```

- 查看表结构

```sql
desc 表名;
```

- 创建表
- auto_increment表示自动增长

```sql
CREATE TABLE table_name(
    column1 datatype contrai,
    column2 datatype,
    column3 datatype,
    .....
    columnN datatype,
    PRIMARY KEY(one or more columns)
);
```

例：创建班级表

```sql
create table classes(
    id int unsigned auto_increment primary key not null,
    name varchar(10)
);
```

例：创建学生表

```sql
create table students(
    id int unsigned primary key auto_increment not null,
    name varchar(20) default '',
    age tinyint unsigned default 0,
    height decimal(5,2),
    gender enum('男','女','人妖','保密'),
    cls_id int unsigned default 0
)
```

- 修改表-添加字段

```sql
alter table 表名 add 列名 类型;
例：
alter table students add birthday datetime;
```

- 修改表-修改字段：重命名版

```sql
alter table 表名 change 原名 新名 类型及约束;
例：
alter table students change birthday birth datetime not null;
```

- 修改表-修改字段：不重命名版

```sql
alter table 表名 modify 列名 类型及约束;
例：
alter table students modify birth date not null;
```

- 修改表-删除字段

```sql
alter table 表名 drop 列名;
例：
alter table students drop birthday;
```

- 删除表

```sql
drop table 表名;
例：
drop table students;
```

- 查看表的创建语句

```sql
show create table 表名;
例：
show create table classes;
```

### 8.3 增删改查(curd)

curd的解释: 代表创建（Create）、更新（Update）、读取（Retrieve）和删除（Delete）

**查询基本使用**

- 查询所有列

```sql
select * from 表名;
例：
select * from classes;
```

- 查询指定列
- 可以使用as为列或表指定别名

```sql
select 列1,列2,... from 表名;
例：
select id,name from classes;
```

**增加**

> 格式:INSERT [INTO] tb**_**name [(col**_**name,...)] {VALUES | VALUE} ({expr | DEFAULT},...),(...),...

- 说明：主键列是自动增长，但是在全列插入时需要占位，通常使用0或者 default 或者 null 来占位，插入成功后以实际数据为准
- 全列插入：值的顺序与表中字段的顺序对应

```sql
insert into 表名 values(...)
例：
insert into students values(0,’郭靖‘,1,'蒙古','2016-1-2');
```

- 部分列插入：值的顺序与给出的列顺序对应

```sql
insert into 表名(列1,...) values(值1,...)
例：
insert into students(name,hometown,birthday) values('黄蓉','桃花岛','2016-3-2');
```

- 上面的语句一次可以向表中插入一行数据，还可以一次性插入多行数据，这样可以减少与数据库的通信
- 全列多行插入：值的顺序与给出的列顺序对应

```sql
insert into 表名 values(...),(...)...;
例：
insert into classes values(0,'python1'),(0,'python2');
insert into 表名(列1,...) values(值1,...),(值1,...)...;
例：
insert into students(name) values('杨康'),('杨过'),('小龙女');
```

**修改**

> 格式: **UPDATE** ***tbname*** **SET col1={expr1|DEFAULT} [,col2={expr2|default}]...[where 条件判断]**

```sql
update 表名 set 列1=值1,列2=值2... where 条件
例：
update students set gender=0,hometown='北京' where id=5;
```

**删除**

> **DELETE FROM tbname [where 条件判断]**

```sql
delete from 表名 where 条件
例：
delete from students where id=5;
```

- 逻辑删除，本质就是修改操作

```sql
update students set isdelete=1 where id=1;
```

### 8.4 备份

- 运行mysqldump命令

```sql
mysqldump –uroot –p 数据库名 > python.sql;

# 按提示输入mysql的密码
```

### 8.5 恢复

- 连接mysql，创建新的数据库
- 退出连接，执行如下命令

```sql
mysql -uroot –p 新数据库名 < python.sql

# 根据提示输入mysql密码
```

## 9. 数据库设计

- 关系型数据库建议在E-R模型的基础上，我们需要根据产品经理的设计策划，抽取出来模型与关系，制定出表结构，这是项目开始的第一步
- 在开发中有很多设计数据库的软件，常用的如power designer，db desinger等，这些软件可以直观的看到实体及实体间的关系
- 设计数据库，可能是由专门的数据库设计人员完成，也可能是由开发组成员完成，一般是项目经理带领组员来完成
- 现阶段不需要独立完成数据库设计，但是要注意积累一些这方面的经验

### 9.1 三范式

- 经过研究和对使用中问题的总结，对于设计数据库提出了一些规范，这些规范被称为范式(Normal Form)

- 目前有迹可寻的共有8种范式，一般需要遵守3范式即可

- ◆ 第一范式（1NF）：强调的是列的原子性，即列不能够再分成其他几列。

  > 考虑这样一个表：【联系人】（姓名，性别，电话） 如果在实际场景中，一个联系人有家庭电话和公司电话，那么这种表结构设计就没有达到 1NF。要符合 1NF 我们只需把列（电话）拆分，即：【联系人】（姓名，性别，家庭电话，公司电话）。1NF 很好辨别，但是 2NF 和 3NF 就容易搞混淆。

- ◆ 第二范式（2NF）：首先是 1NF，另外包含两部分内容，一是表必须有一个主键；二是没有包含在主键中的列必须完全依赖于主键，而不能只依赖于主键的一部分。

  > 考虑一个订单明细表：【OrderDetail】（OrderID，ProductID，UnitPrice，Discount，Quantity，ProductName）。 因为我们知道在一个订单中可以订购多种产品，所以单单一个 OrderID 是不足以成为主键的，主键应该是（OrderID，ProductID）。显而易见 Discount（折扣），Quantity（数量）完全依赖（取决）于主键（OderID，ProductID），而 UnitPrice，ProductName 只依赖于 ProductID。所以 OrderDetail 表不符合 2NF。不符合 2NF 的设计容易产生冗余数据。
  >
  > 可以把【OrderDetail】表拆分为【OrderDetail】（OrderID，ProductID，Discount，Quantity）和【Product】（ProductID，UnitPrice，ProductName）来消除原订单表中UnitPrice，ProductName多次重复的情况。

- ◆ 第三范式（3NF）：首先是 2NF，另外非主键列必须直接依赖于主键，不能存在传递依赖。即不能存在：非主键列 A 依赖于非主键列 B，非主键列 B 依赖于主键的情况。

  > 考虑一个订单表【Order】（OrderID，OrderDate，CustomerID，CustomerName，CustomerAddr，CustomerCity）主键是（OrderID）。 其中 OrderDate，CustomerID，CustomerName，CustomerAddr，CustomerCity 等非主键列都完全依赖于主键（OrderID），所以符合 2NF。不过问题是 CustomerName，CustomerAddr，CustomerCity 直接依赖的是 CustomerID（非主键列），而不是直接依赖于主键，它是通过传递才依赖于主键，所以不符合 3NF。 通过拆分【Order】为【Order】（OrderID，OrderDate，CustomerID）和【Customer】（CustomerID，CustomerName，CustomerAddr，CustomerCity）从而达到 3NF。 *第二范式（2NF）和第三范式（3NF）的概念很容易混淆，区分它们的关键点在于，2NF：非主键列是否完全依赖于主键，还是依赖于主键的一部分；3NF：非主键列是直接依赖于主键，还是直接依赖于非主键列。

### 9.2 不遵循1NF

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140436.png)

### 9.3 不遵循2NF

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140446.png)

### 9.4 不遵循3NF

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140456.png)

### 9.5 最终表

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140503.png)

### 9.6 E-R模型

- E表示entry，实体，设计实体就像定义一个类一样，指定从哪些方面描述对象，一个实体转换为数据库中的一个表
- R表示relationship，关系，关系描述两个实体之间的对应规则，关系的类型包括包括一对一、一对多、多对多
- 关系也是一种数据，需要通过一个字段存储在表中
- 实体A对实体B为1对1，则在表A或表B中创建一个字段，存储另一个表的主键值

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140514.png)

- 实体A对实体B为1对多：在表B中创建一个字段，存储表A的主键值

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140520.png)

- 实体A对实体B为多对多：新建一张表C，这个表只有两个字段，一个用于存储A的主键值，一个用于存储B的主键值

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210218140528.png)

- 想一想：举些例子，满足一对一、一对多、多对多的对应关系

**逻辑删除**

- 对于重要数据，并不希望物理删除，一旦删除，数据无法找回
- 删除方案：设置isDelete的列，类型为bit，表示逻辑删除，默认值为0
- 对于非重要数据，可以进行物理删除
- 数据的重要性，要根据实际开发决定

**示例**

- 设计两张表：班级表、学生表
- 班级表classes
  - id
  - name
  - isdelete
- 学生表students
  - id
  - name
  - birthday
  - gender
  - clsid
  - isdelete

**扩展阅读**

- 看看别人家设计的规范
- [58到家数据库30条军规解读](http://mp.weixin.qq.com/s/Yjh_fPgrjuhhOZyVtRQ-SA)