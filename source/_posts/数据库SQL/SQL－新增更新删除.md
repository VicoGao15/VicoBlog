---
title: SQL -新增/更新/删除
date: 2025-7-08 11:00:00
category:
  - 数据库
tags: [面试]
banner: /assets/cover/doc.jpg
---

#### 新增 insert into 
insert into table (col1,col2,...) value (val1,val2,...)

- insert 字段顺序不必须与数据库表的字段顺序一致，但是values值的顺序必须与insert一致
```
insert into students (name,gender,class_id,score) values ("Vico","M",2,88);
```

- 还可以一次性添加多条数据
```
insert into students (class_id,name,gender,score) values 
  (1,"Mark","M",75),
  (1,"Sally","F",95),
  (4,"John","M",80);
```

#### 更新 update set
```
update students set name = "VicoGao",score = 100 where id = 1
```
- 一次性更新多条数据
```
update students set score = 88 where id >= 3 and id <= 6;
```
- 使用表达式
```
update students set score = score+5 where score >= 55 and score <60;
```
- 没有`where`条件过滤，所有数据都会被更新。批量更新
```
update students set class_id = 2;
```

#### 删除 delete from
```
delete from students where name = "Vico";
```
- 批量删除
```
delete from students where id >= 5 and id <= 7;
```