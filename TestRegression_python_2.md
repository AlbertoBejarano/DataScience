```python
import pandas as pd
import seaborn as sns
import scipy as sp
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import r2_score
from sklearn import linear_model
```


```python
df = pd.read_csv('Data/TestData.tsv', header=0, sep='\t', quotechar='"', error_bad_lines=False)
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
      <th>SampleID</th>
      <th>EGFR</th>
      <th>RB1</th>
      <th>TP53</th>
      <th>CDKN2A</th>
      <th>MYC</th>
      <th>RB2</th>
      <th>TP54</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Sample 1</td>
      <td>12.08</td>
      <td>2.92</td>
      <td>2.80</td>
      <td>81.40</td>
      <td>1.16</td>
      <td>2.31</td>
      <td>4165.196191</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sample 2</td>
      <td>12.38</td>
      <td>3.53</td>
      <td>3.22</td>
      <td>46.17</td>
      <td>0.89</td>
      <td>1.88</td>
      <td>3561.146205</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sample 3</td>
      <td>14.02</td>
      <td>2.59</td>
      <td>4.01</td>
      <td>72.80</td>
      <td>0.89</td>
      <td>2.72</td>
      <td>4284.348574</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Sample 4</td>
      <td>17.67</td>
      <td>6.75</td>
      <td>2.63</td>
      <td>39.81</td>
      <td>1.08</td>
      <td>1.88</td>
      <td>5098.680869</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Sample 5</td>
      <td>17.52</td>
      <td>4.57</td>
      <td>3.18</td>
      <td>10.94</td>
      <td>1.51</td>
      <td>1.90</td>
      <td>3406.132832</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>195</th>
      <td>Sample 196</td>
      <td>11.95</td>
      <td>3.13</td>
      <td>2.97</td>
      <td>67.18</td>
      <td>0.80</td>
      <td>2.06</td>
      <td>3847.571003</td>
    </tr>
    <tr>
      <th>196</th>
      <td>Sample 197</td>
      <td>17.99</td>
      <td>9.87</td>
      <td>3.38</td>
      <td>44.32</td>
      <td>0.98</td>
      <td>2.08</td>
      <td>5601.227131</td>
    </tr>
    <tr>
      <th>197</th>
      <td>Sample 198</td>
      <td>12.12</td>
      <td>2.27</td>
      <td>3.52</td>
      <td>57.07</td>
      <td>-0.04</td>
      <td>1.73</td>
      <td>3409.575363</td>
    </tr>
    <tr>
      <th>198</th>
      <td>Sample 199</td>
      <td>15.55</td>
      <td>4.48</td>
      <td>2.48</td>
      <td>58.25</td>
      <td>1.89</td>
      <td>2.35</td>
      <td>5087.592149</td>
    </tr>
    <tr>
      <th>199</th>
      <td>Sample 200</td>
      <td>20.89</td>
      <td>7.54</td>
      <td>3.23</td>
      <td>46.17</td>
      <td>1.71</td>
      <td>2.27</td>
      <td>6662.622385</td>
    </tr>
  </tbody>
</table>
<p>200 rows × 8 columns</p>
</div>




```python
g = sns.lmplot(data=df, x='EGFR', y='RB1')
```


    
![png](output_3_0.png)
    



```python
# https://aegis4048.github.io/mutiple_linear_regression_and_visualization_in_python
plt.style.use('default')
plt.style.use('ggplot')
X = df['EGFR'].values.reshape(-1,1)
Y = df['RB1'].values
ols = linear_model.LinearRegression()
model = ols.fit(X, y)
response = model.predict(X)
r2 = model.score(X, y).round(2)
```


```python
fig, ax = plt.subplots(figsize=(6, 6))
ax.plot(X, response, color='k', label=r2)
ax.scatter(X, Y, edgecolor='k', facecolor='grey', alpha=0.9, label='Sample data')
ax.text(0.11, 0.92, "R\N{SUPERSCRIPT TWO} = ", fontsize=14, ha='center', va='center', transform=ax.transAxes, color='black', alpha=1)
ax.text(0.20, 0.92, r2, fontsize=14, ha='center', va='center', transform=ax.transAxes, color='black', alpha=1)
ax.set_ylabel('EGFR', fontsize=14)
ax.set_xlabel('RB1', fontsize=14)
fig.tight_layout()
```


    
![png](output_5_0.png)
    



```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
