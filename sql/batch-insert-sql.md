# 批量插入语句写法

```sql
<insert id="batchInsert" parameterType="java.util.List">
	insert into table_name (
		ID,
		NAME,
		AGE
	) values
	<foreach collection="list" item="item" separator=",">
	(
		#{item.id},
		#{item.name},
		#{item.age}
	)
	</foreach>
	on duplicate key update
	NAME = values(NAME),
	AGE = values(AGE)
</insert>
```