```python
# put your plotting code here
ax.hist(df['rt'])

# Don't modify the code below here
# Add a solid line at the median and dashed lines at the 25th and 75th 
# percentiles (done for you)
plt.axvline(df['rt'].describe()['25%'], 0, 1, color='turquoise', linestyle='--')
plt.axvline(df['rt'].median(), 0, 1, color='cyan', linestyle='-')
plt.axvline(df['rt'].describe()['75%'], 0, 1, color='turquoise', linestyle='--')

# Rememebr to use plt.show() to see your plots (often they show anyway, but with some garbagy text at the top)
plt.show()
```




![png](Histogram%20Example_files/Histogram%20Example_0_0.png)


