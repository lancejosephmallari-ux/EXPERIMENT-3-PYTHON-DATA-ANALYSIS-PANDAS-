# EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)-PA2_ECE2112_MALLARI,LJN
**Submitted by Lance Joseph N. Mallari**

**2ECE-A    Date: 09/15/2026**
---
This is repository contains all the necessary code for PA3 along with the breakdown for each line of code
## I. Intended Learning Outcomes
At the end of this laboratory activity, the student should be able to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.
---
## II. Instructions
Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Note-
book and import Pandas as pd. The dataset contains the Model column together with the vehicle
variables used in the original experiment.

• Load the CSV file into a DataFrame named cars.

• Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any
requested table or answer.

• Do not modify values in cars; create a new DataFrame or Series for each requested subset.

• Preserve the row order of the source dataset unless stated otherwise.

• Display every requested result in an executed notebook cell.
---
## III. Programming Problems
After loading cars, complete the following operations.
  
**Requirement:** The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.
---
## PART A CODE:
```
import pandas as pd

# Loads the dataset (cars) into the DataFrame 
cars = pd.read_csv('cars.csv')
```
a. Display the shape and complete list of column names of cars.
```
# Part (a): Displays the shape and column names
print("DataFrame Shape:", cars.shape)
print("Column Names:", cars.columns.tolist())
```
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
     the first data row is row 1.
```
# Part (b): Positional slicing for rows 6 through 10 (0-based indices 5 through 9)
cars_6_to_10 = cars.iloc[5:10]
```
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.
```
# Part (3): Select specified columns using column labels
result_a_c = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
display(result_a_c)
```
