# 关系型数据库

SQL Server 、 MySQL


## 数据库知识点


视图包含下列结构是不可以更新的


- 1：集合运算符 union，union all, intersect，minus
- 2：distinct关键字
- 3：group by,order by,connect by,或者start with
- 4：子查询
- 5：分组函数
- 6：需要更新的列不是视图定义的
- 7：具有连接查询(可以更新键值保存表的数据)
- 8：违反基表的约束条件；连接视图是指基于多表连接查询创建的视图（一般不容易修改，但通用instead of触发器可以实现修改的功能）


数据库语句执行顺序：
- 1、from子句组装来自不同数据源的数据；
- 2、where子句基于指定的条件对记录行进行筛选；
- 3、group by子句将数据划分为多个分组；
- 4、使用聚集函数进行计算；
- 5、使用having子句筛选分组；
- 6、select计算所有的表达式；
- 7、使用order by对结果集进行排序。