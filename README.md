# GB:  Итоговая проверочная работа первого блока обучения

## Задача

Написать программу, которая из имеющегося массива строк формирует массив из строк, длина которых меньше либо равна 3 символа.
Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма.
При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

### Примеры

	[ "hello", "2", "world", ":-)" ] -> [ "2", ":-)" ]
	[ "1234", "1567", "-2", "computer science" ] -> [ "-2" ]
	[ "Russia", "Denmark", "Kazan" ] -> [ ]

## Описание решения

* Решение реализовано на языке C# для среды выполнения dotnet.
* Основано на использовании стандартных одномерных массивов типа string.

Поскольку массивы в C# имеют фиксированную длину, а количество элементов, удовлетворяющих условию задачи по длине строки, заранее неизвестно, то возможно два варианта формирования результирующего массива:

1. с предварительным подсчётом числа элементов, удовлетворяющих условию по длине строки, либо
2. с использованием временного промежуточного массива.

Решение реализовано вторым способом.

При старте программы пользователю предлагается задать число элементов исходного массива и, далее, ввести его элементы построчно.

В теле метода *GetFilteredArray*, предназначенного для формирования результирующего массива, создаётся временный массив строк *tempArray* той же длины что и исходный массив, передаваемый в метод в качестве параметра *array*. Значение максимально допустимой длины строки, используемое для фильтрации элементов, передаётся в метод как параметр *maxLength* типа *int*.

На первом этапе, в процессе поэлементного перебора исходного массива, элементы-строки длина которых не превышает *maxLength*, копируются во временный массив, а количество таких найденных строк запоминается в локальной переменной метода *count*.

На втором этапе создаётся результирующий массив *result* уже известной необходимой длины *count*, и все первые *count* элементов временного массива *tempArray* копируются в данный результирующий массив.

Далее метод возвращает результирующий массив.

### Примеры работы программы

![example-1](https://user-images.githubusercontent.com/109767480/191015957-a4166802-ebdb-4646-898d-97382babe466.png)

![example-2](https://user-images.githubusercontent.com/109767480/191015973-f7b41449-1146-4d58-ad73-3f03a06729a9.png)

![example-3](https://user-images.githubusercontent.com/109767480/191015984-25b95e4f-3b5a-4d02-ab0d-381c545c1951.png)

![example-4](https://user-images.githubusercontent.com/109767480/191016003-52f00f2c-8640-4b8e-9cc7-644a19ea0e80.png)

### _Принципиальная_ блок-схема алгоритма

![algorithm-diagram](https://user-images.githubusercontent.com/109767480/191016017-9eae8c2f-a9f4-4893-8cf5-94d209b1c5d7.png)
