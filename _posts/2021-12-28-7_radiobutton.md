---
layout: post
title: 7.radiobutton
date: 2021-12-27 13:34:00 -0500
categories: [Visual_Studio, GUI] 
tags: [GUI, python, Visual_Studio]
---



# radiobutton



```python
from tkinter import *
from typing import List

root = Tk()
root.title("GUI")  # 제목
root.geometry("640x480")  # 가로 x 세로
# root.geometry("640x480+300+100")  # 가로 x 세로 + x좌표 + y좌표


Label(root, text="메뉴를 선택하세요").pack()


burger_var = IntVar()   # int형으로 값을 저장한다.
btn_buger1 = Radiobutton(root, text="햄버거", value=1, variable=burger_var)
btn_buger1.select()
btn_buger2 = Radiobutton(root, text="치즈버거", value=2, variable=burger_var)
btn_buger3 = Radiobutton(root, text="치킨버거", value=3, variable=burger_var)

btn_buger1.pack()
btn_buger2.pack()
btn_buger3.pack()

Label(root, text="음료를 선택하세요").pack()

drink_var = StringVar()
btn_drink1 = Radiobutton(root, text="콜라", value="콜라", variable=drink_var)
btn_drink1.select()  # 기본값 선택
btn_drink2 = Radiobutton(root, text="사이다", value="사이다", variable=drink_var)
btn_drink3 = Radiobutton(root, text="환타", value="환타", variable=drink_var)

btn_drink1.pack()
btn_drink2.pack()
btn_drink3.pack()


def btncmd():
    print(burger_var.get())  # 햄버거 중 선택된 라디오 항목의 값을 출력
    print(drink_var.get())


btn = Button(root, text="주문", command=btncmd)
btn.pack()




root.resizable(False, False)  # x(너비), y(높이) 값 변경 불가 (창 크기 변경 불가)

root.mainloop()
```
