1. CreateTime、UpdateTime字段自动创建
```sql
Create table `tb1` (
  `CreateTime` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `UpdateTime` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)
```
2. 创建触发器
```sql
DELIMITER $$
create trigger task_document
after update on upbim.task for each row
begin
    if (new.Status=2) then
    update upbim.document set Active=1 where ModelId= new.ModelId;
    end if;
end;
```
