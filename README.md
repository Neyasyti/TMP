# Практика 0
```
@startuml "Практическая работа 1"
left to right direction
title Информационная система жилищного агенства
skinparam backgroundcolor PowderBlue
actor Квартиросъемщик AS kvr
actor Владелец AS vld
rectangle Система {
    vld ---> (Предоставить информацию о жилье)
    kvr ---> (Поиск жилья)
    (Поиск жилья) <... (Зарегистрироваться в системе):<<include>>
    (Поиск жилья) ...> (Снять жилье):<<include>>
    (Предоставить информацию о жилье) <... (Зарегистрироваться в системе):<<include>>
    (Предоставить информацию о жилье) ...> (Сдать жилье):<<include>>
}
@enduml
```
# Практика 1
```
@startuml "Практическая работа 1"
left to right direction
title Информационная система жилищного агенства
skinparam backgroundcolor PowderBlue
actor Квартиросъемщик AS kvr
actor Владелец AS vld
rectangle Система {
    vld ---> (Зарегистрироваться в системе)
    vld ---> (Предоставить информацию о жилье)
    kvr ---> (Зарегистрироваться в системе)
    kvr ---> (Поиск жилья)
    (Поиск жилья) <... (Зарегистрироваться в системе):<<include>>
    (Поиск жилья) ...> (Снять жилье):<<include>>
    (Предоставить информацию о жилье) <... (Зарегистрироваться в системе):<<include>>
    (Предоставить информацию о жилье) ...> (Сдать жилье):<<include>>
}
@enduml
```

![Система](https://github.com/Smipos/TMP/blob/main/practices/practice_1/1.png)

```
@startuml
skinparam backgroundcolor PowderBlue
class Владелец{
+ФИО
+Паспортные данные
+Документы на квартиру
Регистраия в системе()
Предоставить информацию о жилье()
Сдать жилье()
}

class Квартиросъемщик{
+ФИО
+Паспортные данные
+Справка о доходах
+Справка о судимости
Регистраия в системе()
Поиск жилья()
Снять жилье()
}

class Квартира{
+Адрес квартиры
+Номер этажа
+Номер квартиры
+Количество комнат
+Техника в квартире
}

class Аккаунт{
+Логин
+Пароль
+Номер телефона
+Верификация
}

Владелец ---> Аккаунт:Регистрирует акк
Квартиросъемщик --> Аккаунт:Регистрирует акк
Аккаунт ...> Квартира: Выставить и поиск 
Владелец ---> Квартира:Регистрирует в системе
Владелец ---> Квартира:Сдать жилье
Квартиросъемщик ---> Квартира: Снять жилье
@enduml
```
![Действия](https://github.com/Smipos/TMP/blob/main/practices/practice_1/2.png)
