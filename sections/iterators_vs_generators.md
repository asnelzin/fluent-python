# Iterators vs Generators

`yield` было добавлено в Python 2.3;

Python 3 использует генераторы повсеместно;

Каждая коллекция в Python — `iterable`;

Каждый раз, когда интерпретатору нужно сделать итерацию по объекту `x`, автоматически вызывается `iter(x)`;

Функция `iter` проверяет является ли объект `iterable`. Это может быть достигнуто двумя способами: `__iter__` (должен вернуть итератор); `__getitem__` (python сам создаст итератор по индексам). Если не получилось, райзится `TypeError`;

Интерфейс итератора: `__next__` (следующее занчений или `raise StopIteration`); `__iter__` (возвращает `self`);

Исходя из интерфейса следует, что любой итератор — `iterable`, но обратное не верно;

`(x for x in gen())` — generator expression;

В Python 3.3 был добавлен `yield from` — помогает заменять внутреннее разворачевание генераторов;

У функции `iter` на самом деле есть второй аргумент, который обозначает stop-значение для итератора;

Есть по крайней мере три способа взглянуть на связь между итераторами и генераторами:

Первый — __интерфейс__: генератор реализует интерфейс `__iter__ + __next__`, поэтому с этой точки зрения каждый генератор — это итератор.

Второй — __реализация__: генератор может быть реализован двумя способами (функция с `yield` и generator expression). При этом создается объект типа `GeneratorType`, который также реализует интерфейс итератора. Но можно написать итератор, который не будет генератором.

Третий — __концептуальный__: как описано в GoF, итератор обходит коллекцию и возвращает значение по одному. Итератор может быть очень сложным (например, обход древоподобной стрктуры), но не смотря на всю сложность итератор читает данные из существующего источника. С другой стороны, генератор может создавать значения на лету, без существующей коллекции. И даже используя коллекцию генераторы не обязательно должны возвращать только значения из коллекции (например, enumerate создает tuples используя коллекцию). С концептуальной точки зрения реализация не важна. Например, можно написать генератор, не используя python generator object;

В python документации и комьюнити слова iterator и generator почти синонимы.
