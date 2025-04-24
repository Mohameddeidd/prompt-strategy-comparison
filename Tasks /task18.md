
---

### `task_18.md`

```markdown
# Task 18: Fix Boolean Return in JS Function

**Best Model:** ChatGPT  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Fix the bug in the following JavaScript function. It always returns true, even when the condition is false:

function isEven(n) {
    if (n % 2 === 0);
        return true;
    return false;
}
```

### ChatGPT Output (Zero-Shot)
```
function isEven(n) {
    if (n % 2 === 0) {
        return true;
    }
    return false;
}
```

### Claude Output (Zero-Shot)
```
function isEven(n) {
    if (n % 2 === 0) {
        return true;
    }
    return false;
}
```

---

## Chain-of-Thought Prompt
```
Let’s fix this step-by-step. First, identify the condition being checked: n % 2 === 0. Then, examine the semicolon after the if-statement. Is it preventing the conditional block from executing correctly? Finally, rewrite the logic so it evaluates and returns correctly.
```

### ChatGPT Output (Chain-of-Thought)
```
function isEven(n) {
    // Remove semicolon to correctly bind return to condition
    if (n % 2 === 0) {
        return true;
    }
    return false;
}
```

### Claude Output (Chain-of-Thought)
```
function isEven(n) {
    // Semicolon after if prevents conditional behavior
    if (n % 2 === 0) {
        return true;
    }
    return false;
}
```

---

## Analysis
```
Both models correctly diagnosed the semicolon as the cause of the logic error. ChatGPT’s chain-of-thought output provided a concise, well-explained fix and clean syntax, making it clearer for readers. Therefore, the best method was Chain-of-Thought, and the best model was ChatGPT.
```
```

---

