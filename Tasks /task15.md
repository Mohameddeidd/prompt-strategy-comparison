
---

### `task_15.md`

```markdown
# Task 15: Constructor Completion – Python

**Best Model:** Both  
**Best Strategy:** Equal  

---

## Zero-Shot Prompt
```
Complete the constructor for the following class so that it initializes name and age:

class Person:
    def __init__(self):
        # TODO
```

### ChatGPT Output (Zero-Shot)
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

### Claude Output (Zero-Shot)
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

---

## Chain-of-Thought Prompt
```
Let’s build the constructor step-by-step. First, identify what parameters the constructor needs (name and age). Then assign them to instance variables using self. Finally, make sure the function signature includes these parameters.
```

### ChatGPT Output (Chain-of-Thought)
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

### Claude Output (Chain-of-Thought)
```
class Person:
    def __init__(self, name, age):
        # Step 1: Assign parameters to instance variables
        self.name = name
        self.age = age
```

---

## Analysis
```
Both models generated the correct constructor logic under both prompting methods. The task was simple and deterministic, resulting in identical and correct outputs across the board. Therefore, the best method and best model were effectively equal for this task.
```
```

---
