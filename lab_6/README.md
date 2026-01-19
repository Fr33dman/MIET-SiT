## Лабораторная 6 — VLAN / VTP

### Схема сети
![image.png](images/lab_6_01.png)

## VTP

### VTP сервер 1Switch1
![image.png](images/lab_6_02.png)

### VTP клиент 1Switch11
![image.png](images/lab_6_03.png)

### VTP клиент 1Switch12
![image.png](images/lab_6_04.png)

## VLAN

### VLAN 10/20 созданы на сервере
![image.png](images/lab_6_05.png)

### VLAN 10/20 видны на клиентах
![image.png](images/lab_6_06.png)
![image.png](images/lab_6_07.png)

## Trunk

### Trunk‑порты
![image.png](images/lab_6_08.png)

## Access‑порты

### Порты доступа на 1Switch11
![image.png](images/lab_6_06.png)

### Порты доступа на 1Switch12
![image.png](images/lab_6_07.png)

## Router‑on‑a‑Stick

### Подинтерфейсы на 1Router1
![image.png](images/lab_6_09.png)

## IP адреса хостов

### IP конфиг PC111/PC112
![image.png](images/lab_6_10.png)
![image.png](images/lab_6_11.png)

### IP конфиг PC121/PC122
![image.png](images/lab_6_12.png)
![image.png](images/lab_6_13.png)

## Проверка

### Пинг между VLAN 10 и VLAN 20
![image.png](images/lab_6_14.png)

> *Примечание:
> Только в macos я в packet tracer наконец таки смог успешно сохранить свою конфигурацию, она лежит
> в `lab_6_configuration.pkt`, на windows при сохранении CPT вылетал и весь проект терялся, 
> поэтому мне приходилось работать без сохранений и не выключать комп. К сожалению
> все предыдущие лабы остаются без снапшотов, ну хотя бы начиная с этой снапшоты будут.*

## Ответы на вопросы для самопроверки

1. **Можно ли задать коммутатору IP‑адрес?** Да, на SVI (`interface vlan X`).
2. **Зачем нужна VLAN?** Сегментация сети, безопасность, контроль трафика.
3. **Что будет, если у нового VTP‑сервера revision больше?** Он перезапишет VLAN‑базу клиентов.
4. **Почему uplink должен быть trunk?** Чтобы передавать трафик всех VLAN.
5. **Что нужно для связи между VLAN?** Router‑on‑a‑stick или L3‑коммутатор.
6. **Какая VLAN по умолчанию?** VLAN 1.
7. **3 команды для ввода нового коммутатора в VTP‑домен:** `vtp domain`, `vtp mode`, `vtp password`.
8. **Режим VTP по умолчанию:** server.
9. **2 команды для удаления VLAN и сброса:** `delete vlan.dat` + `reload`.
10. **Команда для списка портов VLAN:** `show vlan brief`.
11. **Что мешает обновлениям VLAN на клиенте:** неверный домен/пароль, не trunk, несовпадение VTP версии, revision.
