
---

### `task_09.md`

```markdown
# Task 9: Ktor REST API – Kotlin

**Best Model:** Claude  
**Best Strategy:** Zero-Shot  

---

## Zero-Shot Prompt
```
Using Ktor in Kotlin, create a REST API with GET and POST routes for a Product data class:

data class Product(val id: Int, val name: String)
```

### ChatGPT Output (Zero-Shot)
```
fun Application.module() {
    routing {
        get("/products") {
            call.respond(listOf(Product(1, "Sample")))
        }
        post("/products") {
            val product = call.receive<Product>()
            call.respond(HttpStatusCode.Created, product)
        }
    }
}
```

### Claude Output (Zero-Shot)
```
fun Application.module() {
    val products = mutableListOf<Product>()

    routing {
        get("/products") {
            call.respond(products)
        }
        post("/products") {
            val product = call.receive<Product>()
            products.add(product)
            call.respond(HttpStatusCode.Created, product)
        }
    }
}
```

---

## Chain-of-Thought Prompt
```
Let’s build this API step-by-step. First, define a route to return all products. Then, define a route to accept new products via POST and add them to an in-memory list. Make sure the response is returned in JSON format.
```

### ChatGPT Output (Chain-of-Thought)
```
fun Application.module() {
    val products = mutableListOf<Product>()

    routing {
        get("/products") {
            call.respond(products)
        }
        post("/products") {
            val product = call.receive<Product>()
            products.add(product)
            call.respond(HttpStatusCode.Created, product)
        }
    }
}
```

### Claude Output (Chain-of-Thought)
```
fun Application.module() {
    val products = mutableListOf<Product>()

    routing {
        get("/products") {
            call.respond(products)
        }
        post("/products") {
            val product = call.receive<Product>()
            products.add(product)
            call.respond(HttpStatusCode.Created, product)
        }
    }
}
```

---

## Analysis
```
Both models produced nearly identical outputs under both prompting strategies, correctly implementing GET and POST routes. However, Claude’s zero-shot response was clean, correct, and efficient without the need for scaffolding. Since its zero-shot output required no iteration or clarification, it was the most effective. Therefore, the best method was Zero-Shot, and the best model was Claude.
```
```

---
