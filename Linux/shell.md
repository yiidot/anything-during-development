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
4. 禁用防火墙
```shell
# 关闭防火墙
systemctl stop firewalld
# 立即生效
setenforce 0
# 关闭开机自启
systemctl disable firewalld
```
5. 开放防火墙端口(上面禁用防火墙不安全)
```shell
## Add
firewall-cmd --permanent --zone=public --add-port=8080/tcp
## Reload
firewall-cmd --reload
## 检查是否生效
firewall-cmd --zone=public --query-port=8080/tcp
```

