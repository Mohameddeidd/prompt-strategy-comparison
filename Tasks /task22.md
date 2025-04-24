
---

### `task_22.md`

```markdown
# Task 22: File Processor – Clean and Count Words

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Complete the following Python script to remove punctuation from each line, convert text to lowercase, and count word frequencies correctly:

import string

def load_file(filepath):
    with open(filepath, 'r') as f:
        return f.readlines()

def clean_line(line):
    # TODO: Remove punctuation and make lowercase
    pass

def count_words(lines):
    word_counts = {}
    for line in lines:
        clean = clean_line(line)
        for word in clean.split():
            word_counts[word] = word_counts.get(word, 0) + 1
    return word_counts

def main():
    filepath = 'input.txt'
    lines = load_file(filepath)
    counts = count_words(lines)
    for word, count in sorted(counts.items()):
        print(f"{word}: {count}")

if __name__ == '__main__':
    main()
```

### ChatGPT Output (Zero-Shot)
```
def clean_line(line):
    translator = str.maketrans('', '', string.punctuation)
    return line.translate(translator).lower()
```

### Claude Output (Zero-Shot)
```
def clean_line(line):
    # Remove punctuation and convert to lowercase
    line = line.translate(str.maketrans('', '', string.punctuation))
    return line.lower()
```

---

## Chain-of-Thought Prompt
```
Let’s complete the clean_line function step-by-step. First, create a translation table that removes all punctuation. Then use translate to strip punctuation. Finally, convert the result to lowercase before returning it.
```

### ChatGPT Output (Chain-of-Thought)
```
def clean_line(line):
    # Remove punctuation and convert to lowercase
    translator = str.maketrans('', '', string.punctuation)
    return line.translate(translator).lower()
```

### Claude Output (Chain-of-Thought)
```
def clean_line(line):
    # Step 1: Create translation table to remove punctuation
    translator = str.maketrans('', '', string.punctuation)
    # Step 2: Apply it to the line
    line = line.translate(translator)
    # Step 3: Convert to lowercase
    return line.lower()
```

---

## Analysis
```
Claude’s chain-of-thought response provided clear and well-commented reasoning, explaining each transformation step. This clarity is especially helpful in processing tasks where subtle mistakes can distort results. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---