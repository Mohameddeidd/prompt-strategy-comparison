
---

### `task_10.md`

```markdown
# Task 10: Function Summarization – Reverse Words (Python)

**Best Model:** ChatGPT  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Summarize the functionality of the following Python function:

def reverse_words(sentence):
    return ' '.join(sentence.split()[::-1])
```

### ChatGPT Output (Zero-Shot)
```
This function takes a string and returns a new string with the order of the words reversed.
```

### Claude Output (Zero-Shot)
```
The function splits a sentence into words, reverses the order of the words, and then joins them back into a string.
```

---

## Chain-of-Thought Prompt
```
Let’s walk through the function line-by-line. First, consider what sentence.split() does. Then, observe how slicing with [::-1] affects the word order. Finally, interpret the join operation and describe what the function returns.
```

### ChatGPT Output (Chain-of-Thought)
```
1. The function splits the sentence into a list of words using sentence.split().
2. It then reverses the list using slicing [::-1].
3. It joins the reversed list back into a single string using ' '.join().
4. Therefore, it returns the input sentence with the word order reversed.
```

### Claude Output (Chain-of-Thought)
```
Step 1: The sentence is split into words based on spaces.
Step 2: The list of words is reversed using [::-1] slicing.
Step 3: The reversed words are joined back together with spaces between them.
Result: A sentence with the word order reversed is returned.
```

---

## Analysis
```
Both models accurately described the function’s behavior. The chain-of-thought responses were more pedagogically valuable. ChatGPT's breakdown was especially structured, breaking the function into individual operations and showing how each part contributes to the final result. Therefore, the best method was Chain-of-Thought, and the best model was ChatGPT.
```
```

---
