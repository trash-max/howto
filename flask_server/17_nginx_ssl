#### Nginx и https

Допишем секцию server в нашем конфиге, теперь он выглядит так:

```
server {
    listen 80;
    listen [::]:80;

    # server_name your_domain www.your_domain;

    location / {
        include proxy_params;
        proxy_pass http://unix:/home/trash/flaskproject/flaskproject.sock;
    }

}

server {
    listen 443 ssl default_server;
    listen [::]:443 ssl default_server;
    server_name flaskserver.deadend.xyz;

    #ssl on;
    ssl_certificate /etc/letsencrypt/live/flaskserver.deadend.xyz/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/flaskserver.deadend.xyz/privkey.pem;

    location / {
        include proxy_params;
        proxy_pass http://unix:/home/trash/flaskproject/flaskproject.sock;
    }

}
```

Далее опять запускаем запускаем тест конфигурации:

```bash
sudo nginx -t
```

И если нет ошибок:

```
sudo systemctl nginx reload
```

теперь откроем в браузере и увидим, что работает все на https

далее надо решить с 80 портом. Закрывать не вариант, так что делаем переадресацию

Опять идем в кофиг сайта на nginx

теперь он должен выглядеть так



```bash
server {
    listen 80;
    listen [::]:80;
    # server_name your_domain www.your_domain;

    location / {
        include proxy_params;
        proxy_pass http://unix:/home/trash/flaskproject/flaskproject.sock;
    }

}

server {
    listen 443 ssl default_server;
    listen [::]:443 ssl default_server;
    server_name flaskserver.deadend.xyz;

    #ssl on;
    ssl_certificate /etc/letsencrypt/live/flaskserver.deadend.xyz/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/flaskserver.deadend.xyz/privkey.pem;

    location / {
        include proxy_params;
        proxy_pass http://unix:/home/trash/flaskproject/flaskproject.sock;
    }

}
```

Далее опять запускаем запускаем тест конфигурации

```bash
sudo nginx -t
```

И если нет ошибок:

```bash
sudo systemctl nginx reload
```

После чего в браузере открываем ссылку http и видим переадресацию на https
