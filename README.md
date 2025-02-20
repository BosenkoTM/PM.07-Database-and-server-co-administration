# PM.07 Database and server co-administration
## МДК.07.01 Database management and automation

# Lecturer
Timur Bosenko M. (bosenko@bmstu.ru)

Здесь Вы можете найти все материалы по дисциплине **`PM.07 Database and server co-administration`**. 

## Программное обеспечение 

`УДАЛЕННОЕ РАБОЧЕЕ МЕСТО`:
   
 - OC **`Ubuntu 20.04`**  Для предоставления результатов работы потребуется клиент [anydesk](https://anydesk.com/en/downloads/windows).
   
 - `ВИРТУАЛЬНАЯ ГОСТЕВАЯ ОС`.


## Текущая успеваемость

 [ТБД-81](https://docs.google.com/spreadsheets/d/1LhJVeOt4SUAfcl2VqmtYIUsI1eZX3sz-OJBXRNctIz4/edit?usp=sharing)

### [Индивидуальное задание 1](/practice/Ind_z_1.pdf)

1.	Реализовать мониторинг сети в системе [Zabbix](https://www.zabbix.com/ru/) (смотреть рисунок к заданию). Построить карту сети и настроить триггеры компонентов сети в зависимости от типа контролируемого оборудования (для серверов – сервер-шаблон использовать, для сетевого оборудования – маршрутизатор-шаблон). Все компоненты компьютерной сети виртуализировать на виртуальной машине. На сервере установить одну из современных СУБД ([Postgre sql](https://www.postgresql.org/), [MySql](https://www.mysql.com/)), реализовать следующие компоненты:
- установить [Docker](https://www.docker.com/);

- установить [Docker Compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-ru);

- настроить файл `docker-compose.yml` [по примеру](https://github.com/BosenkoTM/zabbix-composer);

- создать тестовую базу данных в СУБД с выгрузкой из внешнего файла ([репозиторий тут](/Data/Import)), не менее 5 таблиц, в таблице не менее 5 записей;

- создать разноуровневый доступ (пользователь, администратор);

- организовать журнал аудита и файл логов с анализом по операциям создания, удаления, обновления информации в таблицах;

- организовать систему резервного копирования (средствами СУБД, внешними утилитами);
 
- организовать резервное копирование базы данных;

Описать политики безопасности корпоративной сети и СУБД.

Подготовить отчет, загрузить в [Gogs](http://95.131.149.21:3000/) отчет, файл `docker-compose.yml`, ссылку на видеоотчет с пояснениями работы системы.


### Индивидуальное задание 2

Реализовать [интеграцию данных](https://disk.yandex.ru/d/nq4RLfxiJMELlw) в формате CSV с/на сервер БД

1. **Загрузить данные в СУБД `MySQL`**

  - развернуть докер-контейнер сервер `Mysql`;
  
  - реализовать алгоритм загрузки данных:
  
       - [**`данные1`**](https://disk.yandex.ru/d/gmrhTgGjYNX-eg) импортировать через сервис [ `SQLizer`, конверт `csv` в `DDL`(сервис доступен при включенном VPN)](https://sqlizer.io/#/); 
       
  - сгенерировать физическую схему бд; 
  
  - оформить отчет.
2. **Загрузить данные в СУБД `Postgres`**

  - развернуть [докер-контейнер](https://hub.docker.com/r/dpage/pgadmin4/) или [инсталятор](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads) сервер Postgres+Pgadmin;
  
  - реализовать алгоритм загрузки данных:

      - [**`данные1`**](https://disk.yandex.ru/d/gmrhTgGjYNX-eg) импортировать через сервис [ `SQLizer`, конверт `csv` в `DDL`(сервис доступен при включенном VPN)](https://sqlizer.io/#/); 
      
      - [**`данные2`**](https://disk.yandex.ru/d/40Xq-CfWklBNfQ) импортировать с использованием локального коннектора [`DBeaver`](https://dbeaver.io/).
  - сгенерировать физическую схему бд.

### Индивидуальное задание 3

Теоретический минимум [Mysql triggers](/sql-tasks/README.md).

Сертификация [Triggers](/questions/README.md).

[mysql-guides: triggers](https://github.com/yesnik/mysql-guides/blob/master/triggers.md).

## `Учебная практика` 

**Виды работ** (Работа с базой данных: добавление, удаление, обновление данных):
1. Разработка запросов на выборку, обработку данных в СУБД: `Oracle`, `MySQL`, `PostgreSQL`, `MongoDB`.

2. Обслуживание и поддерживание работу современных баз данных.

3. Технологии администрирования баз данных в следующих СУБД: `Oracle`, `MySQL`, `PostgreSQL`, `MongoDB`. 

4. Функции системы управления базами данных в среде СУБД SQL сервера.

5. Технологии администрирования серверов баз данных.

6. Защита и сохранность информации баз данных.

Практическое задание [DE_1](https://github.com/BosenkoTM/PM.07-Database-and-server-co-administration/tree/main/edu_practice/DE_01).

 - Развернуть `Postgres Server`+`pgadmin4`.
 
 - Развернуть `Mysql Server`.
 
 - Загрузить [схему данных БД](/edu_practice/DE_01/Сессия%201/my.sql) в СУБД `MySQL`, `Postgres`.
 
 - Загрузить в [схему данных БД](/edu_practice/DE_01/Сессия%201/my.sql) входные данные из [CSV-файлов](/edu_practice/DE_01/Сессия%201/service_s_import.csv)  и [txt](/edu_practice/DE_01/Сессия%201/client_s_import.txt).
 
 - Построить `Case`-диаграмму.

- Построить словарь данных.

## Теоретические вопросы

1.	Технология установки и настройка сервера MySQL в операционной системе Windows.
2.	Клиентские настойки, протоколирование, безопасность.
3.	Технология установки и настройка сервера MySQL в операционных системах Linux.
4.	Удаленное администрирование.
5.	Аудит базы данных. Аудиторский журнал. Установка опций, включение и отключение аудита. Очистка и уменьшение размеров журнала.
6.	Технологии создания базы данных с применением языка SQL.
7.	Создание запросов, процедур и триггеров.
8.	Динамический SQL и его операторы.
9.	Особенности обработки данных в объектно-ориентированных базах данных.
10.	Инструменты мониторинга нагрузки сервера.
11.	Законодательство Российской Федерации в области защиты информации. Перечислите основные федеральные законы в области защиты информации и опишите ключевые моменты этих законов.
12.	Перечислите задачи системы безопасности и основные инструменты защиты ОС. Классы защиты автоматизированных систем.
13.	Опишите принцип работы утилиты архивации и восстановления.  Опишите принцип работы шифрования диска. Опишите принцип работы Службы доверенного платформенного модуля. 
14.	Определите назначение политики безопасности системы.  Где производится настройка политики безопасности системы? Что такое групповые политики? Как запретить доступ сетевых пользователей к компьютеру? 
15.	Как разрешить доступ сетевым пользователям, которым разрешено работать в системе к компьютеру?  Определите назначения пункта политики безопасности Разрешать вход в систему через службу терминалов. 
16.	Как предоставить определенной группе пользователей вносить изменения в системное время?  Определите назначение пункта политики безопасности Отладка программ. 
17.	Каким образом запретить вход определенной группе пользователей в систему по локальной сети? Определите назначение пункта политики безопасности Принудительное удаленное завершение. 
18.	Как установить пользователей и их группы, которые могут локально входить в систему? Как запретить определенной группе пользователей завершать работу системы, и в каких случаях это актуально? 
19.	В каком разделе производится настройка глобальных параметров безопасности? Определите назначение политики обновления. Как произвести настройку политики обновления? 
20.	Какие события безопасности должны фиксироваться в журнале аудита? Какие параметры определяют политику аудита? Какие факторы влияют на определение размеров доменов безопасности? 
21.	Какие дополнительные возможности разграничения доступа к информационным ресурсам предоставляет шифрующая файловая система? Как осуществляется проверка целостности жесткого диска, с какой целю выполняются эти процедуры.
22.	Какие виды мониторинга рабочих операций пользователя существуют? Дайте характеристику современным программным средств мониторинга действий пользователей. Какое программное средство вы порекомендовали бы нашей организации? Почему? 
23.	Вид сертификации ПО.Орган по сертификации ПО в регионе.
24.	Документы, необходимые для процедуры сертификации ПО.  Порядок получения сертификата.  Документ, получаемый при положительном результате сертификационных испытаний. 
25.	Перечислите факторы по которым отличают резервную копию для быстрого восстановления от архива.
26.	Принципиальное отличие резервного копирования от систем избыточного резервирования.
27.	Каким методом можно обеспечить информационную безопасность - В случае вирусной атаки или повреждение данных из-за пресловутого «человеческого фактора».
28.	Полное резервное копирование. Перечислите преимущества и недостатки этого метода
29.	Инкрементное копирование. Обратное инкрементное резервное копирование. Опишите механизм выполнения таких методов копирования.
30.	Дифференциальное резервное копирование. Перечислите преимущества и недостатки этого метода и его отличие от инкрементного копирования.
31.	Топология резервного копирования - какие бывают схемы резервного копирования.
32.	Какими средствами решается задача мониторинга компьютерных сетей. Какие функции выполняют Анализаторы протоколов. Какими свойствами обладают Анализаторы протоколов.
33.	Назначение и функции экспертных систем. Система обнаружения и предотвращения проникновения (IDS). Почему следует использовать IDPS, особенно если уже имеются межсетевые экраны, антивирусные инструментальные средства и другие средства защиты?
34.	На какие этапы делится аудит информационной безопасности. Какую основную информацию регламент содержит.


## ТЕСТ 1. МДК 07.01 Тема 7.1.1. Принципы построения и администрирования баз данных(Docker). 
[ССЫЛКА ДЛЯ ВХОДА](https://docs.google.com/forms/d/e/1FAIpQLSdTic2iU8W_1mf1gLclVd6aRMFfXs6tvFYpJUCeNoHqz4QrMA/viewform?usp=sf_link)

## ТЕСТ 2. МДК 07.01 Тема 7.1.1. Принципы построения и администрирования баз данных(SQL+Zabbix). 
[ССЫЛКА ДЛЯ ВХОДА]()
