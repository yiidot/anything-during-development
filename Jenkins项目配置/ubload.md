```shell
# 自定义工作空间
E:/0_Code
# svn
https://192.168.100.90/svn/Code/UPBIM/Branch/V1.1/UBLoad/Revit/BELoadRvt
# Local module directory
./UBLoad

Emulate clean checkout by first deleting unversioned/ignored files, then 'svn update'

# 脚本构建
UBLoad

# poll scm
H/10 9-22 * * 1-5

# 构建
echo %SVN_REVISION%
cd /d E:\0_Jenkins\UBLoad\Builder
start.bat

# 构建后操作
E-mail notification
weihl@ai-eco.cn

# Editable email notification

$JOB_NAME
$DEFAULT_RECIPIENTS
$DEFAULT_REPLYTO
$DEFAULT_SUBJECT
$DEFAULT_CONTENT
```
