
# Useful concepts for any projects. 

### 🔹 1. What is `import java.util.UUID 

# How to Explain in Interview Sample Answer :

> “`java.util.UUID` is a class used to generate universally unique identifiers (UUIDs).
> It's really helpful when we need a unique ID that won’t clash with others, even across our systems or in networks.
> For example, in a database, if multiple services are adding users at the same time. So using UUIDs it ensures that
each user gets a unique ID. We usually use `UUID.randomUUID()` to generate one.
> It's commonly used in web apps, file uploads, and distributed systems.”

# For Self understanding. 

### 🔹 What is `import java.util.UUID;`?

* This line **imports the UUID class** from the `java.util` package.
* **UUID** stands for **Universally Unique Identifier**.
* It's a **128-bit value** used to **uniquely identify** something (like a user, a session, a file, etc.).

---
### 🔹 Why is UUID used?

* Imagine you need to generate a unique ID (like a ticket number or a user ID) and **you don’t want any duplicates**.
* You could use random numbers or incremental counters, but they can be same/**collide** or repeat, especially in distributed systems.
* `UUID` gives you a way to **generate IDs that are globally unique** — the chance of two UUIDs being the same is extremely low.
---

### 🔹 When is UUID used?

* When Need a unique ID for database records, especially when multiple systems might generate them.
* When Creating unique session tokens for users.
* When Assigning unique names to files.
* When Working in distributed systems where there's no central system to assign IDs.
---

### 🔹 Types of UUIDs

The most common one is **randomly generated UUID**, called **UUID version 4 (UUIDv4)**.

---

### 🔹 Simple Java Program using UUID

```java
import java.util.UUID;

public class UUIDExample {
    public static void main(String[] args) {

        // Generate a random UUID
        UUID uniqueID = UUID.randomUUID();

        // Print the UUID
        System.out.println("Generated UUID: " + uniqueID);

    }
}
```

### 🔸 Output:

```
Generated UUID: 3f50c3e8-1f0b-4e3c-93bb-624e2dc32c94
```
> Note: Every time you run the program, it generates a different UUID.

