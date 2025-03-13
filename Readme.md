# Data Viz Practice 1: 200 years, 200 countries, in 4 minutes

## Abstract
The series of data viz practice is based on the homework of online course [7 Data Viz projects](https://hahow.in/courses/667242066282be4de9eabf8f). These practices are based on Python and I am going to use the same data in R as well.

## Intrudoction
This project is to reproduce the famous [Hans Rosling's 200 countries, 200 years, 4 minutes](https://youtu.be/jbkSRLYSojo?si=xYCYuMmqRDfb3QyB) data visualisation. We use `pandas`, `sqlite 3` to create database, `matplotlib ` to validate the concept and `plotly.express` to create final chart. 
## How to reproduce
* Install [miniconda](https://docs.anaconda.com/miniconda)
* Create environment via `environment.yml`
``` bash
conda env create -f environment.yml
```
* Place 4 csv files in data/ folder
* `conda activate gapminder_clone` and 
  `python create_gapminder_db.py` to create gapminder.db
* `python plot_with_px.py` to create gapminder_clone.html

## Knowledge Recap - Python
* **dictionary**:
    * Key-value pairs
    * unordered
    * mutable (it can be modified)
    * accessed by keys
```python
#create dictionary
empty_dict = {}
my_dict = {"key1": "value1", "key2": "value2"}
df_dict = dict()

#transfer by dict()
my_dict = dict(name="Alice", age=25, city="New York")
pairs = [("name", "Bob"), ("age", 30), ("city", "London")]
my_dict = dict(pairs)
print(my_dict)  # Output: {'name': 'Bob', 'age': 30, 'city': 'London'}

```
* **dataframe**: 2D data structure, just like a table in database. You will create a dafaframe from
    1. dictionary
    2. list of dictionary
    3. list of list with column names
    4. read_csv
    ```python
    df = pd.read_csv("file.csv")
    ```
    * summary statistics
    ```python
    print(df.describe())
    ```
* **sqlite3**
    * a connection object
    ```python
    import sqlite3
    con = sqlite3.connect("test.db")
    ```
    * get the cursor to execute connection object
    ```python
    cur = con.cursor()
    ```
    * execute sql queries by cursor, and also fetch it
    ```python
    res = cur.execute("SELECT name FROM sqlite_master")
    res.fetchall()
    ```
    * remember to close the connect at the end.
    ```python
    con.close()
    ```
* matplotlib : [matplotlib document]("https://matplotlib.org/stable/index.html")
