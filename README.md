# Captcha Recognition Project

### Выполнено командой: *Хритоненков Олег*

### Цель работы:

Распознать буквенно-цифровые символы на изображениях с шумом. В проекте используется набор капч с [тайваньского вебсайта](http://bsr.twse.com.tw/bshtm/) в качестве образцов.   

![alt text](https://sun9-2.userapi.com/c840734/v840734541/69e0/H3-xuUnAxw8.jpg)
![alt text](https://sun9-2.userapi.com/c840734/v840734541/69d9/vFmUrkpVLR8.jpg)
![alt text](https://sun9-2.userapi.com/c840734/v840734541/69d2/vYBRk3f2QnE.jpg)
![alt text](https://sun9-2.userapi.com/c840734/v840734541/69cb/16PpmtZodx0.jpg)

### Используемые библиотеки: 
>- [OpenCV](http://opencv.org/) и [Tesseract](https://github.com/tesseract-ocr/tesseract).
>- [Scipy](https://www.scipy.org/) и [Numpy](http://www.numpy.org/)

Проект выполнен при помощи Anaconda. Это дистрибутив Python с множеством пакетов и библиотек для научных и инженерных расчетов, которые уже установлены и сконфигурированы.

```python 

import glob
import os

from IPython.display import display
from pytesseract import image_to_string
from __future__ import division
import numpy as np
import cv2

```
