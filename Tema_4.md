# Тема 4. Функции и модули.
Отчет по Теме #4 выполнил:
- Наговицын Дмитрий
- АИС-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |  |
| Задание 7 | + |  |
| Задание 8 | + |  |
| Задание 9 | + |  |
| Задание 10 | + |  |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
### Напишите функцию, которая выполняет любые арифметические действия и выводит результат в консоль. Вызовите функцию используя “точку входа”.

```python
def main():
    print(2+2)

if __name__ == '__main__':
  main()
```
### Результат.

![](/pic/4лб_1.png)


## Лабораторная работа №2
### Напишите функцию, которая выполняет любые арифметические действия, возвращает при помощи return значение в место, откуда вызывали функцию. Выведите результат в консоль. Вызовите функцию используя “точку входа”.

```python
def main():
    return 2+2

if __name__ == '__main__':
  print(main())
```
### Результат

![](/pic/4лб_2.png)


## Лабораторная работа №3
### Напишите функцию, в которую передаются два аргумента, над ними производится арифметическое действие, результат возвращается туда, откуда эту функцию вызывали. Выведите результат в консоль. Вызовите функцию в любом небольшом цикле. На скриншоте ниже приведен пример программы, в которой аргумент функции “x“ превращается в параметр “one”, то же самое происходит с “y” и “two”.

```python
def main(one, two):
  result = one + two
  return result


for i in range(5):
  x = 1
  y = 10
  answer = main (x, y)
  print(answer)
```
### Результат

![](/pic/4лб_3.png)


## Лабораторная работа №4
### Напишите функцию, на вход которой подается какое-то изначальное неизвестное количество аргументов, над которыми будет производится арифметические действия. Для выполнения задания необходимо использовать кортеж “*args”.

```python
def main (x, *args):
  one = x
  two = sum(args)
  three = float(len(args))
  print(f"one={one}\ntwo={two}\nthree={three}")

  return x + sum(args) / float(len(args))

if __name__ == '__main__':
  result = main(10, 0, 1, 2, -1, 0, -1, 1, 2)
  print(f"\nresult={result}")
```
### Результат

![](/pic/4лб_4.png)

   
## Лабораторная работа №5
### Напишите функцию, которая на вход получает кортеж “**kwargs” и при помощи цикла выводит значения, поступившие в функцию. На скриншоте ниже указаны два варианта вызова функции с “**kwargs” и два варианта работы с данными, поступившими в эту функцию. Комментарии в коде и теоретическая часть помогут вам разобраться в этом нелегком аспекте. Вызовите функцию используя “точку входа”.

```python
def main(**kwargs):
  for i in kwargs.items():
    print(i[0], i[1])

    print()

    for key in kwargs:
        print(f"{key} = {kwargs[key]}")

if __name__ == '__main__':
  main(x=[1, 2, 3], y=[3, 3, 0], z=[2, 3, 0], q=[3, 3, 0], w=[3, 3, 0])
  print()

  
  main(**{'x': [1, 2, 3], 'y': [3, 3, 0]})
```
### Результат

![](/pic/4лб_5.png)


## Лабораторная работа №6
### Напишите две функции. Первая – получает в виде параметра “**kwargs”. Вторая считает среднее арифметическое из значений первой функции. Вызовите первую функцию используя “точку входа” и минимум 4 аргумента.

```python
def main(**kwargs):



  for i, j in kwargs.items():
    print(f"{i}. Mean = {mean(j)}")

def mean(data):

  return sum(data) / float(len(data))


if __name__ == "__main__":
  main(x=[1, 2, 3], y=[3, 3, 0])

```

### Результат

![](/pic/4лб_6.png)


## Лабораторная работа №7
### Создайте дополнительный файл .py. Напишите в нем любую функцию, которая будет что угодно выводить в консоль, но не вызывайте ее в нем. Откройте файл main.py, импортируйте в него функцию из нового файла и при помощи “точки входа” вызовите эту функцию.
main.py
```python
from for_import import say_hello

if __name__ == '__main__':\
  say_hello()
```
for_import.py
```python
def say_hello():
    print('Hello students!')
```
### Результат

![](/pic/4лб_7.1.png)

![](/pic/4лб_7.2.png)


## Лабораторная работа №8
### Напишите программу, которая будет выводить корень, синус, косинус полученного от пользователя числа.

```python
import math


def main():
    value = int(input('Введите значение: '))
    print(math.sqrt(value))
    print(math.sin(value))
    print(math.cos(value))


if __name__ == '__main__':
    main()
```

### Результат

![](/pic/4лб_8.png)


## Лабораторная работа №9
### Напишите программу, которая будет рассчитывать какой день недели будет через n-нное количество дней, которые укажет пользователь. В результате день недели указан в виде цифры, где 1 = понедельник, 2 = вторник, 3 = среда и так далее.
```python
from datetime import datetime as dt
from datetime import timedelta as td


def main():
    print(
        f"Сегодня {dt.today().date()}. "
        f"День недели - {dt.today().isoweekday()}"
    )
    n = int(input('Введите количество дней: '))
    today = dt.today()
    result = today + td(days=n)
    print(
        f"Через {n} дней будет {result.date()}. "
        f"День недели - {result.isoweekday()}"
    )
if __name__ == '__main__':
    main()

```

### Результат

![](/pic/4лб_9.png)


## Лабораторная работа №10
### Напишите программу с использованием глобальных переменных, которая будет считать площадь треугольника или прямоугольника в зависимости от того, что выберет пользователь. Получение всей необходимой информации реализовать через input(), а подсчет площадей выполнить при помощи функций. Результатом программы будет число, равное площади, необходимой фигуры.

```python
global result

def rectangle():
    a = float(input("Ширина: "))
    b = float(input("Высота: "))
    global result
    result = a * b


def triangle():
    a = float(input("Основание: "))
    h = float(input("Высота: "))
    global result
    result = 0.5 * a * h

figure = input("1-прямоугольник, 2-треугольник: ")

if figure == '1':
    rectangle()
elif figure == '2':
    triangle()
print(f"Площадь: {result}")

```

### Результат

![](/pic/4лб_10.png)


## Самостоятельная работа №1
### Дайте подробный комментарий для кода, написанного ниже. Комментарий нужен для каждой строчки кода, нужно описать что она делает. Не забудьте, что функции комментируются по-особенному.
![](/pic/задание1.png)


### Выводы
1. from datetime import datetime: - импортируем библиотеку datetime для работы с датами и временем.
2. from math import sqrt: - импортируем функцию sqrt из библиотеки math для расчета квадратного корня.
3. def main(**kwargs):: - объявляем функцию main, которая принимает произвольное количество именованных аргументов.
4. Функция main() вычисляет длину вектора для каждого набора координат, переданного в аргументах. Документация функции main описывает ее предназначение.
5. for key, value in kwargs.items():: - проходим по всем парам ключ-значение в словаре kwargs.
6. result = sqrt(value[0] * 2 + value[1] * 2): - рассчитываем длину вектора для текущего набора координат..
7. print(result): - выводим результат.
8. if __name__ == '__main__'::  - проверяем, запускается ли текущий модуль как основная программа.
9. start_time = datetime.now(): - запоминаем время начала работы программы.
10. main(...): - Вызываем функцию main с набором координат.
11. time_costs = datetime.now() - start_time: - вычисляем время на выполнение программы.
12. print(f"Время выполнения программы - {time_costs}"): - выводим время выполнения программы.


## Самостоятельная работа №2
### Напишите программу, которая будет заменять игральную кость с 6 гранями. Если значение равно 5 или 6, то в консоль выводится «Вы победили», если значения 3 или 4, то вы рекурсивно должны вызвать эту же функцию, если значение 1 или 2, то в консоль выводится «Вы проиграли». При этом каждый вызов функции необходимо выводить в консоль значение “кубика”. Для выполнения задания необходимо Михаил А. Панов использовать стандартную библиотеку random. Программу нужно написать, используя одну функцию и “точку входа”

```python
import random

def roll_dice():
    value = random.randint(1, 6)
    print(f"Выпало: {value}")

    if value in (5, 6):
        print("Вы победили!")
    elif value in (3, 4):
        roll_dice()
    else:
        print("К сожалению, это проигрыш...")

if __name__ == '__main__':
    roll_dice()
```

### Результат

![](/pic/4ср_2.png)

### Вывод
Сначала импортируется модуль random, который используется для генерации случайных чисел.
Внутри функции roll_dice происходит имитация броска кубика.
Функция random.randint(1, 6) генерирует случайное целое число от 1 до 6, что соответствует возможным результатам броска игральной кости. Сразу выводится результат броска: "Выпало: {значение}".
Условия определения проигрыша или выигрыша есть в формулировке задачи. Когда пользователь запускает программу, она выполняет бросок игральной кости, выводит результат и определяет, выиграл ли игрок, проиграл или должен бросить кость еще раз.

## Самостоятельная работа №3
### Напишите программу, которая будет выводить текущее время, с точностью до секунд на протяжении 5 секунд. Программу нужно написать с использованием цикла. Подсказка: необходимо использовать модуль datetime и time, а также вам необходимо как-то “усыплять” программу на 1 секунду

```python
import datetime
import time

for i in range(5):
    current_time = datetime.datetime.now().strftime('%H:%M:%S')
    print(f'Current time: {current_time}')
    time.sleep(1)
```

### Результат
![](/pic/4ср_3.png)

### Выводы
Программа выводит текущее время в формате "Ч:М:С" пять раз, с интервалом в одну секунду между выводами.
Функция datetime.datetime.now() возвращает текущую дату и время в виде объекта datetime.datetime. 
Метод strftime('%H:%M:%S') форматирует данный объект в строку, которая отображает только время в формате "часы:минуты:секунды".
time.sleep(1) приостанавливает выполнение программы на 1 секунду, позволяя выводить время каждую секунду.

## Самостоятельная работа №4
### Напишите программу, которая считает среднее арифметическое от аргументов вызываемое функции, с условием того, что изначальное количество этих аргументов неизвестно. Программу необходимо реализовать используя одну функцию и “точку входа”.
```python
def average(*args):
    return sum(args) / len(args) if args else 0

def main():
    print("Введите любое количество чисел через пробел:")
    numbers = [float(x) for x in input().split()]
    result = average(*numbers)
    print(f"Среднее арифметическое равно: {result:.2f}")

if __name__ == "__main__":
    main()
```

### Результат
![](/pic/4ср_4.png)

### Вывод
Функция average принимает произвольное количество аргументов. Если аргументы есть, она вычисляет среднее арифметическое (сумма деленная на количество); если аргументов нет, то возвращает 0.
Функция main: просит пользователя ввести числа через пробел, считывает ввод, переводит каждое число в тип float и сохраняет в список numbers, вызывает average, передавая числа как отдельные аргументы и выводит результат на экран с двумя знаками после запятой.
Запуск программы происходит при выполнении файла вызывается функция main.


## Самостоятельная работа №5
### Создайте два Python файла, в одном будет выполняться вычисление площади треугольника при помощи формулы Герона (необходимо реализовать через функцию), а во втором будет происходить взаимодействие с пользователем (получение всей необходимой информации и вывод результатов). Напишите эту программу и выведите в консоль полученную площадь.

```python
import math


def geron_f(a, b, c):
    s = (a + b + c) / 2
    area = math.sqrt(s * (s - a) * (s - b) * (s - c))
    return area
```

```python
from geron import geron_f

def main():
    print("Введите длины сторон треугольника:")
    a = float(input("Сторона a: "))
    b = float(input("Сторона b: "))
    c = float(input("Сторона c: "))
    if a + b > c and a + c > b and b + c > a:
        area = geron_f(a, b, c)
        print(f"Площадь треугольника: {area:.2f}")
    else:
        print("Ошибка: такие стороны не могут образовать треугольник.")

if __name__ == "__main__":
    main()
```
### Результат

![](/pic/4ср_5.1.png)
![](/pic/4ср_5.2.png)

### Вывод
Первый файл содержит функцию для вычисления площади треугольника по формуле Герона.
Второй файл взаимодействует с пользователем, получает значения сторон треугольника и выводит результат.


## Общие выводы по теме №4.
Функции и модули являются важными концепциями в программировании. 

Функции – это блоки кода, выполняющие определенную задачу. Они помогают структурировать и организовывать код, делая его более читабельным. Функции принимают аргументы, выполняют вычисления и возвращают результат. Они способствуют повторному использованию кода, упрощению отладки и поддержки.

Модули – это файлы с определениями функций, классов и переменных. Они обеспечивают модульность приложения, организуя код в логические блоки и упрощая тестирование, развертывание и поддержку. Модули могут быть импортированы в другие части программы, способствуя повторному использованию кода.

Функции определяются внутри модулей и экспортируются для использования в других частях программы. Модули позволяют группировать связанные функции и переменные, обеспечивая эффективную организацию кода.

Преимущества использования функций и модулей:

1. Повторное использование кода.  
2. Повышение читаемости и упрощение поддержки.  
3. Упрощение процесса отладки и тестирования.  
4. Увеличение модульности и гибкости приложения.  
5. Эффективное управление сложностью программного обеспечения.