1. 开启端口
```shell
vim /etc/sysconfig/iptables-config

# 将这行添加到iptables文件中
-A INPUT -p tcp -m state --state NEW -m tcp --dport 3306 -j ACCEPT
```
2. 查看catalina日志
```shell
tail -f catalina.sh
```
3. 查看Tomcat进程
```shell
ps -ef | grep tomcat
```
4. 挂载/卸载nas文件系统
```shell
// 挂载
sudo mount -t cifs -o username=weihl,password=xxxxxxxxxxxx //192.168.100.109/Share /mnt/nas
// 卸载
sudo umount -v /mnt/nas
```
