
## Подготовка к выполнению

1. Подготовьте в Yandex Cloud три хоста: для `clickhouse`, для `vector` и для `lighthouse`.
2. Репозиторий LightHouse находится [по ссылке](https://github.com/VKCOM/lighthouse).

## Основная часть

1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает LightHouse.
2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
3. Tasks должны: скачать статику LightHouse, установить Nginx или любой другой веб-сервер, настроить его конфиг для открытия LightHouse, запустить веб-сервер.
4. Подготовьте свой inventory-файл `prod.yml`.
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
9. Подготовьте README.md-файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.
10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-03-yandex` на фиксирующий коммит, в ответ предоставьте ссылку на него.

---

### Ответ

В Yandex Cloud запущено 3 ВМ:

![Screen1](https://github.com/megasts/08-ansible-03-yandex/blob/master/img/2024-12-23_00-19-21.png)

Готовый playbook находится [здесь.](https://github.com/megasts/08-ansible-03-yandex/blob/master/playbook)

Подтверждение работы playbook:

1. В результате работы темплейта на хосте Vector появился конфигурационный файл vector.yml: 

![Screen2](https://github.com/megasts/08-ansible-03-yandex/blob/img/2024-12-23_00-39-15.png)

2. Clickhouse-client работает на хосте clickhouse:

![Screen3](https://github.com/megasts/08-ansible-03-yandex/blob/img/2024-12-23_00-36-30.png)

3. Lighthouse запущен:

![Screen4](https://github.com/megasts/08-ansible-03-yandex/blob/img/2024-12-23_00-37-42.png)



### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
