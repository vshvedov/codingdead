---
layout: post
title: "Отображение прогресса в терминале"
date: 2012-08-17 18:07
comments: true
author: Vlad Shvedov
categories: ruby
---
Зачастую, отображение прогресса работы терминального приложения на Ruby это не столько дань уважения к конечному пользователю, сколько единственная возможность оповестить человека по ту сторону экрана о том, что скрипт не завис и продолжает работать. Простейший вариант отображения текущего состояния может выглядеть так:

{% codeblock lang:ruby %}
1.upto(100) do |i|
  printf("\rZombies killed (in percents): %d%", i)
  sleep(0.1)
end
{% endcodeblock %}

Весь секрет в использовании escape-символа '\r' (0x0d) — возврат каретки в операторе printf. Вот еще один пример похожий на прогресс-бар из wget:

{% codeblock lang:ruby %}
0.step(100, 5) do |i|
  printf("\rLoading shotgun: [%-20s]", "=" * (i/5))
  sleep(0.5)
end
{% endcodeblock %}

И еще один, для любителей перфекционизма:

{% codeblock lang:ruby %}
spinner = Enumerator.new do |e|
  loop do
    e.yield '|'
    e.yield '/'
    e.yield '-'
    e.yield '\\'
  end
end

1.upto(100) do |i|
  progress = "=" * (i/5) unless i < 5
  printf("\rEating brains: [%-20s] %d%% %s", progress, i, spinner.next)
  sleep(0.1)
end
{% endcodeblock %}