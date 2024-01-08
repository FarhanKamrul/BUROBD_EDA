# EDA on 'BU_trained Data.xlsx'

## Dataframe information

| #   | Column            | Non-Null Count | Dtype    |
| --- | ------------------ | -------------- | -------- |
| 0   | BranchCode         | 5363 non-null  | int64    |
| 1   | LoaneeNo           | 5363 non-null  | int64    |
| 2   | ItemCode           | 5363 non-null  | float64  |
| 3   | LoanTerm           | 5363 non-null  | int64    |
| 4   | Gender             | 5363 non-null  | object   |
| 5   | HomeType           | 5363 non-null  | object   |
| 6   | FamilyMember       | 5363 non-null  | int64    |
| 7   | TotalWealth        | 5363 non-null  | int64    |
| 8   | Self_Employed      | 5363 non-null  | object   |
| 9   | PrincipalLoan      | 5363 non-null  | int64    |
| 10  | PaymentFrequency   | 5363 non-null  | object   |
| 11  | PurposeCode        | 5363 non-null  | float64  |
| 12  | DueAmount          | 5363 non-null  | int64    |
| 13  | DueDays            | 5363 non-null  | int64    |
| 14  | SavingsBalance     | 5363 non-null  | int64    |
| 15  | DFS_Status         | 5363 non-null  | object   |
| 16  | DueType            | 5363 non-null  | object   |

Apologies for the confusion earlier. Here's how you can perform the steps on your actual dataset:

1. **Create a dataframe from the sample data**:

```python
import pandas as pd

data = 'BU_trained Data.xlsx'

df = pd.DataFrame(data)
```

2. **Basic data exploration**:

```python
# Print the first 5 rows of the dataframe
print(df.head())

# Print the summary statistics
print(df.describe())

# Print the information about the dataframe
print(df.info())
```

3. **Visualize the data**:

```python
import matplotlib.pyplot as plt

# For numerical columns, you can use histograms or boxplots
df['TotalWealth'].hist()
plt.show()

# For categorical columns, you can use bar plots
df['Gender'].value_counts().plot(kind='bar')
plt.show()
```

4. **Formulate and test hypotheses**:

Formulating a hypothesis depends on the questions you're interested in answering with your data. Once you have a hypothesis, you can test it statistically. For example, if you want to know if the mean of a numerical column is significantly different from zero, you can use a t-test.

```python
from scipy import stats

t_statistic, p_value = stats.ttest_1samp(df['TotalWealth'], 0)
print(f'T statistic: {t_statistic}')
print(f'P value: {p_value}')
```
