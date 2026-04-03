# Python Cheatsheet
<details>
<summary>Python Basic Variable Types </summary>

## Lists, []
**Type:** Ordered, mutable collection of elements  

| Command | Description |
|---------|-------------|
| `my_list = [1,2,3]` | Create a list |
| `my_list.append(4)` | Add an element at the end |
| `my_list.insert(0,0)` | Insert at a specific index |
| `my_list.remove(2)` | Remove first occurrence of a value |
| `len(my_list)` | Get number of elements |
| `my_list.sort()` | Sort the list |
| `my_list.reverse()` | Reverse the list |

### Example
```python
numbers = [10, 5, 8]
numbers.append(3)
numbers.sort()
print(numbers)  # Output: [3, 5, 8, 10]
```
## Advanced Alternatives:
numpy.array([]) → numerical arrays with vectorized operations
pandas.Series([]) → labeled 1D array with analysis methods

## Dictionaries, {}

**Type:** Key-value mapping (unordered, mutable)  

| Command | Description |
|---------|-------------|
| `my_dict = {'a':1,'b':2}` | Create a dictionary |
| `my_dict['c'] = 3` | Add or update key-value pair |
| `my_dict.get('a')` | Get value safely (returns None if key missing) |
| `del my_dict['b']` | Remove key-value pair |
| `my_dict.keys()` | List all keys |
| `my_dict.values()` | List all values |
| `my_dict.items()` | List of (key, value) tuples |

### Example
```python
person = {'name':'Alice', 'age':30}
person['city'] = 'Athens'
print(person.keys())  # Output: dict_keys(['name','age','city'])
```
Advanced Alternatives:
pandas.DataFrame({'name':['Alice'],'age':[30]}) → tabular key-value-like structure
collections.defaultdict(int) → dictionary with default values for missing keys

## Sets, set()

**Type:** Unordered collection of unique elements  

| Command | Description |
|---------|-------------|
| `my_set = {1,2,3}` | Create a set |
| `my_set.add(4)` | Add element |
| `my_set.remove(2)` | Remove element |
| `my_set.union({5,6})` | Combine sets |
| `my_set.intersection({3,4,5})` | Elements present in both sets |

### Example
```python
numbers = {1,2,3}
numbers.add(2)  # duplicates ignored
print(numbers)  # Output: {1,2,3}
```
Advanced Alternatives:
numpy.unique(array) → unique elements from an array

## Tuples ,()

**Type:** Ordered, immutable collection  

| Command | Description |
|---------|-------------|
| `my_tuple = (1,2,3)` | Create a tuple |
| `my_tuple[0]` | Access element |
| `len(my_tuple)` | Length |
| `my_tuple.count(2)` | Count occurrences |
| `my_tuple.index(3)` | Index of value |

### Example
```python
point = (10, 20)
x, y = point  # unpack tuple
print(x, y)   # Output: 10 20
```

## Classes / Object-Oriented Programming

**Type:** User-defined objects with attributes and methods  

| Command | Description |
|---------|-------------|
| `class ClassName:` | Define a class |
| `def __init__(self, ...)` | Constructor; initializes object attributes |
| `self.attribute = value` | Assign an attribute to the object |
| `def method(self, ...)` | Define a method for the class |
| `obj = ClassName(args)` | Create an instance of the class |
| `obj.method()` | Call a method on the instance |
| `obj.attribute` | Access an attribute |

### Example
```python
class Order:
    def __init__(self, order_id, amount):
        self.order_id = order_id
        self.amount = amount
    
    def summary(self):
        return f"Order {self.order_id}: ${self.amount}"

# Create an instance
my_order = Order(order_id=101, amount=250)
print(my_order.summary())  # Output: Order 101: $250

# Access attributes
print(my_order.order_id)   # Output: 101
print(my_order.amount)     # Output: 250
```
</details>


<details>
<summary> Python Built-in / Special Commands</summary>

## Special Variables
| Command | Description |
|---------|-------------|
|"__name__"| Name of the module; "__main__" if running script directly |
|"__file__"| Full path of the current file |

### Example
```python

print("Module name:", __name__)
print("Current file path:", __file__)
```

## Python Built-in Commands
| Command | Description |
|---------|-------------|
| open(path, mode) | Open file (mode='w' for writing, 'r' for reading, etc.) |
| with ... as ... | Context manager: auto-closes file at block end |
| file.write(data) | Write string to file |
| file.read() | Read data from file |
| file.close() | Close file (usually handled automatically with 'with') |

### Example
```python

with open(file_path, "w") as f:
    f.write(f"Hello from {__name__}!\n") 
    content = f.read()                  
    print("File content:\n", content)

```


</details>

<details>
<summary>OS Module Cheatsheet</summary>

## OS Operations
| Command | Description |
|---------|-------------|
| os.getcwd() | Get the current working directory |
| os.path.abspath(path) | Get the absolute path of a file or folder |
| os.path.join(path1, path2, ...) | Join folders/files into a complete path |
| os.path.dirname(path) | Get the folder part of a path |
| os.path.basename(path) | Get the file or folder name from a path |
| os.listdir(path='.') | List files and folders in the given path |
| os.path.exists(path) | Check if a path exists |
| os.path.isfile(path) | Check if the path is a file |
| os.path.isdir(path) | Check if the path is a folder |
| os.mkdir(path) | Create a new folder |
| os.makedirs(path) | Create nested folders |
| os.remove(path) | Delete a file |
| os.rmdir(path) | Delete an empty folder |

### Example
```python
import os

cwd = os.getcwd()
print("Contents:", os.listdir(cwd))#Λίστα περιεχομένων τρέχοντος φακέλου
folder_name = "test_dir"
folder_path = os.path.join(cwd, folder_name) #Δημιουργία πλήρους path για φάκελο

file_name = "example.txt"
file_path = os.path.join(cwd, "subfolder name" ,file_name)#Δημιουργία πλήρους path για νέο αρχείο
```
</details> 

<details>
<summary>Pathlib Cheatsheet</summary>


## Path / File Operations
| Command | Description |
|---------|-------------|
| Path.cwd() | Return the current working directory as a Path object |
| Path.home() | Return the user’s home directory |
| path.exists() | Check if the path exists (file or folder) |
| path.is_file() | Check if the path is a file |
| path.is_dir() | Check if the path is a folder |
| path.name | Return the name of the file/folder |
| path.stem | Return the file name without extension |
| path.suffix | Return the file extension |
| path.parent | Return the parent directory |
| path.mkdir(exist_ok=True) | Create a folder (ignore if it already exists) |
| path.touch() | Create an empty file or update its timestamp |
| path.unlink() | Delete the file |
| path.rmdir() | Delete an empty folder |
| path.iterdir() | Return a generator of files/folders in the directory |
| path.glob(pattern) | Search for files/folders matching a pattern in the folder |
| path.rglob(pattern) | Recursively search all subfolders for matching pattern |

## Combining Paths
| Command | Description |
|---------|-------------|
| parent / "child_folder" | Συνδυάζει φακέλους/αρχεία με `/` operator, π.χ. `path / "file.txt"` |

### Example
```python

from pathlib import Path

BASE_DIR = Path.cwd()           
file_path = BASE_DIR / "data.xlsx"

if not file_path.exists():
    #file_path.touch()            # create empty file
    found_xlsx_files=list(BASE_DIR.glob("*/*.xlsx*")) #if searching for xlsx files in subfolders
    print("found xlsx files:", found_xlsx_files) 
    file_path=found_xlsx_files[0] # take the first found file
```
### Example
```python
#Inspect file properties
print(file_path.stem)            # όνομα χωρίς extension
print(file_path.suffix)          # extension
print(file_path.parent)          # φάκελος που ανήκει
print(list(BASE_DIR.glob("*")))    # όλα τα αρχεία
print(list(BASE_DIR.glob("*.xlsx"))) # μόνο αρχεία .xlsx
```

</details>

<details>
<summary>Pandas Cheatsheet</summary>

## Excel / CSV Handling
| Command | Description |
|---------|-------------|
| pd.ExcelFile(path) | Load Excel file to inspect sheet names |
| pd.read_excel(path) | Read Excel file into a DataFrame |
| df.to_excel(path, sheet_name='Sheet1', index=False) | Write DataFrame to Excel file |
| pd.read_excel(path, sheet_name='Sheet1', usecols='A:C') | Read specific columns from Excel |
| pd.read_excel(path, sheet_name='Sheet1', skiprows=1) | Skip rows when reading Excel |
| pd.read_csv(path) | Read CSV file into a DataFrame (default separator is ',') |
| pd.read_csv(path, sep=';') | Read CSV file using `;` as separator |

## Quick Inspecting of DataFrame (useful after reading input)
### What is a DataFrame?
A DataFrame is a 2D table-like data structure in pandas with rows and columns, similar to an Excel sheet or SQL table.

| Command | Description |
|---------|-------------|
| df.head(n) | Display first n rows of DataFrame |
| df.tail(n) | Display last n rows of DataFrame |
| df.shape | Get number of rows and columns |
| df.columns | List column names |
| df.dtypes | Show data types of each column |
| df.info() | Summary of DataFrame (columns, dtypes, non-null counts) |

### Example
```python
import pandas as pd

# Read data (CSV or Excel)
df_csv = pd.read_csv("data.csv", sep=';')        # for CSV
df_excel = pd.read_excel("data.xlsx")            # for Excel

# Quick inspection
print(df_csv.head())     # First rows
print(df_csv.shape)      # (rows, columns)
print(df_csv.columns)    # Column names
print(df_csv.dtypes)     # Data types
print(df_csv.info())     # Summary info
```

## Date / Time
| Command | Description |
|---------|-------------|
| pd.date_range(start, end) | Generate a sequence of dates between start and end |
| pd.to_datetime(col) | Convert a column (or value) to pandas datetime |
| df['col'].dt.date | Extract only the date part from a pandas Timestamp |
| df['col'].dt.time | Extract only the time part from a pandas Timestamp |
| df['col'].dt.year / .month / .day | Extract year, month, or day |
| df['col'].dt.strftime('%Y-%m-%d') | Format datetime as string |

### Example
```python
import pandas as pd
df = pd.read_csv(csv_path) #Read CSV into a DataFrame
print("Columns in CSV:", df.columns)
time_data = pd.to_datetime(df['timestamp']).dt.time #Convert timestamp to datetime
print("Type of 'time_data':", type(time_data))          
print("Type of individual element:", type(time_data.iloc[0]))  
```

### Options / Settings
| Command | Description |
|---------|-------------|
| pd.set_option('future.no_silent_downcasting', True) | Disable silent dtype downcasting |
| pd.options.mode.chained_assignment = None | Disable chained assignment warning |
</details>

<details>
<summary>Numpy Cheatsheet</summary>

## Basic Operations
| Command | Description |
|---------|-------------|
| np.array() | Create a NumPy array |
| np.arange(start, stop, step) | Create array with evenly spaced values |
| np.zeros(shape) | Create array of zeros |
| np.ones(shape) | Create array of ones |
| np.reshape(array, shape) | Reshape array |
| np.mean(array) | Compute mean of array |
| np.sum(array) | Compute sum of array |

</details>