# Перемножение матриц

Ссылка на **[google colab](https://colab.research.google.com/drive/1nQe4A7esZ7bB8rWZSxbzTjscCLD_SSr8#scrollTo=Lsttyai_Rq6E)**

В работе были созданы матрицы А и В размером от (100,100) до (2000,2000) для вычислений на CPU, затем матрицы были перенесены на GPU при помощи команды `cp.asarray`. 

Матрица С предсатвляет собой пространство, в котором хранится результат перемножения матриц А и В. 

### Про параллельное вычиcление умножения матриц:

Умножение матриц представляет собой следующую процедуру: каждый элемент строки матрицы А умножается на элемент столбца В, затем результат суммируется и получается элемент в матрице С. При этом матрица С имеет размер [i,j],
где i - количество строк в матрице А, j - количество столбцов в матрице В. 

Функция `matmul_gpu(A, B, C)` реализует параллельное перемножение. 
Параллельное умножение матриц заключется в селдующем: мы формируем сетку, в которой располагается определенное количество блоков. В каждом блоке имеется несколько потоков (в данной работе 16 на 16 потоков = 256). 
Количество потоков соответствует количеству элементов в результирующей матрице С. Каждый поток выполняет вычисление одного элемента матрицы С. Все потоки работают параллельно, т.е. вычисление элементов матрицы происходит одновременно, за счет этого достигается уменьшение скорости расчета результата перемножения матриц. 

### Алгоритм работы: 
1. Задаемся размерами матриц.
2. На хосте формируются матрицы А и В, которые заполнены псевдослучайными вещественными числами от 0 до 1. Затем данные массивы копируются из памяти хоста в память устройства (GPU).
3. Вызывается функция умножения матрицы на CPU, рассчитывается время умножения.
4. Формируем сетку из определенного количества потоков на блок. Проверяем, чтобы сетка не была размерами меньше, чем выходной массив.
5. Вызываеься функция умножения матрицы на GPU. Чтобы поток не захватывал элементы, не входящие в массив С, используется проверка: `row < C.shape[0] and col < C.shape[1]`, рассчитывается время умножения.
6. Выполняется проверка корректности умножения при помощи функции: `np.allclose(C_cpu, C_gpu)`
7. Вывод результатов в виде графиков.

### Графики времени умножения и ускорения: 
![Графики времени умножения и ускорения](https://github.com/vmokook/HPC-2023/blob/main/MatMul/1.png)