
---

### `task_21.md`

```markdown
# Task 21: CSV Refactor for Safety

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Refactor the following code to safely process a CSV file and avoid common exceptions like file not found or malformed input:

with open('data.csv', 'r') as file:
    lines = file.readlines()
    for line in lines:
        fields = line.split(',')
        print(fields[1])
```

### ChatGPT Output (Zero-Shot)
```
try:
    with open('data.csv', 'r') as file:
        for line in file:
            fields = line.strip().split(',')
            if len(fields) > 1:
                print(fields[1])
except FileNotFoundError:
    print("File not found.")
```

### Claude Output (Zero-Shot)
```
try:
    with open("data.csv", "r") as f:
        for line in f:
            parts = line.strip().split(",")
            if len(parts) > 1:
                print(parts[1])
except FileNotFoundError:
    print("data.csv not found.")
except Exception as e:
    print(f"Error: {e}")
```

---

## Chain-of-Thought Prompt
```
Let’s refactor this step-by-step. First, wrap the file operation in a try-except block to catch missing file errors. Then, loop through lines using a safe iterator. Before printing the second field, check if there are enough fields. Handle any other exceptions generically.
```

### ChatGPT Output (Chain-of-Thought)
```
try:
    with open('data.csv', 'r') as file:
        for line in file:
            fields = line.strip().split(',')
            if len(fields) > 1:
                print(fields[1])
except FileNotFoundError:
    print("The file was not found.")
except Exception as e:
    print("An error occurred:", e)
```

### Claude Output (Chain-of-Thought)
```
try:
    with open("data.csv", "r") as file:
        for line in file:
            # Strip and split line into fields
            fields = line.strip().split(",")
            # Check if at least two fields exist
            if len(fields) > 1:
                print(fields[1])
except FileNotFoundError:
    print("File not found.")
except Exception as e:
    print(f"Unexpected error: {e}")
```

---

## Analysis
```
Claude’s chain-of-thought response not only correctly handled multiple edge cases, but it also included structured commentary that enhances code readability and maintainability. It demonstrated a broader view of real-world safety in file operations. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---
