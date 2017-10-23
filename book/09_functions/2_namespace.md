## Пространства имен. Области видимости
У переменных в Python есть область видимости. В зависимости от места в коде, где переменная была определена, определяется и область видимости, то есть, где переменная будет доступна.

При использовании имен переменных в программе, Python каждый раз ищет, создает или изменяет эти имена в соответствующем пространстве имен.
Пространство имен, которое доступно в каждый момент, зависит от области, в которой находится код.

У Python есть правило LEGB, которым он пользуется при поиске переменных.

Например, если внутри функции выполняется обращение к имени переменной, Python ищет переменную в таком порядке по областям видимости (до первого совпадения):
* L (local) - в локальной (внутри функции)
* E (enclosing) - в локальной области объемлющих функций (это те функции, внутри которых находится наша функция)
* G (global) - в глобальной (в скрипте)
* B (built-in) - в встроенной (зарезервированные значения Python)

Соответственно, есть локальные и глобальные переменные:
* локальные переменные:
 * переменные, которые определены внутри функции
 * эти переменные становятся недоступными после выхода из функции
* глобальные переменные
 * переменные, которые определены вне функции
 * эти переменные 'глобальны' только в пределах модуля
   * например, чтобы они были доступны в другом модуле, их надо импортировать

Пример локальной и глобальной переменной result:
```python
In [1]: result = 'test string'

In [2]: def open_file( filename ):
   ...:     with open(filename) as f:
   ...:         result = f.read()
   ...:         return result
   ...:

In [3]: open_file('r1.txt')
Out[3]: '!\nservice timestamps debug datetime msec localtime show-timezone year\nservice timestamps log datetime msec localtime show-timezone year\nservice password-encryption\nservice sequence-numbers\n!\nno ip domain lookup\n!\nip ssh version 2\n!\n'

In [4]: result
Out[4]: 'test string'
```

Обратите внимание, что переменная result по-прежнему осталась равной 'test string', несмотря на то, что внутри функции ей присвоено содержимое файла.
