
---

### `task_06.md`

```markdown
# Task 6: SQL Schema for Review App

**Best Model:** Claude  
**Best Strategy:** Chain-of-Thought  

---

## Zero-Shot Prompt
```
Write an SQL schema for a review app. It should include tables for users, books, and reviews. Ensure that primary and foreign key constraints are included appropriately.
```

### ChatGPT Output (Zero-Shot)
```
-- Table for users
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

-- Table for books
CREATE TABLE books (
    id INT PRIMARY KEY,
    title VARCHAR(200) NOT NULL
);

-- Table for reviews
CREATE TABLE reviews (
    id INT PRIMARY KEY,
    user_id INT,
    book_id INT,
    rating INT CHECK (rating >= 1 AND rating <= 5),
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);
```

### Claude Output (Zero-Shot)
```
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

CREATE TABLE books (
    id INT PRIMARY KEY,
    title VARCHAR(200) NOT NULL
);

CREATE TABLE reviews (
    id INT PRIMARY KEY,
    user_id INT NOT NULL,
    book_id INT NOT NULL,
    rating INT CHECK (rating BETWEEN 1 AND 5),
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);
```

---

## Chain-of-Thought Prompt
```
Let’s design this step-by-step. First, define the users and books tables with primary keys. Then, define the reviews table with foreign keys linking to both users and books. Make sure to include constraints for data integrity.
```

### ChatGPT Output (Chain-of-Thought)
```
-- Define the users table
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

-- Define the books table
CREATE TABLE books (
    id INT PRIMARY KEY,
    title VARCHAR(200) NOT NULL
);

-- Define the reviews table
CREATE TABLE reviews (
    id INT PRIMARY KEY,
    user_id INT,
    book_id INT,
    rating INT CHECK (rating >= 1 AND rating <= 5),
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);
```

### Claude Output (Chain-of-Thought)
```
-- Step 1: Create users table
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

-- Step 2: Create books table
CREATE TABLE books (
    id INT PRIMARY KEY,
    title VARCHAR(200) NOT NULL
);

-- Step 3: Create reviews table with foreign keys and rating constraint
CREATE TABLE reviews (
    id INT PRIMARY KEY,
    user_id INT NOT NULL,
    book_id INT NOT NULL,
    rating INT CHECK (rating BETWEEN 1 AND 5),
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);
```

---

## Analysis
```
All outputs correctly implemented the SQL schema with appropriate primary and foreign key usage. Claude's schema used stricter data constraints and cleaner formatting. The chain-of-thought version from Claude walked through the table structure with clear rationale, making it more instructive and thorough. Therefore, the best method was Chain-of-Thought, and the best model was Claude.
```
```

---
