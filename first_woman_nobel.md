```python
# Picking out the first woman to win a Nobel Prize
nobel[nobel.sex == 'Female'].nsmallest(1,'year')
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
      <th>year</th>
      <th>category</th>
      <th>prize</th>
      <th>motivation</th>
      <th>prize_share</th>
      <th>laureate_id</th>
      <th>laureate_type</th>
      <th>full_name</th>
      <th>birth_date</th>
      <th>birth_city</th>
      <th>...</th>
      <th>sex</th>
      <th>organization_name</th>
      <th>organization_city</th>
      <th>organization_country</th>
      <th>death_date</th>
      <th>death_city</th>
      <th>death_country</th>
      <th>usa_born_winner</th>
      <th>decade</th>
      <th>female_winner</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>19</th>
      <td>1903</td>
      <td>Physics</td>
      <td>The Nobel Prize in Physics 1903</td>
      <td>"in recognition of the extraordinary services ...</td>
      <td>1/4</td>
      <td>6</td>
      <td>Individual</td>
      <td>Marie Curie, née Sklodowska</td>
      <td>1867-11-07</td>
      <td>Warsaw</td>
      <td>...</td>
      <td>Female</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1934-07-04</td>
      <td>Sallanches</td>
      <td>France</td>
      <td>False</td>
      <td>1900</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 21 columns</p>
</div>


