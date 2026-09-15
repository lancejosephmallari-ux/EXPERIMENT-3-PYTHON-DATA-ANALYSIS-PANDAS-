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
### A. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations.

a. Display the shape and complete list of column names of cars.

b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.

c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.
  
*Requirement:* The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.
---

## PROBLEM A CODE:
After downloading and transferring the *car.csv* file into the same folder as our *.ipnyb* file we need to run this code for the file to read the data within the *.csv* file
```
import pandas as pd

# Loads the dataset (cars) into the DataFrame 
cars = pd.read_csv('cars.csv')

# Part (a): Displays the shape and column names
print("DataFrame Shape:", cars.shape)
print("Column Names:", cars.columns.tolist())

# Part (b): Positional slicing for rows 6 through 10 (0-based indices 5 through 9)
cars_6_to_10 = cars.iloc[5:10]

# Part (3): Select specified columns using column labels
result_a_c = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
display(result_a_c)
```

## PROBLEM A OUTPUT:
```
DataFrame Shape: (32, 12)
Column Names: ['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
Model	mpg	cyl	hp	gear

5	Valiant	18.1	6	105	3
6	Duster 360	14.3	8	245	3
7	Merc 240D	24.4	4	62	4
8	Merc 230	22.8	4	95	4
9	Merc 280	19.2	6	123	4
```
## Detailed Explanation of Each Function in A:
• `import pandas as pd:` Imports the Pandas library using the standard alias pd.

• `cars = pd.read_csv('cars.csv'):` Loads the dataset file cars.csv into a Pandas DataFrame named cars.  
• `print("DataFrame Shape:", cars.shape):` Displays the dimensions of DataFrame cars as a tuple representing (rows, columns).

• `print("Column Names:", cars.columns.tolist()):` Extracts the column labels of cars and converts them into a standard Python list.

• `cars_6_to_10 = cars.iloc[5:10]:` Uses positional slicing (iloc) to extract rows 6 through 10 (indices 5 to 9) into DataFrame cars_6_to_10.  Where index 5 corresponds to row 6 because Pandas uses zero-based indexing.

• `result_a_c = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]:` Selects and reorders columns Model, mpg, cyl, hp, and gear using label-based column indexing.  

• `display(result_a_c):` Displays the resulting subset DataFrame formatted in the Jupyter Notebook cell.

---

## B. MODEL LOOKUP
Use Boolean indexing on the Model column to answer both requests.
a. Display the complete row for Toyota Corolla.

b. For Pontiac Firebird, display only Model, mpg, hp, and wt.

Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

## PROBLEM B CODE:
```
# Part (1): Boolean indexing for Toyota Corolla (Complete Row)
toyota = cars[cars['Model'] == 'Toyota Corolla']
display(toyota)

# Part (2): Boolean indexing for Pontiac Firebird (Selected Columns)
pontiac = cars[cars['Model'] == 'Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt']]
display(pontiac)
```

## PROBLEM B OUTPUT:
```
Model	mpg	cyl	disp	hp	drat	wt	qsec	vs	am	gear	carb
19	Toyota Corolla	33.9	4	71.1	65	4.22	1.835	19.9	1	1	4	1

Model	mpg	hp	wt
24	Pontiac Firebird	19.2	175	3.845
```

## Detailed Explanation of Each Function in B:
• `toyota = cars[cars['Model'] == 'Toyota Corolla']`: Performs Boolean indexing on column **Model** to extract the complete row where the vehicle matches **Toyota Corolla**, saving the result in DataFrame **toyota**

• `display(toyota)`: Displays the complete row retrieved for **Toyota Corolla**

• `pontiac = cars[cars['Model'] == 'Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt']]`: Filters the dataset for **Pontiac Firebird** using Boolean indexing and selects columns **Model**, **mpg**, **hp**, and **wt**, saving the result in DataFrame **pontiac**  --> Where double brackets `[['...']]` specify the exact subset of column labels to retain

• `display(pontiac)`: Displays the filtered column subset for **Pontiac Firebird**
