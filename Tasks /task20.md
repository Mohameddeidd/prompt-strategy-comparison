
---

### `task_20.md`

```markdown
# Task 20: Average Calculator – Python

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Write a Python function that takes a list of numbers and returns their average. Handle empty lists gracefully.
```

### ChatGPT Output (Zero-Shot)
```
def average(nums):
    if not nums:
        return 0
    return sum(nums) / len(nums)
```

### Claude Output (Zero-Shot)
```
def average(numbers):
    if not numbers:
        return 0
    return sum(numbers) / len(numbers)
```

---

## Chain-of-Thought Prompt
```
Let’s solve this step-by-step. First, check if the list is empty. If it is, return 0 to avoid division by zero. Otherwise, compute the sum and divide by the number of elements.
```

### ChatGPT Output (Chain-of-Thought)
```
def average(nums):
    if not nums:
        return 0
    total = sum(nums)
    count = len(nums)
    return total / count
```

### Claude Output (Chain-of-Thought)
```
def average(numbers):
    # Step 1: Check for empty list
    if not numbers:
        return 0
    # Step 2: Compute total and count
    total = sum(numbers)
    count = len(numbers)
    # Step 3: Return average
    return total / count
```

---

## Analysis
```
Both models implemented the correct solution, but Claude’s chain-of-thought response was especially thorough. It included inline comments and made clear each stage of the logic. This helps avoid silent bugs and makes the code easier to maintain. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---