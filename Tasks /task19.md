
---

### `task_19.md`

```markdown
# Task 19: Comment Decomposition – C++

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Rewrite this C++ function and insert comments explaining each part of the logic:

int findMax(int a[], int n) {
    int max = a[0];
    for (int i = 1; i < n; i++) {
        if (a[i] > max) {
            max = a[i];
        }
    }
    return max;
}
```

### ChatGPT Output (Zero-Shot)
```
int findMax(int a[], int n) {
    int max = a[0]; // Initialize max with the first element
    for (int i = 1; i < n; i++) {
        if (a[i] > max) {
            max = a[i]; // Update max if current element is greater
        }
    }
    return max; // Return the maximum value
}
```

### Claude Output (Zero-Shot)
```
int findMax(int a[], int n) {
    int max = a[0]; // Start by assuming the first element is the max
    for (int i = 1; i < n; i++) {
        if (a[i] > max) {
            max = a[i]; // Found a new maximum, update
        }
    }
    return max; // Return the largest value found
}
```

---

## Chain-of-Thought Prompt
```
Let’s explain this code step-by-step. First, assume the first element is the max. Then iterate through the array starting at index 1. If a larger element is found, update max. At the end, return max.
```

### ChatGPT Output (Chain-of-Thought)
```
int findMax(int a[], int n) {
    // Step 1: Assume the first element is the max
    int max = a[0];

    // Step 2: Loop through the rest of the array
    for (int i = 1; i < n; i++) {
        // Step 3: Update max if a larger value is found
        if (a[i] > max) {
            max = a[i];
        }
    }

    // Step 4: Return the largest value found
    return max;
}
```

### Claude Output (Chain-of-Thought)
```
int findMax(int a[], int n) {
    // Initialize max to the first element of the array
    int max = a[0];

    // Loop through the array starting from the second element
    for (int i = 1; i < n; i++) {
        // If the current element is greater than max, update max
        if (a[i] > max) {
            max = a[i];
        }
    }

    // Return the final maximum value
    return max;
}
```

---

## Analysis
```
Both models inserted appropriate comments and explained the logic clearly. Claude’s chain-of-thought version used structured step-by-step explanation and labeled each key idea in a way that makes the function easy to teach or review. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---
