# Двухсторонний фильтр Гаусса

Ссылка на [код](https://colab.research.google.com/drive/1lP658twfp1JgtdjH0hgBfe0l_wIdcnY8?usp=sharing)

### Результаты:
Изображение 128х128: 

![Изображение 128х128](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/images/128.png)

Изображение 256х256: 

![Изображение 256х256](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/images/256.png)

Изображение 512х512: 

![Изображение 512х512](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/images/512.png)

Изображение 1024х1024: 

![Изображение 1024х1024](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/images/1024.png)

Изображение 2048х2048: 

![Изображение 2048х2048](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/images/2048.png)

Параллельность вычислений на GPU заключается в том, что все потоки GPU обрабатывают различные пиксели изображения. 
Каждый поток отвечает за свой пиксель. 

### Графики времени умножения и ускорения: 
![Графики времени умножения и ускорения](https://github.com/vmokook/HPC-2023/blob/main/Bilateral/images/Графики.png)

Вывод: был реализован двухсторонний фильтр Гаусса на CPU и GPU. Выполнен сравнительный анализ на основе 5 изображений 
разной размерности от 128х128 до 2048х2048. Подсчитано время фильтрации на CPU и GPU данных изображений, а также рассчитано ускорение. 
