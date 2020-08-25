## Creating a new data frame to showcase means

This sample shows the code used to create a new data frame that shows the mean age and gray matter volume of the age categories. This code builds off previous code that was used to group participants together into age categories and find the mean values within those categories. This data frame was created to allow for the comparison of the gray matter volume means to the linear regression done at the beginning of this project to confirm the relationship that was seen in the data. 


```python
#mean age list
age_mean_list = [ag_mean_min24['age'], ag_mean_2534['age'], ag_mean_3544['age'], ag_mean_4554['age'], ag_mean_5564['age'], ag_mean_6574['age'], ag_mean_7584['age'], ag_mean_8594['age'], ag_mean_95max['age']]

#mean grey matter volume
gm_mean_list = [ag_mean_min24['gray_matter_vol'], ag_mean_2534['gray_matter_vol'], ag_mean_3544['gray_matter_vol'], ag_mean_4554['gray_matter_vol'], ag_mean_5564['gray_matter_vol'], ag_mean_6574['gray_matter_vol'], ag_mean_7584['gray_matter_vol'], ag_mean_8594['gray_matter_vol'], ag_mean_95max['gray_matter_vol']]

```


```python
data = {'Age': ['=< 24', '25-34', '35-44', '45-54', '55-64', '65-74', '75-84', '85-94', '95 =<' ],
       'Mean Age': age_mean_list,
       'Mean Gray Matter Volume':gm_mean_list}

df_ag_mean= pd.DataFrame(data)
```


```python
df_ag_mean
```





<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Mean Age</th>
      <th>Mean Gray Matter Volume</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>=&lt; 24</td>
      <td>21.066667</td>
      <td>641.716458</td>
    </tr>
    <tr>
      <th>1</th>
      <td>25-34</td>
      <td>27.893617</td>
      <td>603.565191</td>
    </tr>
    <tr>
      <th>2</th>
      <td>35-44</td>
      <td>40.600000</td>
      <td>575.753533</td>
    </tr>
    <tr>
      <th>3</th>
      <td>45-54</td>
      <td>49.315789</td>
      <td>542.800289</td>
    </tr>
    <tr>
      <th>4</th>
      <td>55-64</td>
      <td>59.548387</td>
      <td>526.929806</td>
    </tr>
    <tr>
      <th>5</th>
      <td>65-74</td>
      <td>70.480000</td>
      <td>498.318000</td>
    </tr>
    <tr>
      <th>6</th>
      <td>75-84</td>
      <td>79.582090</td>
      <td>493.017164</td>
    </tr>
    <tr>
      <th>7</th>
      <td>85-94</td>
      <td>88.741935</td>
      <td>465.930000</td>
    </tr>
    <tr>
      <th>8</th>
      <td>95 =&lt;</td>
      <td>96.000000</td>
      <td>476.571000</td>
    </tr>
  </tbody>
</table>



