---
layout: post
title: naver_crawling
date: 2021-12-20 13:30:00 -0500
categories: [Visual_Studio, crawling] 
tags: [crawling, python, Visual_Studio]
---


# naver_crawling



```python
import urllib.request
from urllib.parse import quote_plus
from bs4 import BeautifulSoup
from selenium import webdriver
import time

def scroll_down():
    global driver
    last_height = driver.execute_script("return document.body.scrollHeight")

    while True:
        driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")
        time.sleep(2)
        new_height = driver.execute_script("return document.body.scrollHeight")

        if new_height == last_height:
            time.sleep(2)
            new_height = driver.execute_script("return document.body.scrollHeight")

            try:
                driver.find_element_by_class_name("mye4qd").click()
            except:

               if new_height == last_height:
                   break


        last_height = new_height

keyword = input('검색할 태그를 입력하세요 : ')
url = 'https://search.naver.com/search.naver?where=image&sm=tab_jum&query={}'.format(keyword)

driver = webdriver.Chrome()

driver.get(url)
time.sleep(1)
body = driver.find_element_by_css_selector('body')

scroll_down()

       
req = driver.page_source
soup = BeautifulSoup(req, 'html.parser')

images = soup.find_all('img', attrs={'class':'_image _listImage'})


print('number of img tags: ', len(images))

n = 1
for i in images:

    try:
        imgUrl = i["data-lazy-src"]
    except:
        imgUrl = i["src"]

    with urllib.request.urlopen(imgUrl) as f:
        with open('C:/apps/crawling/selenium/' + str(n) + '.jpg', 'wb') as h:
            img = f.read()
            h.write(img)

    n += 1


driver.quit()
```

