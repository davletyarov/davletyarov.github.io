---
layout: post
title: Расширение для Сортировки подсчётом
---

Сортировка подсчётом.

Предположим, что входной массив состоит целых чисел в диапазоне от N до M
нужно отсортировать за O(N) и используя доп. память для массива сортировки

N = -6 и M = 11

> То есть, заранее известно то что числа **g** в наборе будут только в **N <= g <= M**

```text
-6 11
-3 -5 9 -6 -6 9 11 8 0 -2 -5 -5 -5 -5 1 1 1 1 9 9 9 -6
```



```python
left, right = map(int, input().split(' '))

nums = list(map(int, input().split(' ')))

length_index = abs(left) + abs(right)

# Учитывать ноль, когда возможны отрицательные числа в наборе
if left < 0:
    length_index += 1

sorted_nums = [0] * length_index

for number in nums:
    sorted_nums[abs(left) + number] += 1

for index, value in enumerate(sorted_nums):
    if value == 0:
        continue
    print(*repeat(left + index, value), end=' ')
```


после сортировки получаем


```text
-6 -6 -6 -5 -5 -5 -5 -5 -3 -2 0 1 1 1 1 8 9 9 9 9 9 11
```


![Состояние объектов](/images/nums.png)
