# 🚀 Exciting Data Analysis Journey on Stack Overflow! 🚀

Did you know that the oldest programming language still in use today is FORTRAN, dating back to 1957? Time has witnessed the birth of many programming languages, but which one reigns supreme in the programming world, capturing everyone's attention like Kim Kardashian in the celebrity world?

Let's embark on a data-driven quest to find out! 📊

**Step 1: Loading the Data**

```python
import pandas as pd

# Load data with column names
df = pd.read_csv('QueryResults.csv', names=['DATE', 'TAG', 'POSTS'], header=0)

# Verify data with first and last 5 rows
df.head()
df.tail()
```

**Step 2: Exploring the Data**

```python
# Check dimensions of the DataFrame
df.shape

# Count non-NaN entries in each column
df.count()
```

**Step 3: Unveiling the Most Popular Language**

```python
# Group by programming language and sum the number of posts
df.groupby("TAG").sum()

# Count entries in each column per programming language
df.groupby("TAG").count()
```

**Step 4: Data Type Inspection and Transformation**

```python
# Check data type of 'DATE' column
type(df["DATE"][1])

# Convert 'DATE' column to datetime format
df.DATE = pd.to_datetime(df.DATE)
df.head()
```

**Step 5: Data Manipulation - Pivoting DataFrames**

```python
# Pivot the DataFrame
pivoted_df = df.pivot(index='DATE', columns='TAG', values='POSTS')

# Fill NaN values with 0
pivoted_df = pivoted_df.fillna(0)
```

**Step 6: Data Visualization with Matplotlib**

```python
import matplotlib.pyplot as plt

# Create a line chart for Java
plt.figure(figsize=(16, 10))
plt.plot(pivoted_df.index, pivoted_df['java'])

# Style the chart
plt.xticks(fontsize=14)
plt.yticks(fontsize=14)
plt.xlabel('Date', fontsize=14)
plt.ylabel('Number of Posts', fontsize=14)
plt.ylim(0, 35000)
```

**Step 7: Multi-Line Charts for Popular Languages**

```python
# Plot multiple programming languages on the same chart
plt.figure(figsize=(16, 10))

for column in pivoted_df.columns:
    plt.plot(pivoted_df.index, pivoted_df[column], linewidth=3, label=column)

# Add legend
plt.legend(fontsize=16)
```

**Step 8: Smoothing out Time-Series Data**

```python
# Create a rolling mean for a smoother chart
roll_df = pivoted_df.rolling(window=6).mean()

# Plot the smoothed data
plt.figure(figsize=(16, 10))

for column in roll_df.columns:
    plt.plot(roll_df.index, roll_df[column], linewidth=3, label=column)

# Add legend
plt.legend(fontsize=16)
```

Get ready for a visual feast of programming languages! 🌐📈 Share your thoughts on which language stands out in the data jungle. Stay tuned for more insights and analysis in the upcoming GitHub post! 🚀🔍 #ProgrammingLanguages #DataAnalysis #StackOverflowInsights #TechTrends
