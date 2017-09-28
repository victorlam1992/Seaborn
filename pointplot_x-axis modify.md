# Set the x-axis to specific interval

Seaborn pointplot is a categorical plot.
This means that the different categories are simply placed one by one along the x axis.

The idea would therefore be to change the locator as well as the formatter for the xticks.


```python
import seaborn.apionly as sns
import matplotlib.pyplot as plt
import matplotlib.ticker as ticker
import numpy as np; np.random.seed(1)

x = np.random.randint(0,20,size=(100))
y = np.random.rand(100)

ax = sns.pointplot(x,y )
ax.xaxis.set_major_locator(ticker.MultipleLocator(5))
ax.xaxis.set_major_formatter(ticker.ScalarFormatter())

plt.show()
```

By using set_major_locator and formatter, it will load the x-axis categories, and then decide how many data points for 
generating one category

- e.g. The x-axis is from 2017-01-01 to 2017-01-31
  - 30 data points
  - x-axis will show interval with 5
