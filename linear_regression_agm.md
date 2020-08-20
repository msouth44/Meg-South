## Linear regression of age and gray matter volume to explore relationship

This sample shows how linear regression was used to gain an initial idea of the relationship between the data gathered about age and gray matter volume. The code below is built off of previous code where NumPy arrays were created from a dataset that only included the age and gray matter volume column from the original dataset. 


```python
# linear regression: age and gray matter volume
plt.plot(np_age, np_gmv, 'o')

m, b = np.polyfit(np_age, np_gmv, 1)

plt.plot(np_age, m*np_age + b)

plt.xlabel('Age')
plt.ylabel('Gray Matter Volume')
```




    






![png](linear_regression_agm_2_1.png)


