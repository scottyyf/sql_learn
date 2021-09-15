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
