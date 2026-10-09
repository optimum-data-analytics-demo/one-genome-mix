# Getting Started with pandas

pandas is a fast, powerful, flexible, and easy-to-use open-source data analysis and manipulation tool built on top of the Python programming language.

## Installation

Install pandas using pip or conda:

```bash
pip install pandas
# OR
conda install pandas
```

## Basic Usage

### 1. Import pandas

```python
import pandas as pd
import numpy as np
```

### 2. Core Data Structures

pandas has two primary components: the **Series** (a 1D array) and the **DataFrame** (a 2D table).

```python
# Creating a Series
s = pd.Series([1, 3, 5, np.nan, 6, 8])

# Creating a DataFrame using a dictionary
df = pd.DataFrame({
    "A": 1.0,
    "B": pd.Timestamp("20261009"),
    "C": pd.Series(1, index=list(range(4)), dtype="float32"),
    "D": np.array([3] * 4, dtype="int32"),
    "E": pd.Categorical(["test", "train", "test", "train"]),
    "F": "foo"
})
```

### 3. Viewing Data

```python
# View the top rows
df.head()

# View the bottom rows
df.tail(3)

# Get a quick statistic summary of your data
df.describe()

# Transpose your data
df.T

# Sort by an axis
df.sort_index(axis=1, ascending=False)

# Sort by values
df.sort_values(by="B")
```

### 4. Selection & Filtering

```python
# Selecting a single column (yields a Series)
df["A"]

# Selecting via fractional rows (slicing)
df[0:3]

# Selection by label
df.loc[:, ["A", "B"]]

# Selection by position
df.iloc[3]
df.iloc[3:5, 0:2]

# Boolean indexing (Filtering)
df[df["A"] > 0]
```

### 5. Operations & Missing Data

```py
# Calculate descriptive statistics
df.mean()

# Drop rows with missing data
df.dropna(how="any")

# Fill missing data
df.fillna(value=5)
```

### 6. File I/O

```py
# Write to a CSV file
df.to_csv("foo.csv")

# Read from a CSV file
pd.read_csv("foo.csv")
```
