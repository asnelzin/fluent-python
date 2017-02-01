# Sequences

Container sequences:
	list, tuple and collections.deque могут содержать элементы разного типа

Flat sequences:
	str, bytes, bytearray, memoryview and array.array содержат итемы одного типа

Mutable sequences
	list, bytearray, array.array, collections.deque, and memoryview

Последовательности-контейнеры хранят ссылки на объекты, которые они содержат (могут быть любого типа), тогда как flat-последовательности физически хранят значения каждого элемента в своей собственной памяти;

Flat-последовательности более компактны, но могут хранить только приметивные типы данных;

Mutable sequences
	list, bytearray, array.array, collections.deque, and memoryview

Immutable sequences
	tuple, str, and bytes

slice очень мощный и удобный инструмент;

Существует slice object;

`[['_'] * 3] * 3` is equal to:
```
	row = ['_'] * 3
	board = []
	for i in range(3):
		board.append(row)
```

```
	t = (1,2,[30,40])
	t[2] += [50, 60]
```
+= not atomic;
