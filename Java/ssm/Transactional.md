# @Transactional 注解的使用

1.@Transactional 默认只对RuntimeException进行回滚

2. sping mvc中配置事务

3. try catch中使用事务
```java
try {
} catch (Exception e) {
  // 手动硬编码开启spring事务管理
  TransactionAspectSupport.currentTransactionStatus().setRollbackOnly();
}

```
