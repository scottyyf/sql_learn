1. action to table DDL

* desc t_score;
* show create table table t_score;
* create table t_score(name varchar(25), age int, heights double(4,1);
* drop table t_score;
* alter table t_score add weights double(4,1); # 添加列
* alter table t_score drop weights;
* alter table t_score modify weights double(5,1); # 修改列属性
* alter table t_score change weights weight double(4,1); # 列重命名
* alter table t_score character set gbk; # 表设置
* alter table t_score rename t_scores; # 表重命名

2. dml

```sql
-- DELETE FROM t_student;
-- 删除表中数据


-- TRUNCATE t_student;\
-- 删除表并重新新建表

-- WHERE
-- = != <> > < >= ,BETWEEN AND, IN ,IS NULL, and, OR, NOT
-- IS NOT NULL, NOT IN,

-- _匹配一个字符 % 匹配任意个字符
```

* insert into t_score values ('mali', 14, 18.1);
* insert into t_score (name, age) values ('xiaoli', 15);
* insert into t_score values ('nary', 12, 14.1), ('mandy', 12,12);

* delete from t_score; # dangerous
* truncate t_score;
* delete from t_score where age between 10 and 20;
* delete from t_score where height is null;
* delete from t_score where height in (10, 20,30);

* update t_score set age=10 where name like '__h';
* update t_score set age=10,name='pp' where name='hide'; 

* select * from t_score where name='xx';
