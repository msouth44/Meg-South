# Heart Failure Clinical Records

This is the full workflow of the project that I created to play around with coding and exploring the Heart Failure Clinical Records dataset. 


```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
df= pd.read_csv('heart_failure_clinical_records_dataset.csv')
```


```python
df
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>anaemia</th>
      <th>creatinine_phosphokinase</th>
      <th>diabetes</th>
      <th>ejection_fraction</th>
      <th>high_blood_pressure</th>
      <th>platelets</th>
      <th>serum_creatinine</th>
      <th>serum_sodium</th>
      <th>sex</th>
      <th>smoking</th>
      <th>time</th>
      <th>DEATH_EVENT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>75.0</td>
      <td>0</td>
      <td>582</td>
      <td>0</td>
      <td>20</td>
      <td>1</td>
      <td>265000.00</td>
      <td>1.9</td>
      <td>130</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>55.0</td>
      <td>0</td>
      <td>7861</td>
      <td>0</td>
      <td>38</td>
      <td>0</td>
      <td>263358.03</td>
      <td>1.1</td>
      <td>136</td>
      <td>1</td>
      <td>0</td>
      <td>6</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>65.0</td>
      <td>0</td>
      <td>146</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td>162000.00</td>
      <td>1.3</td>
      <td>129</td>
      <td>1</td>
      <td>1</td>
      <td>7</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>50.0</td>
      <td>1</td>
      <td>111</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td>210000.00</td>
      <td>1.9</td>
      <td>137</td>
      <td>1</td>
      <td>0</td>
      <td>7</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>65.0</td>
      <td>1</td>
      <td>160</td>
      <td>1</td>
      <td>20</td>
      <td>0</td>
      <td>327000.00</td>
      <td>2.7</td>
      <td>116</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
      <td>1</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>294</th>
      <td>62.0</td>
      <td>0</td>
      <td>61</td>
      <td>1</td>
      <td>38</td>
      <td>1</td>
      <td>155000.00</td>
      <td>1.1</td>
      <td>143</td>
      <td>1</td>
      <td>1</td>
      <td>270</td>
      <td>0</td>
    </tr>
    <tr>
      <th>295</th>
      <td>55.0</td>
      <td>0</td>
      <td>1820</td>
      <td>0</td>
      <td>38</td>
      <td>0</td>
      <td>270000.00</td>
      <td>1.2</td>
      <td>139</td>
      <td>0</td>
      <td>0</td>
      <td>271</td>
      <td>0</td>
    </tr>
    <tr>
      <th>296</th>
      <td>45.0</td>
      <td>0</td>
      <td>2060</td>
      <td>1</td>
      <td>60</td>
      <td>0</td>
      <td>742000.00</td>
      <td>0.8</td>
      <td>138</td>
      <td>0</td>
      <td>0</td>
      <td>278</td>
      <td>0</td>
    </tr>
    <tr>
      <th>297</th>
      <td>45.0</td>
      <td>0</td>
      <td>2413</td>
      <td>0</td>
      <td>38</td>
      <td>0</td>
      <td>140000.00</td>
      <td>1.4</td>
      <td>140</td>
      <td>1</td>
      <td>1</td>
      <td>280</td>
      <td>0</td>
    </tr>
    <tr>
      <th>298</th>
      <td>50.0</td>
      <td>0</td>
      <td>196</td>
      <td>0</td>
      <td>45</td>
      <td>0</td>
      <td>395000.00</td>
      <td>1.6</td>
      <td>136</td>
      <td>1</td>
      <td>1</td>
      <td>285</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>299 rows × 13 columns</p>





```python
#NaN check
pd.isna(df).sum()
```




    age                         0
    anaemia                     0
    creatinine_phosphokinase    0
    diabetes                    0
    ejection_fraction           0
    high_blood_pressure         0
    platelets                   0
    serum_creatinine            0
    serum_sodium                0
    sex                         0
    smoking                     0
    time                        0
    DEATH_EVENT                 0
    dtype: int64




```python
df[['creatinine_phosphokinase','ejection_fraction']]
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>creatinine_phosphokinase</th>
      <th>ejection_fraction</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>582</td>
      <td>20</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7861</td>
      <td>38</td>
    </tr>
    <tr>
      <th>2</th>
      <td>146</td>
      <td>20</td>
    </tr>
    <tr>
      <th>3</th>
      <td>111</td>
      <td>20</td>
    </tr>
    <tr>
      <th>4</th>
      <td>160</td>
      <td>20</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>294</th>
      <td>61</td>
      <td>38</td>
    </tr>
    <tr>
      <th>295</th>
      <td>1820</td>
      <td>38</td>
    </tr>
    <tr>
      <th>296</th>
      <td>2060</td>
      <td>60</td>
    </tr>
    <tr>
      <th>297</th>
      <td>2413</td>
      <td>38</td>
    </tr>
    <tr>
      <th>298</th>
      <td>196</td>
      <td>45</td>
    </tr>
  </tbody>
</table>
<p>299 rows × 2 columns</p>





```python
# df containing cpk and ejection fraction
df_cpk_ef= df[['creatinine_phosphokinase','ejection_fraction']]
```


```python
# np array: cpk
np_cpk = np.array(df_cpk_ef['creatinine_phosphokinase'])
```


```python
# np array: ejection fraction
np_ef = np.array(df_cpk_ef['ejection_fraction'])
```


```python
# linear regression: cpk(DV) and ejection fraction(IV)
plt.plot(np_ef, np_cpk, 'o')

m, b = np.polyfit(np_ef, np_cpk, 1)

plt.plot(np_ef, m*np_ef + b)

plt.xlabel('Ejection Fraction')
plt.ylabel('Creatinine Phosphokinase')

plt.show()
```




![png](heart_failure_9_0.png)




```python
sns.countplot(x="ejection_fraction",data= df)
plt.show()
```




![png](heart_failure_10_0.png)




```python
# descriptive stats for ejection_fraction
df['ejection_fraction'].describe()
```




    count    299.000000
    mean      38.083612
    std       11.834841
    min       14.000000
    25%       30.000000
    50%       38.000000
    75%       45.000000
    max       80.000000
    Name: ejection_fraction, dtype: float64




```python
# Histogram: look at data distribution 
fig, ax = plt.subplots()
ax.hist(df['ejection_fraction'],bins= 14,edgecolor='black', linewidth=1.2, align= 'mid')

plt.xlabel('ejection_fraction')
plt.ylabel('Number of Patient')

#Median and Quartiles
plt.axvline(df['ejection_fraction'].describe()['25%'], 0, 1, color='red', linestyle='--')
plt.axvline(df['ejection_fraction'].median(), 0, 1, color='red', linestyle='-')
plt.axvline(df['ejection_fraction'].describe()['75%'], 0, 1, color='red', linestyle='--')

plt.show()
```




![png](heart_failure_12_0.png)




```python
#conditions 
conditions = [
    (df['ejection_fraction'] <= 55),
    (df['ejection_fraction'] >= 55)]

#mapping
mapping=[
    'Abnormal',
    'Normal'
    ]
```


```python
df[conditions[0]]
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>anaemia</th>
      <th>creatinine_phosphokinase</th>
      <th>diabetes</th>
      <th>ejection_fraction</th>
      <th>high_blood_pressure</th>
      <th>platelets</th>
      <th>serum_creatinine</th>
      <th>serum_sodium</th>
      <th>sex</th>
      <th>smoking</th>
      <th>time</th>
      <th>DEATH_EVENT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>75.0</td>
      <td>0</td>
      <td>582</td>
      <td>0</td>
      <td>20</td>
      <td>1</td>
      <td>265000.00</td>
      <td>1.9</td>
      <td>130</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>55.0</td>
      <td>0</td>
      <td>7861</td>
      <td>0</td>
      <td>38</td>
      <td>0</td>
      <td>263358.03</td>
      <td>1.1</td>
      <td>136</td>
      <td>1</td>
      <td>0</td>
      <td>6</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>65.0</td>
      <td>0</td>
      <td>146</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td>162000.00</td>
      <td>1.3</td>
      <td>129</td>
      <td>1</td>
      <td>1</td>
      <td>7</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>50.0</td>
      <td>1</td>
      <td>111</td>
      <td>0</td>
      <td>20</td>
      <td>0</td>
      <td>210000.00</td>
      <td>1.9</td>
      <td>137</td>
      <td>1</td>
      <td>0</td>
      <td>7</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>65.0</td>
      <td>1</td>
      <td>160</td>
      <td>1</td>
      <td>20</td>
      <td>0</td>
      <td>327000.00</td>
      <td>2.7</td>
      <td>116</td>
      <td>0</td>
      <td>0</td>
      <td>8</td>
      <td>1</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>293</th>
      <td>63.0</td>
      <td>1</td>
      <td>103</td>
      <td>1</td>
      <td>35</td>
      <td>0</td>
      <td>179000.00</td>
      <td>0.9</td>
      <td>136</td>
      <td>1</td>
      <td>1</td>
      <td>270</td>
      <td>0</td>
    </tr>
    <tr>
      <th>294</th>
      <td>62.0</td>
      <td>0</td>
      <td>61</td>
      <td>1</td>
      <td>38</td>
      <td>1</td>
      <td>155000.00</td>
      <td>1.1</td>
      <td>143</td>
      <td>1</td>
      <td>1</td>
      <td>270</td>
      <td>0</td>
    </tr>
    <tr>
      <th>295</th>
      <td>55.0</td>
      <td>0</td>
      <td>1820</td>
      <td>0</td>
      <td>38</td>
      <td>0</td>
      <td>270000.00</td>
      <td>1.2</td>
      <td>139</td>
      <td>0</td>
      <td>0</td>
      <td>271</td>
      <td>0</td>
    </tr>
    <tr>
      <th>297</th>
      <td>45.0</td>
      <td>0</td>
      <td>2413</td>
      <td>0</td>
      <td>38</td>
      <td>0</td>
      <td>140000.00</td>
      <td>1.4</td>
      <td>140</td>
      <td>1</td>
      <td>1</td>
      <td>280</td>
      <td>0</td>
    </tr>
    <tr>
      <th>298</th>
      <td>50.0</td>
      <td>0</td>
      <td>196</td>
      <td>0</td>
      <td>45</td>
      <td>0</td>
      <td>395000.00</td>
      <td>1.6</td>
      <td>136</td>
      <td>1</td>
      <td>1</td>
      <td>285</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>263 rows × 13 columns</p>





```python
df_ab= df[conditions[0]]
```


```python
# Levels Dictionary
levels = {'CPK': df_ab['creatinine_phosphokinase'], 'Platelets': df_ab['platelets'], 'Creatinine': df_ab['serum_creatinine'], 'Sodium': df_ab['serum_sodium']}
```


```python
# Exploratory Plots of Levels
fig= plt.figure(figsize=[8,18])

subplot_counter= 1
for l in levels:
    ax = fig.add_subplot(len(levels), 1, subplot_counter)
    ax.hist(levels[l], bins=34,edgecolor='black', linewidth=1.2, align= 'mid')
    plt.ylabel('Number of Patients')
    plt.title(l) 
    plt.tight_layout()
   
    subplot_counter += 1
```




![png](heart_failure_17_0.png)


