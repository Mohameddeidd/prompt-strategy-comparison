
---

### `task_14.md`

```markdown
# Task 14: Recursive Fibonacci Function

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Write a recursive function in Python to compute the nth Fibonacci number.
```

### ChatGPT Output (Zero-Shot)
```
def fib(n):
    if n <= 1:
        return n
    return fib(n - 1) + fib(n - 2)
```

### Claude Output (Zero-Shot)
```
def fib(n):
    if n <= 1:
        return n
    return fib(n - 1) + fib(n - 2)
```

---

## Chain-of-Thought Prompt
```
Let’s build the Fibonacci function step-by-step. First, define the base cases: fib(0) = 0 and fib(1) = 1. Then, for any n > 1, return fib(n-1) + fib(n-2). Use recursion to express this logic.
```

### ChatGPT Output (Chain-of-Thought)
```
def fib(n):
    if n <= 1:
        return n
    return fib(n - 1) + fib(n - 2)
```

### Claude Output (Chain-of-Thought)
```
def fib(n):
    # Base case
    if n <= 1:
        return n
    # Recursive case
    return fib(n - 1) + fib(n - 2)
```

---

## Analysis
```
Both models provided correct recursive implementations. The chain-of-thought prompts led to clearer outputs, especially in Claude’s version, which used inline comments to distinguish base and recursive cases. Claude’s educational tone and breakdown made it more effective for learners. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---