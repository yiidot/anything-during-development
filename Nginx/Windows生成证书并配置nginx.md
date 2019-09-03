1. 生成证书
```cmd
keytool -genkey -v -alias tomcat -keyalg RSA -keystore d:\local.keystore -validity 36500
```
2. 解压缩 [JKS2PFX下载](https://github.com/yiidot/anything-useful-during-development/blob/master/Nginx/jks2pfx.zip)
```cmd
# JKS2PFX <KeyStore文件> <KeyStore密码> <Alias别名> <导出文件名> [Java Runtime的目录]
JKS2PFX server.jks 123456 tomcat exportfile c:\progra~1\Java\jre1.5.0_06\bin
```
3. 配置 nginx
```shell

# HTTPS server
#
server {
   listen       443 ssl;
   server_name  localhost;
 
   ssl_certificate      exportfile.crt;
   ssl_certificate_key  exportfile.key;
 
 
 
   ssl_session_cache    shared:SSL:1m;
   ssl_session_timeout  5m;
 
   ssl_ciphers  HIGH:!aNULL:!MD5;
   ssl_prefer_server_ciphers  on;
 
}
```
