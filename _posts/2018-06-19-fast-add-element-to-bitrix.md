---
layout: post
title: Ускоренное добавление элементов в 1C-Bitrix
---

Стоит задача, добавить более 170 тыс элементов в инфоблок через **API**.

 
Нужно будет преднамеренно выйти из обработчика событии в классе **SitemapIblock** штатного модуля SEO.
Т.е. в файле **/bitrix/modules/seo/lib/sitemapiblock.php** находится класс SitemapIblock, в ней имеется статичный метод **__callStatic**.
Нужно будет добавить оператор return c пустым выражением, первым в теле этой функции, чтобы миновать построение SiteMap.xml. 
Но! После добавления убрать,его. Потому что, при каждом структурном изменении инфоблока, будет обновляться не нужны сайтмап. Можно так же повысить скорость добавления элементов, удалив во время разработки, штатный модуль «Поиска». После того как, выполнив задачу, убедившись в правильности работы, включить модуль поиска. 
Конечно, удалить его можно в случаи только если задача не связано с поиском. Как вариант, отключив индексирование элементов и разделов инфоблока. Но, после добавления нужно будет — переиндексировать весь инфоблок в которую было добавленно элементы и разделы.



