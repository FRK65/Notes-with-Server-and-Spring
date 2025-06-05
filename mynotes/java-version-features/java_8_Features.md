# 1. Lambda Expression :

A **Lambda Expression** in Java is a concise way to express **anonymous functions**.
 **anonymous functions**— functions that don’t require a name or explicit declaration. 
 It Introduced in **Java 8**, it simplifies code by eliminating unnecessary boilerplate, 
 especially when working with functional interfaces.


### **🔹 Key Features of Lambda Expressions**

✅ **Eliminates anonymous classes**, making code more readable.  
✅ **Can be passed as arguments**, making functional programming easier.  
✅ **Works with functional interfaces** (interfaces with only one abstract method).  
✅ **Improves code maintainability** by reducing verbosity.



### **🔹 Basic Syntax of a Lambda Expression**
Lambda expressions follow this structure:
```java
(parameters) -> expression
```

Example:
```java
// Traditional way using anonymous class
Runnable r1 = new Runnable() {
    @Override
    public void run() {
        System.out.println("Hello, Lambda!");
    }
};

// Using Lambda Expression
Runnable r2 = () -> System.out.println("Hello, Lambda!");
```
🚀 **Much cleaner and more concise!**

### **🔹 Types of Lambda Expressions**

#### **1️⃣ No Parameters**
```java
() -> System.out.println("Hello, World!")
```
👉 Used when no arguments are required.


#### **2️⃣ Single Parameter**
```java
name -> System.out.println("Hello, " + name)
```
👉 Parentheses `()` are **optional** when there's only **one parameter**.


#### **3️⃣ Multiple Parameters**
```java
(a, b) -> a + b
```
👉 Parentheses `()` are **required** when multiple parameters exist.


#### **4️⃣ Lambda with Code Block**
```java
(a, b) -> {
    int sum = a + b;
    return sum;
}
```
👉 When **multiple statements** are needed, **use `{}` and `return`**.


### **🔹 Using Lambda Expressions with Functional Interfaces**
Java **already provides many built-in functional interfaces**, 
such as `Runnable`, `Callable`, `Predicate`, `Consumer`.

Example with **Predicate**:
```java
Predicate<Integer> isEven = num -> num % 2 == 0;
System.out.println(isEven.test(4)); // Output: true
```

🚀 **Lambda expressions make functional programming easier!**


### **🔹 Why Use Lambda Expressions?**
✅ **Reduces code complexity**  
✅ **Improves readability**  
✅ **Enhances functional programming**  
✅ **Boosts performance** in collections processing  

---

# 2. Functional Interfaces :

**Functional Interfaces** in Java are interfaces that contain **only one abstract method**, 
making them perfect for **Lambda Expressions** and functional programming. 
It introduced in **Java 8**, they enable **cleaner, more readable code** by reducing unnecessary anonymous classes.


### **🔹 Key Features of Functional Interfaces**
✅ **Has only one abstract method** (though it can have multiple default/static methods).  
✅ **Used with Lambda Expressions** to simplify coding.  
✅ **Encourages functional programming**, making Java more expressive.  
✅ **Marked with `@FunctionalInterface` annotation** (optional but recommended).


### **🔹 Example of a Functional Interface**
```java
@FunctionalInterface
public interface Calculator {
    int operate(int a, int b);
}
```
Since `Calculator` has **only one abstract method**, it's a **valid functional interface**.

Now, **using Lambda Expression**:
```java
Calculator addition = (a, b) -> a + b;
System.out.println(addition.operate(5, 3)); // Output: 8
```
🚀 **No need for an anonymous class—just a simple lambda expression!**


### **🔹 Predefined Functional Interfaces in Java**
Java provides many **built-in functional interfaces** inside `java.util.function` package, including:

✅ `Predicate<T>` → Takes input and returns `true` or `false`.  
✅ `Consumer<T>` → Accepts input but **does not return a value**.  
✅ `Function<T, R>` → Takes an input and **returns a result**.  
✅ `Supplier<T>` → **Produces a value** without taking input.  

Example using **Predicate**:
```java
Predicate<Integer> isEven = num -> num % 2 == 0;
System.out.println(isEven.test(4)); // Output: true
```

### **🔹 Why Use Functional Interfaces?**
🚀 **Reduces boilerplate code**  
🚀 **Enhances readability**  
🚀 **Encourages functional programming**  
🚀 **Works seamlessly with Streams & Lambdas**  

Java 8 **transformed coding** by introducing Functional Interfaces, making Java more modern and expressive!

---

# 3. Streams API.

The **Streams API**, introduced in **Java 8**, is a powerful tool for processing collections **declaratively** and **efficiently**. Instead of traditional `for` loops, Streams allow **functional-style programming**, making code more **concise, readable, and parallelizable**.



### **🔹 Key Features of Streams API**
✅ **Processes collections declaratively** (no explicit loops).  
✅ **Supports functional operations** like `map`, `filter`, `reduce`.  
✅ **Works efficiently with large data sets**.  
✅ **Can run in parallel** (`parallelStream()`) for faster execution.  



### **🔹 Example: Using Streams API**
Suppose we have a **list of names**, and we want to filter out those that start with `"A"`.

**❌ Traditional approach (using loop):**
```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "Adam");
List<String> filteredNames = new ArrayList<>();

for (String name : names) {
    if (name.startsWith("A")) {
        filteredNames.add(name);
    }
}

System.out.println(filteredNames); // Output: [Alice, Adam]
```

**✅ Streams API approach:**
```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "Adam");

List<String> filteredNames = names.stream()
                                  .filter(name -> name.startsWith("A"))
                                  .collect(Collectors.toList());

System.out.println(filteredNames); // Output: [Alice, Adam]
```

🚀 **Cleaner, more readable, and efficient!**



### **🔹 Common Stream Operations**
1️⃣ **`filter(Predicate<T>)`** → Selects elements that satisfy a condition.  
2️⃣ **`map(Function<T, R>)`** → Transforms elements (e.g., convert names to uppercase).  
3️⃣ **`sorted(Comparator<T>)`** → Sorts elements.  
4️⃣ **`forEach(Consumer<T>)`** → Performs an action on each element.  
5️⃣ **`reduce(BinaryOperator<T>)`** → Aggregates elements into a single result.  
6️⃣ **`collect(Collectors.toList())`** → Converts the processed stream into a list.


### **🔹 Example: Transforming & Sorting**
```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie");

List<String> sortedNames = names.stream()
                                .map(String::toUpperCase)   // Convert to uppercase
                                .sorted()                  // Sort alphabetically
                                .collect(Collectors.toList());

System.out.println(sortedNames); // Output: [ALICE, BOB, CHARLIE]
```

🚀 **Chaining multiple operations keeps code simple and efficient!**


### **🔹 Parallel Streams for Faster Processing**
If working with large datasets, **parallel streams** can speed up execution.

```java
List<Integer> numbers = List.of(1, 2, 3, 4, 5);

int sum = numbers.parallelStream()
                 .reduce(0, Integer::sum);

System.out.println(sum); // Output: 15
```

🚀 **Automatically splits work across multiple CPU cores for better performance!**


### **🔹 Why Use Streams API?**
✅ **Removes boilerplate code**  
✅ **Improves readability**  
✅ **Boosts performance with parallel execution**  
✅ **Encourages functional programming**  

Java 8’s **Streams API** makes handling data **simpler, faster, and more elegant**!

---

# 4. Default & Static Methods in Interfaces

**Default & Static Methods in Interfaces**, introduced in **Java 8**, revolutionized how interfaces 
work by allowing method implementations inside them. 
This improves **code flexibility** and ensures **backward compatibility** without breaking existing functionality.


### **🔹 What Are Default Methods in Interfaces?**
Before Java 8, interfaces could only have **abstract methods**, 
meaning every implementing class had to provide an implementation. 
**Default methods** allow interfaces to have **method implementations**, 
so classes that don’t override them still have usable functionality.

#### **🔹 Example: Default Method**
```java
public interface Vehicle {
    default void start() {
        System.out.println("Vehicle is starting...");
    }
}
```
Now, any class that **implements `Vehicle`** can use the `start()` method **without needing to override it**.

🚀 **Ensures backward compatibility without forcing changes in all implementing classes!**


### **🔹 What Are Static Methods in Interfaces?**
Java 8 also introduced **static methods in interfaces**, allowing methods to be defined **without needing an instance**.

#### **🔹 Example: Static Method**
```java
public interface Utility {
    static void printMessage(String message) {
        System.out.println("Utility Message: " + message);
    }
}
```
To call the method:
```java
Utility.printMessage("Hello, Java!");
```
🚀 **Acts as a helper method, available directly from the interface!**


### **🔹 Key Benefits**
✅ **Default methods provide backward compatibility**  
✅ **Static methods serve as utility methods in interfaces**  
✅ **Removes the need for separate utility classes**  
✅ **Improves code organization and flexibility**  

Java 8 made interfaces **smarter** with these features! 

---

# 5. Optional Class

The **Optional Class**, introduced in **Java 8**, is designed 
to **handle null values safely**, preventing `NullPointerException` and improving code reliability.


### **🔹 What Is `Optional`?**
✅ `Optional<T>` is a **container object** that may **or may not** contain a non-null value.  
✅ Encourages developers to **explicitly check for missing values**, avoiding unexpected null-related crashes.  
✅ Provides **utility methods** to handle null cases effectively.


### **🔹 Example: Using `Optional` Instead of Null Checks**
**❌ Traditional Approach (Prone to NullPointerException)**
```java
public String getUserName(User user) {
    if (user != null) {
        return user.getName();
    }
    return "Default Name";
}
```

**✅ Using `Optional` (Safer)**
```java
public Optional<String> getUserName(User user) {
    return Optional.ofNullable(user.getName());
}

// Retrieving value safely
Optional<String> userName = getUserName(user);
System.out.println(userName.orElse("Default Name")); // Output: "Default Name" if user is null
```

🚀 **Cleaner, more readable, and prevents null-related crashes!**

### **🔹 Common `Optional` Methods**
1️⃣ **`isPresent()`** → Checks if a value is present.  
2️⃣ **`ifPresent(Consumer<T>)`** → Executes a block of code if a value exists.  
3️⃣ **`orElse(defaultValue)`** → Returns value if present; otherwise, returns default.  
4️⃣ **`orElseGet(Supplier<T>)`** → Provides default dynamically.  
5️⃣ **`map(Function<T, R>)`** → Transforms the optional value.  
6️⃣ **`filter(Predicate<T>)`** → Filters based on a condition.



### **🔹 Example: Avoiding Null Checks in Streams**
```java
List<String> names = Arrays.asList("Alice", null, "Charlie");

List<String> validNames = names.stream()
                               .map(Optional::ofNullable) // Wrap each name in Optional
                               .filter(Optional::isPresent) // Remove null values
                               .map(Optional::get) // Extract values
                               .collect(Collectors.toList());

System.out.println(validNames); // Output: [Alice, Charlie]
```

🚀 **Streams + Optional = Clean and Safe Code!**



### **🔹 Why Use `Optional`?**
✅ **Eliminates manual null checks**  
✅ **Avoids NullPointerExceptions**  
✅ **Encourages best practices in handling missing values**  
✅ **Integrates seamlessly with Java 8 Streams and Functional Programming**  

Java 8’s **Optional Class** makes Java development **more robust, safe, and modern**! 

---

# 6. New Date & Time API (java.time package)

The **New Date & Time API (`java.time` package)**, introduced in **Java 8**, 
replaces the outdated `java.util.Date` and `Calendar` classes, offering 
**immutable, thread-safe, and easy-to-use** alternatives.


### **🔹 Why Was a New API Needed?**
Before Java 8, handling dates and times with `Date` and `Calendar` was:
❌ **Mutable**, leading to potential bugs.  
❌ **Complex**, requiring manual parsing and formatting.  
❌ **Not thread-safe**, making concurrent applications difficult.  

🚀 **The `java.time` package solves all these issues!**


### **🔹 Key Classes in `java.time`**
✅ **`LocalDate`** → Represents a **date (YYYY-MM-DD)** without time or zone.  
✅ **`LocalTime`** → Represents **time (HH:MM:SS)** without date or zone.  
✅ **`LocalDateTime`** → Combines **date and time**, but no timezone.  
✅ **`ZonedDateTime`** → Includes **timezone information**.  
✅ **`Instant`** → Represents a **timestamp (epoch time)**.  



### **🔹 Example: Using `LocalDate`, `LocalTime`, and `LocalDateTime`**
```java
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.LocalDateTime;

public class DateTimeExample {
    public static void main(String[] args) {
        LocalDate date = LocalDate.now();
        LocalTime time = LocalTime.now();
        LocalDateTime dateTime = LocalDateTime.now();

        System.out.println("Current Date: " + date);
        System.out.println("Current Time: " + time);
        System.out.println("Current Date & Time: " + dateTime);
    }
}
```
✅ **Immutable & Thread-Safe**  
✅ **No more manual parsing!**  


### **🔹 Example: Formatting a Date (`DateTimeFormatter`)**
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateFormatterExample {
    public static void main(String[] args) {
        LocalDate date = LocalDate.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd-MM-yyyy");

        System.out.println("Formatted Date: " + date.format(formatter));
    }
}
```
🚀 **Cleaner formatting with built-in utility!**


### **🔹 Example: Handling Timezones (`ZonedDateTime`)**
```java
import java.time.ZonedDateTime;
import java.time.ZoneId;

public class TimeZoneExample {
    public static void main(String[] args) {
        ZonedDateTime zonedTime = ZonedDateTime.now(ZoneId.of("America/New_York"));
        System.out.println("New York Time: " + zonedTime);
    }
}
```
✅ **No more manual timezone conversions!**  


### **🔹 Why Use the New Date & Time API?**
🚀 **Immutable & Thread-Safe**  
🚀 **Readable & More Intuitive**  
🚀 **No manual time calculations needed**  
🚀 **Handles time zones effortlessly**  

Java 8’s **`java.time` package** makes date handling **cleaner, safer, and easier!**
