## Циклы и условия в Python.



#### Что такое цикл ?

Иногда программу нужно заставить **много раз повторить** одно и то же действие. Для этого в языках программирования, в том числе в Python, существует специальный инструмент — **цикл**.

Простыми словами цикл - это конструкция которая выполняет наши команды много раз.



#### Что такое условие ?

**Условие** – **это** логическое выражение, т.е. выражение, результатом которого является логическое значение `True` (истина/правда) или `False` (ложь) или же `1`(истина/правда) и `0`(ложь).

Для создания условий в Python используются ключевые слова `if`, `elif` и `else`.

Программа будет **поочередно** проходиться по каждому **условию** и если условие **истинно** выполнять блок кода для этого условия.

Пример условия в Python:

```python
"""
В программе ниже мы будем выводить больше или равно число которое введет пользователь 10.
"""

num = int(input("Введите число:"))

if num == 10:
    print("Число равно 10")
elif num > 10:
    print("Число больше 10")
else:
    print("Число меньше 10")
```

**Скопируй** пример выше и посмотри как работает наша программа. Из примера выше можно заметить что условия имеют следующий формат:

```python
if УСЛОВИЕ:
    # БЛОК КОДА
else:
    # БЛОК КОДА

или

if УСЛОВИЕ:
    # БЛОК КОДА
# БЛОК КОДА

или

if УСЛОВИЕ:
    # БЛОК КОДА
elif УСЛОВИЕ:
    # БЛОК КОДА
else:
    # БЛОК КОДА
```

| Условие кодом       | Условие словами                                                   | Пример                         | Пояснение                                         |
| ------------------- | ----------------------------------------------------------------- | ------------------------------ | ------------------------------------------------- |
| `a` > `b`:          | `a` больше `b`                                                    | 10 > 3 # True                  | **Правда**, 10 больше 3                           |
| `a` < `b`           | `a` меньше `b`                                                    |                                |                                                   |
| `a` >= `b`          | `a` больше или равно `b`                                          |                                |                                                   |
| `a` <= `b`          | `a` меньше или равно `b`                                          |                                |                                                   |
| `i` in `iterable`\* | `i` есть в `iterable`                                             | 'a' in 'andrew' # True         | **Правда**, символ 'a' есть в строке 'andrew'     |
|                     |                                                                   | 'A' in 'andrew' # False        | **Ложь**, символа 'a' нет в строке 'andrew'       |
|                     |                                                                   | 1 in [1, 2, 3] # True          | **Правда**, число 1 есть в списке [1, 2, 3]       |
| `a` == `b`          | `a` равно `b`                                                     | [1, 2, 3] == [1, 2, 3] # True  | **Правда**, список [1, 2, 3] равен сторому списку |
|                     |                                                                   | 5 == 5 # True                  | **Правда**, 5 равно 5                             |
|                     |                                                                   | 5 == 10 # False                | **Ложь**, 5 не равно 5                            |
| `a` != `b`          | `a` не равно `b`                                                  | 5 != 5 # False                 | **Ложь**, 5 равно 5                               |
| `a` is `b`          | `a` и `b` это один и тот-же объект в памяти                       | 1 is 1 # True                  | **Правда**, в памяти они хранятся как один объкт  |
|                     |                                                                   | [1, 2, 3] is [1, 2, 3] # False | **Ложь**, в памяти это два **разных объекта**\**  |
| `a` % `b` == 0      | Остаток при делени `a` на `b` равен 0 | 4 % 2 == 0 # True              | **Правда**, остаток от деления 4 на 2 равен 0     |



#### Циклы в Python.

Теперь можно вернуться к теме циклов. В Python есть два вида циклов `for` и `while`. 

Цикл `for` работает с **итерируемыми**\* объектами, поочередно проходясь по каждому элементу.

Пример объявления цикла **for**:

```python
"""
Программа ниже напечатает все элементы нашего списка.

вывод:
1
2
3
4
"""
my_list = [1, 2, 3, 4]
for i in my_list:
    print(i)



```

В циклах мы можем использовать такие конструкции как `break` и `continue`,  `break` -  **выходит из цикла**, а `continue` **переходит на следующую итерацию**.

Пример:

```python
"""
Программа ниже напечатает элементы с индексом меньше 2.

вывод:
1
2
"""
my_list = [1, 2, 3, 4]
for i in my_list:
    if my_list.index(i) == 2:
        break
    print(i)


"""
Программа ниже напечатает все элемента кроме элемента с индексом 2.

вывод:
1
2
4
"""
my_list = [1, 2, 3, 4]
for i in my_list:
    if my_list.index(i) == 2:
        continue
    print(i)
```

У циклов  `for`  и  `while` может быть блок **else**, который выполнится в том случае если **цикл сам завершит** свое выполнение т.е. без **break**. Пример:

```python
"""
вывод кода ниже будет:
0
1
2
Все готово!
"""
for i in range(3):
    print(i)
else:
    print("Все готово!")

"""
вывод кода ниже будет:
0
"""

for i in range(3):
    print(i)
    break # вышли из цикла
else:
    print("Все готово!")
```



#### Цикл while.

Цикл `while` это цикл с условием, пример:

```python
"""
вывод чисел от 0 до 9:
0
1
2
...
8
9
"""
i = 0 # в начале программы i = 0

while i < 10: # пока i меньше 10
    print(i) # вывести i
    i += 1 # увеличить i на 1

```

\* - к **итерируем** объектам в Python относятся большенство колекций (**списки, строки, множества, кортежи**)

\** - можно использовать команду `id(obj)` - она выводит номер ячейки памяти где хранится объект и мы заметим что списки хранятся в разных местах т.к. они являются **изменяемым** типом данных.
