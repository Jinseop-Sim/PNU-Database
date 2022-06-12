# Hypothesis Test
---
## One Sample T-test
- Take Data
```python
import pandas as pd
data = pd.read_csv("https://raw.githubusercontent.com/inetguru/IDS-CB35533/main/students.csv")
data.head()

# Data from http://github.com/integuru, PNU professor Jong duck Kim
# Class from PNU Data Science, by Professor Myeon ho Lee
```

- T-test
```python
import scipy.stats as stats # Need Scipy 1.7.3!

# Null Hypothesis : IQ's Mean == 120
# Alternative : IQ's Mean != 120

null_Hypo_Mean = 120 
sample = data['IQ']

result = stats.ttest_1samp(sample, null_Hypo_Mean)
print("T-statistic : ", result.statistic, "P-value : ", result.pvalue) # Two-sided Test

result_one = stats.ttest_1samp(sample, null_Hypo_Mean, alternative = 'less') # One-Sided Test
print("T-statistic : ", result_one.statistic, "P-value : ", result_one.pvalue) # result.pvalue/2 == result_one.pvalue
```

## Two Sample T-test
```python
import scipy.stats as stats # Need Scipy 1.7.3!

# Null Hypothesis : Male's SCORE1's Mean == Female's SCORE1's Mean
# Alternative : Male's SCORE1's Mean != Female's SCORE1's Mean

val_male = data['SCORE1'][data['Gender'] == 'Male']
val_female = data['SCORE1'][data['Gender'] == 'Female']

stats.ttest_ind(val_male, val_female)
stats.ttest_ind(val_male, val_female, equal_var = False) # Not equal Variance ==> Welch's Ttest
```

## One Table Chi-square Test
```python
import numpy as np

# Null Hypothesis : Employees are absent equally during the week
# Alternative : Employees are absent some day on weeks more than others

val_ob = np.array([15, 12, 9, 9, 15]) # Observed Data
val_ex = np.array([12, 12, 12, 12, 12]) # Expected Data

stats.chisquare(val_ob, val_ex)
```

## Two Table Chi-square Test
```python
# Null Hypothesis : The amount of Reading is independent of Gender
# Alternative : The amount of Reading is dependent of Gender

cross = pd.crosstab(data['Gender'], data['Reading']) # Use crosstable to calculate Expected Value
print(cross)

val_ob = np.array([6, 10, 11, 9, 7, 5, 9, 4, 7, 8, 5, 8, 5, 6]) # Observed Data
val_ex = np.array([8, 8, 10, 10, 6, 6, 6.5, 6.5, 7.5, 7.5, 6.5, 6.5, 5.5, 5.5]) # Expected Data, # of Male == # of Female

stats.chisquare(val_ob, val_ex, ddof = 7) # Delta Degree of Freedom = i + j - 2 (Using for 2-table Chi-square)
```  
![image](https://user-images.githubusercontent.com/71700079/173227043-c22ae0a2-2b61-4e06-8f84-649334a75d91.png)
