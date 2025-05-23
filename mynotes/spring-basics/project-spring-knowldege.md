
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

# 2 What is @Transactional?

@Transactional is like a guarantee in Java Spring project that make sure a group of tasks/insructions will either all executed and completed successfully or none will happen at all. 
This means if something goes wrong during the process, everything is rolled back to keep things consistent.

# Real-life analogy:
Imagine you’re transferring money from your bank account to a friend’s account.

Step 1: Debit money out from your account.
Step 2: Credit money into your friend’s account.
You want both steps to happen together. If the money is taken/Debit out of your account but doesn’t get added/Credited to your friend’s account, that’s a problem!
So, the bank treats this whole process as a transaction: if anything fails, they cancel the whole operation and no money moves anywhere.

# How @Transactional works in Spring:
When you put @Transactional on a method, it means:
- Start the transaction before the method runs.
- If the method finishes without errors, commit the changes (save them permanently).
- If an error happens, rollback (undo) all changes made during the method.


### Simple Java Spring example:

```java
@Service
public class BankService {

    @Autowired
    private AccountRepository accountRepository;

    @Transactional
    public void transferMoney(Long fromAccountId, Long toAccountId, double amount) {

        // Step 1: Withdraw money from sender
        Account fromAccount = accountRepository.findById(fromAccountId).get();
        fromAccount.withdraw(amount);
        accountRepository.save(fromAccount);

        // Step 2: Deposit money to receiver
        Account toAccount = accountRepository.findById(toAccountId).get();
        toAccount.deposit(amount);
        accountRepository.save(toAccount);

        // If something goes wrong (e.g., insufficient funds), Spring will rollback everything
    }
}
```

---

### `@Transactional` on a **Class**

When you put `@Transactional` on a **class**, it means **all the public methods inside that class** will be treated as transactional by default.

* So, **every method** in that class will start a transaction when called.
* If any method fails, all changes inside that method will be rolled back.

**Example:**

```java
@Transactional
@Service
public class BankService {

    public void transferMoney(...) {
        // This method is transactional
    }

    public void depositMoney(...) {
        // This method is transactional too
    }
}
```

---

### `@Transactional` on a **Method**

When you put `@Transactional` on a **specific method**, it means **only that method** will be transactional.

* Other methods in the class will NOT be transactional unless they have their own `@Transactional`.
* You can use this if you want to control which specific operations need transactions.

**Example:**

```java
@Service
public class BankService {

    @Transactional
    public void transferMoney(...) {
        // This method is transactional
    }

    public void checkBalance(...) {
        // This method is NOT transactional
    }
}
```

---

### Why use class-level vs method-level?

* Use **class-level** when most or all methods need transactions — it’s easier and cleaner.
* Use **method-level** when only certain methods require transaction control.

---

### Real-life analogy:

* Class-level `@Transactional` = a company policy that **all employees** must follow safety rules.
* Method-level `@Transactional` = a rule that applies **only to some employees**, like intern/visitor/contract based employee.

---

### Quick interview summary:

* **Class-level `@Transactional`**: All methods are transactional by default.
* **Method-level `@Transactional`**: Only the annotated method is transactional.
* Use method-level for fine control, class-level for broad, default behavior.

---



