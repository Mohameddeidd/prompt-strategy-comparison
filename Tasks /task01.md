
---

### 📄 `task_01.md`

```markdown
# Task 1: Java Method Summarization

**Best Model:** ChatGPT  
**Best Strategy:** Chain-of-Thought  

---

## 🔹 Zero-Shot Prompt
```
Summarize the functionality of the following Java method:

```java
public Map<String, Integer> countWordFrequency(List<String> words) {
    Map<String, Integer> freqMap = new HashMap<>();
    for (String word : words) {
        freqMap.put(word, freqMap.getOrDefault(word, 0) + 1);
    }
    return freqMap;
}
```
```

###ChatGPT Output (Zero-Shot)
```
This method takes a list of words and returns a map where each word is a key and the corresponding value is the number of times that word appears in the list.
```

###Claude Output (Zero-Shot)
```
The method counts how many times each word appears in a list and returns a map of words to their frequency counts.
```

---

##Chain-of-Thought Prompt
```
Think of a step-by-step to understand what this Java method does. First, look at the parameters. Then, consider how the map is populated. Finally, interpret what the method returns.
```

###ChatGPT Output (Chain-of-Thought)
```
1. The method takes a list of strings as input.
2. It creates an empty map to count word frequencies.
3. It loops through the list and uses getOrDefault to either retrieve the existing count or default to 0, then increments the count.
4. Finally, it returns the map containing word frequencies.
```

###Claude Output (Chain-of-Thought)
```
The method takes a list of words and uses a HashMap to count frequency. It uses getOrDefault to fetch the current count or start at 0, and updates the value. Finally, it returns the complete frequency map.
```

---

## Analysis
```
Zero-shot responses were accurate but brief. Chain-of-thought prompting led to clearer, more step-by-step reasoning. ChatGPT provided a structured breakdown that’s easier to follow, making it the preferred choice for this task.
```
```
