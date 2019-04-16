1. 开启端口
```
vim /etc/sysconfig/iptables-config

# 将这行添加到iptables文件中
-A INPUT -p tcp -m state --state NEW -m tcp --dport 3306 -j ACCEPT
```
