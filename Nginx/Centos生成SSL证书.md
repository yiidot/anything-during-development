转载自[Nginx自签SSL证书创建及配置方法](https://blog.csdn.net/weixin_34290000/article/details/93043685)
1. 建立服务器私钥（过程需要输入密码，请记住这个密码）生成RSA密钥
```shell
openssl genrsa -des3 -out server.key 1024
```
2. 生成一个证书请求   
```shell
openssl req -new -key server.key -out server.csr
#需要依次输入国家，地区，组织，email。最重要的是有一个common name，可以写你的名字或者域名。如果为了https申请，这个必须和域名吻合，否则会引发浏览器警报。生成的csr文件交给CA签名后形成服务端自己的证书
#---------------------------------------------------------------------------------------------------------------
Enter pass phrase for server.key:                                      #之前输入的密码
Country Name (2 letter code) [XX]:                   #国家
State or Province Name (full name) []:                 #区域或是省份
Locality Name (eg, city) [Default City]:                #地区局部名字
Organization Name (eg, company) [Default Company Ltd]:         #机构名称：填写公司名
Organizational Unit Name (eg, section) []:               #组织单位名称:部门名称
Common Name (eg, your name or your server's hostname) []:     #网站域名
Email Address []:                             #邮箱地址
A challenge password []:                         #输入一个密码，可直接回车
An optional company name []:                       #一个可选的公司名称，可直接回车
```
3. 输入完这些内容，就会在当前目录生成server.csr文件
```shell
cp server.key server.key.org
openssl rsa -in server.key.org -out server.key
```

4. 使用上面的密钥和CSR对证书进行签名
```shell
#以下命令生成v1版证书
openssl x509 -req  -days 365 -sha256   -in server.csr -signkey server.key -out servernew.crt
#以下命令生成v3版证书
openssl x509 -req  -days 365 -sha256 -extfile openssl.cnf -extensions v3_req   -in server.csr -signkey server.key -out servernew.crt
```
