
---

### `task_05.md`

```markdown
# Task 5: Flask API JSON Greeting Endpoint

**Best Model:** Claude  
**Best Strategy:** Zero-Shot  

---

## Zero-Shot Prompt
```
Complete the following Flask API endpoint so that it returns a JSON response greeting the given username:

@app.route('/greet/<username>')
def greet(username):
    # Complete this
```

### ChatGPT Output (Zero-Shot)
```
from flask import Flask, jsonify

app = Flask(__name__)

@app.route('/greet/<username>')
def greet(username):
    return jsonify({"message": f"Hello, {username}!"})
```

### Claude Output (Zero-Shot)
```
from flask import Flask, jsonify

app = Flask(__name__)

@app.route('/greet/<username>')
def greet(username):
    return jsonify(message=f"Hello, {username}!")
```

---

## Chain-of-Thought Prompt
```
Let’s work through this step-by-step. First, recall how Flask handles routes with parameters. Then, think about how to construct a JSON response using the jsonify function. Finally, return a greeting message with the given username.
```

### ChatGPT Output (Chain-of-Thought)
```
from flask import Flask, jsonify

app = Flask(__name__)

@app.route('/greet/<username>')
def greet(username):
    return jsonify({"message": f"Hello, {username}!"})
```

### Claude Output (Chain-of-Thought)
```
from flask import Flask, jsonify

app = Flask(__name__)

@app.route('/greet/<username>')
def greet(username):
    # Step 1: Extract the username from the URL parameter
    # Step 2: Format the message
    # Step 3: Return it as a JSON object
    return jsonify({"message": f"Hello, {username}!"})
```

---

## Analysis
```
Both models correctly implemented the endpoint. Claude’s zero-shot output used a cleaner syntax with direct parameter binding and minimal boilerplate, showing clear and production-ready code. While chain-of-thought outputs added clarity, the most effective response came from Claude’s zero-shot solution. Therefore, the best method was Zero-Shot, and the best model was Claude.
```
```

---