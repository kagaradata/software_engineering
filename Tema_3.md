# Тема 2. Базовые операции языка Python
Отчет по Теме #3 выполнил:
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
### Создайте две переменные, значение которых будете вводить через консоль. Также составтье условие, в котором созданные ранее переменные будут сравниваться, если условие выполняется, то выведете в консоль "Выполняется", если нет, то "Не выполняется".

```python
one = int(input('Введите значение первой переменной:'))
two = int(input('Введите значение второй переменной:'))
if one >= two:
  print('Выполняется')
else:
  print('Не выполняется')
```
### Результат.

![](/pic/лр_1.jpg)


## Лабораторная работа №2
### Напишите программу, которая будет определять значения переменной меньше 0, больше 0 и меньше 10 или больше 10. Это нужно реализовать при помощи одной переменной, значение которой будет вводиться через консоль, а также при помощи конструкций if, elif, else.

```python
one = int(input('Введите значение переменной:'))
if one < 0:
  print('Переменная меньше 0:')
elif 0 < one < 10:
  print('Переменная больше 0 и меньше 10')
else:
  print('Переменная больше 10')

```
### Результат

![](/pic/tema2/2.jpg)


## Лабораторная работа №3
### Напишите программу, в которой будет проверяться есть ли переменная в указанном массиве используя логический оператор in. Самостоятельно посмотрите, как работает программа со значениями, которых нет в массиве numbers.

```python
numbers = [1,3,5,7,9]
value = int(input('Введите число:'))
if value in numbers:
  print('Переменная есть в данном массиве')
else:
  print('Переменной нет в этом массиве')
```
### Результат

![](/pic/tema2/3.jpg)


## Лабораторная работа №4
### Напишите программу, которая будет определять находится ли переменная в указанном массиве и если да, то проверьте четная она или нет. Самостоятельно претестируйте данную программу с разными значениями переменной value.

```python
numbers = [1,3,5,7,9]
value = int(input('Введите число:'))
if value in numbers:
    if value % 2 == 0:
        print('Число четное и есть в массиве')
    else:
        print('Число нечетное и есть в массиве')
else:
    print(f"Числа нет в массиве, и оно равно {value}")
```
### Результат

![](/pic/tema2/4.jpg)

   
## Лабораторная работа №5
### Напишите программу, в которой циклом for значения переменной будут меняться от 0 до 10 и посмотрите, как разные виды сравнений и операций работают в цикле.

```python
for i in range(10):
    print('i = ', i)
    if i == 0:
        i += 2
    if i == 1:
        continue
    if i == 2 or i == 3:
        print('Переменная равна 2 или 3')
    elif i in [4, 5, 6]:
        print('Переменная равна 4, 5 или 6')
    else:
        break
```
### Результат

![](/pic/tema2/5.jpg)


## Лабораторная работа №6
### Напишите программу, в которой при помощи цикла for определяется есть ли переменная value в строке string и посмотрите, как работает оператор else для циклов. Самостоятельно посмотрите, что выведет программа, если значение переменной value оказалось в строке string.

```python
string = 'Привет всем изучающим Python!'
value = input()
for i in string:
    if i == string.find(value):
        print(f"Буква '{value}' есть в строке под {index} индексом")
        break
else:
    print(f"Буквы '{value}' нет в указанной строке")
```

### Результат

![](/pic/tema2/6.jpg)


## Лабораторная работа №7
### Напишите программу, в которой вы наглядно посмотрите, как работает цикл for проходя в обратном порядке, то есть, к примеру не от 0 до 10, а от 10 до 0. В уже готовой программе показано вычитание из 100, а вам во время реализации программы будет необходимо придумать свой вариант применения обратного цикла.

```python
string = 'еда приготовится через:'
for i in range(10, -1, -1):
    print(string, i)
```

### Результат

![](/pic/tema2/7.jpg)


## Лабораторная работа №8
### Напишите программу используя цикл while, внутри которого есть какие-либо проверки.

```python
value = 0
while value < 100:
    if value == 0:
        value += 10
    elif value // 5 > 1:
        value *= 5
    else:
        value -= 5
    print(value)
```

### Результат

![](/pic/tema2/8.jpg)


## Лабораторная работа №9
### Напишите программу с использованием вложенных циклов и одной проверкой внутри них.

```python
value = 0
for i in range(10):
    for j in range(10):
        if i != j:
            value += j
        else:
            pass
print(value)
```

### Результат

![](/pic/tema2/9.jpg)


## Лабораторная работа №10
### Напишите программу с использованием flag, которая будет определять есть ли нечетное число в массиве.

```python
even_array = [2, 4, 6, 8, 9]
flag = False
for value in even_array:
    if value % 2 == 1:
        flag = True

if flag is True:
    print('В массиве есть нечетное число')
else:
    print('В массиве все числа четные')
```

### Результат

![](/pic/tema2/10.jpg)
