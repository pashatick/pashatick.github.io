# **Space Details:**

|**Key**|EL|
| :-: | :- |
|**Name**|Elephant|
|**Description**||
|**Created by**|61d2ca349ee70a00684f364a (мар. 17, 2022)|


## **Навигация по документу:**

  - [Elephant Project](#ElephantProject) 
    - [Глоссарий](#1.Глоссарий)
    - [1. Исходные требования](#Исходныеданные)
    - [2. Описание бизнес-процесса и участников](#2.Описаниебизнес-процессаиучастников) 
      - [2.1. Участники бизнес процесса](#2.1.Участникибизнеспроцесса)
      - [2.2. Описание бизнес-процесса приобретения животнго](#2.2.Описаниебизнес-процессаприобретенияживотнго)
      - [2.3. Описание бизнес-процесса возврата животных](#2.3.Описаниебизнес-процессавозвратаживотных)
      - [2.4. Описание процесса добавления нового животного](#2.4.Описаниепроцессадобавленияновогоживотного)
    - [3. Users Storyes](#3.UsersStoryes) 
      - [3.1 US пользователя системы (клиент фермы)](#3.1USпользователясистемы(клиентфермы)) 
        - [UC 3.1.1 UC Регистрация пользователя](#UC3.1.1Регистрацияпользователя)
        - [UC 3.1.2 UC Приобретение животного](#3.1.2.UCПриобретениеживотного)
        - [UC 3.1.3 UC Оформление возврата](#3.1.3UCОформлениевозврата)
      - [3.2. US Персонал фермы](#3.2.USПерсоналфермы) 
        - [3.2.1. UC добавление информации о животных](#3.2.1UCдобавлениеинформацииоживотных)
        - [3.2.2. UC редактирование данных](#3.2.2.UCредактированиеданных)
        - [3.2.3. UC Удаление животного из системы](#3.2.3.UCУдалениеживотногоизсистемы)
    - [4. Модель базы данных](#4.Модельбазыданных)
    - [5. API системы](#5.APIсистемы)
    - [6. UX/UI](#6.UX/UI) 
      - [UI клиентов системы](#UIклиентовсистемы)
    - [7. Архитектура проекта](#7.Архитектурапроекта)

### **Elephant Project**  <a name="ElephantProject"></a>
|**ФИО/организация**|**Роль**|**Цель**|
|--|--|--|
|Школа SA Сбер|Заказчик|- Найм новых сотрудников -Оценка качества освоения учебной программы.|
|Гобелков Павел|Исполнитель (системный аналитик, UI, Back-End и БД)|- Трудоустройство - Освоение методов системного анализа; - Практическое применение полученных навыков; - Разработка проектов для портфолио.|

##### **Задание на работу:** 

Подготовить Системные требования к автоматизированной системе (Техническое задание для программиста). В проработку должны входить:

1. Спроектированный образец UI системы

2. Сформировать API (Проектирование API интерфейса нужно выполнить в нотации [Open API Specification](https://swagger.io/specification/)

3. Спроектировать логику на БэкЭнде в виде UML activity diagram или BPMN (на выбор).

4. Спроектировать реляционную БД (Таблицы, их атрибуты и характеристики атрибутов. ER-diagram)

5. Схемы можно рисовать там, где удобно, главное прислать её изображения.

6. Спроектировать отчет

##### **Что должно получиться:**

[x] Хотя бы одна форма UI

[x] Хотя бы 3 API

[x] Хотя бы 1 схема UML activity diagram или BPMN из 7-20 элементов

[x] Хотя бы 2-3 таблицы в БД и связи между ними в виде ERD

[x] Образец отчёта и описание его показателей

### **Исходные требования** <a  name="Исходныеданные"></a>
|**id**|**Описание**|**Комментарий**|**Ответ**|
|--|--|--|--|
|1| Должен быть реализован учет имеющихся в наличии слонов с указанием их характеристик (ID слона, вес, площадь ушей, длина хобота, цвет глаз, пол, вид, возраст).|Требование по учету цвета глаз слона предлагаю не реализовывать, т.к. большинство слонов имеют карий цвет глаз. Является ли площадь ушей и длина хоботом важным качественным признаком? Так же предлагаю добавить информацию о половой принадлежность, возрасте и виде слона.|--| 
|2| Необходимо обеспечить возможность выдачи слона.|Оставить без изменений|--|
|3| Доступ к услуге «Раздача слонов» должен осуществляться при обращении клиента непосредственно в пункт выдачи| Предлагаю осуществить возможность заблаговременного бронирования через сервис|--|
|4| Необходимо осуществить проверку заказчика  на возможность его содержания (наличие вольера или иного места содержания, кормовой базы)|**НЕ РЕАЛИЗОВЫВАТЬ**|Отклонено|
|5| Необходимо обеспечить возможность возврата слона. Возврат м.б. осуществлен не позднее 7 рабочих дней с момента выдачи.| Достаточно ли времени для возврата с учетом того, что мы предоставляем животных в зоопарки на различном удалении, возможно стоит увеличить время?|**Приянято**|
|6| Необходимо обеспечить возможность обмена слона на другого при условии, что вес сдаваемого слона будет меньшим, чем вес выдаваемого.|Оставить без изменений|--|
|7| Необходимо разработать отчетность по учету наличия слонов в пунктах выдачи и учету движения слонов (возврат/обмен).|Оставить без изменений|--| 
	

### **1. Глоссарий** <a  name="1.Глоссарий"></a>

### **2. Описание бизнес-процесса и участников** <a  name="2.Описаниебизнес-процессаиучастников"></a>
**Описание AS IS:**

Компания, занимающаяся разведением слонов для поставок в зоопарки мира на безвозмездной основе, приняла решение открыть дополнительной бизнес – бесплатную раздачу слонов.

На текущий момент есть Платформа, позволяющая реализовывать бизнес-логику (Back-End), в качестве хранилища данных используется реляционная СУБД. Необходимо разработать продукт реализующий выдачу, обмен и возврат слонов.

Продукт разрабатывается с нуля, при этом на платформе уже реализованы и работают другие продукты (Back-End), обеспечивающие автоматизацию деятельности разведения, кормления и поставок слонов в зоопарки мира. Платформа является частью (Back-End) общего IT ландшафта компании.


### **2.1. Участники бизнес процесса** <a  name="2.1.Участникибизнеспроцесса"></a>

Участниками бизнес процесса являются лица, организации,системы, заинтересованные в предоставлении/получении услуг, которые являются результатом работы бизнес-процесса.

|Участник БП|Портрет пользователя|Цели и задачи|
|--|--|--|
|Клиент фермы|Очень богатый человек с кучей свободного времени, который хочет потратить его на уход за слоном|Получить слона|
|Админ|Лицо ответственное за передачу/возврат/обмен товара надлежащего качества|Проверка товара на соответствие параметров приема/сдачи |
|Система учета и уонтроля|Автоматизированая система по управлению поголовьем фермы, осуществляющая контроль количественного и качесвтенного состава поголовья.|Оптимизация работы по обслуживанию|
|Система раздачи животных|Система контроля перемещения животных от производителя к получателю.|Оптимизация работы по передачи животных|


### **2.2. Описание бизнес-процесса приобретения животнго** <a  name="2.2.Описаниебизнес-процессаприобретенияживотнго"></a>
<br>

![](/bpmn/bpmnBye.png)

### **2.3. Описание бизнес-процесса возврата животных** <a  name="2.3.Описаниебизнес-процессавозвратаживотных"></a>
<br>

![](/bpmn/bpmnRefund.png)


### **2.4. Описание процесса добавления нового животного** <a  name="2.4.Описаниепроцессадобавленияновогоживотного"></a>
<br>

![](/bpmn/bpmnAdd.png)


### **3. Users Storyes** <a  name="3.UsersStoryes"></a>
### **3.1 US пользователя системы (клиент фермы)** <a  name="3.1USпользователясистемы(клиентфермы)"></a>
### **UC 3.1.1 UC Регистрация пользователя** <a  name="UC 3.1.1UCРегистрацияпользователя"></a>
*Опсиание UC*


|**UC Link**|[Сслыка Jira](https://pashatick.atlassian.net/browse/EL-10)|
|--|--|
|**Действующее лицо**|Клиент системы|
|**Краткое описание**| Регистрация пользователя в системе раздачи слонов|
|**Предварительные условия**|Клиент зашел в веб приложение|
|**Сыылкана API**|[openAPI](https://app.swaggerhub.com/apis/pashatick/elephantAPI/1.0.0#/)|
|**Пример UI**|<img src="/ui/21102993.png" width="100" height="75"<br>
<img src="/ui/21102978.png" width="100" height="75"><br>
<img src="/ui/21102981.png" width="100" height="75">|


![UMLUC](/uml/createAcc.png)

*Действия пользователя:*

|Действие|<span style="color:Green">Ожидаемый результат</span>|<span style="color:Red">Альтернативный</span>|
|--|--|--|
|Нажать кнопку "Регистрация"|*200*<br> Открылась форма регистрации|*500* <br> сервер не отвечает|
|Ввод данных пользователем|*200*<br>Регистрация успешна|*422*<br>НЕ заполенны обязательные поля|
|**Конец операции**|Успешная регистарция пользователя|Пользователь не зарегистрирован|


Список задач по кейсу:

|**Ссылка на задачу**|**Исполнитель**|
|--|--|
|||
|||
|||


### **UC 3.1.2 UC Приобретение животного** <a  name="UC 3.1.2UCПриобретениеживотного"></a>
### **UC 3.1.3 UC Оформление возврата** <a  name="UC 3.1.3UCОформлениевозврата"></a>
### **3.2. US Персонал фермы** <a  name="3.2.USПерсоналфермы"></a>
### **3.2.1. UC добавление информации о животных** <a  name="3.2.1.UCдобавлениеинформацииоживотных"></a>
### **3.2.2. UC редактирование данных** <a  name="3.2.2.UCредактированиеданных"></a>
### **3.2.3. UC Удаление животного из системы** <a  name="3.2.3.UCУдалениеживотногоизсистемы"></a>
### **4. Модель базы данных** <a  name="4.Модельбазыданных"></a>
**Краткое описание**

Модель построена при помощи инструментов сервиса SmartMarket Stidio в редакторе DataSpace. 

Модель представлена двумя агрегатами: 

- DistSystem 
  - DistSystem(базовый)
  - Customer 
- ControlSystem связаных
  - ControlSystem
  - Staff
  - Valier
  - AnimalsProp
Так же содержит семь нумерованных списков:
- SPECIES
- SUBSPECIES
- GENDERKIND
- STATUSLIST
- VALIESRTYPE
- OPERATIONLIST
- DISTPOINLIST

XML образ:

<`<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<model model-name="ds_______285d75f6_8a00_4245_ad35_51a4c9c" version="0.0.2">
  <layout>
    <model/>
    <enums>
      <enum name="SubSpecies">
        <value name="SAVAN" x="-82" y="-214"/>
        <value name="FOREST" x="-78" y="-159"/>
        <value name="DWARF_OF_CYPRUS" x="-78" y="-99"/>
        <value name="DWARF_OF_SICILIAN" x="-78" y="-39"/>
        <value name="ASIAN" x="-73" y="20"/>
      </enum>
      <enum name="GenderKind">
        <value name="MALE" x="-221" y="184"/>
        <value name="FEMALE" x="-222" y="241"/>
      </enum>
      <enum name="VALIERSTYPE">
        <value name="OPEN" x="-2210" y="-10"/>
        <value name="CLOSED" x="-2230" y="71"/>
      </enum>
      <enum name="OPERATIONSLIST">
        <value name="RECEIVING" x="-2551" y="-665"/>
        <value name="REFUND" x="-2535" y="-613"/>
      </enum>
      <enum name="DpointList">
        <value name="POINT2" x="-2457" y="-991"/>
        <value name="POINT1" x="-2457" y="-1051"/>
        <value name="POINT3" x="-2457" y="-931"/>
        <value name="MAIN" x="-2456" y="-1115"/>
      </enum>
      <enum name="StatusList">
        <value name="FREE" x="-2086" y="-309"/>
        <value name="SOLD" x="-2089" y="-376"/>
        <value name="RECERVED" x="-2086" y="-447"/>
        <value name="FREE" x="-2086" y="-369"/>
      </enum>
      <enum name="Species">
        <value name="AFRICAN" x="-514" y="-566"/>
        <value name="INDIAN" x="-550" y="-476"/>
      </enum>
    </enums>
    <classes>
      <class name="AnimalsProp">
        <property name="imageLink" x="-593" y="358"/>
        <property name="detachment" x="-593" y="-62"/>
        <property name="weigth" x="-593" y="118"/>
        <property name="tronkLength" x="-593" y="178"/>
        <property name="gender" x="-593" y="238"/>
        <property name="age" x="-593" y="298"/>
        <property name="species" x="-593" y="-2"/>
        <property name="subSpecies" x="-593" y="58"/>
      </class>
      <class name="Valier">
        <property name="serialNum" x="-1471" y="93"/>
        <property name="typeOfvalier" x="-1471" y="-95"/>
        <property name="square" x="-1475" y="33"/>
        <property name="countNumber" x="-1475" y="-27"/>
      </class>
      <class name="DistSystem">
        <property name="customer" x="-1840" y="-1134"/>
        <property name="operationType" x="-1836" y="-952"/>
        <property name="status" x="-1835" y="-889"/>
        <property name="custDate" x="-1840" y="-1074"/>
        <property name="distPoint" x="-1838" y="-1012"/>
        <reference name="animal" x="-1657" y="-819"/>
      </class>
      <class name="Customer">
        <property name="name" x="-1274" y="-1316"/>
        <property name="country" x="-1274" y="-1256"/>
        <property name="address" x="-1274" y="-1136"/>
        <property name="phone" x="-1274" y="-1076"/>
        <property name="email" x="-1274" y="-1016"/>
        <property name="city" x="-1274" y="-1196"/>
      </class>
      <class name="AnimalsControl">
        <property name="expDate" x="-1040" y="110"/>
        <property name="name" x="-1040" y="-70"/>
        <property name="valier" x="-1040" y="-10"/>
        <property name="staff" x="-1040" y="50"/>
        <property name="distStatus" x="-1040" y="170"/>
        <property name="valierNum1" x="-1043" y="238"/>
      </class>
      <class name="Staff">
        <property name="vacancy" x="-1449" y="362"/>
        <property name="lastName" x="-1449" y="302"/>
        <property name="firstName" x="-1462" y="242"/>
        <property name="petCount" x="-1449" y="422"/>
      </class>
    </classes>
  </layout>
  <enum name="SubSpecies">
    <value name="SAVAN"/>
    <value name="FOREST"/>
    <value name="DWARF_OF_CYPRUS"/>
    <value name="DWARF_OF_SICILIAN"/>
    <value name="ASIAN"/>
  </enum>
  <enum name="GenderKind">
    <value name="MALE"/>
    <value name="FEMALE"/>
  </enum>
  <enum name="VALIERSTYPE">
    <value name="OPEN"/>
    <value name="CLOSED"/>
  </enum>
  <enum name="OPERATIONSLIST">
    <value name="RECEIVING" label="ПОЛУЧЕНИЕ ЗАКАЗА"/>
    <value name="REFUND" label="возврат"/>
  </enum>
  <enum name="DpointList">
    <value name="POINT2"/>
    <value name="POINT1"/>
    <value name="POINT3"/>
    <value name="MAIN"/>
  </enum>
  <enum name="StatusList" label="Список возможных состояний позиции">
    <value name="FREE"/>
    <value name="SOLD" label="ПРОДАН"/>
    <value name="RECERVED" label="ЗАБРОНИРОВАН ПОКУПАТЕЛЕМ"/>
  </enum>
  <enum name="Species">
    <value name="AFRICAN"/>
    <value name="INDIAN"/>
  </enum>
  <class name="AnimalsProp" strategy="SINGLE_TABLE" is-abstract="false" embeddable="false">
    <property name="imageLink" type="STRING" label="сслка на фото животного" length="254"/>
    <property name="detachment" type="AnimalsControl" label="отряд" parent="true" mandatory="true"/>
    <property name="weigth" type="FLOAT" label="вес животного" mandatory="true"/>
    <property name="tronkLength" type="INTEGER" label="длина хобота в см" mandatory="true"/>
    <property name="gender" type="GenderKind" label="пол животного" mandatory="true"/>
    <property name="age" type="SHORT" label="возраст животного"/>
    <property name="species" type="Species" label="вид животного" mandatory="true"/>
    <property name="subSpecies" type="SubSpecies" label="одвид животного"/>
  </class>
  <class name="Valier" strategy="JOINED" is-abstract="false" embeddable="false">
    <property name="serialNum" type="AnimalsControl" label="нмер вальера" parent="true" mandatory="true"/>
    <property name="typeOfvalier" type="VALIERSTYPE" label="тип вальера" parent="false"/>
    <property name="square" type="FLOAT" label="площадь вальера"/>
    <property name="countNumber" type="SHORT" label="номер вальера" mandatory="true" default-value="0"/>
  </class>
  <class name="DistSystem" label="Система раздачи" strategy="JOINED" is-abstract="false" embeddable="false">
    <property name="customer" type="Customer" label="заказчик" mandatory="true" mappedBy="name"/>
    <property name="operationType" type="OPERATIONSLIST" mandatory="true"/>
    <property name="status" type="StatusList" label="стутс жтвотного (свободен/зарезервирован/продан))" mandatory="true" default-value="FREE"/>
    <property name="custDate" type="LOCALDATETIME" length="3" mandatory="true"/>
    <property name="distPoint" type="DpointList" label="пункт выдачи" parent="false" mandatory="true" default-value="MAIN"/>
    <reference name="animal" type="AnimalsControl" collection="SET"/>
  </class>
  <class name="Customer" strategy="JOINED" is-abstract="false" embeddable="false">
    <property name="name" type="DistSystem" parent="true" mandatory="true"/>
    <property name="country" type="STRING" parent="false" length="254" mandatory="true"/>
    <property name="address" type="STRING" length="254"/>
    <property name="phone" type="STRING" length="254"/>
    <property name="email" type="STRING" length="254"/>
    <property name="city" type="STRING" length="254"/>
  </class>
  <class name="AnimalsControl" strategy="JOINED" is-abstract="false" embeddable="false">
    <property name="expDate" type="LOCALDATE" label="да иезменения записи" mandatory="true"/>
    <property name="name" type="AnimalsProp" label="имя животного" mandatory="true" mappedBy="detachment"/>
    <property name="valier" type="Valier" label="номер вальера" mandatory="true" mappedBy="serialNum"/>
    <property name="staff" type="Staff" label="номе сотрудника обслуживания" mappedBy="firstName"/>
    <property name="distStatus" type="BOOLEAN" label="Готовность к выдаче" mandatory="true"/>
    <property name="valierNum1" type="INTEGER"/>
  </class>
  <class name="Staff" strategy="JOINED" is-abstract="false" embeddable="false">
    <property name="vacancy" type="STRING" label="наименование вакансии" length="254" mandatory="true"/>
    <property name="lastName" type="STRING" label="Фамилия" length="254" mandatory="true"/>
    <property name="firstName" type="AnimalsControl" label="имя сотрудника" parent="true" mandatory="true"/>
    <property name="petCount" type="SHORT" label="количество подопечных животных" parent="false" default-value="0"/>
  </class>
</model>`>
![](/bdSchemas/21102906.png)

My SQL ER-diagram

![My SQL ER-diagram](/bdSchemas/21102903.png)

### **5. API системы** <a  name="5.APIсистемы"></a>
### **6. UX/UI** <a  name="6.UX/UI"></a>
### **7. Архитектура проекта** <a  name="7.Архитектурапроекта"></a>

Document generated by Confluence on мар. 17, 2022 14:56

[Atlassian](http://www.atlassian.com/)
