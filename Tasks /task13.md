
---

### `task_13.md`

```markdown
# Task 13: Delete Node from Linked List – C

**Best Model:** ChatGPT  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Complete the following C function to delete a node from a singly linked list by its value:

struct Node {
    int data;
    struct Node* next;
};

void deleteNode(struct Node** head, int key) {
    // TODO: Implement node deletion
}
```

### ChatGPT Output (Zero-Shot)
```
void deleteNode(struct Node** head, int key) {
    struct Node* temp = *head;
    struct Node* prev = NULL;

    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        return;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) return;

    prev->next = temp->next;
    free(temp);
}
```

### Claude Output (Zero-Shot)
```
void deleteNode(struct Node** head, int key) {
    struct Node* current = *head;
    struct Node* previous = NULL;

    while (current != NULL && current->data != key) {
        previous = current;
        current = current->next;
    }

    if (current == NULL) return;

    if (previous == NULL)
        *head = current->next;
    else
        previous->next = current->next;

    free(current);
}
```

---

## Chain-of-Thought Prompt
```
Let’s implement this step-by-step. First, check if the head node contains the key. If so, update the head and free the node. Otherwise, loop through the list to find the node with the key. Keep track of the previous node to adjust pointers, then free the target node.
```

### ChatGPT Output (Chain-of-Thought)
```
void deleteNode(struct Node** head, int key) {
    struct Node* temp = *head;
    struct Node* prev = NULL;

    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        return;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) return;

    prev->next = temp->next;
    free(temp);
}
```

### Claude Output (Chain-of-Thought)
```
void deleteNode(struct Node** head, int key) {
    struct Node* current = *head;
    struct Node* previous = NULL;

    while (current != NULL && current->data != key) {
        previous = current;
        current = current->next;
    }

    if (current == NULL) return;

    if (previous == NULL)
        *head = current->next;
    else
        previous->next = current->next;

    free(current);
}
```

---

## Analysis
```
Both models produced correct and complete implementations. Claude’s version added clarity by treating the head node as a special case with clean logic, but ChatGPT’s chain-of-thought response more explicitly mirrored the algorithm taught in most C programming courses. Its stepwise logic and comments made the flow easier to follow. Therefore, the best method was Chain-of-Thought, and the best model was ChatGPT.
```
```

---