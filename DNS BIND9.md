# DNS BIND9

```
apt-get install bind9
cd /etc/bind/ 
ls -al (список всех файлов)
``` 

```
nano named.conf.options (удаляем все комментарии, остается 3 строчки)
``` 
dns-sec-validation no;

```
nano named.conf.default-zones
```
удаляем сверху комментарии
localhost меняем на имя домена, за который отвечает зона DNS-сервера (например, wsr.mv)
file можно поменять на свой путь (например: /var/dns/wsr.mv.db)
