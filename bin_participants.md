## Grouping participants into age categories and finding the means

This sample shows the code that groups participants together into age categories. Each category spans 10 years. These categories were based off previous code that was used to find the oldest and youngest participants so appropriate categories could be created that would span the full range of participant age.


```python
# participants min-24
df_age_grey[df_age_grey['age'] <= 24]

#mean
ag_mean_min24= df_age_grey[df_age_grey['age'] <= 24].mean()
```


```python
# participants 25-34
df_age_grey[(df_age_grey['age'] >= 25) & (df_age_grey['age'] <= 34)]

#mean
ag_mean_2534= df_age_grey[(df_age_grey['age'] >= 25) & (df_age_grey['age'] <= 34)].mean()
```


```python
# participants 35-44
df_age_grey[(df_age_grey['age'] >= 35) & (df_age_grey['age'] <= 44)]

#mean
ag_mean_3544= df_age_grey[(df_age_grey['age'] >= 35) & (df_age_grey['age'] <= 44)].mean()
```


```python
# participants 45-54
df_age_grey[(df_age_grey['age'] >= 45) & (df_age_grey['age'] <= 54)]

#mean
ag_mean_4554= df_age_grey[(df_age_grey['age'] >= 45) & (df_age_grey['age'] <= 54)].mean()
```


```python
# particpants 55-64
df_age_grey[(df_age_grey['age'] >= 55) & (df_age_grey['age'] <= 64)]

#mean
ag_mean_5564= df_age_grey[(df_age_grey['age'] >= 55) & (df_age_grey['age'] <= 64)].mean()
```


```python
# particpants 65-74
df_age_grey[(df_age_grey['age'] >= 65) & (df_age_grey['age'] <= 74)]

#mean
ag_mean_6574= df_age_grey[(df_age_grey['age'] >= 65) & (df_age_grey['age'] <= 74)].mean()
```


```python
# particpants 75-84
df_age_grey[(df_age_grey['age'] >= 75) & (df_age_grey['age'] <= 84)]

#mean
ag_mean_7584= df_age_grey[(df_age_grey['age'] >= 75) & (df_age_grey['age'] <= 84)].mean()
```


```python
# particpants 85-94
df_age_grey[(df_age_grey['age'] >= 85) & (df_age_grey['age'] <= 94)]

#mean
ag_mean_8594= df_age_grey[(df_age_grey['age'] >= 85) & (df_age_grey['age'] <= 94)].mean()
```


```python
# particpants 95-max
df_age_grey[(df_age_grey['age'] >= 95)]

#mean
ag_mean_95max= df_age_grey[(df_age_grey['age'] >= 95)].mean()
```
