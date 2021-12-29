---
layout: post
title: 3.auto_screenshot
date: 2021-12-28 13:47:00 -0500
categories: [Visual_Studio, GUI_project] 
tags: [GUI, python, Visual_Studio]
---




# 3. auto_screenshot
```python
from PIL import ImageGrab
import time

time.sleep(5)  # 5초 대기: 사용자가 준비하는 시간

for i in range(1, 11):  # 2초 간격으로 10개 이미지 저장
    img = ImageGrab.grab()   # 현재 스크린 이미지를 가져옴
    img.save("image{}.png".format(i))  # 파일로 저장
    time.sleep(2)  # 2초 단위
    

```
