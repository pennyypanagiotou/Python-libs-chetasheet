# Python Cheatsheet
<details>
<summary>Python Built-in / Special Commands</summary>

### Special Variables
| Command | Description |
|---------|-------------|
| __name__ | Name of the module; "__main__" if running script directly |
| __file__ | Path of the current file |

### Python Built-in Commands
| Command | Description |
|---------|-------------|
| open(path, mode) | Open file (mode='w' for writing, 'r' for reading, etc.) |
| with ... as ... | Context manager: auto-closes file at block end|
| "file".write() | Write string to file |

e.g with open(path,w) as f: f.write(command)


</details>

<details>
<summary>OS Module Cheatsheet</summary>

### Path Operations
| Command | Description |
|---------|-------------|
| os.path.abspath() | Absolute path ενός αρχείου/φακέλου |
| os.path.join() | Συνδέει φακέλους/αρχεία σε path |
| os.path.dirname() | Επιστρέφει folder από path |
| os.path.basename() | Επιστρέφει όνομα αρχείου/φακέλου |
| os.getcwd() | Current working directory |

| Command | Description |
|---------|-------------|
| os.listdir() | Λίστα αρχείων/φακέλων |
| os.mkdir() | Δημιουργία νέου φακέλου |
| os.makedirs() | Δημιουργία nested φακέλων |
| os.remove() | Διαγραφή αρχείου |
| os.rmdir() | Διαγραφή κενό φακέλου |

</details>

<details>
<summary>Pandas Cheatsheet</summary>

### Options / Settings
| Command | Description |
|---------|-------------|
| pd.set_option('future.no_silent_downcasting', True) | Disable silent dtype downcasting |


### Date / Time
| Command | Description |
|---------|-------------|
| pd.date_range(start, end) | Generate a sequence of dates between start and end |


</details>

<details>
<summary>Numpy Cheatsheet</summary>



</details>