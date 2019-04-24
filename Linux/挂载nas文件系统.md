挂载/卸载nas文件系统
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

```
