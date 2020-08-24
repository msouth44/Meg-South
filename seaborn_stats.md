# Descriptive Statistics and Histogram

This sample of code showcases the use of the Seaborn count function to get inital insight into the ejection fraction data. The Seaborn plot shows that the data looks not quite normal which lead to the use of descriptive stats and a histogram to look further into the distribution of the data. After further inspection, you can see that the data is skewed, showing majority of patients have abnormal ejection fractions (below 55).


```python
sns.countplot(x="ejection_fraction",data= df)
plt.show()
```




![png](seaborn_stats_files/seaborn_stats_1_0.png)




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




![png](seaborn_stats_files/seaborn_stats_3_0.png)


