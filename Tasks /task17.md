
---

### `task_17.md`

```markdown
# Task 17: Bug Fix – Logic vs Name Mismatch

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Fix the bug in the following C++ function. It returns the wrong greeting due to a logic error:

string greet(string name) {
    if (name == "admin") {
        return "Welcome, user!";
    } else {
        return "Welcome, admin!";
    }
}
```

### ChatGPT Output (Zero-Shot)
```
string greet(string name) {
    if (name == "admin") {
        return "Welcome, admin!";
    } else {
        return "Welcome, user!";
    }
}
```

### Claude Output (Zero-Shot)
```
string greet(string name) {
    if (name == "admin") {
        return "Welcome, admin!";
    } else {
        return "Welcome, user!";
    }
}
```

---

## Chain-of-Thought Prompt
```
Let’s walk through this function. First, examine the if condition and the expected result. Ask: what should happen when the name is "admin"? Then confirm if the greeting message aligns. Finally, correct the message if it’s reversed.
```

### ChatGPT Output (Chain-of-Thought)
```
string greet(string name) {
    if (name == "admin") {
        return "Welcome, admin!";
    } else {
        return "Welcome, user!";
    }
}
```

### Claude Output (Chain-of-Thought)
```
string greet(string name) {
    // If the input is "admin", the correct greeting should welcome the admin.
    if (name == "admin") {
        return "Welcome, admin!";
    } else {
        return "Welcome, user!";
    }
}
```

---

## Analysis
```
Both models fixed the logic reversal by correctly associating "admin" with the appropriate greeting. However, Claude’s chain-of-thought version included inline clarification and demonstrated a better grasp of intent versus implementation, which is critical in debugging scenarios. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---
