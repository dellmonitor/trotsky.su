---
title: "Про страницу 404"
date: 2022-05-26T07:06:10+03:00
author: "Маяк Александрийский"
draft: false 
---
Если страница не&nbsp;найдена, следует хоть <nobr>что-нибудь</nobr> показать пользователю.

Страница ```404.html``` создается в&nbsp;папке ```/layouts```. Код страницы на&nbsp;этом сайте:
```html
<!DOCTYPE html>
<html lang="{{ .Site.LanguageCode | default "en" }}">
    {{ partial "head.html" . }}
    <style>
        a {
            text-decoration: underline;
        }
        a:hover {
            color: #AAAA
        }
        a:visited {
            color: #8E44AD;
        }
    </style>
    <body>
            {{ partial "darkmode.html" . }}
            <div  style="height: 10 em; display: flex; align-items: center; justify-content: center;">
            <h1>404: Старикам&nbsp;тут&nbsp;не&nbsp;<a href="{{ "/" | relURL }}">место</a></h1>
            </div>
    </body>
</html>
```

Стили ссылок и заголовков такие же, как на&nbsp;остальном сайте. Присутствует переключение темной темы. Возможно, это лишнее и&nbsp;стоит сделать серую страницу с&nbsp;антиквой, чтобы сразу возникало желание вернуться на&nbsp;основную часть сайта.
<!--more-->
