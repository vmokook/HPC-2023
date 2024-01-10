# Двухсторонний фильтр Гаусса

Ссылка на [код](https://colab.research.google.com/drive/1lP658twfp1JgtdjH0hgBfe0l_wIdcnY8?usp=sharing)

### Результаты:
Изображение 64х64: 

![Изображение 64х64](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/Images/64.png)

Изображение 128х128: 

![Изображение 128х128](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/Images/128.png)

Изображение 164х164: 

![Изображение 164х164](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/Images/164.png)

Изображение 256х256: 

![Изображение 256х256](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/Images/256.png)

Изображение 512х512: 

![Изображение 512х512](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/Images/512.png)

Параллельность вычислений на GPU заключается в том, что все потоки GPU обрабатывают различные пиксели изображения. 
Каждый поток отвечает за свой пиксель. 

### Графики времени умножения и ускорения: 
![Графики времени умножения и ускорения](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/Images/Графики.png)

Вывод: был реализован двухсторонний фильтр Гаусса на CPU и GPU. Выполнен сравнительный анализ на основе 5 изображений 
разной размерности от 64х64 до 512х512. Подсчитано время фильтрации на CPU и GPU данных изображений, а также рассчитано ускорение. 
