
---

### `task_08.md`

```markdown
# Task 8: CSV Parser with Quoted Field Support

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Improve the following Python CSV parser so that it correctly handles quoted fields in the input string:

def parse_csv_line(line):
    return line.split(',')
```

### ChatGPT Output (Zero-Shot)
```
import csv

def parse_csv_line(line):
    # Use Python's built-in csv module to handle quoted fields and commas inside quotes
    return next(csv.reader([line]))
```

### Claude Output (Zero-Shot)
```
import csv

def parse_csv_line(line):
    # Use csv.reader to handle quoted fields and commas inside quotes
    return next(csv.reader([line]))
```

---

## Chain-of-Thought Prompt
```
Let’s improve this function step-by-step. First, think about how splitting by commas fails when fields are quoted and contain commas. Then, consider using Python’s csv module to handle these cases. Finally, rewrite the function to correctly parse quoted fields.
```

### ChatGPT Output (Chain-of-Thought)
```
import csv

def parse_csv_line(line):
    # Use the csv.reader to correctly handle quoted fields and commas inside quotes
    return next(csv.reader([line]))
```

### Claude Output (Chain-of-Thought)
```
import csv

def parse_csv_line(line):
    # Step 1: Recognize that fields can contain commas if quoted
    # Step 2: Use csv.reader to correctly parse those cases
    return next(csv.reader([line]))
```

---

## Analysis
```
Both models replaced the naive split(',') with csv.reader, correctly solving the issue. Claude’s chain-of-thought output provided a clearer reasoning path and emphasized why the fix works, using inline comments to explain each step. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---