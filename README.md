# hse_hw4_scRNA_seq

[Ссылка на Colab](https://colab.research.google.com/drive/1eMQDqpJKQ9a9WVY9rtQlfUWP0PExMX1B?usp=sharing)


## Нормализация данных
Данные были нормализованы методом TPM, обычный метод TPM задается следующей формулой

<img src="https://render.githubusercontent.com/render/math?math={\LARGE TPM_i = \frac{q_i / l_i}{\sum (q_j / l_j)} \cdot 10^6}#gh-light-mode-only">
<img src="https://render.githubusercontent.com/render/math?math={\LARGE \color{white}TPM_i = \frac{q_i / l_i}{\sum (q_j / l_j)} \cdot 10^6}#gh-dark-mode-only">

Где <img src="https://render.githubusercontent.com/render/math?math={q_i}#gh-light-mode-only"> <img src="https://render.githubusercontent.com/render/math?math={\color{white} q_i}#gh-dark-mode-only"> - риды попавшие на транскрипцию, а <img src="https://render.githubusercontent.com/render/math?math={l_i}#gh-light-mode-only"> <img src="https://render.githubusercontent.com/render/math?math={\color{white} l_i}#gh-dark-mode-only"> - длина транскрипции, однако нам длина неизвестна, так что мы будем использовать следующую формулу

<img src="https://render.githubusercontent.com/render/math?math={TPM_i = \frac{q_i}{\sum q_j} \cdot 10^6}#gh-light-mode-only">
<img src="https://render.githubusercontent.com/render/math?math={\color{white}TPM_i = \frac{q_i}{\sum q_j} \cdot 10^6}#gh-dark-mode-only">


## Heatmap
Как мы видим, несмотря на отсутсвие длин, мы получили такой же Heatmap, как и ожидалось
![Image](/img/mark.png)
На картинке можно заметить несколько (~5) кластеров клеток, это свидительствует о том, что клетки каждого кластера принадлежат одному типу. 

## UMAP и PCA
Также были визуализированы UMAP и PCA, используя [anndata](https://anndata.readthedocs.io/en/latest/) и [scanpy](https://scanpy.readthedocs.io/en/stable/)

UMAP | PCA 
 --- | ---
![Image](/img/UMAP.png) | ![Image](/img/PCA.png)

Тут мы разбили данные по группам cTEC, mTEC-I, mTEC-II, mTEC-III, mTEC-IV, тем самым понизив размерность данных и получив деление на группы


