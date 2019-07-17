# welunch-infra

## Get Startted

1. pull latest welunch-apple image

```
docker pull registry.cn-hangzhou.aliyuncs.com/stupidism/welunch-apple
```

2. compose it up

```
cd apple
docker-compose up
```
or directly:  

```
docker-compose -f apple/docker-compose.yml up
```


### Trouble Shooting

1. if you get this error:
```
nginx_1    | 2019/07/17 15:18:53 [emerg] 1#1: open() "/etc/letsencrypt/options-ssl-nginx.conf" failed (2: No such file or directory) in /etc/nginx/conf.d/app.conf:38
nginx_1    | nginx: [emerg] open() "/etc/letsencrypt/options-ssl-nginx.conf" failed (2: No such file or directory) in /etc/nginx/conf.d/app.conf:38
nginx_1    | 2019/07/17 15:18:56 [emerg] 1#1: open() "/etc/letsencrypt/options-ssl-nginx.conf" failed (2: No such file or directory) in /etc/nginx/conf.d/app.conf:38
nginx_1    | nginx: [emerg] open() "/etc/letsencrypt/options-ssl-nginx.conf" failed (2: No such file or directory) in /etc/nginx/conf.d/app.conf:38
nginx_1    | 2019/07/17 15:18:58 [emerg] 1#1: open() "/etc/letsencrypt/options-ssl-nginx.conf" failed (2: No such file or directory) in /etc/nginx/conf.d/app.conf:38
nginx_1    | nginx: [emerg] open() "/etc/letsencrypt/options-ssl-nginx.conf" failed (2: No such file or directory) in /etc/nginx/conf.d/app.conf:38
apple_nginx_1 exited with code 1
```

You need to run `chmod +x init-letsencrypt.sh` and `sudo ./init-letsencrypt.sh`, as the blog [Nginx and Let’s Encrypt with Docker in Less Than 5 Minutes](https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71) says.
