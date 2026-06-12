---
title: 'Day 2 morning - Programming in Python: Introduction, Variables, and DataFrames'
layout: home
nav_order: 3
---

# Plotting and Programming in Python: Introduction, Variables, and DataFrames

**Based on:** Software Carpentry, *Plotting and Programming in Python*, Gapminder instructor materials: <https://swcarpentry.github.io/python-novice-gapminder/instructor/index.html>

**Notebook format:** Markdown notebook with explanatory text and Python code blocks. You can paste sections into a Jupyter Notebook, or use this as a teaching handout.

---

## Learning goals

By the end of this notebook, learners should be able to:

1. Explain what JupyterLab and Jupyter Notebooks are used for.
2. Create and run code cells and Markdown cells.
3. Store values in Python variables and use those variables in calculations.
4. Display output with `print()`.
5. Understand common variable-related errors, especially `NameError`.
6. Use string indexing and slicing.
7. Import the Pandas library.
8. Read Gapminder CSV files into Pandas DataFrames.
9. Inspect DataFrame structure with `.info()`, `.columns`, `.T`, and `.describe()`.
10. Select rows, columns, and individual values using `.loc` and `.iloc`.
11. Filter tabular data using Boolean conditions.

---

## Required setup

The Carpentries lesson assumes that learners have Python 3 installed and have downloaded the Gapminder lesson data. The expected folder structure is:

```text
project-folder/
├── data/
│   ├── gapminder_gdp_oceania.csv
│   ├── gapminder_gdp_europe.csv
│   ├── gapminder_gdp_americas.csv
│   └── gapminder_all.csv
└── notebook.ipynb
```

In a Jupyter Notebook, your notebook should be started from the same top-level folder that contains the `data/` directory. That is why examples use paths such as:

```python
'data/gapminder_gdp_oceania.csv'
```

---

# Part 1 — Introduction to JupyterLite (Again), JupyterLab and Notebooks

## 1.1 The Difference between JupyterLite and JupyterLab

JupyterLite and JuypterLab are two different tools that we'll be using throughout this workshop.

JupyterLab is the notebook workspace where we will write and run Python code. It lets us open notebooks, write notes, run code cells, view results, and work with data files all in one place.

JupyterLite is a browser-based version of Jupyter that lets us use JupyterLab without installing anything on our computer. Instead of setting up Python and Jupyter locally, we can open a link in a web browser and start working right away.

In this workshop, we will be using JupyterLab notebooks through JupyterLite. That means the notebook interface will look like JupyterLab, but it will run directly in the browser using JupyterLite.

## 1.2 What is JupyterLab?

JupyterLab is an interactive environment for writing, running, and documenting code. It lets you combine:

- Python code
- output from that code
- tables
- plots
- explanatory text
- Markdown notes

This makes it especially useful for data analysis, because you can keep the code, results, and interpretation together in one document.

A Jupyter Notebook is made of **cells**. The two main cell types are:

| Cell type | Purpose |
|---|---|
| Code cell | Runs Python code |
| Markdown cell | Stores formatted notes, headings, lists, links, and explanations |

## 1.3 Starting JupyterLab

From a terminal or Anaconda Prompt, start JupyterLab with:

```bash
jupyter lab
```

This launches a local server and opens JupyterLab in your web browser. The browser is the interface, but the Python code runs through the Jupyter server and kernel.

## 1.4 Creating a new notebook

In JupyterLab:

1. Open the Launcher.
2. Under **Notebook**, select **Python 3**.
3. Rename the notebook to something descriptive, such as:

```text
gapminder_intro_variables_dataframes.ipynb
```

## 1.5 Command mode vs. Edit mode

Jupyter notebooks have two important modes:

| Mode | How to enter | What it does |
|---|---|---|
| Command mode | Press `Esc` | Lets you manage cells |
| Edit mode | Press `Enter`/`Return` | Lets you type inside a cell |

Useful shortcuts in Command mode:

| Shortcut | Action |
|---|---|
| `a` | Add a cell above |
| `b` | Add a cell below |
| `x` | Delete selected cell |
| `z` | Undo last cell action |
| `m` | Convert cell to Markdown |
| `y` | Convert cell to Code |
| `Shift` + `Enter` | Run selected cell |

## 1.6 Markdown basics

Markdown is a lightweight way to format text. Try putting the following into a Markdown cell:

```markdown
# My Gapminder Notebook

## Goals

- Learn basic Python syntax
- Store values in variables
- Read tabular data with Pandas
- Select rows and columns from a DataFrame

[Software Carpentry](https://software-carpentry.org)
```

When you run the Markdown cell, Jupyter renders it as formatted text.

### Practice: Markdown cell

Create a Markdown cell with:

1. A level-1 heading with the title of your notebook.
2. A short paragraph describing what Gapminder data contains.
3. A bullet list of three things you want to learn.

---

# Part 2 — Variables and Assignment

## 2.1 What is a variable?

A **variable** is a name that stores a value. In Python, the assignment operator `=` assigns the value on the right to the variable name on the left.

```python
age = 42
first_name = 'Ahmed'
```

Here:

- `age` stores the integer value `42`
- `first_name` stores the string value `'Ahmed'`

The variable is created at the moment you assign a value to it.

## 2.2 Variable naming rules

Python variable names:

- can contain letters, numbers, and underscores
- cannot start with a number
- are case-sensitive
- should be meaningful

Valid examples:

```python
age = 42
first_name = 'Ahmed'
gdp_per_capita = 10039.59
sample_count = 12
```

Invalid or poor examples:

```python
# Invalid: starts with a number
# 1st_name = 'Ahmed'

# Valid, but not descriptive
x = 42

# Valid, but confusing because capitalization matters. These are two different variables. 
Age = 42
age = 43
```

## 2.3 Displaying values with `print()`

The `print()` function displays values as text.

```python
age = 42
first_name = 'Ahmed'

print(first_name, 'is', age, 'years old')
```

Expected output:

```text
Ahmed is 42 years old
```

`print()` automatically adds spaces between comma-separated items and moves to a new line at the end.

## 2.4 Variables must exist before use

If you try to use a variable before assigning it, Python raises a `NameError`.

```python
print(last_name)
```

Expected error:

```text
NameError: name 'last_name' is not defined
```

This often means one of two things:

1. The variable was never created.
2. The variable name was misspelled.

### Important Jupyter note: execution order matters

In a notebook, Python remembers cells that have already been run. The order in which cells are **executed** matters more than the order in which they appear.

For example, this cell will fail if run first:

```python
print(myval)
```

But this cell creates the variable:

```python
myval = 1
```

If you run the assignment cell first and then run `print(myval)`, it works. To check that a notebook runs cleanly from top to bottom, use:

```text
Kernel → Restart Kernel and Run All Cells
```

## 2.5 Updating variables

Variables can be used in calculations.

```python
age = 42
age = age + 3
print('Age in three years:', age)
```

Expected output:

```text
Age in three years: 45
```

This line:

```python
age = age + 3
```

means: take the current value of `age`, add `3`, and assign the result back to `age`.

## 2.6 Tracing variable changes

Trace the values step by step:

```python
x = 1.0
y = 3.0
swap = x
x = y
y = swap

print('x:', x)
print('y:', y)
print('swap:', swap)
```

Expected output:

```text
x: 3.0
y: 1.0
swap: 1.0
```

This uses `swap` as temporary storage so that the values of `x` and `y` can be exchanged.

## 2.7 Strings, indexing, and slicing

A **string** is text stored in quotes.

```python
atom_name = 'carbon'
```

You can access characters by position using an **index**. Python counts from zero.

```python
atom_name = 'carbon'
print(atom_name[0])
print(atom_name[1])
print(atom_name[2])
```

Expected output:

```text
c
a
r
```

You can access part of a string using a **slice**:

```python
atom_name = 'carbon'
print(atom_name[1:3])
```

Expected output:

```text
ar
```

The slice `[1:3]` starts at index `1` and stops before index `3`.

## 2.8 String length with `len()`

Use `len()` to count the number of characters in a string.

```python
atom_name = 'carbon'
print(len(atom_name))
```

Expected output:

```text
6
```

## 2.9 Practice: variables

### Exercise 1 — Create and print variables

Create variables for:

- your first name
- your favorite organism
- the number of samples in a small dataset

Then print a sentence using all three variables.

```python
# Write your code here
```

### Exercise 2 — Predict before running

What will this print?

```python
initial = 'left'
position = initial
initial = 'right'
print(position)
```

Write your prediction here:

```text
Prediction:
```

### Exercise 3 — Slicing

Given this string:

```python
species_name = 'Acacia buxifolia'
```

Predict the result of each expression:

```python
species_name[2:8]
species_name[11:]
species_name[:4]
species_name[:]
species_name[11:-3]
species_name[-5:-3]
```

Then run the code to check your answers.

---

# Part 3 — Reading Tabular Data into Pandas DataFrames

## 3.1 What is Pandas?

Pandas is a Python library for working with tabular data. It is especially useful for CSV files, spreadsheets, and datasets where observations are arranged in rows and variables are arranged in columns.

The standard import is:

```python
import pandas as pd
```

The alias `pd` is a common convention that makes Pandas commands shorter to type.

## 3.2 What is a DataFrame?

A **DataFrame** is a two-dimensional table.

- Rows usually represent observations.
- Columns usually represent variables.
- Each column has a name.
- Different columns can contain different data types.

For Gapminder GDP data:

- each row is a country
- each column is GDP per capita for a particular year

## 3.3 Read a CSV file

Read the Oceania GDP data:

```python
import pandas as pd

# Read the CSV file into a DataFrame
data_oceania = pd.read_csv('data/gapminder_gdp_oceania.csv')

# Display the DataFrame
print(data_oceania)
```

This creates a DataFrame variable named `data_oceania`.

## 3.4 File paths and common errors

The path:

```python
data/gapminder_gdp_oceania.csv
```

means:

1. Start in the current working directory.
2. Go into the `data/` folder.
3. Open the file named `gapminder_gdp_oceania.csv`.

If the file path is wrong, you may see:

```text
FileNotFoundError: [Errno 2] No such file or directory
```

To debug this:

```python
import os
print(os.getcwd())
print(os.listdir())
print(os.listdir('data'))
```

## 3.5 Use `index_col` for row labels

By default, Pandas gives rows numeric labels: `0`, `1`, `2`, and so on. For Gapminder data, it is often more useful to use the `country` column as the row index.

```python
data_oceania_country = pd.read_csv(
    'data/gapminder_gdp_oceania.csv',
    index_col='country'
)

print(data_oceania_country)
```

Now the country names are row labels instead of regular values in a column.

## 3.6 Inspect a DataFrame with `.info()`

Use `.info()` to summarize the structure of a DataFrame.

```python
data_oceania_country.info()
```

This tells you:

- the object type
- the number of rows
- the number of columns
- the column names
- how many non-null values each column contains
- the data type of each column
- memory usage

## 3.7 Inspect column names with `.columns`

The `.columns` attribute stores the column labels.

```python
print(data_oceania_country.columns)
```

Notice that `.columns` does **not** use parentheses. It is an attribute, not a method.

Compare:

```python
# Attribute: no parentheses
print(data_oceania_country.columns)

# Method: uses parentheses
print(data_oceania_country.describe())
```

## 3.8 Transpose a DataFrame with `.T`

Transposing flips rows and columns.

```python
print(data_oceania_country.T)
```

This can be useful when years are currently stored as columns but you want to view them as rows.

## 3.9 Summary statistics with `.describe()`

Use `.describe()` to calculate summary statistics for numerical columns.

```python
data_oceania_country.describe()
```

This reports values such as:

- count
- mean
- standard deviation
- minimum
- quartiles
- maximum

## 3.10 Preview rows with `.head()` and `.tail()`

Read the Americas dataset:

```python
data_americas = pd.read_csv(
    'data/gapminder_gdp_americas.csv',
    index_col='country'
)
```

Show the first five rows:

```python
data_americas.head()
```

Show the first three rows:

```python
data_americas.head(n=3)
```

Show the last three rows:

```python
data_americas.tail(n=3)
```

## 3.11 Writing a DataFrame to a CSV file

Use `.to_csv()` to save a DataFrame.

```python
data_americas.to_csv('processed_americas.csv')
```

This writes the file to the directory where your notebook session is running.

## 3.12 Practice: reading data

### Exercise 4 — Read Europe data

Read the Europe Gapminder GDP data and use `country` as the row index.

```python
# Write your code here
```

### Exercise 5 — Inspect the DataFrame

Use commands to answer:

1. How many rows are in the Europe dataset?
2. How many columns are in the Europe dataset?
3. What are the column names?
4. What data type is stored in the GDP columns?

```python
# Write your code here
```

---

# Part 4 — Working with Pandas DataFrames

## 4.1 Load the Europe dataset

```python
import pandas as pd

data = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
```

Use `.head()` to confirm that the file loaded correctly:

```python
data.head()
```

## 4.2 Select by position with `.iloc`

Use `.iloc` when you want to select by integer position.

```python
print(data.iloc[0, 0])
```

This means:

- row position `0`
- column position `0`

Because Python uses zero-based indexing, this selects the first row and first column.

## 4.3 Select by label with `.loc`

Use `.loc` when you want to select by row and column labels.

```python
print(data.loc['Albania', 'gdpPercap_1952'])
```

This selects the value for Albania in 1952.

## 4.4 Select an entire row

Use `:` to mean “everything” along an axis.

```python
print(data.loc['Albania', :])
```

This selects all columns for Albania.

The shorter version also works:

```python
print(data.loc['Albania'])
```

## 4.5 Select an entire column

```python
print(data.loc[:, 'gdpPercap_1952'])
```

This selects all rows for the column `gdpPercap_1952`.

A common shortcut for selecting a single column is:

```python
print(data['gdpPercap_1952'])
```

## 4.6 Select ranges of rows and columns

Select rows from Italy through Poland and columns from 1962 through 1972:

```python
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']
print(subset)
```

Important distinction:

| Selection method | Slice behavior |
|---|---|
| `.iloc` | stop position is excluded |
| `.loc` | stop label is included |

For example:

```python
print(data.iloc[0:2, 0:2])
```

includes row positions `0` and `1`, and column positions `0` and `1`.

But:

```python
print(data.loc['Albania':'Belgium', 'gdpPercap_1952':'gdpPercap_1962'])
```

includes `Belgium` and `gdpPercap_1962` because `.loc` includes the ending labels.

## 4.7 Calculate statistics on a subset

Once you select a subset, you can analyze it.

```python
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']

print(subset.max())
print(subset.min())
print(subset.mean())
```

These calculations are applied column by column.

## 4.8 Use comparisons to create Boolean masks

A comparison such as `subset > 10000` is applied to every value in the DataFrame.

```python
subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']

print(subset > 10000)
```

This returns a DataFrame of `True` and `False` values.

## 4.9 Use a Boolean mask to filter values

You can use the Boolean DataFrame as a mask.

```python
high_gdp = subset[subset > 10000]
print(high_gdp)
```

Values that meet the condition are kept. Values that do not meet the condition become `NaN`, which means “Not a Number.” Many summary operations ignore `NaN` values.

```python
high_gdp.describe()
```

## 4.10 Filter rows using a column value

Load the combined Gapminder dataset:

```python
all_data = pd.read_csv('data/gapminder_all.csv', index_col='country')
```

Select only countries in the Americas:

```python
americas = all_data[all_data['continent'] == 'Americas']
americas.head()
```

Break the filtering expression into pieces:

```python
is_americas = all_data['continent'] == 'Americas'
print(is_americas.head())

americas = all_data[is_americas]
americas.head()
```

This is often easier for learners to understand because the Boolean condition is stored in a named variable.

## 4.11 Drop rows or columns

Drop a row by label:

```python
americas_without_puerto_rico = americas.drop('Puerto Rico')
```

Drop a column by label:

```python
americas_gdp_only = americas_without_puerto_rico.drop('continent', axis=1)
```

Use `axis=1` when dropping a column. Rows are the default axis.

## 4.12 Save results

```python
americas_gdp_only.to_csv('americas_gdp_only.csv')
```

## 4.13 Practice: DataFrame selection

### Exercise 6 — Individual value

Find the GDP per capita of Serbia in 2007.

```python
# Write your code here
```

### Exercise 7 — Column selection

Select GDP per capita for all European countries in 1982.

```python
# Write your code here
```

### Exercise 8 — Row selection

Select GDP per capita for Denmark for all years.

```python
# Write your code here
```

### Exercise 9 — Range selection

Select GDP per capita for all countries for years after 1985.

```python
# Write your code here
```

### Exercise 10 — Growth ratio

Calculate GDP per capita in 2007 divided by GDP per capita in 1952 for each European country.

```python
# Write your code here
```

### Exercise 11 — Boolean filtering

Create a subset of European countries where GDP per capita in 2007 is greater than 30,000.

```python
# Write your code here
```

---

# Part 5 — Suggested instructor flow

## 5.1 Timing

Suggested pacing for a short workshop segment:

| Section | Topic | Approx. time |
|---|---|---:|
| Part 1 | JupyterLab and notebooks | 15 min |
| Part 2 | Variables and assignment | 20 min |
| Part 3 | Reading CSV files into DataFrames | 20 min |
| Part 4 | Selecting and filtering DataFrames | 30 min |
| Practice | Exercises and discussion | 20–30 min |

## 5.2 Teaching notes

- Start by distinguishing **code cells** from **Markdown cells**.
- Emphasize that notebooks run in execution order, not visual order.
- Have learners predict outputs before running code.
- Use meaningful variable names from the start.
- When introducing DataFrames, connect rows and columns to familiar spreadsheets.
- Explain `.loc` as “label-based selection” and `.iloc` as “integer-position selection.”
- Pause on Boolean masks; many learners need extra time to understand that a condition can produce a table of `True`/`False` values.

## 5.3 Common learner errors

| Error | Likely cause | Fix |
|---|---|---|
| `NameError` | Variable was not created or was misspelled | Re-run assignment cell; check spelling |
| `FileNotFoundError` | Wrong path or notebook started in wrong folder | Check `os.getcwd()` and `os.listdir()` |
| `KeyError` | Row or column label does not exist | Check `data.index` or `data.columns` |
| Confusing `.loc` and `.iloc` | Mixing labels with positions | Use `.loc` for names; `.iloc` for numbers |
| Unexpected old value | Notebook cells run out of order | Restart kernel and run all cells |

---

# Part 6 — Answer key

## Exercise 1 example

```python
first_name = 'Cassie'
favorite_organism = 'Ralstonia solanacearum'
sample_count = 12

print(first_name, 'is analyzing', sample_count, 'samples of', favorite_organism)
```

## Exercise 2 answer

```python
initial = 'left'
position = initial
initial = 'right'
print(position)
```

Output:

```text
left
```

`position` keeps the value assigned to it. Changing `initial` later does not automatically update `position`.

## Exercise 3 answers

```python
species_name = 'Acacia buxifolia'

print(species_name[2:8])    # acia b
print(species_name[11:])    # folia
print(species_name[:4])     # Acac
print(species_name[:])      # Acacia buxifolia
print(species_name[11:-3])  # fo
print(species_name[-5:-3])  # fo
```

## Exercise 4 answer

```python
import pandas as pd

data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
data_europe.head()
```

## Exercise 5 answer

```python
data_europe.info()
print(data_europe.columns)
print(data_europe.shape)
print(data_europe.dtypes)
```

## Exercise 6 answer

```python
print(data_europe.loc['Serbia', 'gdpPercap_2007'])
```

## Exercise 7 answer

```python
data_europe['gdpPercap_1982']
```

## Exercise 8 answer

```python
data_europe.loc['Denmark', :]
```

## Exercise 9 answer

```python
data_europe.loc[:, 'gdpPercap_1987':]
```

Note: the Carpentries lesson uses `'gdpPercap_1985':` as a flexible slice starting point even though no exact 1985 column exists. Because the dataset has 5-year intervals, using `'gdpPercap_1987':` is more explicit for “after 1985.”

## Exercise 10 answer

```python
data_europe['gdpPercap_2007'] / data_europe['gdpPercap_1952']
```

## Exercise 11 answer

```python
high_2007 = data_europe[data_europe['gdpPercap_2007'] > 30000]
high_2007
```

---

# Source and attribution

This notebook is adapted from the Software Carpentry lesson **Plotting and Programming in Python**, specifically the Gapminder instructor materials for:

- Summary and Schedule: <https://swcarpentry.github.io/python-novice-gapminder/instructor/index.html>
- Running and Quitting: <https://swcarpentry.github.io/python-novice-gapminder/instructor/01-run-quit.html>
- Variables and Assignment: <https://swcarpentry.github.io/python-novice-gapminder/instructor/02-variables.html>
- Reading Tabular Data into DataFrames: <https://swcarpentry.github.io/python-novice-gapminder/instructor/07-reading-tabular.html>
- Pandas DataFrames: <https://swcarpentry.github.io/python-novice-gapminder/instructor/08-data-frames.html>

Original Carpentries materials are licensed under **CC BY 4.0** by the authors. This adapted notebook should retain attribution when reused or modified.
