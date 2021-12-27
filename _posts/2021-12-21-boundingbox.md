---
layout: post
title: boundingbox
date: 2021-12-20 13:30:00 -0500
categories: [Visual_Studio, image_edit] 
tags: [boundingbox, python, Visual_Studio]
---


# boundingbox



```python
import cv2
import numpy as np
import os
import re
from os import remove
import shutil



def createFolder(directory):
    try:
        if not os.path.exists(directory):
            os.makedirs(directory)
    except OSError:
        print ('Error: Creating directory. ' +  directory)

        
#불러올 폴더 이름에 띄어쓰기가 있으면 에러가 발생함
keyword = input('검색할 태그를 입력하세요 : ')
path = 'C:/Users/okok0/OneDrive/바탕 화면/' + keyword # 자신의 파일경로
file_list = os.listdir(path)

file_list_py = [file for file in file_list if file.endswith('.jpg')]
folder_name = path + 'txt'
createFolder(folder_name)
#리사이즈 폴더 만들기
# folder_resize = path+'_resize'
# createFolder(folder_resize)

for file_name in file_list_py:
    
    img_array = np.fromfile(path + '/' + file_name, np.uint8) # 자신의 파일경로
    rgb_image = cv2.imdecode(img_array, cv2.IMREAD_UNCHANGED)
    #일반사이즈
    rect = cv2.selectROI('Select Window', rgb_image, fromCenter=False, showCrosshair=True)
    #리사이즈 코드
    # img_resize = cv2.resize(rgb_image, None, fx=2, fy=2, interpolation = cv2.INTER_CUBIC)
    # rect = cv2.selectROI('Select Window', img_resize, fromCenter=False, showCrosshair=True)
    
    cv2.destroyWindow('Select Window')
    x, y, w, h = rect
    x2= x+w 
    y2 = y+h
    rgb_ = str(x)+' '+str(y)+' '+str(x2)+' '+str(y)+' '+str(x2)+' '+str(y2)+' '+str(x)+' '+str(y2)
    # rgb_ = str(x)+' '+str(y)+' '+str(x2)+' '+str(y2)

    if 0 == x+x2+y+y2:
        shutil.move(path+'/'+ file_name, 'C:/Users/okok0/OneDrive/바탕 화면/etc/' + file_name) #파일이동
        # f = path+'/'+file_name
        # remove(f) # 파일 지워짐
        # pass
    else :    
        shutil.move(path + '/' + file_name, folder_name + '/' + file_name)
        # cv2.imwrite(folder_resize+'/'+file_name,img_resize) #리사이즈 좌표
        file_name = file_name.replace('.jpg', '')
        # f = open(folder_name+'/'+file_name+'.txt','w') #리사이즈 좌표
        f = open(folder_name + '/' + file_name + '.txt','w')
        
        f.write(rgb_+" "+keyword)
        f.close()
```

