---
layout: post
title: 9.progressbar
date: 2021-12-27 13:38:00 -0500
categories: [Visual_Studio, GUI] 
tags: [GUI, python, Visual_Studio]
---



# progressbar



```python
from tkinter import *
import tkinter.ttk as ttk
import time

root = Tk()
root.title("GUI")  # 제목
root.geometry("640x480")  # 가로 x 세로
# root.geometry("640x480+300+100")  # 가로 x 세로 + x좌표 + y좌표


# # progressbar = ttk.Progressbar(root, maximum=100, mode="indeterminate")    indeterminate는 언제 끝날지 모를때
# progressbar = ttk.Progressbar(root, maximum=100, mode="determinate")        # determinate는 점점 채워짐
# progressbar.start(10)  # 10ms 마다 움직임 
# progressbar.pack()



# def btncmd():
#     progressbar.stop()  # 작동 중지


# btn = Button(root, text="중지", command=btncmd)
# btn.pack()


p_var2 = DoubleVar()
progressbar2 = ttk.Progressbar(root, maximum=100, length=150, variable=p_var2)
progressbar2.pack()

def btncmd2():
    for i in range(1, 101):  # 1 ~ 100
        time.sleep(0.01)  # 0.01초 대기

        p_var2.set(i)  # progress bar의 값 설정
        progressbar2.update()  # UI 업데이트
        print(p_var2.get())

btn = Button(root, text="시작", command=btncmd2)
btn.pack()


root.resizable(False, False)  # x(너비), y(높이) 값 변경 불가 (창 크기 변경 불가)

root.mainloop()
```
