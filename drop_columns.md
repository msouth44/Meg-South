```python
# Remove the columns
papers= papers.drop(columns= ['id','event_type','pdf_name'])

# Print out the first rows of papers
papers.head()
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
      <th>title</th>
      <th>abstract</th>
      <th>paper_text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1987</td>
      <td>Self-Organization of Associative Database and ...</td>
      <td>Abstract Missing</td>
      <td>767\n\nSELF-ORGANIZATION OF ASSOCIATIVE DATABA...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1987</td>
      <td>A Mean Field Theory of Layer IV of Visual Cort...</td>
      <td>Abstract Missing</td>
      <td>683\n\nA MEAN FIELD THEORY OF LAYER IV OF VISU...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1988</td>
      <td>Storing Covariance by the Associative Long-Ter...</td>
      <td>Abstract Missing</td>
      <td>394\n\nSTORING COVARIANCE BY THE ASSOCIATIVE\n...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1994</td>
      <td>Bayesian Query Construction for Neural Network...</td>
      <td>Abstract Missing</td>
      <td>Bayesian Query Construction for Neural\nNetwor...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1994</td>
      <td>Neural Network Ensembles, Cross Validation, an...</td>
      <td>Abstract Missing</td>
      <td>Neural Network Ensembles, Cross\nValidation, a...</td>
    </tr>
  </tbody>
</table>
</div>


