---
title: "ВПС, ТГ, АПИ"
date: 2022-06-04T17:51:22+03:00
author: "Маяк Александрийский"
draft: false 
---
Я&nbsp;получил выделенный сервер за&nbsp;40&nbsp;&#8381; в&nbsp;месяц. Одно ядро на&nbsp;2&nbsp;ГГц, 512&nbsp;МБ оперативной памяти, ССД на&nbsp;10&nbsp;ГБ, безлимитный трафик, Линукс. Пока на&nbsp;нем расположен только [телеграм&#x2011;бот](http://t.me/outofprintbot).

При&nbsp;настройке сервера я&nbsp;установил ```sudo``` (т.&nbsp;к.&nbsp;в&nbsp;Дебиане утилита отсутствует), создал нового пользователя с&nbsp;привилегиями, закрыл вход через рут, скачал ```pip``` и&nbsp;```pyhton3```, вставил в&nbsp;```main.py``` код бота и&nbsp;добавил сервис ```weatherbot.service```, чтобы программа работала в&nbsp;фоновом режиме и&nbsp;запускалась при&nbsp;перезагрузке сервера. Все. 

*Но я не&nbsp;понимаю*. 

Бот использует Openweathermap API для погоды и&nbsp;геокодера. Получив команду ```/weather```,  бот вызывает функцию ```weather```. Функция ```weather``` с&nbsp;помощью функции геокодера находит координаты города и&nbsp;передает их&nbsp;функции погоды (если не&nbsp;указывать город, бот найдет координаты Москвы). На домашнем компьютере геокодер выполняет свою работу, функция погоды не выдает результат&nbsp;--- таймаут. Почему? *Я не&nbsp;знаю*. На&nbsp;ВПС все работает, хотя он расположен в&nbsp;России. С&nbsp;другого домашнего компьютера тоже не&nbsp;получается, но&nbsp;компьютер в&nbsp;Дедовске решает проблему. Код тот&nbsp;же самый, пакеты Питона одинаковые.

Пользоваться сервером оказалось проще, чем&nbsp;своим компьютером.
<!--more-->
