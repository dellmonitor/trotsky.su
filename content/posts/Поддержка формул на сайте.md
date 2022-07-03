---
title: "Поддержка формул на сайте"
date: 2022-05-26T05:56:27+03:00
math: true
author: "Маяк Александрийский"
draft: false
---
За&nbsp;отображение формул отвечает отдельная библиотека&nbsp;--- Катек (\\(\KaTeX \\)). Она основана на&nbsp;Теке (\\(\TeX\\)) Дональда Кнута. Катек рендерит быстрее аналогов и&nbsp;прост в&nbsp;использовании.

Чтобы Катек отрендерил формулы, страница с&nbsp;формулами должна содержать ссылку на&nbsp;библиотеку в&nbsp;заголовке. Благодаря шаблонам Хьюго можно создать отдельный файл, содержащий эту ссылку, и&nbsp;указать файл в&nbsp;шаблоне страниц с&nbsp;формулами (формулы могут находится внутри поста или выводится на&nbsp;главную).

Создадим файл ```math.html``` в&nbsp;папке ```/layouts/partials``` и&nbsp;вставим в&nbsp;него следующий код:
```html
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.15.3/dist/katex.min.css" integrity="sha384-KiWOvVjnN8qwAZbuQyWDIbfCLFhLXNETzBQjA/92pIowpC0d2O3nppDGQVgwd2nB" crossorigin="anonymous">

    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.3/dist/katex.min.js" integrity="sha384-0fdwu/T/EQMsQlrHCCHoH10pkPLlKA1jL5dFyUOvB3lfeT2540/2g6YgSi2BL14p" crossorigin="anonymous"></script>

    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.3/dist/contrib/auto-render.min.js" integrity="sha384-+XBljXPPiv+OzfbB3cVmLHf4hdUFHlWNZN5spNQ7rmHTXpd7WvJum6fIACpNNfIR" crossorigin="anonymous"
        onload="renderMathInElement(document.body);"></script>
```

В&nbsp;шаблоне поста (```/layouts/_default/single.html```) укажем, нужно&nbsp;ли добавлять Катек (завист от&nbsp;параметра ```math```, указываемого нами&nbsp;посте):
```html
{{ if or .Params.math .Site.Params.math }}
  {{ partial "math.html" . }}
{{ end }}
```

Добавив в&nbsp;фронт меттер поста ```math: true```, получим отрендеренные формулы:
$$E=mc^2$$

Кстати, \\(\KaTeX\\) и \\(\TeX\\) тоже написаны с&nbsp;помощью Катека.
