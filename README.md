# hse_hw2_chip
Эксперимент на линии Karpas-422 на гистонной метке H3K36me3

Использованные файлы:

Тип | Имя 
--- | ---
Реплика 1 | [ENCFF777FCM](https://www.encodeproject.org/files/ENCFF777FCM/)
Реплика 2 | [ENCFF318MQP](https://www.encodeproject.org/files/ENCFF318MQP/)
Контроль | [ENCFF002AXD](https://www.encodeproject.org/files/ENCFF002AXD/)

Ссылка на [файл Colab](https://colab.research.google.com/drive/1iMvGlNXd8cNPbGK04YRkG4wDdtwzLplf?usp=sharing)

## Выдача FastQC
Анализ FastQC показал, что качество данных реплик неплохое, поэтому для них подрезание чтений не потребовалось

Статистика по | Реплика 1 | Реплика 2
--- | --- | ---
Summary | ![](fastqc_img/ex1_0.png) | ![](fastqc_img/ex2_0.png) 
Per tile sequence quality | ![](fastqc_img/ex1_1.png) | ![](fastqc_img/ex2_1.png) 
Per base sequence content | ![](fastqc_img/ex1_2.png) | ![](fastqc_img/ex2_2.png) 
Per sequence GC content | ![](fastqc_img/ex1_3.png) | ![](fastqc_img/ex2_3.png) 

По анализу видно, что реплики очень похожи по содержанию.

Анализ контрольного образца показал, что необходима его обработка, в частности для уменьшения числа неизвестных нуклеотидов (N). 
Для этого к образцу было применено подрезание с помощью инструмента trimmomatic.


Cтатистика по | Контроль | Подрезанный контроль 
--- | --- | ---
Summary | ![](fastqc_img/con_0.png) | ![](fastqc_img/con_trim_0.png) 
Per base sequence quality | ![](fastqc_img/con_1.png) | ![](fastqc_img/con_trim_1.png) 
Per base sequence content | ![](fastqc_img/con_2.png) | ![](fastqc_img/con_trim_2.png) 
Per sequence GC content | ![](fastqc_img/con_3.png) | ![](fastqc_img/con_trim_3.png) 
Per base N content | ![](fastqc_img/con_4.png) | ![](fastqc_img/con_trim_4.png) 

Общее качество и информативность данных после подрезания улучшились, в основном благодаря удалению неизвестных нуклеотидов (N).

## Анализ bowtie

Образец | Кол-во ридов в файле | Кол-во ридов, выравненных НЕ-уникально | Кол-во не выравненных ридов
--- | --- | --- | ---
Реплика 1 | 26073094 | 2519752 (9.66%) | 22783748 (87.38%)
Реплика 2 | 26915669 | 2617162 (9.72%) | 23501680 (87.32%)
Контроль | 40851379 | 4752822 (11.63%) | 34954718 (85.57%)

## Диаграммы Венна







