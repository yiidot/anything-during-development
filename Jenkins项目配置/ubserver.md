```shell
# svn
https://192.168.100.90/svn/Code/UPBIM/Branch/V1.1/UBServer/bimEngineServer
# Local module directory
.

use 'svn update' as much as possible

# 脚本构建
UBServer

# build
pom.xml

# Post Steps
rd /s/q E:\0_Tomcat\apache-tomcat-9.0.22\webapps\bimEngineServer
del /s/q E:\0_Tomcat\apache-tomcat-9.0.22\webapps\bimEngineServer.war
copy C:\Users\Administrator\.jenkins\workspace\UBServer\target\bimEngineServer.war  E:\0_Tomcat\apache-tomcat-9.0.22\webapps

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
