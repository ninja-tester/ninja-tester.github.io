---
layout: article
title:  "How to generate positive random numbers in SQLite"
date:   2018-12-10 09:30:00 +0400
categories: testing
image:
  feature: fallout_dice.jpg
  teaser: fallout_dice.jpg
  thumb:
---
В [SQLite][sqlite-home] для генерации псевдослучайных значений используется функция random(). Рассмотрим несколько полезных примеров её использования.

Для получения случайного целого числа от -9223372036854775808 до +9223372036854775807:
SELECT random()

Для ограничения диапазона используется конструкция select random() % n так, например, чтобы сгенерировать случайные числа до 100:
SELECT random() % 100

При этом числа будут в диапазоне от -n до n. Чтобы сгенерировать положительные числа возмём абсолютное значение ABS():
SELECT ABD(random() % 100)

Для того, чтобы задать верхнюю и нижнюю границу:
SELECT ABS( random()) % (HIGH - LOW) + LOW
HIGH - верхняя граница
LOW - нижняя граница

[sqlite-home]: https://www.sqlite.org/