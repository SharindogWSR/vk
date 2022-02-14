# DNS BIND9
1.
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

2.
Указываем обратную зону, которую будет обслуживать сервер (ip наоборот)
так же и для второй сети 20
allow-update {any; };
[![https://sun9-1.userapi.com/impg/8MTFqD2MIGPG-ED3a-P2W3ZbH0g_Jl8kytqUBw/6_cp1eC1kKA.jpg?size=464x285&quality=96&sign=aadcd1b1f4904580dfbcac6def1b7f90&type=album](https://sun9-1.userapi.com/impg/8MTFqD2MIGPG-ED3a-P2W3ZbH0g_Jl8kytqUBw/6_cp1eC1kKA.jpg?size=464x285&quality=96&sign=aadcd1b1f4904580dfbcac6def1b7f90&type=album "https://sun9-1.userapi.com/impg/8MTFqD2MIGPG-ED3a-P2W3ZbH0g_Jl8kytqUBw/6_cp1eC1kKA.jpg?size=464x285&quality=96&sign=aadcd1b1f4904580dfbcac6def1b7f90&type=album")](https://sun9-1.userapi.com/impg/8MTFqD2MIGPG-ED3a-P2W3ZbH0g_Jl8kytqUBw/6_cp1eC1kKA.jpg?size=464x285&quality=96&sign=aadcd1b1f4904580dfbcac6def1b7f90&type=album "https://sun9-1.userapi.com/impg/8MTFqD2MIGPG-ED3a-P2W3ZbH0g_Jl8kytqUBw/6_cp1eC1kKA.jpg?size=464x285&quality=96&sign=aadcd1b1f4904580dfbcac6def1b7f90&type=album")

3.
```
named-checkconf
```
проверка, правильно ли составлен файл
если нет ответа - всё хорошо

4.

```
mkdir /var/dns/
    cp ... (db.127 и db.local) /var/dns/... (имя как в зонах, wsr.mv.db, 10.16.172.in-addr.arpa.db и т.д)
```

5 Редактируем wsr.mv.db
ОБЯЗАТЕЛЬНО .
[![https://sun9-62.userapi.com/impg/JwxEccyASyGqp9lKXdaj7mHNOfEUmbNVImEI4Q/CCEoBpgf85g.jpg?size=962x510&quality=96&sign=c058bdf6da3dd2da126fe5aebd6e4d15&type=album](https://sun9-62.userapi.com/impg/JwxEccyASyGqp9lKXdaj7mHNOfEUmbNVImEI4Q/CCEoBpgf85g.jpg?size=962x510&quality=96&sign=c058bdf6da3dd2da126fe5aebd6e4d15&type=album "https://sun9-62.userapi.com/impg/JwxEccyASyGqp9lKXdaj7mHNOfEUmbNVImEI4Q/CCEoBpgf85g.jpg?size=962x510&quality=96&sign=c058bdf6da3dd2da126fe5aebd6e4d15&type=album")](https://sun9-62.userapi.com/impg/JwxEccyASyGqp9lKXdaj7mHNOfEUmbNVImEI4Q/CCEoBpgf85g.jpg?size=962x510&quality=96&sign=c058bdf6da3dd2da126fe5aebd6e4d15&type=album "https://sun9-62.userapi.com/impg/JwxEccyASyGqp9lKXdaj7mHNOfEUmbNVImEI4Q/CCEoBpgf85g.jpg?size=962x510&quality=96&sign=c058bdf6da3dd2da126fe5aebd6e4d15&type=album")

Готовый файл
[![https://sun9-33.userapi.com/impg/Gi01Wv-HMaGr_QgB_5HdDCGWGJp8et13k3XmYQ/zaA5cec_ZBE.jpg?size=556x267&quality=96&sign=03a45073c929f57c677a265b698290a2&type=album](https://sun9-33.userapi.com/impg/Gi01Wv-HMaGr_QgB_5HdDCGWGJp8et13k3XmYQ/zaA5cec_ZBE.jpg?size=556x267&quality=96&sign=03a45073c929f57c677a265b698290a2&type=album "https://sun9-33.userapi.com/impg/Gi01Wv-HMaGr_QgB_5HdDCGWGJp8et13k3XmYQ/zaA5cec_ZBE.jpg?size=556x267&quality=96&sign=03a45073c929f57c677a265b698290a2&type=album")](https://sun9-33.userapi.com/impg/Gi01Wv-HMaGr_QgB_5HdDCGWGJp8et13k3XmYQ/zaA5cec_ZBE.jpg?size=556x267&quality=96&sign=03a45073c929f57c677a265b698290a2&type=album "https://sun9-33.userapi.com/impg/Gi01Wv-HMaGr_QgB_5HdDCGWGJp8et13k3XmYQ/zaA5cec_ZBE.jpg?size=556x267&quality=96&sign=03a45073c929f57c677a265b698290a2&type=album")

6.
Редактируем права доступа
```
nano /etc/apparmor.d/usr.sbin.named
```
добавляем к bind
/var/dns/** rw,

```
service apparmor restart
service bind9 restart 
```
nano /etc/resolv.conf
[![https://sun9-63.userapi.com/impg/-n4Z75_f1iAOD-fHZsyio2O-3-PbM3VJ3buSlw/2Cuaz5yLIqs.jpg?size=408x155&quality=96&sign=5666ae2ddb613178787bb226c6b1e684&type=album](https://sun9-63.userapi.com/impg/-n4Z75_f1iAOD-fHZsyio2O-3-PbM3VJ3buSlw/2Cuaz5yLIqs.jpg?size=408x155&quality=96&sign=5666ae2ddb613178787bb226c6b1e684&type=album "https://sun9-63.userapi.com/impg/-n4Z75_f1iAOD-fHZsyio2O-3-PbM3VJ3buSlw/2Cuaz5yLIqs.jpg?size=408x155&quality=96&sign=5666ae2ddb613178787bb226c6b1e684&type=album")](https://sun9-63.userapi.com/impg/-n4Z75_f1iAOD-fHZsyio2O-3-PbM3VJ3buSlw/2Cuaz5yLIqs.jpg?size=408x155&quality=96&sign=5666ae2ddb613178787bb226c6b1e684&type=album "https://sun9-63.userapi.com/impg/-n4Z75_f1iAOD-fHZsyio2O-3-PbM3VJ3buSlw/2Cuaz5yLIqs.jpg?size=408x155&quality=96&sign=5666ae2ddb613178787bb226c6b1e684&type=album")
