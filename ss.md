<h1 style="color: orange;
    text-align: center;
    font-weight: bold;
    font-size: 35px;">美妆用户行为分析</h1>

<h2 style=" color: blue;
    font-style: italic;
    font-size: 26px;
">说明</h2>

<p style="   color: white;
    font-size: 22px;
">
    本次数据分析基于阿里云天池数据集(美妆用户行为数据集)，使用转化漏斗，对常见电商分析指标，包括转
化率、PV、UV、复购率等进行分析，分析过程中使用Python进行数据的清洗，清洗后的数据导入
MySQL数据库，运用MySQL进行数据提取，使用Power BI进行数据可视化。
</p>


```python
#导入包
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import datetime as dt
```


```python
#导入数据
data = pd.read_csv(r"E:\下载\UserBehavior.csv", header=None,skiprows=5000000, nrows=3000000)
```


```python
data.head()
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
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>309818</td>
      <td>1461532</td>
      <td>3102419</td>
      <td>cart</td>
      <td>1511959462</td>
    </tr>
    <tr>
      <th>1</th>
      <td>309818</td>
      <td>4710383</td>
      <td>1792277</td>
      <td>pv</td>
      <td>1511959603</td>
    </tr>
    <tr>
      <th>2</th>
      <td>309818</td>
      <td>1421743</td>
      <td>4069500</td>
      <td>pv</td>
      <td>1511959759</td>
    </tr>
    <tr>
      <th>3</th>
      <td>309818</td>
      <td>800137</td>
      <td>1216617</td>
      <td>pv</td>
      <td>1511959828</td>
    </tr>
    <tr>
      <th>4</th>
      <td>309818</td>
      <td>2493122</td>
      <td>1216617</td>
      <td>pv</td>
      <td>1511959953</td>
    </tr>
  </tbody>
</table>
</div>


