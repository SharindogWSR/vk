# Настройка файла hosts

``` nano /etc/hosts ```

указываем путь до нужно сервера и его адреса (на скрине с сервера SRV-L до SRV-R)
ip адрес хост внутреннее отображение
ТАК ЖЕ можно добавить через echo (скрин 2)

**ОБЯЗАТЕЛЬНО !!!** Чтобы проверка происходила СНАЧАЛА через DNS (а не через /etc/hosts)
в файле ``` /etc/nsswitch.conf ``` меняем у параметра hosts:
``` files dns ``` НА ``` dns files ```

[![https://sun9-81.userapi.com/impg/oK21UAXU5FyEPdw6gtm-gmoezc7aimwcduv9Fg/xGC14Cf6F5w.jpg?size=476x76&quality=96&sign=673ed4dc6306bd503a258f7fb130ef6e&type=album](https://sun9-81.userapi.com/impg/oK21UAXU5FyEPdw6gtm-gmoezc7aimwcduv9Fg/xGC14Cf6F5w.jpg?size=476x76&quality=96&sign=673ed4dc6306bd503a258f7fb130ef6e&type=album "https://sun9-81.userapi.com/impg/oK21UAXU5FyEPdw6gtm-gmoezc7aimwcduv9Fg/xGC14Cf6F5w.jpg?size=476x76&quality=96&sign=673ed4dc6306bd503a258f7fb130ef6e&type=album")](https://sun9-81.userapi.com/impg/oK21UAXU5FyEPdw6gtm-gmoezc7aimwcduv9Fg/xGC14Cf6F5w.jpg?size=476x76&quality=96&sign=673ed4dc6306bd503a258f7fb130ef6e&type=album "https://sun9-81.userapi.com/impg/oK21UAXU5FyEPdw6gtm-gmoezc7aimwcduv9Fg/xGC14Cf6F5w.jpg?size=476x76&quality=96&sign=673ed4dc6306bd503a258f7fb130ef6e&type=album")

[![https://sun9-55.userapi.com/impg/Khl4uz68z-tPIRoCz2DuIqPMYDTZ6Gnu7g3Esg/wH2Av3StEtw.jpg?size=414x29&quality=96&sign=8b30a4599a8ed9efdbcd26d2e568181a&type=album](https://sun9-55.userapi.com/impg/Khl4uz68z-tPIRoCz2DuIqPMYDTZ6Gnu7g3Esg/wH2Av3StEtw.jpg?size=414x29&quality=96&sign=8b30a4599a8ed9efdbcd26d2e568181a&type=album "https://sun9-55.userapi.com/impg/Khl4uz68z-tPIRoCz2DuIqPMYDTZ6Gnu7g3Esg/wH2Av3StEtw.jpg?size=414x29&quality=96&sign=8b30a4599a8ed9efdbcd26d2e568181a&type=album")](https://sun9-55.userapi.com/impg/Khl4uz68z-tPIRoCz2DuIqPMYDTZ6Gnu7g3Esg/wH2Av3StEtw.jpg?size=414x29&quality=96&sign=8b30a4599a8ed9efdbcd26d2e568181a&type=album "https://sun9-55.userapi.com/impg/Khl4uz68z-tPIRoCz2DuIqPMYDTZ6Gnu7g3Esg/wH2Av3StEtw.jpg?size=414x29&quality=96&sign=8b30a4599a8ed9efdbcd26d2e568181a&type=album")
