# go_web

更改本地 host 
`sudo vi /etc/hosts` 添加 `127.0.0.1 go.web.test`

http://go.web.test


export GOPATH=/home/vhost/go_web


### nginx 反向代理
```
server {
    listen 80;
    listen [::]:80;

    server_name go.web.test;

    root /home/vhost/go_web/public;

    index index.php index.html index.htm index.nginx-debian.html;

    location / {
        proxy_pass    http://127.0.0.1:8080;
        proxy_redirect default;
    }
}
``` 
