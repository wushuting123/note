# 笔记格式

- [xxx]表示需要根据实际需求替换的内容

- “-- 方言”标注方言，不要在其他数据库使用

- {xxx}表示非必填

- 0+表示从0开始



# DDL-定义

## 通用

### 注释

```sql
-- [text]
#[text] -- 方言
/*[text]*/
```



## 库

### 创建库

```sql
create database [databasename] (if not exist);
```



### 查看所有库

```sql
select databases; 
```



### 删除库

```sql
drop database {if exist} [databasename];
```



### 切换数据库

```sql
use [tablename];
```



## 表

### 查看所有表

```sql
select tables;
```



### 查看表结构

```sql
desc [tablename];
```



### 创建表

```sql
create table [tablename] ([col1] [type1],…); 
```



### 数据类型

| **类型** | **格式**                    | **示例**                          | **备注**                                                     |
| :------- | :-------------------------- | :-------------------------------- | :----------------------------------------------------------- |
| double   | double(总长度,小数点后位数) | 0～100，保留两位小数--double(5,2) |                                                              |
| char     | char(最大长度0～255)        | char(10)                          | 定长字符串，设置了长度，则每个数据存储空间都是这个大小，因此存储效率高，但浪费空间，因此适合定长字符串 |
| varchar  | varchar(最大长度0～65535)   | varchar(10)                       | 变长字符串，设置的长度是最大长度，每个数据存储空间按实际大小来，因此存储效率低，但节省空间，因此适合变长字符串 |

 

### 删除表

```sql
drop table (if exist) [tablename];
```

 

### 修改表名称

```sql
alter table [tablename] rename to [newtablename];
```

 

### 新增表字段

```sql
alter table [tablename] add [col] [type];
```

 

### 修改表字段类型

```sql
alter table [tablename] modify [col] [newtype];
```

 

### 同时修改字段名称和字段类型

```sql
alter table [tablename] change [col] [newcol] [newtype];
```

 

### 删除表字段

```sql
alter table [tablename] drop [col];
```



# DQL-查询

## 查询语句结构

```sql
select {distinct} [col] {{as} [othername]},...
from [tablename] 
{where [condition] {connect} ... -- 分组前条件
group by [col],... 
having [condition] {connect} ... -- 分组后条件
order by [col] {ordertype},...
limit [startindex,0+] [size]}; -- 计算公式：(当前页码-1)*每页数据量 -- 方言
```



## 条件类型

| 条件                  | 说明                                                |
| --------------------- | --------------------------------------------------- |
| between   ... and ... | 在某个范围内，且包含边界                            |
| <>                    | 不等于，与!=是一样的效果                            |
| null                  | 为空：is null，不为空：is not null                  |
| like                  | _表示占用一个字符，%表示占用多个字符（包括0个字符） |



## 聚合函数

null不参与计算

| 类型  | 示例       | 备注          |
| ----- | ---------- | ------------- |
| max   | max(col)   |               |
| min   | min(col)   |               |
| avg   | avg(col)   |               |
| count | count(col) | 一般用主键或* |
| sum   | sum(col)   |               |



# DML-操作

## 插入数据

```sql
insert into [tablename] {[col],...} values ([value],...),...;
```

 

## 修改数据

```sql
update [tablename] set [col]=[newvalue],... {where [condition]};
```

 

## 删除数据

```sql
delete from [tablename] {where [condition]};
```







