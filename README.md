#Create container
```
docker run -i -t -d -p 80:80 -p 22:22 cristo/yii /bin/bash
```



#MySQL
```
user: root 
password: root

```
#SSH
```
ssh -p22 root@localhost
password: passwd
```
#NGINX server config file for communicate with docker

```
server {
        listen *:80;
        server_name localhost;
        proxy_set_header Host localhost;
        client_max_body_size 100M;

                location / {
                                proxy_set_header Host $host;
                                proxy_set_header X-Real-IP $remote_addr;
                                proxy_cache off;
                                proxy_pass http://localhost:80;
                        }
}
```

#Origin
[Docker Hub] (https://hub.docker.com/u/cristo/yii/)

[Git Hub] (https://github.com/monte-fm/Yii-Yii2)
