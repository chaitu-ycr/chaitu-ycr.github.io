# 🐼 Pandas Cheat Sheet

## 📦 What is Pandas?
Pandas is a Python library for fast, flexible, and expressive data analysis and manipulation. It makes working with structured data (like tables or spreadsheets) easy and efficient.

---

## 🚩 Key Features & Use Cases

### 🗂️ Data Structures
- **Series**: 1D labeled array.
    ```python
    import pandas as pd
    s = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
    print(s)
    ```
- **DataFrame**: 2D labeled table.
    ```python
    data = {'Name': ['Alice', 'Bob'], 'Age': [25, 30]}
    df = pd.DataFrame(data)
    print(df)
    ```

---

### 🔍 Indexing & Selection
Access data by labels, positions, or conditions.
```python
print(df.loc[0])           # By label
print(df.iloc[1])          # By position
print(df[df['Age'] > 25])  # By condition
```

---

### 🧹 Data Cleaning
Handle missing or inconsistent data.
```python
df['Age'] = df['Age'].fillna(df['Age'].mean())  # Fill missing with mean
df = df.dropna()                                # Drop rows with missing
```

---

### 🔄 Data Manipulation
Reshape or aggregate data.
```python
grouped = df.groupby('Name').sum()
print(grouped)
```

---

### 🔢 Sorting & Ranking
Sort data by column values.
```python
sorted_df = df.sort_values(by='Age', ascending=False)
print(sorted_df)
```

---

### ➕ Calculations & Aggregations
Compute stats on columns or groups.
```python
print(df['Age'].mean())  # Mean
print(df['Age'].sum())   # Sum
```

---

### 🔗 Merging & Joining
Combine multiple DataFrames.
```python
df1 = pd.DataFrame({'ID': [1, 2], 'Name': ['Alice', 'Bob']})
df2 = pd.DataFrame({'ID': [1, 2], 'Score': [90, 80]})
merged = pd.merge(df1, df2, on='ID')
print(merged)
```

---

### 📊 Data Visualization
Quick plots with Matplotlib.
```python
import matplotlib.pyplot as plt
df['Age'].plot(kind='bar')
plt.show()
```

---

### 🕒 Time Series Handling
Work with dates and times.
```python
date_range = pd.date_range(start='2023-01-01', periods=5, freq='D')
print(date_range)
```

---

### 🏢 Hierarchical Data (MultiIndex)
Handle complex, multi-level data.
```python
arrays = [['A', 'A', 'B'], [1, 2, 1]]
index = pd.MultiIndex.from_arrays(arrays, names=('Group', 'Number'))
df = pd.DataFrame({'Value': [10, 20, 30]}, index=index)
print(df)
```

---

### ⚡ Performance Optimization
Use vectorized operations for speed.
```python
df['Age'] = df['Age'] * 2
```

---

## 🛠️ Installation
```bash
pip install pandas
```

---

## 📝 Practice Questions

1. **Create & Manipulate DataFrame**
   - Make a DataFrame with `Name`, `Age`, `City` (5 rows).
   - Select rows where `Age > 25`.
   - Sort by `City`.
   - Fill missing `Age` with average.
2. **Merge DataFrames**
   - Merge one DataFrame with `Employee ID`, `Name` and another with `Employee ID`, `Salary`.
3. **Time Series**
   - Create a DataFrame with daily dates for a week and a column of random numbers. Find the average.
4. **Group & Aggregate**
   - Group a DataFrame by a column and calculate the sum for each group.
