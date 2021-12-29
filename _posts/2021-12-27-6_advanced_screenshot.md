---
layout: post
title: 6.advanced_screenshot
date: 2021-12-28 13:50:00 -0500
categories: [Visual_Studio, GUI_project] 
tags: [GUI, python, Visual_Studio]
---




# 6. advanced_screenshot
```python
import time
import keyboard
from PIL import ImageGrab


def screenshot():
    curr_time = time.strftime("_%Y%m%d_%H%M%S")
    img = ImageGrab.grab()
    img.save("image{}.png".format(curr_time))


keyboard.add_hotkey("F9", screenshot)  # 사용자가 F9 키를 누르면 스크린 샷 저장

keyboard.wait("esc")  # 사용자가 esc 를 누를 때까지 프로그램 수행

```
