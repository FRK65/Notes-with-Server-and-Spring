# 1. String in JAVA

String represents a sequence of characters and is widely used for working with text. 
Strings in Java are immutable, meaning once a String object is created, 
its value cannot be changed.

String is basically an object that represents sequence of char values. 
An array  of characters works same as Java string.
~~~
char[] ch={'F','r','a','n','k'};  
String s=new String(ch);
String s="Frank";
~~~

Java String class provides a lot of methods to perform operations on strings such 
as 
**compare(), concat(), equals(), split(), length(), replace(), compareTo(), intern(), substring() etc.**

The **java.lang.String class** implements Serializable, Comparable and CharSequence interfaces.
~~~
public final class String
implements java.io.Serializable, Comparable<String>, CharSequence {}
~~~

**1.1 Serializable:**
A marker interface that allows an object to be serialized (converted into a byte stream) and deserialized (reconstructed). It doesn’t have any methods; its presence signals that objects of a class can be saved and restored.

**1.2 Comparable:**
An interface that defines a natural order for objects of a class. It has the method
compareTo(To) which is used for comparing objects, typically for sorting them 
(e.g., sorting a list of objects).

**1.3 CharSequence:**
An interface for representing a sequence of characters (e.g., String, StringBuilder). 
It provides methods like **charAt(), length(), and subSequence()** to interact with characters 
in a sequence.

The CharSequence interface is used to represent the sequence of characters. 
String, StringBuffer and StringBuilder classes implement it. It means, we can create strings 
in Java by using these three classes.

# 2. Creation of String

The Java String is immutable which means it cannot be changed. 
Whenever we change any string, a new instance is created.
For mutable strings, you can use StringBuffer and StringBuilder classes.

**What is String in Java?**

Generally, String is a sequence of characters. But in Java, string is an object that represents 
a sequence of characters. The java.lang.String class is used to create a string object.

**How to create a string object?**

There are two ways to create String object:
1.	**By string literal**
2.	**By new keyword**
~~~
      String s1 = "Hello";  // String literal
      String s2 = new String("Hello");  // Using the new keyword
~~~

**String Literal** : Java String literal is created by using double quotes. 
Each time you create a string literal, the JVM checks in the "string constant pool" first.
If the string already exists in the pool, a reference to the pooled instance is returned. 
If the string doesn't exist in the pool, a new string instance is created and placed in the pool.

For example:
~~~
String s1="Welcome";  
String s2="Welcome";//It doesn't create a new instance
~~~

In the above example, only one object will be created. Firstly, JVM will not find any 
string object with the value "Welcome" in string constant pool that is why it will 
create a new object s1. 

After that it will find the string with the value "Welcome" in the pool, 
it will not create a new object but will return the reference to the same instance.

**Note: String objects are stored in a special memory area known as the "string constant pool" 
which in inside the Heap".**



**Why Java uses the concept of String literal?**

To make Java more memory efficient (because no new objects are created if it exists already 
in the string constant pool).

The String Constant Pool is a memory optimization technique where Java stores unique string 
literals. This reduces memory usage by ensuring that identical string literals 
are stored only once. 
It automatically applies to string literals, and you can explicitly use intern() to 
add strings to the pool.
~~~
String which are created via double quotes are String literal.
String s1 = "Hello";  // String literal
~~~

**By new keyword**
~~~
String s=new String("Welcome");
//creates two objects and one reference variable
~~~

**Differences:**

 1. String literals are automatically stored in the String Pool and are reused.

 2. new String() creates a new object on the heap, even if the string already exists in 
    the pool, which can lead to unnecessary memory overhead.

|Aspect |                   	String Literal (String s1 = "Hello";)                   |	Using new String() (String s2 = new String("Hello");) |
| :---         |:---------------------------------------------:|          ---: |
|Memory Location |   Stored in the String Constant Pool    | A new object is created on the heap |
|Memory Efficiency	|       Efficient, reuses the same reference for identical string literals.        | 	Less efficient, creates a new object even if the string is in the pool. |
| Equality Check (== operator) | 	Points to the same object if the string literal is the same. | Points to a new object in the heap, even if the content is the same. |
| Usage | Preferred when you are using string literals frequently | Less common, only needed when explicitly creating a new object |


# 3. Immutability & String Pool terms

**Immutability**: 
Once instantiated, a String object cannot be modified. 
This immutable design is a deliberate choice to ensure thread safety, consistency, 
and efficiency, especially regarding the String pool mechanism.

**String Pool**: Java maintains a pool of string literals to help save memory. 
When a new string literal is created, Java checks the Pool for a matching string. 
If found, the new variable references the pooled string. 
If not, the new string is added to the Pool.


# 4. CharSequence Interface

The CharSequence interface in Java is part of the java.lang package and is implemented by 
classes that represent sequences of characters.

CharSequence is a read-only interface for working with sequences of characters.

It provides a common set of methods for working with character sequences in Java. 
This includes both mutable and immutable types of character sequences 
like String, StringBuilder, and StringBuffer.

It provides essential methods for character access (charAt()), length (length()), 
and sub-sequencing (subSequence()).

Common **classes implementing CharSequence are String, StringBuilder, and StringBuffer.**

It allows flexibility and performance optimization in handling character data in 
both mutable and immutable forms

1.	String
2.	StringBuffer
3.	StringBuilder



Classes Implementing CharSequence:

**String**: Immutable sequence of characters.

**StringBuilder**: Mutable sequence of characters (for efficient string manipulation).

**StringBuffer**: Mutable sequence of characters 
(similar to StringBuilder, but synchronized for thread safety).

# 5. What is String, StringBuilder, and StringBuffer

In Java, String, StringBuilder, and StringBuffer are all classes used to 
represent sequences of characters, but they differ in terms of mutability, performance, 
and thread-safety.

# 5.1 String 
**(Not efficient for frequent modifications)**

- **Immutability**: A String is immutable, meaning once a String object is created, 
  its value cannot be changed.
- **Memory Usage**: Since String objects are immutable, any modification to a 
  String creates a new String object, which can lead to higher memory consumption 
  when performing many string operations.

- **Thread Safety**: Being immutable, String objects are inherently thread-safe.
- **Performance**: String is not suitable for frequent modifications (e.g., in loops) 
  because modifying a String involves creating new String objects every time. 
  This results in less efficient memory usage and performance.

- **When to Use** : Use when you have a constant string value or when you don't need to 
  modify the string after its creation. Since strings are immutable, 
  this is the preferred choice for data that doesn't change (like constants).
- **Using String** (Inefficient for frequent modifications):
~~~
   String s = "Hello";
   s = s + " World";  
   // A new String is created every time this operation is performed
~~~

# 5.2 StringBuilder 
**(Efficient for single-threaded frequent modifications))**

- **Mutability**: StringBuilder is mutable, meaning its value can be changed without 
  creating new objects.

- **Memory Usage**: It is more efficient than String when you need to modify the 
  contents of a string, as it doesn’t create new objects with each modification.  
  It modifies the string in place.

- **Thread Safety**: StringBuilder is not thread-safe, meaning it is not synchronized. 
  Multiple threads modifying a StringBuilder object concurrently can lead to 
  inconsistent results.

- **Performance**: StringBuilder is typically faster than String when performing many string 
  manipulations (like concatenation) in a single thread, because it avoids the overhead of 
  creating multiple string objects.

- **When to use** : StringBuilder Use when you need to modify strings frequently in 
  a single-threaded environment. 
  It's more efficient than String when performing repeated concatenations or modifications.
~~~
   StringBuilder sb = new StringBuilder("Hello");
   sb.append(" World");  // Modifies the existing StringBuilder object
   System.out.println(sb.toString());  // Output: "Hello World"
~~~

# 5.3 StringBuffer 
**(Thread-safe, but slower)**
   
- **Mutability**: Like StringBuilder, StringBuffer is mutable, meaning its value can be modified.
- **Memory Usage**: StringBuffer is also efficient in terms of memory usage because 
  it doesn't create new objects with each modification.
- **Thread Safety**: StringBuffer is thread-safe, meaning its methods are synchronized. 
  This ensures that multiple threads can safely modify a StringBuffer object concurrently, 
  but this comes with a performance cost due to the synchronization overhead.
- **Performance**: StringBuffer is slower than StringBuilder because of its synchronization, 
  making it less suitable for single-threaded applications where thread safety is not a concern.
- **When to use** : StringBuffer Use when you need to modify strings in a multi-threaded 
  environment and require thread safety. However, due to synchronization, 
  it tends to be slower than StringBuilder in a single-threaded scenario.

~~~   
   StringBuffer sbf = new StringBuffer("Hello");
   sbf.append(" World");
   System.out.println(sbf.toString());  // Output: "Hello World"
~~~


| Feature   | String   | StringBuilder   | StringBuffer   |
|------------|------------|------------|------------|
| Mutability | Immutable (cannot be changed) | Mutable (can be modified) | Mutable (can be modified) |
| Thread-Safety | Thread-safe (due to immutability)| Not thread-safe | Thread-safe (synchronized methods) |
| Performance | Not efficient for frequent modifications | Fast for frequent modifications (single-threaded) | Slower due to synchronization overhead |
| Usage | Ideal for constant, unchanging strings | Ideal for single-threaded scenarios with frequent string modifications | Ideal for multi-threaded scenarios where thread safety is needed |
| Memory Consumption | Higher, as new objects are created with each modification | More efficient, modifies the same object | More efficient, modifies the same object |


# 6. String Equality and Identity


**equals()** : Compares the content of two strings.

**==** : Compares the reference or memory address of two string

~~~
String s1 = "Java";
String s2 = "Java";
String s3 = new String("Java");

System.out.println(s1 == s2);  
// true, because both refer to the same object in the string pool

System.out.println(s1 == s3);  
// false, because s3 refers to a new object on the heap

System.out.println(s1.equals(s3));  
// true, because both have the same content
~~~

**String.join()** : Introduced in Java 8, String.join() joins multiple strings with a delimiter.
~~~
String joined = String.join("-", "2024", "12", "20");
// Output: 2024-12-20
~~~

**String Conversion with valueOf()**: 
String.valueOf() can be used to convert other data types (like int, char, boolean, etc.) 
into strings.

~~~
int num = 100;
String str = String.valueOf(num);  // Converts integer to String
~~~


# 7. Common String Methods

Java provides a wide range of methods in the String class to perform various operations 
on strings. 
Some of the most common methods include:

**a) Length of String**

~~~
String s = "Hello";
int len = s.length();  // Returns the number of characters in the string (5)
~~~

**b) Accessing Characters**
~~~
char c = s.charAt(1);  
// Returns the character at index 1, which is 'e'
~~~

**c) Substring**
~~~
String sub = s.substring(1, 4);  
// Returns "ell" (from index 1 to 3)
~~~

**d) String Concatenation**
~~~
String s1 = "Hello";
String s2 = "World";
String result = s1.concat(" " + s2);  
// Concatenates strings
~~~

**e) Replacing Characters**
~~~
String s = "Hello World";
String newStr = s.replace('o', 'a');  
// Replaces 'o' with 'a', result: "Hella Warld"
~~~

**f) Case Conversion**
~~~
String s = "Hello World";
String upper = s.toUpperCase();  // Converts to "HELLO WORLD"
String lower = s.toLowerCase();  // Converts to "hello world"
~~~

**g) Trimming Whitespace**

~~~
String s = "  Hello  ";
String trimmed = s.trim();  
// Removes leading and trailing spaces, result: "Hello"
~~~

**h) String Comparison**
~~~
String s1 = "Hello";
String s2 = "Hello";
String s3 = "World";

boolean equals = s1.equals(s2);  
// true, checks if the content is equal

boolean equalsIgnoreCase = s1.equalsIgnoreCase(s2);  
// true, case insensitive comparison

boolean compare = s1.compareTo(s3);  
// Negative value, as "Hello" is lexicographically less than "World"
~~~


**i) Checking if String Contains a Substring**
~~~
boolean contains = s1.contains("ell");  // true
~~~

**j) Splitting a String**
~~~
String s = "apple,banana,orange";
String[] fruits = s.split(",");  
// Splits the string into an array of strings based on comma
~~~

**k) String to Integer Conversion**
~~~
String s = "123";
int num = Integer.parseInt(s);  
// Converts string "123" to integer 123
~~~


**Here is a comprehensive list of interview questions on String, StringBuffer, and StringBuilder in Java, 
including memory management, immutability, declaration and initialization, and comparison**

# 8. String in Java

**8.1  What is a String in Java?**

A String in Java is an object that represents a sequence of characters. 
It is immutable, meaning its value cannot be changed once created. 
Strings are widely used for working with text.

**8.2 How do you declare and initialize a String in Java?**
~~~
Using string literals: String s = "Hello";

Using the new keyword: String s = new String("Hello");
~~~

**8.3 What is the difference between String and StringBuffer?**

String is immutable, meaning once created, its value cannot be changed. 
Every modification creates a new String object.

StringBuffer is mutable and designed for efficient string manipulation, 
such as appending, deleting, or inserting characters without 
creating new objects each time.

**8.4 What is the difference between String and StringBuilder?**

Both StringBuilder and StringBuffer are mutable and used for efficient string operations.

StringBuilder is not thread-safe, but it is faster than StringBuffer for single-threaded 
environments.

StringBuffer is thread-safe, meaning its methods are synchronized, 
but it is slower than StringBuilder.

**8.5 What is String immutability?**

String immutability means that once a String object is created, its value cannot be 
changed. 
Any operation that appears to modify a string (such as concatenation) results 
in the creation of a new String object.

**8.6 Why are Strings immutable in Java?**

- **Security**: Immutable objects are safe to use across multiple threads.

- **Hashing**: String immutability allows them to be used as keys in HashMap because 
their hashcode remains constant.

- **Caching and Performance**: Immutable objects can be cached, as their values don’t 
change.

- **Simplicity**: Immutability simplifies development by eliminating errors related 
to unexpected changes to data.



**8.7 How does the String pool work in Java?**

Java maintains a String pool to optimize memory usage. 

When you create a String using a 
literal (e.g., String s = "Hello";), 

Java checks if the same string already exists in the pool. 
If it does, the reference to the existing string is returned; otherwise, 
it adds the new string to the pool.

**8.8 Can we modify a String in Java?**

No, Strings are immutable. Any modification creates a new String object. 
For example, if you concatenate two strings, a new String object is created.

**8.9 What happens when two strings have the same content but are created 
in different ways?**

if two strings are created as literals 
(e.g., String s1 = "Hello"; String s2 = "Hello";), 
they will refer to the same object in the String pool.

If one string is created using the new keyword 
(e.g., String s3 = new String("Hello");), 
it will refer to a new object in the heap, not the string pool.

**8.10 What is the difference between equals() and == for String comparison?**

- **==** compares references (memory addresses) of two objects.

- **equals()** compares contents of the strings (i.e., the sequence of characters).
~~~
    String s1 = "Hello";
    String s2 = "Hello";
    System.out.println(s1 == s2);  
    // true, because they refer to the same object in the pool

    System.out.println(s1.equals(s2));  
    // true, because they have the same content
~~~


**8.11 How do you convert a String to an Integer and vice versa?**

- To convert from String to Integer: **Integer.parseInt("123");**

- To convert from Integer to String: **String.valueOf(123);**


**8.12 What is the intern() method in the String class?**

The intern() method is used to ensure that a string object is part of the String pool. 
When you call intern() on a String, it checks if an identical string already exists 
in the pool. 
If it does, it returns the reference to the existing string; 
otherwise, it adds the string to the pool.


# 9. StringBuffer in Java

**9.1 What is a StringBuffer?**

StringBuffer is a mutable sequence of characters. 
It is designed for efficient string manipulation and is particularly useful 
when performing numerous string operations like append, insert, and delete. 
Unlike String, it does not create a new object for each modification.

**9.2 How does StringBuffer differ from String?**

String is immutable, whereas StringBuffer is mutable.
StringBuffer is more efficient than String when performing multiple string 
manipulations because it does not create new objects each time.

**9.3 Is StringBuffer thread-safe?**

Yes, StringBuffer is thread-safe because its methods are synchronized, 
but this comes at the cost of performance compared to StringBuilder.


**9.4 How to append a string using StringBuffer?**

You can append a string using the append() method of StringBuffer:
~~~
StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");  // "Hello World"
~~~

**9.5 What is the capacity() method in StringBuffer?**

The capacity() method returns the current capacity of the StringBuffer. 
The capacity is the total amount of space allocated for characters. 
It may be greater than the actual string length.

**9.6 What happens when a StringBuffer exceeds its capacity?**

When the StringBuffer exceeds its current capacity, its capacity is automatically 
increased, typically by doubling it.


# 10. StringBuilder in Java

**10.1 What is StringBuilder?**

StringBuilder is a mutable sequence of characters that is similar to StringBuffer. 
It is designed for efficient string manipulation but is not thread-safe, 
making it faster than StringBuffer for single-threaded environments.

**10.2 How does StringBuilder differ from StringBuffer?**

StringBuilder is faster than StringBuffer because it is not synchronized and 
is not thread-safe.
StringBuffer is thread-safe and slower due to synchronization.

**10.3 When should you use StringBuilder over StringBuffer?**

Use StringBuilder in single-threaded environments where thread safety is not 
a concern because it provides better performance 
due to the lack of synchronization.



# 11. String Memory Management in Java

**11.1 How does Java handle memory management for Strings?**

Java uses a String Pool (or String Literal Pool) to optimize memory usage for strings. 
When a string is created using a literal, Java checks if the string already exists 
in the pool. 
If it does, it returns the reference to the existing string; if not, the string is 
added to the pool. 
This helps to avoid duplicate string objects in memory.

**11.2 What is the String Pool and how does it work?**

The String Pool is a special area in the JVM heap where all String literals are stored. 
When a String is created as a literal (e.g., String s = "Hello";), 
Java checks if that string already exists in the pool. 
If it exists, the existing reference is returned; otherwise, 
a new String object is created and added to the pool.

**11.3 Can String objects be garbage collected in Java?**

String objects in the String Pool are not eligible for garbage collection. 
However, if a String object is created on the heap (using new keyword), 
and it is no longer referenced, it can be garbage collected.

**11.4 What are the advantages of using String Pool?**

**Memory Efficiency**: String literals are shared, avoiding duplication in memory.

**Performance**: Using the String Pool helps in faster comparisons (==) 
because strings from the pool refer to the same memory location.

**11.5 How do you make sure a string is added to the String Pool?**

You can use the intern() method to ensure that a string is added to the String Pool.
~~~
String s1 = new String("Hello");
String s2 = s1.intern
~~~