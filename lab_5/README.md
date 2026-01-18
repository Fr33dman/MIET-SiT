## Лабораторная 5 — RIP/OSPF/EIGRP

### Схема сети
![image.png](images/lab_5_01.png)

## RIPv2

### Настройка IP на SVC01
![image.png](images/lab_5_02.png)

### Настройка IP на RTR01
![image.png](images/lab_5_03.png)

### Настройка IP на RTR02
![image.png](images/lab_5_04.png)

### Настройка IP на PC0/PC1
![image.png](images/lab_5_05.png)
![image.png](images/lab_5_06.png)

### Настройка IP на PC2/PC3
![image.png](images/lab_5_07.png)
![image.png](images/lab_5_08.png)

### Настройка IP на Server0/Printer0
![image.png](images/lab_5_09.png)
![image.png](images/lab_5_10.png)

### RIP настроен на всех маршрутизаторах
![image.png](images/lab_5_11.png)

### Таблица маршрутизации после RIP
![image.png](images/lab_5_12.png)

### Проверка связи
![image.png](images/lab_5_13.png)

## OSPFv2

### OSPF, OSPF база, маршруты OSPF на RTR01
![image.png](images/lab_5_14.png)

### Проверка связи через OSPF
![image.png](images/lab_5_15.png)

## EIGRP

### EIGRP соседи, EIGRP topology, Маршруты EIGRP на RTR01
![image.png](images/lab_5_16.png)

### Проверка связи через EIGRP
![image.png](images/lab_5_17.png)

## Ответы на вопросы для самопроверки

1. **Максимальное количество переходов RIP:** 15 (16 считается недостижимым).
2. **Почему компания переходит со статических маршрутов на динамические:** масштабируемость, меньше ручной работы, автообновление маршрутов.
3. **Три команды для проверки версии RIP:** `show ip protocols`, `show ip route`, `show running-config`.
4. **Бесклассовая версия RIP с VLSM:** RIPv2.
5. **Какие маршруты показал `show ip rip database` на Router1:** все удаленные подсети, полученные по RIP (LAN Router2, LAN Router3 и линк между ними).
6. **Команда для наблюдения обновлений RIP в реальном времени:** `debug ip rip`.
7. **Почему после настройки OSPF исчезли маршруты RIP:** OSPF имеет меньшую административную дистанцию (110) чем RIP (120), поэтому он вытесняет RIP из RIB.
8. **Команда для полной базы OSPF:** `show ip ospf database`.
9. **Преимущества суммирования маршрутов по умолчанию:** меньше размер таблицы и трафика обновлений, выше масштабируемость.
10. **Когда требуется ручное суммирование:** при VLSM, несмежных подсетях или чтобы уменьшить таблицу маршрутизации.
11. **Сколько маршрутов EIGRP и прямых маршрутов на всех маршрутизаторах:** в топологии с 3 роутерами обычно по 3 прямых и 3 EIGRP у каждого (итого 9 + 9).
12. **Сколько пассивных маршрутов в топологии EIGRP:** все маршруты должны быть в состоянии Passive (Active = 0).
13. **Что выводит `debug eigrp packet`:** обмен EIGRP-пакетами (Hello, Update, Query, Reply).
14. **Что выводит `debug eigrp fsm`:** процессы DUAL/FSM и пересчет маршрутов.
