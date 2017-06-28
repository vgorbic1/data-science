## Thompson Sampling with Python

Use this [sample dataset](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/Sample%20Data/Ads_CTR_Optimisation.csv)

1. Importing the libraries
2. Importing the dataset
3. Implementing Random Selection
4. Visualising the results

```python
# Random Selection

# Importing the libraries
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

# Importing the dataset
dataset = pd.read_csv('Ads_CTR_Optimisation.csv')

# Implementing Random Selection
import random
N = 10000
d = 10
ads_selected = []
total_reward = 0
for n in range(0, N):
    ad = random.randrange(d)
    ads_selected.append(ad)
    reward = dataset.values[n, ad]
    total_reward = total_reward + reward

# Visualising the results
plt.hist(ads_selected)
plt.title('Histogram of ads selections')
plt.xlabel('Ads')
plt.ylabel('Number of times each ad was selected')
plt.show()
```
