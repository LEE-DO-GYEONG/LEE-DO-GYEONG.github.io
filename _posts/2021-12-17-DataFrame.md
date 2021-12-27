---
layout: post
title: DataFrame
date: 2021-12-10 18:32:00 -0500
categories: [python, dataframe] # 큰 폴더
tags: [pandas, dataframe, python] # 작은 폴더
# extensions:
#   preset: gfm
---



# 2. DataFrame
2차원 데이터 (Series 들의 모음)

## Data 준비
사전 (dict) 자료구조를 통해 생성

예) 슬램덩크 주요 인물 8명에 대한 데이터


```python
data = {
    '이름' : ['채치수', '정대만', '송태섭', '서태웅', '강백호', '변덕규', '황태산', '윤대협'],
    '학교' : ['북산고', '북산고', '북산고', '북산고', '북산고', '능남고', '능남고', '능남고'],
    '키' : [197, 184, 168, 187, 188, 202, 188, 190],
    '국어' : [90, 40, 80, 40, 15, 80, 55, 100],
    '영어' : [85, 35, 75, 60, 20, 100, 65, 85],
    '수학' : [100, 50, 70, 70, 10, 95, 45, 90],
    '과학' : [95, 55, 80, 75, 35, 85, 40, 95],
    '사회' : [85, 25, 75, 80, 10, 80, 35, 95],
    'SW특기' : ['Python', 'Java', 'Javascript', '', '', 'C', 'PYTHON', 'C#']
}
data
```




    {'이름': ['채치수', '정대만', '송태섭', '서태웅', '강백호', '변덕규', '황태산', '윤대협'],
     '학교': ['북산고', '북산고', '북산고', '북산고', '북산고', '능남고', '능남고', '능남고'],
     '키': [197, 184, 168, 187, 188, 202, 188, 190],
     '국어': [90, 40, 80, 40, 15, 80, 55, 100],
     '영어': [85, 35, 75, 60, 20, 100, 65, 85],
     '수학': [100, 50, 70, 70, 10, 95, 45, 90],
     '과학': [95, 55, 80, 75, 35, 85, 40, 95],
     '사회': [85, 25, 75, 80, 10, 80, 35, 95],
     'SW특기': ['Python', 'Java', 'Javascript', '', '', 'C', 'PYTHON', 'C#']}




```python
data['이름']
```




    ['채치수', '정대만', '송태섭', '서태웅', '강백호', '변덕규', '황태산', '윤대협']




```python
data['키']
```




    [197, 184, 168, 187, 188, 202, 188, 190]



## DataFrame 객체 생성


```python
import pandas as pd
```


```python
df = pd.DataFrame(data)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>학교</th>
      <th>키</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
      <th>과학</th>
      <th>사회</th>
      <th>SW특기</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>채치수</td>
      <td>북산고</td>
      <td>197</td>
      <td>90</td>
      <td>85</td>
      <td>100</td>
      <td>95</td>
      <td>85</td>
      <td>Python</td>
    </tr>
    <tr>
      <th>1</th>
      <td>정대만</td>
      <td>북산고</td>
      <td>184</td>
      <td>40</td>
      <td>35</td>
      <td>50</td>
      <td>55</td>
      <td>25</td>
      <td>Java</td>
    </tr>
    <tr>
      <th>2</th>
      <td>송태섭</td>
      <td>북산고</td>
      <td>168</td>
      <td>80</td>
      <td>75</td>
      <td>70</td>
      <td>80</td>
      <td>75</td>
      <td>Javascript</td>
    </tr>
    <tr>
      <th>3</th>
      <td>서태웅</td>
      <td>북산고</td>
      <td>187</td>
      <td>40</td>
      <td>60</td>
      <td>70</td>
      <td>75</td>
      <td>80</td>
      <td></td>
    </tr>
    <tr>
      <th>4</th>
      <td>강백호</td>
      <td>북산고</td>
      <td>188</td>
      <td>15</td>
      <td>20</td>
      <td>10</td>
      <td>35</td>
      <td>10</td>
      <td></td>
    </tr>
    <tr>
      <th>5</th>
      <td>변덕규</td>
      <td>능남고</td>
      <td>202</td>
      <td>80</td>
      <td>100</td>
      <td>95</td>
      <td>85</td>
      <td>80</td>
      <td>C</td>
    </tr>
    <tr>
      <th>6</th>
      <td>황태산</td>
      <td>능남고</td>
      <td>188</td>
      <td>55</td>
      <td>65</td>
      <td>45</td>
      <td>40</td>
      <td>35</td>
      <td>PYTHON</td>
    </tr>
    <tr>
      <th>7</th>
      <td>윤대협</td>
      <td>능남고</td>
      <td>190</td>
      <td>100</td>
      <td>85</td>
      <td>90</td>
      <td>95</td>
      <td>95</td>
      <td>C#</td>
    </tr>
  </tbody>
</table>
</div>



## 데이터 접근


```python
df['이름']
```




    0    채치수
    1    정대만
    2    송태섭
    3    서태웅
    4    강백호
    5    변덕규
    6    황태산
    7    윤대협
    Name: 이름, dtype: object




```python
df['키']
```




    0    197
    1    184
    2    168
    3    187
    4    188
    5    202
    6    188
    7    190
    Name: 키, dtype: int64




```python
df[['이름', '키']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>키</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>채치수</td>
      <td>197</td>
    </tr>
    <tr>
      <th>1</th>
      <td>정대만</td>
      <td>184</td>
    </tr>
    <tr>
      <th>2</th>
      <td>송태섭</td>
      <td>168</td>
    </tr>
    <tr>
      <th>3</th>
      <td>서태웅</td>
      <td>187</td>
    </tr>
    <tr>
      <th>4</th>
      <td>강백호</td>
      <td>188</td>
    </tr>
    <tr>
      <th>5</th>
      <td>변덕규</td>
      <td>202</td>
    </tr>
    <tr>
      <th>6</th>
      <td>황태산</td>
      <td>188</td>
    </tr>
    <tr>
      <th>7</th>
      <td>윤대협</td>
      <td>190</td>
    </tr>
  </tbody>
</table>
</div>



## DataFrame 객체 생성 (Index 지정)


```python
df = pd.DataFrame(data, index=['1번', '2번', '3번', '4번', '5번', '6번', '7번', '8번'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>학교</th>
      <th>키</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
      <th>과학</th>
      <th>사회</th>
      <th>SW특기</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1번</th>
      <td>채치수</td>
      <td>북산고</td>
      <td>197</td>
      <td>90</td>
      <td>85</td>
      <td>100</td>
      <td>95</td>
      <td>85</td>
      <td>Python</td>
    </tr>
    <tr>
      <th>2번</th>
      <td>정대만</td>
      <td>북산고</td>
      <td>184</td>
      <td>40</td>
      <td>35</td>
      <td>50</td>
      <td>55</td>
      <td>25</td>
      <td>Java</td>
    </tr>
    <tr>
      <th>3번</th>
      <td>송태섭</td>
      <td>북산고</td>
      <td>168</td>
      <td>80</td>
      <td>75</td>
      <td>70</td>
      <td>80</td>
      <td>75</td>
      <td>Javascript</td>
    </tr>
    <tr>
      <th>4번</th>
      <td>서태웅</td>
      <td>북산고</td>
      <td>187</td>
      <td>40</td>
      <td>60</td>
      <td>70</td>
      <td>75</td>
      <td>80</td>
      <td></td>
    </tr>
    <tr>
      <th>5번</th>
      <td>강백호</td>
      <td>북산고</td>
      <td>188</td>
      <td>15</td>
      <td>20</td>
      <td>10</td>
      <td>35</td>
      <td>10</td>
      <td></td>
    </tr>
    <tr>
      <th>6번</th>
      <td>변덕규</td>
      <td>능남고</td>
      <td>202</td>
      <td>80</td>
      <td>100</td>
      <td>95</td>
      <td>85</td>
      <td>80</td>
      <td>C</td>
    </tr>
    <tr>
      <th>7번</th>
      <td>황태산</td>
      <td>능남고</td>
      <td>188</td>
      <td>55</td>
      <td>65</td>
      <td>45</td>
      <td>40</td>
      <td>35</td>
      <td>PYTHON</td>
    </tr>
    <tr>
      <th>8번</th>
      <td>윤대협</td>
      <td>능남고</td>
      <td>190</td>
      <td>100</td>
      <td>85</td>
      <td>90</td>
      <td>95</td>
      <td>95</td>
      <td>C#</td>
    </tr>
  </tbody>
</table>
</div>



## DataFrame 객체 생성 (Column 지정)
data 중에서 원하는 컬럼만 선택하거나, 순서 변경 가능


```python
df = pd.DataFrame(data, columns=['이름', '학교', '키'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>학교</th>
      <th>키</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>채치수</td>
      <td>북산고</td>
      <td>197</td>
    </tr>
    <tr>
      <th>1</th>
      <td>정대만</td>
      <td>북산고</td>
      <td>184</td>
    </tr>
    <tr>
      <th>2</th>
      <td>송태섭</td>
      <td>북산고</td>
      <td>168</td>
    </tr>
    <tr>
      <th>3</th>
      <td>서태웅</td>
      <td>북산고</td>
      <td>187</td>
    </tr>
    <tr>
      <th>4</th>
      <td>강백호</td>
      <td>북산고</td>
      <td>188</td>
    </tr>
    <tr>
      <th>5</th>
      <td>변덕규</td>
      <td>능남고</td>
      <td>202</td>
    </tr>
    <tr>
      <th>6</th>
      <td>황태산</td>
      <td>능남고</td>
      <td>188</td>
    </tr>
    <tr>
      <th>7</th>
      <td>윤대협</td>
      <td>능남고</td>
      <td>190</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 순서 변경
df = pd.DataFrame(data, columns=['키', '학교', '이름'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>키</th>
      <th>학교</th>
      <th>이름</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>197</td>
      <td>북산고</td>
      <td>채치수</td>
    </tr>
    <tr>
      <th>1</th>
      <td>184</td>
      <td>북산고</td>
      <td>정대만</td>
    </tr>
    <tr>
      <th>2</th>
      <td>168</td>
      <td>북산고</td>
      <td>송태섭</td>
    </tr>
    <tr>
      <th>3</th>
      <td>187</td>
      <td>북산고</td>
      <td>서태웅</td>
    </tr>
    <tr>
      <th>4</th>
      <td>188</td>
      <td>북산고</td>
      <td>강백호</td>
    </tr>
    <tr>
      <th>5</th>
      <td>202</td>
      <td>능남고</td>
      <td>변덕규</td>
    </tr>
    <tr>
      <th>6</th>
      <td>188</td>
      <td>능남고</td>
      <td>황태산</td>
    </tr>
    <tr>
      <th>7</th>
      <td>190</td>
      <td>능남고</td>
      <td>윤대협</td>
    </tr>
  </tbody>
</table>
</div>




```python

```