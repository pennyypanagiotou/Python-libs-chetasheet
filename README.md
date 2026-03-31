# Python Cheatsheet
<details>
<summary>Python Built-in / Special Commands</summary>

### Special Variables
| Command | Description |
|---------|-------------|
|"__name__"| Name of the module; "__main__" if running script directly |
|"__file__"| Path of the current file |

### Python Built-in Commands
| Command | Description |
|---------|-------------|
| open(path, mode) | Open file (mode='w' for writing, 'r' for reading, etc.) |
| with ... as ... | Context manager: auto-closes file at block end |
| "file".write() | Write string to file |
| "file".read() | Read data from file |
| "file".close() | Close file (usually handled automatically with 'with') |

</details>

<details>
<summary>OS Module Cheatsheet</summary>

### Path Operations
| Command | Description |
|---------|-------------|
| os.getcwd() | Get current working directory |
| os.path.abspath(path) | Absolute path ενός αρχείου/φακέλου |
| os.path.join(path1, path2, ...) | Συνδέει φακέλους/αρχεία σε ένα πλήρες path |
| os.path.dirname(path) | Επιστρέφει τον φάκελο ενός path |
| os.path.basename(path) | Επιστρέφει το όνομα αρχείου/φακέλου από ένα path |

### File & Directory Operations
| Command | Description |
|---------|-------------|
| os.listdir(path='.') | Λίστα αρχείων/φακέλων στο path |
| os.mkdir(path) | Δημιουργία νέου φακέλου |
| os.makedirs(path) | Δημιουργία nested φακέλων |
| os.remove(path) | Διαγραφή αρχείου |
| os.rmdir(path) | Διαγραφή κενό φακέλου |

### Example
```python
import os

cwd = os.getcwd()
folder_name = "test_dir"
folder_path = os.path.join(cwd, folder_name)
if not os.path.exists(folder_path):
    os.mkdir(folder_path)
print("Contents:", os.listdir(cwd))#Λίστα περιεχομένων τρέχοντος φακέλου
file_name = "example.txt"
file_path = os.path.join(folder_path, file_name)#Δημιουργία πλήρους path για νέο αρχείο

```
</details> 

<details>
<summary>Pathlib Cheatsheet</summary>

### Path / File Operations
| Command | Description |
|---------|-------------|
| Path.cwd() | Επιστρέφει το τρέχον working directory ως Path |
| Path.home() | Επιστρέφει τον φάκελο home του χρήστη |
| path.exists() | Ελέγχει αν υπάρχει το path (αρχείο ή φάκελος) |
| path.is_file() | Ελέγχει αν είναι αρχείο |
| path.is_dir() | Ελέγχει αν είναι φάκελος |
| path.name | Επιστρέφει το όνομα αρχείου/φακέλου |
| path.stem | Επιστρέφει το όνομα αρχείου χωρίς extension |
| path.suffix | Επιστρέφει το extension (π.χ. ".xlsx") |
| path.parent | Επιστρέφει τον γονικό φάκελο |
| path.mkdir(exist_ok=True) | Δημιουργεί φάκελο (ελέγχει αν υπάρχει ήδη) |
| path.touch() | Δημιουργεί άδειο αρχείο ή ενημερώνει timestamp |
| path.unlink() | Διαγράφει το αρχείο |
| path.rmdir() | Διαγράφει κενό φάκελο |
| path.iterdir() | Επιστρέφει generator με τα αρχεία/φακέλους του φακέλου |
| path.glob(pattern) | Ψάχνει αρχεία/φακέλους που ταιριάζουν με pattern στο folder |
| path.rglob(pattern) | Αναδρομική αναζήτηση σε όλους τους υποφακέλους με pattern |

### Combining Paths
| Command | Description |
|---------|-------------|
| parent / "child_folder" | Συνδυάζει φακέλους/αρχεία με `/` operator, π.χ. `path / "file.txt"` |

### Example
```python
from pathlib import Path

BASE_DIR = Path.cwd()            # τρέχων φάκελος
file_path = BASE_DIR / "data.xlsx"
if not file_path.exists():
    file_path.touch()            # δημιουργεί κενό αρχείο

print(file_path.stem)            # όνομα χωρίς extension
print(file_path.suffix)          # extension
print(file_path.parent)          # φάκελος που ανήκει
print(list(BASE_DIR.glob("*")))    # όλα τα αρχεία
print(list(BASE_DIR.glob("*.xlsx"))) # μόνο αρχεία .xlsx
```

</details>

<details>
<summary>Pandas Cheatsheet</summary>

### Excel Handling
| Command | Description |
|---------|-------------|
| pd.read_excel(path, sheet_name=None) | Read Excel file into a DataFrame |
| df.to_excel(path, sheet_name='Sheet1', index=False) | Write DataFrame to Excel file |
| pd.ExcelFile(path) | Load Excel file to inspect sheet names |
| pd.read_excel(path, sheet_name='Sheet1', usecols='A:C') | Read specific columns from Excel |
| pd.read_excel(path, sheet_name='Sheet1', skiprows=1) | Skip rows when reading Excel |

### Date / Time
| Command | Description |
|---------|-------------|
| pd.date_range(start, end) | Generate a sequence of dates between start and end |
| Timestamp.date() | Get date part (datetime.date) from a pandas Timestamp |

### Options / Settings
| Command | Description |
|---------|-------------|
| pd.set_option('future.no_silent_downcasting', True) | Disable silent dtype downcasting |
| pd.options.mode.chained_assignment = None | Disable chained assignment warning |
</details>

<details>
<summary>Numpy Cheatsheet</summary>

### Basic Operations
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