1. 修改nginx.conf
```conf
location / {
       proxy_pass http://localhost:8080/v1/;
       proxy_set_header    REMOTE-HOST $remote_addr;
       proxy_set_header   Host $host;
       proxy_set_header   X-Real-IP $remote_addr;
       proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
       #root   html;
       #index  index.html;
}

location /v1/ {
       proxy_pass http://localhost:8080/v1/;
       proxy_set_header    REMOTE-HOST $remote_addr;
       proxy_set_header   Host $host;
       proxy_set_header   X-Real-IP $remote_addr;
       proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
       #root   html;
       #index  index.html;
}
```
