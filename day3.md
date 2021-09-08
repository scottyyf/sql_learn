1. select * from t_table where xxx;

这里的顺序是这样的，先从 from table where 里面获取一张新的画像， 然后再select对应字段

select 可以追加字段

* select *,mysql + linux + hadoop 'SCORE' from t_table;

这里将score作为一个独立的行进行展示

* select *, IFNULL(mysql, 0) +linux+hadoop from t_table;

null和任何数字做计算时，都是null，所以这里使用了IFNULL

2. ORDER BY COL DESC ASC(默认升序)

* select *,  IFNULL(mysql, 0) +linux+hadoop from t_table ORDER BY mysql,linux DESC;

先按mysql进行排序，mysql相等的再按linux进行排序

3. count, sum, avg, max, min聚合函数，纵向计算

* select count(name) from t_score;
 如果这个时候，select name, count(name) 那么name出现的是第一行的name，而count是name这咧的总数，并不是某个具体name的计数

* select * from t_score where mysql > 1;
* select count(name) from t_score where mysql > 1; 
先where出一个数据表，然后对这个表做count

4. 分组，聚合函数作用于分组 GROUP BY

* select `group`, count(name) from t_score group by `group`;

先用分组出一个数据表，然后对这张表做count

* select `group`, count(name) from t_score where mysql > 2 GROUP BY `group`;
where 对数据过滤，必须放在GROUP BY前面，即先出数据表，然后数据表分组

* select `group`, count(name), avg(java), sum(linux) from t_table GROUP BY `group`;

5. HAVING

having和where的比较，他们都是过滤

* where 是分组之前，having是分组之后
* where不能加聚合函数，having可以使用聚合函数

select `group`, AVG(java) from t_score GROUP BY `group` HAVING avg(java) < 2;


