# АВЛ-дерево
([Другие задания](https://github.com/Ljts42/itmo-cpp))

## Деревья поиска

В этом задании вам необходимо реализовать сбалансированное двоичное дерево поиска - иерархичную структуру данных в pointer machine model, узлы которой содержат значения, а также некоторые имеют левого и/или правого потомка, каждый из которых является корнем левого и правого поддеревьев соответственно. Узлы без потомков называются листями, остальные - внутренними. Узел, находящийся на самом верхнем уровне (не являющийся чьим либо потомком) называется корнем (в дереве всегда только один корень).

Все значения в левом поддереве узла меньше, чем значение в самом узле. Аналогично, все значения в правом поддереве - больше, чем значение в узле.

Введем понятие высоты узла:
* Высота листа равна нулю
* Высота внутреннего узла равна максимуму между высотами его потомков, увеличенному на один

Высота дерева определяется как высота его корня.

Дерево называется сбалансированным, если его высота не превышает значение C&middot;log(n) для некоторого C, где n - это количество элементов в дереве.

## Модификация
Ваша модификация - АВЛ-дерево с ручным управлением памятью (без использования умных указателей) на множестве целых чисел (`int`).

Особенность данной модификации заключается в том, что в АВЛ дереве поддерживается следующее свойство: для каждой вершины высота её поддеревьев отличается не больше чем на 1. В остальном оно похоже классическое дерево поиска.

Ваша реализация должна удовлетворять интерфейсу, изложенному в файле `include/AVLTree.h`:

```C++
class AVLTree
{
public:
    bool contains(int value) const;
    bool insert(int value);
    bool remove(int value);

    std::size_t size() const;
    bool empty() const;

    std::vector<int> values() const;

    ~AVLTree();
};
```

В задании основной акцент ставится на отсутствие утечек памяти, а также грамотное вынесение общего кода. Подсказки для реализации вашей структуры можете найти на [Викиконспектах](https://neerc.ifmo.ru/wiki/index.php?title=%D0%90%D0%92%D0%9B-%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE#:~:text=AVL-Tree) или на [записи лекции по АиСД](https://www.youtube.com/watch?v=N4xPvklbA24&list=PLrS21S1jm43gVKLfBnBW4Ig3SEinCD96n&index=5).
