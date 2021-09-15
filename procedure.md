## 存储过程
大批量的时候，使用存储过程方便且搞笑

1. 输入输出
   * IN
   * OUT
   * INOUT
 
2. 定义存储过程
```sql
create procedure `p_name`(IN i int)
begin
  while i<10 do
  insert into TABLE values (i,i);
  set i=i+1;
  end while;
end
```

```sql
CREATE DEFINER=`root`@`%` PROCEDURE `p1`()
BEGIN
	DECLARE i int DEFAULT 1;
	WHILE i<10 DO
	DELETE FROM sky_roles WHERE `name`=cast(i as char); # 变量类型转化
	set i=i+1;
	END WHILE;
END
```
