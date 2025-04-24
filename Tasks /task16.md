
---

### `task_16.md`

```markdown
# Task 16: Binary Search – Java

**Best Model:** Claude  
**Best Strategy:** Zero-Shot  

---

## Zero-Shot Prompt
```
Complete the binary search function in Java:

public int binarySearch(int[] arr, int target) {
    // TODO
}
```

### ChatGPT Output (Zero-Shot)
```
public int binarySearch(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left <= right) {
        int mid = (left + right) / 2;
        if (arr[mid] == target)
            return mid;
        else if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }
    return -1;
}
```

### Claude Output (Zero-Shot)
```
public int binarySearch(int[] arr, int target) {
    int left = 0;
    int right = arr.length - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2; // prevents overflow
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }

    return -1;
}
```

---

## Chain-of-Thought Prompt
```
Let’s build this step-by-step. First, define your search window with two pointers. Then repeatedly find the midpoint, compare it to the target, and adjust the pointers accordingly. Be careful to avoid integer overflow when calculating the midpoint.
```

### ChatGPT Output (Chain-of-Thought)
```
public int binarySearch(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left <= right) {
        int mid = (left + right) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```

### Claude Output (Chain-of-Thought)
```
public int binarySearch(int[] arr, int target) {
    int left = 0;
    int right = arr.length - 1;

    while (left <= right) {
        // Use overflow-safe midpoint calculation
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }

    return -1;
}
```

---

## Analysis
```
Both models implemented the algorithm correctly. Claude’s output used the overflow-safe midpoint formula (left + (right - left) / 2), demonstrating greater awareness of edge cases. Claude also applied it in both prompting styles. Therefore, the best method was Zero-Shot, and the best model was Claude.
```
```

---