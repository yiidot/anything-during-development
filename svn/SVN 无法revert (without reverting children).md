Q:

报错信息大致为 'cleanup failed to process the following paths ...  without reverting children'

A:
```bash
  # cd到目录，执行以下脚本
  svn revert . --depth infinity
```
