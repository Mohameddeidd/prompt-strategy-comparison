
---

### `task_12.md`

```markdown
# Task 12: Fix Factorial for Zero Input

**Best Model:** ChatGPT  
**Best Strategy:** Zero-Shot  

---

## Zero-Shot Prompt
```
Fix the bug in the following Python function. It incorrectly returns 0 for factorial(0):

def factorial(n):
    result = 1
    for i in range(1, n):
        result *= i
    return result
```

### ChatGPT Output (Zero-Shot)
```
def factorial(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result
```

### Claude Output (Zero-Shot)
```
def factorial(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result
```

---

## Chain-of-Thought Prompt
```
Let’s fix this function step-by-step. First, recall that factorial(0) = 1 by definition. Then, check whether the loop includes the last number. If it doesn’t, modify the range accordingly. Ensure the function works for both n = 0 and positive n.
```

### ChatGPT Output (Chain-of-Thought)
```
def factorial(n):
    result = 1
    for i in range(1, n + 1):  # Include n in the product
        result *= i
    return result
```

### Claude Output (Chain-of-Thought)
```
def factorial(n):
    result = 1
    for i in range(1, n + 1):  # Corrects the range to include n
        result *= i
    return result
```

---

## Analysis
```
Both models corrected the loop to include n in the multiplication. However, ChatGPT’s zero-shot response was immediately correct and required no setup or scaffolding, reflecting a strong understanding of factorial logic. Therefore, the best method was Zero-Shot, and the best model was ChatGPT.
```
```

---
