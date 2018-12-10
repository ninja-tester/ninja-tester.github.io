---
layout: article
title:  "How to generate positive random numbers in SQLite"
date:   2018-12-10 09:30:00 +0400
categories: testing
image:
  feature: dice.jpg
  teaser: fallout_dice.jpg
  thumb:
---
В [SQLite][sqlite-home] для генерации псевдослучайных значений используется функция RANDOM(). Рассмотрим несколько полезных примеров её использования.

Базовый вызов:
{% highlight sql %}
SELECT RANDOM()
{% endhighlight %}
вернёт нам случайное число от -9223372036854775808 до +9223372036854775807:

Для ограничения диапазона используется конструкция:
{% highlight sql %}
SELECT RANDOM() % N
{% endhighlight %}
 так, например, чтобы сгенерировать случайные числа до 100:
{% highlight sql %}
SELECT RANDOM() % 100
{% endhighlight %}

В этом примере  будут сгенерированы числа диапазоне от -100 до 100. Чтобы сгенерировать только положительные числа возмём абсолютное значение ABS():
{% highlight sql %}
SELECT ABS(RANDOM() % 100)
{% endhighlight %}

Для того, чтобы задать верхнюю и нижнюю границу:
{% highlight sql %}
SELECT ABS(RANDOM()) % (HIGH - LOW) + LOW
{% endhighlight %}
HIGH - верхняя граница,
LOW - нижняя граница

[sqlite-home]: https://www.sqlite.org/