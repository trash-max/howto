#### letsencript

Теперь займемся защитой. (Не обязательный пункт)

Ставим сертификат от letsencript. Рекомендуется ставить с помощью специального бота:

ссылка

https://certbot.eff.org/

Раньше бота можно было ставить напрямую из репозитория

```bash
sudo apt install certbot certbot-python-nginx
```

Но сейчас так не работает, поскольку все переехало на снап.

(Хорошо это или плохо, тема отдельного холливара)

https://snapcraft.io/ - это для убунту

https://flathub.org/home - для гнома

В общем ставим


Проверим наличие Snap:

```bash
sudo snap
```

Если нет - ставим.

https://snapcraft.io/docs/installing-snapd

```bash
sudo apt install snapd
```

Установим самого бота:
```bash
sudo snap install --classic certbot
```

И пробросим символьную ссылку:
```bash
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```


Автоматический режим установки сертификатов может не помочь, будем ставить вручную.

(Это удобно, может у вас еще откуда есть сертификаты.)

```bash
sudo certbot certonly --nginx
```

ключ certonly говорит только загрузить сертификаты.

По умолчанию сертификаты залиты в:

/etc/letsencrypt/

Для проверки возможности обновления сущеуствует ключ

(Без самого обновления)

```bash
sudo certbot renew --dry-run
```

Сами сертификаты лежат в ../live/host-name
