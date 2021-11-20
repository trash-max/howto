```bash
server {
    listen 80 default_server;
    listen [::]:80 default_server;
    # server_name your_domain www.your_domain;

    location / {
        include proxy_params;
        proxy_pass http://unix:/home/trash/flaskproject/flaskproject.sock;
    }
}
```