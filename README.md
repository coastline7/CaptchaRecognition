# Captcha Recognition Project

### Выполнено командой: *Хритоненков Олег*

### Цель работы:

Распознать буквенно-цифровые символы на изображениях с шумом. В проекте используется набор капч с [тайваньского вебсайта](http://bsr.twse.com.tw/bshtm/) в качестве образцов.   

![alt text](https://sun9-2.userapi.com/c840734/v840734541/69e0/H3-xuUnAxw8.jpg)
![alt text](https://sun9-2.userapi.com/c840734/v840734541/69d9/vFmUrkpVLR8.jpg)
![alt text](https://sun9-2.userapi.com/c840734/v840734541/69d2/vYBRk3f2QnE.jpg)
![alt text](https://sun9-2.userapi.com/c840734/v840734541/69cb/16PpmtZodx0.jpg)

### Используемые библиотеки: 

>- [OpenCV](http://opencv.org/) и [Tesseract OCR](https://github.com/tesseract-ocr/tesseract).
>- [Scipy](https://www.scipy.org/) и [Numpy](http://www.numpy.org/)

Проект выполнен при помощи [Anaconda](https://www.continuum.io/downloads). Это дистрибутив Python с множеством пакетов и библиотек для научных и инженерных расчетов, которые уже установлены и сконфигурированы.

```python 

import glob
import os
import numpy as np
import re
import cv2

from IPython.display import display
from pytesseract import image_to_string
from __future__ import division
from scipy import misc as ms

```

### Очистка изображения:

Необходимо очистить изображение от шума, чтобы библиотека Tesseract смогла получить хороший результат распознавания. Для лучшего контраста образцы конвертируются в черно-белые сразу же после чтения. Затем используются эрозия [erode](http://docs.opencv.org/3.0-beta/doc/py_tutorials/py_imgproc/py_morphological_ops/py_morphological_ops.html) и функция шумоподавления [fastNlMeansDenoising](http://docs.opencv.org/2.4/modules/photo/doc/denoising.html) из библиотеки OpenCV для того, чтобы удалить весь точечный шум и полосу на изображении. После этого шага получается достаточно чистый образец для Tesseract. Для лучшей точности OCR необходимо настроить форму и размер ядра эрозии и величину h в fastNlMeansDenoising.


