---
layout: post
title: 1.create_frame
date: 2021-12-27 13:30:00 -0500
categories: [Visual_Studio, GUI] 
tags: [GUI, python, Visual_Studio]
---


# create_frame



```python
from tkinter import *

root = Tk()
root.title("GUI")  # 제목
root.geometry("640x480")  # 가로 x 세로
# root.geometry("640x480+300+100")  # 가로 x 세로 + x좌표 + y좌표

root.resizable(False, False)  # x(너비), y(높이) 값 변경 불가 (창 크기 변경 불가)

root.mainloop()
```
