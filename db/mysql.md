1. CreateTime、UpdateTime字段自动创建
```sql
Create table `tb1` (
  `CreateTime` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `UpdateTime` datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)
```
