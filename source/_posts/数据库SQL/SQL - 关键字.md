---
title: SQL - 关键字
date: 2025-7-08 11:00:00
category:
  - 数据库
banner: /assets/cover/doc.jpg
---

#### like
like在where子句中，用于模糊查询。
有两个通配符与like一起使用：
- % 百分号表示，0个、1个或多个
- _ 下划线表示，单个字符
```
... where name like '高％'  －－名字以高开头，姓高
... where name like '高_'   －－姓高，且名字为两个字
... where name like '%锋'   －－以锋结尾
... where name like '％锋％' －－名字中含有锋
```

#### having
having与where都是用于过滤结果。
- where：不能使用聚合函数
- having: 可以使用聚合函数,常与分组后的统计一起使用
```
... where name = 'Vico'
...group by sex having count(*) > 5
```

#### between and
在where中使用，取值介于两个值之间的数据范围。数字、文本或日期。
```
... where age between 10 and 20
```