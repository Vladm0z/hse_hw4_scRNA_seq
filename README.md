# hse_hw4_scRNA_seq

[Ссылка на Colab](https://colab.research.google.com/drive/1eMQDqpJKQ9a9WVY9rtQlfUWP0PExMX1B?usp=sharing)

## Нормальизация данных
Данные были нормализованы методом TPM, обычный метод TPM задается следующей формулой

<img src="https://render.githubusercontent.com/render/math?math=TPM_i = \frac{q_i \slash l_i}{\sum (q_j \slash l_j)} \cdot 10^6">

Где <img src="https://render.githubusercontent.com/render/math?math=q_i"> - риды попавшие на транскрипцию, а <img src="https://render.githubusercontent.com/render/math?math=l_i"> - длина транскрипции, однако нам длина неизвестна, так что мы будем использовать следующую формулу

<img src="https://render.githubusercontent.com/render/math?math=TPM_i = \frac{q_i}{\sum q_j} \cdot 10^6">

Как мы видим, несмотря на отсутсвие длин, мы получили такой же Heatmap, как и ожидалось
![Image](/img/mark.png)

Также были визуализированы UMAP и PCA

UMAP | PCA 
 --- | ---
![Image](/img/UMAP.png) | ![Image](/img/PCA.png)
