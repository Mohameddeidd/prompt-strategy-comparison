
---

### `task_03.md`

```markdown
# Task 3: Bug Classification – C++ Memory Return

**Best Model:** ChatGPT  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Classify the type of bug in the following C++ function and explain why it's problematic:

int* getArray(int size) {
    int arr[size];  // Local array
    return arr;     // Returns pointer to local memory
}
```

### ChatGPT Output (Zero-Shot)
```
The bug in the function is a use-after-return error. The array arr is a local variable, so its memory is deallocated when the function returns. Returning a pointer to this invalid memory causes undefined behavior.

Fix: Use dynamic memory allocation with new or malloc to ensure the memory persists after the function returns.
```

### Claude Output (Zero-Shot)
```
This function returns a pointer to a local variable arr, which is allocated on the stack. Once the function exits, that memory is no longer valid, and using the returned pointer causes undefined behavior.
```

---

## Chain-of-Thought Prompt
```
Let’s think through the function step-by-step. First, look at how the array is declared. Then, consider the scope and memory duration of that array. Finally, analyze the implications of returning a pointer to it.
```

### ChatGPT Output (Chain-of-Thought)
```
1. The array int arr[size]; is declared locally inside the function. It is created on the stack and its size is determined by the size parameter.
2. The array arr exists only within the scope of the function. Once the function exits, the stack memory for arr is deallocated.
3. Returning a pointer to arr means that the caller receives a pointer to memory that is no longer valid.

Implications: Returning a pointer to a local variable causes undefined behavior and can lead to crashes or corrupted data.
```

### Claude Output (Chain-of-Thought)
```
The array arr is a local variable, so it only exists while the function is running. Returning a pointer to it means the caller receives a pointer to deallocated stack memory. This is unsafe and causes undefined behavior.

Recommendation: Use dynamic memory allocation instead if persistent memory is needed.
```

---

## Analysis
```
Both models correctly identified the issue as returning a pointer to a local (stack-allocated) array. However, ChatGPT's chain-of-thought response was clearer in walking through the memory lifetime and implications step-by-step. It also explicitly recommended dynamic allocation as a fix. Therefore, the best method was Chain-of-Thought, and the best model was ChatGPT.
```
```

---
