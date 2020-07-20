### Set

Set это специальная коллекция произвольных данных любого типа.

* Set не имеет индексов, его элементы не упорядочены
* Каждый элемент в Set является уникальным (дубликаты запрещены)
* Элементы в Set являются иммутабельными (после создания их нельзя изменить)
* Сам Set позволяет добавлять и удалять из него элементы

Кроме того Set позволяет выполнять такие математические операции как объединение, исключение и пересечение.

## Создание Set

Самый простой способ создать Set это заключить набор элементов через запятую в фигурные скобки. Второй способ это использовать встроеный конструктор `set()`.

Пример создания Set:

```python
s = {1,2,3,4,5}
s = set([1, "str", (1,2)])
```

Стоить отметить что в Set можно добавить только иммутабельные элементы. Попытка добавления в Set списка или словаря приведет к ошибке.

## Добавление элементов в Set

Set позволяет добавлять и удалять элементы уже после создания объекта. Для добавления новых элементов в Set используется метод `add()`, который добавляет один элемент, и  `update()`, который может добавлять сразу несколько элементов.

Пример добавления элементов в Set:

```python
s = set()
s.add(1)
s.update(['s','t','r'])
# s = {1,'s','t','r'}
```

## Удаление элементов из Set

Существуют несколько методов которые позволяют удалить элементы из Set:

* `discard()` - удаляет элемент из Set. Если в Set нет такого элемента, то ничего не происходит.
* `remove()` - удаляет элемент из Set. Если в Set нет такого элемента, то вызывает ошибку KeyError.
* `pop()` - Извлекает и возвращает произвольный элемент из Set
* `clear()` - очищает Set от элементов полность.

`discard()` и `remove()` принимают в качестве аргумента удаляемое значение.

## Операции над множествами

Как уже было сказано Set позволяет выполнять математические операции над элементами. Для каждой операции существует специальный оператор и метод (их результат идентичен).

Операция объединения:

```python
a = {1,2,3}
b = {2,3,4,5}
с = a | b
# или
с = a.union(b) # Не имеет значения на каком Set применяется метод, результат будет одинаков.
# с = {1,2,3,4,5}
```

Операция пересечения:

```python
a = {1,2,3}
b = {2,3,4,5}
с = a & b
# или
с = a.intersection(b)
# с = {2,3}
```

Операция разность:

```python
a = {1,2,3}
b = {2,3,4,5}
с = a - b # Здесь результат будет зависеть от перестановки операндов в выражении
с = a.difference(b)
# с = {1}
# или
с = b - a
с = b.difference(a)
# с = {4,5}
```

Операция пересечения:

```python
a = {1,2,3}
b = {2,3,4,5}
с = a & b
# или
с = a.intersection(b)
# с = {2,3}
```

Операция симметричная разность:

```python
a = {1,2,3}
b = {2,3,4,5}
с = a ^ b
# или
с = a.symmetric_difference(b)
# с = {1,4,5}
```

## Перебор Set

Перебор в Set осуществляется также, как и в других итерируемых объектах через `for in`.

## Проверка на наличие

Проверка на наличие осуществляется с помощью оператора `in` как и в других итерируемых объектах.

## Frozenset

Помимо стандартного Set существует специальная разновидность, которую нельзя изменить после создания. Этот тип позволяет использовать все виды операций на Set кроме удаления и добавления новых элементов. Чтобы создать такого рода объекты используется конструктор `frozenset()`.

Пример создания frozenset:

```python
fs = frozenset([1,2,3,4,5])
```

В отличии от обычного Set Frozenset может использоваться в качестве ключа в словаре, так как является hashable бъектом.