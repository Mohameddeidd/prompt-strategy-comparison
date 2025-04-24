
---

### `task_11.md`

```markdown
# Task 11: Prompt from Code Comments – Prime Check

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Complete the function below based on the comments:

def is_prime(n):
    # Return False for numbers less than or equal to 1
    # Check divisibility up to the square root of n
    # If divisible by any number in that range, return False
    # Otherwise, return True
```

### ChatGPT Output (Zero-Shot)
```
import math

def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True
```

### Claude Output (Zero-Shot)
```
import math

def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True
```

---

## Chain-of-Thought Prompt
```
Let’s build this function step-by-step. First, return False for n <= 1. Then loop through all numbers from 2 to sqrt(n) to check for divisibility. If any divide evenly, return False. If none do, return True.
```

### ChatGPT Output (Chain-of-Thought)
```
import math

def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True
```

### Claude Output (Chain-of-Thought)
```
import math

def is_prime(n):
    # Step 1: Handle edge case
    if n <= 1:
        return False
    # Step 2: Only need to check up to square root
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    # Step 3: Return True if no divisors found
    return True
```

---

## Analysis
```
All implementations were correct. However, Claude’s chain-of-thought output included inline reasoning and highlighted the mathematical optimization, making it more instructive and better aligned with the comment-driven prompt. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---