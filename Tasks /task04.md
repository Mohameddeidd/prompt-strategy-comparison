
---

### `task_04.md`

```markdown
# Task 4: Email Validator using Regex

**Best Model:** ChatGPT  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Complete the following Python function using regular expressions to validate basic email addresses:

def is_valid_email(email):
    # TODO: Complete using regex
    pass
```

### ChatGPT Output (Zero-Shot)
```
import re

def is_valid_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return bool(re.match(pattern, email))
```

### Claude Output (Zero-Shot)
```
import re

def is_valid_email(email):
    return bool(re.match(r'^[\w\.-]+@[\w\.-]+\.\w+$', email))
```

---

## Chain-of-Thought Prompt
```
Let’s approach this step-by-step. First, consider what makes a string a valid email address. Then, think about how to express that using a regex pattern. Finally, use Python’s re module to apply it in the function.
```

### ChatGPT Output (Chain-of-Thought)
```
def is_valid_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return bool(re.match(pattern, email))
```

### Claude Output (Chain-of-Thought)
```
import re

def is_valid_email(email):
    # Step 1: Convert pattern to match valid emails
    pattern = r'^[\w\.-]+@[\w\.-]+\.\w{2,}$'
    return bool(re.match(pattern, email))
```

---

## Analysis
```
Both models returned valid regex-based validators. ChatGPT's pattern was stricter and covered more edge cases, while Claude's was simpler. The chain-of-thought prompts led both models to explain their regex structure better. ChatGPT gave the most robust solution in both accuracy and reasoning. Therefore, the best method was Chain-of-Thought, and the best model was ChatGPT.
```
```

---