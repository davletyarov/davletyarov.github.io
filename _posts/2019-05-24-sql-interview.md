---
layout: post
title: Тестовое задание на PostgreSQL 
---

Имеется таблица на **PostgreSQL**. 
<script src="https://gist.github.com/davletyarov/2b6b12f9fbaed18b87c525cc99ea70b7.js"></script>
Нужно написать 3 штуки запроса и нужные индексы для них.
### 0-й запрос
На выборку всех категорий верхнего уровня, начинающихся на “авто”
<script src="https://gist.github.com/davletyarov/5e03fa82dabbbcfc6ed6bd9a300d7737.js"></script>
### 1-й запрос
На выборку всех категорий, имеющих не более трёх подкатегорий следующего уровня (без глубины)
<script src="https://gist.github.com/davletyarov/bb3b8eb4351f23241d794175eb6f2b6f.js"></script>
### 2-й запрос
На выборку всех категорий нижнего уровня (т.е. не имеющих детей)
<script src="https://gist.github.com/davletyarov/0c15b2921a1eab2f5e2af0e393300618.js"></script>
Чтобы 0-й запрос работал быстрее нужно сделать частичный индекс для атрибута **name** по значению **авто%**. 
По дефолту **PostgreSQL** создает B-tree индекс.
<script src="https://gist.github.com/davletyarov/77b09ddf96317705f81b939ed489647f.js"></script>

