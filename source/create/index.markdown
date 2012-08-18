---
layout: page
title: "Как написать статью"
date: 2012-08-17 12:11
comments: false
sharing: true
footer: true
---
### Введение
*CodingDead* работает на [Octopress](http://octopress.org/) со всеми вытекающими из этого следствиями. Хостинг на GitHub в [репозитории](https://github.com/vshvedov/codingdead) (ветка master для исходников, ветка gh-pages для сгенерированной статики). Что бы добавить новую сатью, необходимо сделать форк этого репозитория, и после генерации статьи — pull request. Те же операции необходимо совершить и для исправления ошибки (стилистической, орфографической или логической). Все обсуждения и отзывы также возложены на дюжие плечи GitHub. Если вы пишете статью или перевод, пул реквест должен содержать только .markdown файл (не стоит убирать '_deploy' из .gitignore) без статики.

### Пример заголовка статьи в markdown

{% codeblock %}
---
layout: post
title: "Заголовок статьи"
author: "Sir Lorem Ipsum"
date: 2012-08-10 15:54
comments: true
categories: ruby, rails
---
{% endcodeblock %}

[Шпаргалка по Markdown](http://warpedvisions.org/projects/markdown-cheat-sheet/)

_Версия 0.0.2_