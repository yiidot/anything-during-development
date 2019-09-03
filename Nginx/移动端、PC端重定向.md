1. PC端 conf
```shell
server {
  listen 443;
  ssl on;
  server_name www.test.com;
  # permanent 对应 http 状态码 301, 表示永久转移, 如果写为 redirect, 则状态码为 302, 表示暂时转移
  if ($http_user_agent ~* (mobile|nokia|iphone|ipad|android|samsung|htc|blackberry)) {
    rewrite ^(.*) https://m.test.com$1 permanent;
  }
  
  index index.html index.htm index.php default.html default.htm default.php;
}
```

2. 移动端 conf
```shell
server{
    listen 443;
    ssl on;
    #listen [::]:80;
    server_name m.test.com;
    
    if ($http_user_agent !~* (mobile|nokia|iphone|ipad|android|samsung|htc|blackberry)) {
    # $1之前加一个 /, 不知道为什么, 但是加了地址显示正常
        rewrite  ^(.*)    https://www.test.com/$1 permanent;
    }

    index index.html index.htm index.php default.html default.htm default.php;
}
```
