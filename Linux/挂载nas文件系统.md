### 挂载/卸载nas文件系统
```shell
# 安装cifs-utils
# 1. 检查是否安装了cifs-utils
rpm -q cifs-utils
# 2. 安装cifs-utils
yum install cifs-utils

# 挂载
sudo mount -t cifs -o username=weihl,password=xxxxxxxxxxxx //192.168.100.109/Share /mnt/nas
# 卸载
sudo umount -v /mnt/nas

# 添加到开机启动项
# 1. 移动脚本到/etc/rc.d/init.d目录下
mv yourshell.sh /etc/rc.d/init.d
# 2. 增加脚本的可执行权限
chmod +x /etc/rc.d/init.d/yourshell.sh
# 3. 添加脚本到开机启动项中
cd /etc/rc.d/init.d
chkconfig --add yourshell.sh
chkconfig yourshell.sh on

## 脚本必须包含以下注释头内容

#!/bin/sh
# chkconfig: 112 63 37

sudo mount -t cifs -o username=weihl,password=xxxxxxxxxxxx //192.168.100.109/Share /mnt/nas

```

### 使Tomcat可读nas中的数据
1. 创建软连接使Tomcat的静态资源目录链接到nas目录
```shell
sudo ln -s -v /mnt/nas /root/tomcat/webapps/yourApp/filesRoot
```
2. 修改Tomcat/conf/context.xml
```xml
<Context>
  <!-- 添加允许链接 -->
  <Resources allowLinking="true" />
</Context>
```
3. 重启Tomcat
