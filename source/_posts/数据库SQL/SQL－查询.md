---
title: SQL - 查询
date: 2025-7-08 11:00:00
category:
  - 数据库
tags: [面试]
banner: /assets/cover/doc.jpg
---

#### 基本查询
```
select * from students where name = "Vico";
select * from students where score >= 85;
select * from students where name = "Vico" and gender = "M";
```

条件表达式：and or not，not优先级最高，其次是and，最后是or
<> 不等于比较符号
() 要组合多个查询条件

#### 投影查询
只返回需要的列数据，而不是所有的列  
`select id,name,score from students;`

列名的别名：score重命名为point  
`select id,score points,name from student;`

#### 排序
- 使用order by 列
- ASC 升序，默认
- DESC 降序

`select * from students order by score;`  
默认低到高的正序，加上desc表示倒序排序    
`select * from students order by score desc;`  

按照多个列进行排序：先对score进行排序，如果有相同的score，再根据gender进行排序    
`select * from students order by score,gender;`

order by要放在where后面：  
```
select id,name,score
from students
where class_id = 1
order by score desc;
```

#### 分页查询
从结果集中截取从 m～n 的数据
使用limit n offset m
```
select id,name,score from students limit 10 offset 0;
select id,name,score from students limit 10 offset 10;
select id,name,score from students limit 10 offset 20;
```

limit表示最多返回多少条数据；  limit设置为pagesize
offset表示从哪条数据开始返回；  offset设置为pagesize*(pageindex-1)  

#### 聚合查询
聚合函数：对于统计总数、平均数这类计算，SQL提供了专门的函数，就是聚合函数，使用聚合函数的查询就是聚合查询，可以快速获得结果

`select count(*) from students where score >= 85;`

返回二维表，只有一行一列：列名count(*),数据为结果行数

给列名count(*)设置别名：  
`select count(*) num from students where score >= 85;`

- count(*) 和 count(id) 是一样的效果

其他聚合函数：  
- sum(列名)，计算某一列的合计值，该列必须为数值类型
- avg(列名)，计算某一列的平均值，该列必须为数值类型
- max(列名)，返回某一列的最大值
- min(列名)，返回某一列的最小值

```
select sum(score) from students; 计算所有学生总得分
select avg(score) average_m from students where gender = "M";
select max(score) m_max_score from students where gender = "M"; 返回男生中的最高分
select min(score) F_min_score from students where gender = "F"; 返回女生中的最低分
```

分组查询：  
使用group by
```
select count(*) num from students group by gender;
select gender,count(*) num from students group by gender;
```
也可以使用多个列进行分组：
```
select class_id,gender,count(*) num from students group by class_id,gender;
```

#### 多表查询
- 同时从表students和classes的乘积，结果是一个二维表。
- 多表查询又称为**笛卡尔查询**

`select * from students,classes`

- 多个表中可能存在相同字段的列名，使用投影查询设置别名  
- 使用`表名.列名`来引用列
```
select 
  students.id sid,
  students.name sname,
  students.gender,
  students.score,
  classes.id cid,
  classes.name cname
  from students,classes;
```
- 还可以对表名设置别名
```
select 
  s.id sid,
  s.name sname,
  s.gender,
  s.score,
  c.id cid,
  c.name cname
  from students s, classes c;
```

- 多表的`where`条件查询
- 下面where条件语句中的的c.id ＝ 1不能用cid ＝ 1替代
```
select 
  s.id sid,
  s.name sname,
  s.gender,
  s.score,
  c.id cid,
  c.name cname
  from students s, classes c
  where s,gender = "M" and c.id = 1;
```

- 一般使用主键或者外键进行多表关联查询，笛卡尔乘积没有太多意义，很容易查询爆炸，不建议实际使用
- 以上students和classes表中，students的外键class_id和classes的主键classes.id相关连
```
select 
  s.id sid,
  s.name sname,
  s.gender,
  s.score,
  c.id cid,
  c.name cname
  from students s, classes c
  where s.gender = "M" and s.class_id = c.id;
```

#### 连接查询
连接查询是另一种多表查询，使用join，先确定主表，然后把另一个表的数据附加到结果集中
- `内连接，inner join`
- 先确定主表，仍然使用FROM <表1>的语法；
- 再确定需要连接的表，使用INNER JOIN <表2>的语法；
- 然后确定连接条件，使用ON <条件...>，这里的条件是s.class_id = c.id，表示students表的class_id列与classes表的id列相同的行需要连接；
- 可选：加上WHERE子句、ORDER BY等子句。

```
-- 查询所有学生，同时返回班级
select 
  s.id,s.name student_name,s.gender,s.score,c.name class_name
  from students s
  inner join classes c
  on s.class_id = c.id
```

- 内连接inner join：只返回同时存在于两张表的行数据
- `外连接，outer join`
- `右连接，right outer join`，返回右表都存在的行，如果某一行在左表中不存在，左表所有行使用null填充
- `左连接，left outer join`，返回左表都存在的行，如果某一行在右表中不存在，右表所有行使用null填充
- `全连接，full outer join`，把两张表的所有记录全部选择出来，并把对方不存在的列填充为null

{% image /assets/PostImg/SQL/outerjoin.jpg %}