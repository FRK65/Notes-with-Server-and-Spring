# 1. Object, Class, State of Object, Behaviour of Object in Java

**Class**: A class is a blueprint or template that defines the structure and behavior of objects. 
It defines the properties (data) and methods (functions) that the objects 
created from the class will have.

**Object**: An object is an instance of a class. It has the properties and behaviours defined 
in the class.

**State of Object**: The state of an object refers to the values of its attributes (data members). 
In Java, the state is defined by the values of fields in the object.

Example: In the Car class, color and model are data members that define the state of an object.

**Behaviour of Object** : The behaviour of an object refers to the actions or methods 
that can be performed on that object. 
This is what the object can do or what can be done to it.

Example: In the Car class, the start() method represents the behavior of a car.

# 2. First Program Explanation :
**Key Takeaways:**
-	**Static**: The main method must be static.
-	**Correct Signature**: The method signature must always be **public static void main(String[] args)** 
    for the JVM to recognize it as the entry point.
-	**Access Modifier**: The method must be public, otherwise, the JVM will not be able to 
    access it.
-	**Method Name**: The method name must be main.
-	**Args Parameter**: While you can choose not to use args, 
it must still be present in the method signature.

~~~
public class HelloWorld 
{
    public static void main(String[] args) {
        
        System.out.println("Hello, World!");
    }
}
~~~

**Explanation of Each Word** in **public static void main(String[] args)**

1. **public**:

-   This is an access modifier that specifies the visibility of the class, method, or field. 
    When used with the main method, it means the method is accessible from anywhere.
-   It makes the class or method accessible to all other classes and packages.
-   If you make the main method private, Java will still compile the code. 
    However, when running the program, the Java runtime will not be able to access 
    the main method, as it's private. 
You will get a runtime error: **No main method found in class HelloWorld.**

2. **static:**

-	This keyword indicates that the method or field belongs to the class, 
rather than object of the class. 
-   The main method is static because it is invoked by the JVM when the program starts, 
 without creating an object of the class.
-	static methods can be called without creating an instance of the class.
-	If you remove the static keyword from the main method, the method will no longer be 
recognized as the entry point by the Java runtime. 
- This will result in the following error at runtime:
No main method found in class HelloWorld

3. **void:**

- This is the return type of the main method. void means that the method does not 
return any value.

4. **main**

- This is the entry point of any Java application. The Java Virtual Machine (JVM) 
  calls this method when you run the program.
- If you change the method name to something other than main, such as main1, 
the Java runtime will not recognize it as the entry point. 
- The main method must always be named main for the JVM to start execution. 
In this case, you'll get a runtime error:
No main method found in class HelloWorld
- If there is no main method, the class cannot be executed from the command line or any Java runtime environment. 
You will get an error message from the Java runtime like this:
Error: Main method not found in class HelloWorld, please define the main method as: 
public static void main(String[] args).

5. **String[] args**

- This is a parameter that represents command-line arguments. args is an array of String 
objects that can hold values passed to the program when it's run. 
The program can access and use these values.
- Example: If you run java HelloWorld arg1 arg2, then args[0] will contain "arg1" and args[1] will 
contain "arg2".
- The main method must take a String[] args parameter because it's the signature expected 
by the JVM. If you remove or change this parameter, it will not match the expected entry point. 
The program will still compile, but when you attempt to run it, you'll get the following error:
No main method found in class HelloWorld.
- If you provide the args parameter but do not use it in the method body, 
the program will still compile and run correctly. 
- The args parameter is optional for the functionality of the program. 
You can ignore it or leave it unused without any issue. 
The program will still output "Hello, World!" as expected.
- Java allows the use of "varargs" (String... args) in place of a regular array (String[] args). 
This will still work perfectly fine, and the program will compile and run successfully, 
printing "Hello, World!". This is simply a syntactic alternative to using an array.

6. **Making the class abstract or final**

**Abstract Class**: If you make the class abstract, the main method is still allowed because 
it's a static method and doesn't require instantiation of the class. 
The program will compile and run without any issue.
~~~
public abstract class HelloWorld {
    
    public static void main(String[] args) {
    
        System.out.println("Hello, World!");
    }
}
~~~

7. **Final Class**: If you make the class final, no subclassing is allowed, 
but that doesn't affect the execution of the program. 
The program will compile and run normally.
~~~
public final class HelloWorld {

    public static void main(String[] args) {
    
        System.out.println("Hello, World!");
    
    }
}
~~~

# 3. Data Members, Methods, and Types of Data Types in Java

1. **Data Members:** Data members are variables defined inside a class but outside any 
method or constructor. They hold the state of the object.

2. **Methods** : A method is a function that defines the behaviour of an object. 
It performs operations on data members or performs any specific task.

3. **Types of Data Types** 

**Primitive Data Types**: These are basic types like int, char, boolean, float, double, long, 
byte, and short

Example: int age = 25;

**Reference Data Types**: These refer to objects or arrays. They hold references (or addresses) 
to objects in memory.

Example: String name = "John";


# 3. What are Wrapper classes?

1. **Wrapper classes** in Java are object-oriented representations of the primitive data types. 
Each primitive type (like int, char, double, etc.) has a corresponding wrapper class:
~~~
int → Integer
char → Character
~~~

These wrapper classes provide methods to conversion between primitive values and objects, 
and they allow primitive types to be used in contexts where objects are required 
(e.g., in collections like ArrayList).

2. **Why do we need Wrapper classes in Java?**

- Working with Collections:
- Autoboxing and Unboxing
- Utility Methods : Integer.parseInt(), Double.valueOf(), Character.isDigit()
- Nullability: Primitive types can't be null, but wrapper classes can
Interoperability with Reflection and APIs:

3. **What are the different ways of creating Wrapper class instances?**

**Using Constructor** :
~~~
Integer intObj = new Integer(10); 
 
char Obj = new Character('A'); 
~~~
**Using ValueOf() Method**:
~~~
Integer intObj = Integer.valueOf(10); 
// Preferred 
Double doubleObj = Double.valueOf(3.14);
~~~
**Autoboxing (Automatic Conversion)**:
~~~
int primitive = 10;
Integer intObj = primitive; // Autoboxing: automatically converts int to Integer
~~~
**Using Constructor for String Conversion**:
~~~
Integer intObj = new Integer("10");
Using parse Methods (For Parsing Strings)
int primitiveInt = Integer.parseInt("100");
~~~



4. **What is Type casting**

In Java, type casting refers to the conversion of one data type to another. 
Java supports two types of type casting:

-	**Implicit Type Casting** (also called Widening Casting or Automatic Type Conversion)
-	**Explicit Type Casting** (also called Narrowing Casting or Manual Type Conversion)

**Implicit Type Casting (Widening Casting)** : 
Implicit type casting occurs automatically when you are converting a smaller data type to a 
larger data type. 
The Java compiler performs this conversion automatically without any loss of data.

Implicit Casting Rules: **byte → short → int → long → float → double**

The conversion is done automatically when converting from a smaller type to a larger type.
~~~
int num = 100;       // int type
double d = num;      // Implicit casting: int to double
~~~

**Explicit Type Casting (Narrowing Casting)**: Explicit type casting occurs when you want to 
convert a larger data type to a smaller data type. 
Java does not perform this conversion automatically because it may lead to loss of 
data or precision. You must explicitly tell the compiler to cast the value.

Explicit Casting Rules: **double → float → long → int → short → byte**

You must explicitly cast when converting from a larger type to a smaller type, 
as it can result in a loss of data or precision.
~~~
double num = 100.99;   // double type
int i = (int) num;     // Explicit casting: double to int
System.out.println(i);  // Output: 100 (fractional part is lost)
~~~


# 4. Constructor and Destructor in Java

**Constructor** : A constructor is a special method used to initialize objects. 
It is called when an object is created.

**When are Constructors Called?**
- A constructor is automatically called when an object is created using the new keyword.
- The constructor initializes the object's instance variables based on the values passed 
to it (for parameterized constructors) or assigns default values (for the default constructor).

Key Characteristics of Constructors:
-	A constructor has the same name as the class.
-	A constructor does not have a return type (not even void).
-	A constructor is automatically invoked when an object is created using the new keyword.
-	A constructor is used to initialize objects.
-	Constructors do not return values.
-	If no constructor is explicitly defined, Java provides a default constructor that initializes fields to their default values.
-	A parameterized constructor is a constructor that takes one or more arguments. It is used when you need to provide different initial values for the object attributes when creating an object

**In Java, there are two types of constructors:**
1.	**Default Constructor** (No-Argument Constructor)
2.	**Parameterized Constructor**

**Constructor Overloading**

Java allows constructor overloading, which means you can define multiple constructors with 
different parameter lists within the same class. This enables you to create objects in 
different ways, depending on what parameters you pass.

**Destructor** : Java does not have explicit destructors. 
Instead, it has garbage collection, which automatically manages memory and removes 
objects that are no longer in use. 
The finalize() method is called by the garbage collector before an object is destroyed 
(though its use is discouraged).



# 5. Access Specifiers and Access Modifiers in Java

**Access Specifiers:**

- **Public**: The member is accessible from any class.
- **Private**: The member is accessible only within the class it is defined.
- **Protected**: The member is accessible within the same package and subclasses.
- **Default (no specifier)**: The member is accessible only within the same package.

**Access Modifiers:**

public, private, protected, and default are also considered access modifiers. 
In addition, we have:

- **static**: Makes the member belong to the class rather than any instance.
- **final**: Used to declare constants, prevent method overriding, or prevent inheritance.
- **synchronized**: Ensures that only one thread can access the method or block at a time.
- **volatile**: Ensures that a variable is directly read from or written to the main memory.
- **transient**: Prevents a field from being serialized.

# 6. this() and super() in Java

**this() Keyword**:

The this() keyword is used to call a constructor of the current class. 
It helps in constructor chaining — invoking one constructor from another within the same class.

**Key Features and Concepts of this()**
1.	**Constructor Chaining:** 
-   this() is used to call another constructor of the same class. This must be the first statement in the constructor body.
2.	**Purpose**:
      -	this() helps initialize the object using a different constructor, 
        making the code more maintainable and concise.
      - It is used to delegate the initialization of an object to another constructor in 
       the same class.
3.	**Constructor Overloading:**
      - In a class, you can have multiple constructors with different parameter lists. 
        You can use this() to call a constructor with different arguments.
4.	**Usage**: Call another constructor within the same class:
5.	**Limitation**: The this() constructor call must be the first statement in a constructor.

6. **When to Use this():**
   - To avoid repetition of constructor code.
   - When you have multiple constructors with different parameters but want to 
     initialize the same state in the object.

**super() Keyword**:
The super() keyword refers to the parent class (superclass) and is used in two major contexts: 
**calling the parent class constructor and invoking parent class methods.**

Key Features and Concepts of **super()**
1.	**Calling Parent Class Constructor**:
      - super() is used to call the constructor of the parent class. 
      - It must be the first statement in the child class constructor.
      - If no explicit call to super() is made, the default constructor of the 
      superclass is called automatically (if it exists).
2.	**Accessing Parent Class Methods and Variables**:
      - You can use super to call parent class methods or access parent class fields 
       if they are hidden or overridden in the child class.
      - It is especially useful when a method is overridden, and you want to call 
      the parent class method.
3.	**Constructor Chaining Across Classes**:
      - In a class hierarchy, super() can be used to chain constructor calls from the 
      subclass to the superclass. 
      - This allows proper initialization of the inherited part of the object.
4.	**Usage**:
      - Calling the superclass constructor:
5.	**Accessing Parent Class Fields and Methods:**
      - If a field or method in the child class hides or overrides a field or method in 
       the parent class, you can use super to access the parent class's version.

**Important Concepts and Behavior:**
1.	**super() vs this():**
      - this() calls a constructor in the same class, while super() calls the constructor of the superclass.
      - You cannot use both this() and super() in the same constructor, 
       because both are constructor calls, and Java allows only one constructor call 
      in the beginning of a constructor.
      
2.	**Calling Parent Constructor Implicitly**:
      - If you don’t explicitly call super(), the default constructor of the parent class is 
       called automatically.
      - If the parent class doesn’t have a default constructor, you must explicitly call a 
      constructor of the parent class using super(<arguments>).
3.	**Accessing Parent Members**:
      - super is particularly useful to access members (fields, methods) that are hidden or 
      overridden in the subclass.
4.	**Constructor Chaining Across Classes:**
      - Constructor chaining occurs when a constructor calls another constructor 
      (either within the same class using this() or from the parent class using super()).

**Tricky and Complex Concepts:**
1. It’s important to note that constructors in Java do not inherit from the parent class. 
2. Each class must explicitly define its own constructor. 
 You use super() to invoke a constructor from the parent class.
3. Constructor of Abstract Classes:
      - In case the parent class is abstract, you still need to call its constructor 
        explicitly using super(). 
      - The abstract class constructor will still run, but you cannot instantiate 
        the abstract class directly.
3.	Constructor Overloading and Inheritance:
      - In case of constructor overloading, the choice of which constructor to call (using this() or super()) 
        depends on the arguments passed during object creation.
4.	Multiple Inheritance in Java:
      - Java doesn’t support multiple inheritance via classes (you can use interfaces for that), 
       but the super() keyword still ensures that only one parent class constructor 
       is invoked in a single inheritance hierarchy.

**Interview Questions on this() and super():**
1.	What is the difference between this() and super()?
- this() calls a constructor of the same class, while super() calls a constructor of the superclass.

2. Can you call this() and super() in the same constructor?
- No, you cannot call both this() and super() in the same constructor. 
Only one constructor call is allowed, and it must be the first statement in the constructor.

3.	What happens if you don’t explicitly call super() in a constructor?
- If you don't explicitly call super(), the default constructor of the superclass is called implicitly, 
if the superclass has a no-argument constructor.

4.	Can super() be used to call a constructor from the parent class with arguments?
- Yes, super() can be used to call a constructor of the parent class with arguments, 
like super(arg1, arg2).

5.	Can you access the private members of a parent class using super?
- No, super cannot access private members of the parent class. It can only access public or 
protected members of the parent class.

6.	Is it possible to call the constructor of the superclass without using super()?
- Yes, but only if the superclass has a no-argument constructor. 
In this case, it is called automatically.
      
7.	What will happen if you try to call super() after this() in a constructor?
      - It will result in a compile-time error, as Java only allows one constructor call 
       (super() or this()) in a constructor, and it must be the first statement.
      
8.	Can we use this to refer to another object of the same class?
- Yes, this refers to the current instance of the class, but it can also be passed to methods or 
 constructors of the same class as an argument.

# 7. Different Keywords in Java

# 7.1 Static keyword

The static keyword in Java used to define class-level members (variables, methods, blocks, etc.) 
that are shared by all instances of the class rather than tied to individual objects.

**Summary**:

- The static keyword can be applied to variables, methods, blocks, inner classes, etc.
- It is used for memory management and to ensure that certain properties are shared across 
 all instances of a class.
- You cannot override static methods, but you can overload them.
- You cannot declare an interface or an abstract class as static.
- Static members can be used with other keywords like final, volatile, transient, etc., 
 with specific constraints and behaviors.


**Static Variable (Class Variable):**
- A static variable is shared by all instances of the class.
- It is initialized only once when the class is loaded into memory and is common 
  for all objects of that class.
- All instances of the class share the same static variable, so any changes made to 
  the static variable affect all objects.
- Static variables can be accessed using the class name or the object name, 
  but using the class name is recommended.

**Static Method :**
- A static method belongs to the class rather than instances of the class. 
- It can be called without creating an object of the class.
- Static methods can access only static variables and static data members of the class.
- Static methods cannot access instance variables or instance methods directly.
- Static methods can be called using the class name (preferred) or through an object. (Thread.start())
- Instance methods (non-static methods) belong to an instance of the class, and 
you need an object to call them.
- We can access a static method using an object of a class, but this is generally considered poor practice

**Can We Override and Overload Static Methods ?**

**No**, **static methods cannot be overridden** because they are bound to the class rather 
than to an instance of the class. When you declare a static method in a subclass with 
the same signature as a static method in the superclass, 
it is considered **method hiding (not overriding)**.

**Yes**, **static methods can be overloaded**. 
Overloading is when you have multiple methods with the same name but different parameter lists.

**Static Block:**
- A static block is used for static initialization of a class. 
- It is executed only once when the class is loaded into memory.
- Static blocks are used to initialize static variables or perform other one-time operations 
during class loading.
- It is executed before the main method or any static methods.
- It is executed only once, even if multiple objects are created.

**Static Class:**

- In Java, static classes are inner classes (nested classes) that are declared with 
the static keyword.
- A static nested class can access static members of the outer class.
- A static class can be instantiated without an instance of the outer class.
- It cannot access instance members of the outer class.

**Can We Make an Interface Static ?**

**No, interfaces cannot be declared as static in Java**. 
An interface is implicitly static because all its members (constants and abstract methods) 
are implicitly static. 

However, **you can have static methods in an interface since Java 8**.

**Can We Make an Abstract Class Static ?**

**No, an abstract class cannot be declared static**. 
The static keyword is used with nested classes (inner classes) and does not apply 
to top-level classes like abstract classes.

**How to Use Static Keywords with Variable, Method, and Class**

1. **When to Use Static with Variable** :
-	Use static variables when you want them to be shared among all instances of the class.
-	Example: Counter for tracking the number of instances of a class

2. **When to Use Static with Method:**
-	Use static methods for operations that do not depend on the instance of the class.
-	Example: Utility functions like Math.sqrt()
     When to Use Static with Class:
-	Use static classes when the nested class does not require an instance of the outer class.

**Static Keyword with Other Keywords :**

1. **Static and Final**:
-	A static final variable is a constant, meaning it cannot be changed once initialized.
-	A static final method cannot be overridden but can be called using the class name.

2. **Static and Volatile:**
Volatile and static are typically used together when you need a variable to be shared 
across threads and modified in a thread-safe manner. 

    - A volatile static variable is a shared variable that can be accessed and modified by multiple 
threads.

3. **Static and Transient:**
The transient keyword prevents a field from being serialized, but it can still be static. 
Static fields are not serialized because they are part of the class, not the object instance.

**Can we instantiate a static class?**

- **Yes**, you can instantiate a static nested class without creating an instance of the outer class.

**What happens if you declare a static method inside an instance method?**
- This is not allowed. Static methods can only be declared inside a class or interface, 
  not within instance methods or constructors.

**Can we access non-static members of a class from a static context?**

No, you cannot directly access non-static members (variables or methods) from a static context. 
You would need to create an instance of the class to access non-static members.

**What is the behavior of static variables in multithreading?**

Static variables are shared among all threads, which can lead to issues in 
multi-threaded applications if they are not handled properly (e.g., using synchronization).

**Can you initialize static variables inside the constructor?** 
No, static variables should be initialized in the static block or at the point of 
declaration, not inside constructors.


# 7.2 Final keyword 

**Final keyword** Used to define constants (variables that cannot change), 
prevent method overriding, or prevent inheritance.

**Summary**

-	The final keyword in Java ensures immutability and prevents modification in various 
    contexts (variables, methods, classes).
-	**Final Variables**: Constants or values that can only be assigned once.
-	**Final Methods**: Methods that cannot be overridden by subclasses.
-	**Final Classes**: Classes that cannot be subclassed.
-	**Final with Other Keywords**: Can be used with static, volatile, and transient for additional behavior (e.g., thread safety, constant values).

**final with Variables :**

-	When a variable is declared as final, it means that its value cannot be changed once 
    it has been initialized.
-	A final variable can only be assigned once, either during initialization or in 
    the constructor if it is an instance variable.
-	If a reference type variable is declared final, the reference itself cannot be 
    changed to point to another object, but the object that the reference points to 
    can still be modified (if mutable).
-	Local variables inside methods can also be declared final, meaning their values 
    cannot be changed after initialization.

**final with Methods:**

-	A final method cannot be overridden by subclasses. 
-   It can be used to ensure that the method behaviour is not modified
-	A final method is guaranteed to retain its behaviour across subclasses.
-	It Prevent Method Overriding
-	Final Methods in Inheritance, The method will always execute the same way, 
    no matter what class calls it, and can't be changed by subclasses

**final with Classes:**

-	A final class cannot be subclassed. This is useful when you want to prevent inheritance 
    for security or design reasons.
-	**Preventing Inheritance**: A final class cannot have any subclass. It cannot be extended.
-	Common Usage: The String class in Java is final, meaning you cannot subclass it.

**final with Interfaces:**

-	You cannot declare an interface as final because interfaces are designed to be implemented 
    by other classes. 
-   The concept of "no inheritance" is not applicable to interfaces.
-	Java does not allow interfaces to be declared final.
-	If you want to restrict the implementation of a certain method in an interface, 
    you can use default methods and make them final (but this is rarely done).


**final with Abstract Classes:**

-	You cannot declare an abstract class as final because an abstract class is 
    designed to be subclassed, and final prevents inheritance.
-	Since abstract classes are meant to be extended, they cannot be declared final.
-	An abstract class can be used as a template for subclasses, and final would 
    contradict this purpose.

**Can We Override and Overload final Methods?**

**No, final methods cannot be overridden in subclasses.** 
The purpose of declaring a method final is to lock the behaviour and prevent any subclass 
from changing it.

**Yes, you can overload a final method.** 
Overloading is based on method signatures (parameters), and it doesn't change the behaviour 
of the existing method.


**How to Use and When to Use the final Keyword**

**When to Use final with Variables**:
-	**Constants**: To define constant values that should not change, e.g., PI, MAX_SIZE, etc.
-	**Thread Safety**: Final variables in multi-threaded environments are automatically 
     thread-safe after initialization because their values cannot change.
-	**Ensuring Initialization**: Final instance variables must be initialized in the constructor 
    or at the point of declaration. This is helpful for creating immutable objects.

**When to Use final with Methods:**
-	**Prevent Method Overriding**: Use final when you want to ensure that a method cannot be overridden by any subclass (for example, to maintain security or consistency of behavior).
-	**Performance Optimization**: Some JVMs can optimize final methods better, especially in cases like method dispatch.
     When to Use final with Classes:
-	**Prevent Inheritance**: Use final when you want to prevent a class from being subclassed. This can be important for security or if you want the class to function as a singleton (like String in Java).


**final Keyword with Other Keywords**

**final and static:**
-	**Final Static Variables**: A final static variable is a constant that is shared across 
    all instances of the class. It cannot be changed after initialization
-	**Final Static Methods**: A final static method cannot be overridden or changed by subclasses.
     final and volatile:
-	**Final Volatile Variables**: A final volatile variable guarantees that once the variable is 
    assigned a value, its value is visible to all threads. 
    The value of the variable cannot change once set. final and transient:
-	**Final Transient Variables**: You can declare a final transient variable, 
    but it means the value of the final variable will not be serialized.

**Tricky Questions and Answers on final:**

**Can we initialize a final variable multiple times?**

No, a final variable can only be assigned once, either in the constructor 
(for instance variables) or at the point of declaration.

**What happens if a final variable is initialized in a constructor?**

If a final variable is initialized in a constructor, 
it can be different for each instance of the class, 
but it can still only be assigned once per instance.

**Can we create an array of final objects?**

Yes, but while the reference to the array is final (i.e., you cannot reassign the reference), 
the elements of the array can still be modified if they are mutable objects.
~~~
Example:

    final int[] arr = new int[5];
    arr[0] = 10;  // This is allowed
    arr = new int[10];
    // Compile-time error: cannot assign a new array to final variable arr
~~~

**Can a final class have a constructor?**
Yes, a final class can have a constructor. 
Declaring a class final just prevents subclassing but doesn't affect the ability to 
initialize instances of the class.

**Can we extend a final class and implement its final methods?**

**No**, you cannot extend a final class, and you cannot override its final methods. 
However, you can still call the final methods from the subclass.

**Can we make a method final and synchronized at the same time?**

Yes, you can declare a method final and synchronized together. 
A final method is just one that cannot be overridden, and synchronized ensures that only 
one thread can access it at a time.
~~~
Example:
class Example {
    final synchronized void display() {
        
        System.out.println("Thread-safe and non-overridable method");
    }
}
~~~


# 7.3 Volatile keyword in java

Volatile keyword is Used for variables that can be modified by multiple threads simultaneously. 
It ensures that the most up-to-date value is always used.

The volatile keyword in Java is used primarily in multithreading to ensure that changes to a 
variable are visible to all threads. 
It guarantees that when one thread modifies the value of a volatile variable, 
the updated value is immediately visible to all other threads.

However, the volatile keyword has specific usage rules, and it cannot be applied 
to methods or classes directly.
~~~
volatile boolean flag = false;
~~~

**Summary**
-	The volatile keyword ensures that changes to a variable are visible to all threads.
-	It is only applicable to variables, not methods, classes, or blocks.
-	Use volatile when you need visibility across threads for simple variables, such as flags or state indicators.
-	Combine volatile with synchronized or atomic variables when you need atomicity for compound operations.
-	It is not a substitute for synchronization in complex multithreaded applications.


**What is the volatile Keyword?**

The volatile keyword in Java is applied to instance variables to indicate that the variable's 
value may be modified by multiple threads. 
It ensures that the most recent value of the variable is always visible to all threads, 
and prevents the thread from caching the value locally.

**Key Features** :

-	**Visibility Guarantee**: It ensures that the value of the variable is always read from and 
    written to the main memory, preventing the local thread's cache from keeping stale copies 
    of the value.
-	**Atomicity**: The volatile keyword guarantees that reads and writes to a volatile variable 
    are atomic (i.e., the operations are completed entirely or not at all). 
    However, only writes and reads of single variables are atomic. Operations like increment (i++) 
    are not atomic even on volatile variables.
-	**No Synchronization**: While volatile ensures visibility, it does not provide atomicity 
    for compound actions (like incrementing or checking and then updating). 
    It doesn't guarantee mutual exclusion or thread-safety for complex operations


**Can We Apply volatile to Methods, Blocks, or Classes?**

No, we can not apply volatile to methods, blocks and classes.

**volatile with Methods:**

You cannot apply the volatile keyword to a method. The volatile keyword is only applicable to variables. You cannot use volatile on methods because it doesn't make sense in the context of method invocation or behaviours.

**volatile with Blocks:**

There is no concept of a volatile block in Java. The volatile keyword can only be applied to variables. Synchronization blocks (e.g., synchronized blocks) are typically used to ensure atomicity and mutual exclusion.

**volatile with Classes:**

You cannot declare a class as volatile. The volatile keyword is only used for variables, 
not for classes or methods.


**Can We Overload or Override volatile Methods?**

you cannot apply the volatile keyword to a method, so cannot override  or overload a 
volatile method because volatile is not a feature of methods. 
It's a modifier for variables

**Can We Make a Class volatile?**

No, you cannot declare a class as volatile. 
The volatile keyword can only be applied to variables (fields). 
Classes cannot be declared as volatile.

**Can We Inherit a volatile Class?**

Since volatile cannot be applied to a class, the question of inheriting a volatile 
class is not applicable. However, if a class contains volatile fields, 
subclasses will inherit those fields and can interact with them accordingly.

**Can We Make an Interface volatile?**

No, interfaces cannot be declared as volatile because volatile applies only 
to instance variables. 
Interfaces are blueprints for classes and do not contain instance variables, 
making the volatile keyword irrelevant for interfaces.


**Can We Make an Abstract Class volatile?**

No, abstract classes cannot be declared as volatile either. 
Similar to interfaces, abstract classes may have volatile fields, 
but the class itself cannot be declared as volatile.



**How to Use and When to Use the volatile Keyword**

**When to Use volatile with Variables:**
-	**Shared Variables** : Use volatile for variables that are shared among multiple threads. 
    This ensures that when one thread changes the value, all other threads 
    immediately see the updated value.
-	**Flags/Flags for Communication**: The most common use of volatile is for flags that indicate the 
    state of a task or for signalling between threads (e.g., stopping a thread).
-	**Performance Considerations**: In cases where synchronization might be too expensive, and only 
    visibility (not atomicity) is needed, volatile is more lightweight than using locks 
    (synchronized blocks).

**When Not to Use volatile:**
     **Complex Operations**: If your code requires atomicity for complex operations 
     (like incrementing a value), you should not use volatile because it only guarantees visibility, 
     not atomicity. Use synchronized blocks or java.util.concurrent classes instead.

**volatile with Other Keywords**

**volatile and static:**
- **Static Volatile Variables**: You can use volatile with static variables to ensure that the value 
  of the static variable is immediately visible across all threads.

**volatile and final:**
- **Final Volatile Variables**: A final volatile variable is usually used when you need to ensure 
  that the value is set once and is visible across all threads.

**volatile and transient**:  
- **Transient Volatile Variables**: A transient volatile variable can be used when the variable should 
  not be serialized but still requires visibility across threads. 
  The transient keyword prevents the variable from being serialized, while volatile ensures visibility 
  across threads during runtime. 
~~~
transient volatile int count;
~~~

**volatile and synchronized:**
- **Combining volatile and synchronized**: volatile provides visibility, while synchronized provides 
  both visibility and atomicity. When you need both, you can combine volatile for visibility and 
  synchronized for atomicity.

~~~
class Counter {
    private volatile int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}
// The synchronized keyword ensures that the increment operation is atomic, 
while the volatile keyword ensures that the latest value of count is always 
visible across threads.
~~~

**Tricky Questions on volatile**
1.	**Is volatile thread-safe?**
- No, volatile ensures visibility, not atomicity. For compound operations like increment  (i++), 
  you need to use synchronization or atomic classes from java.util.concurrent.

2.	**What happens if a volatile variable is updated by one thread but read by another?**
- The update will be immediately visible to other threads. However, if you're performing a 
  complex operation (e.g., read-modify-write), you need synchronization or atomic variables.

3.	**Can we use volatile to make a variable thread-safe?**
- No, volatile only provides visibility guarantees, not thread-safety for compound operations. 
  For thread-safety of complex actions, use synchronization or atomic classes.

4.	**What happens if we use volatile with a reference type variable?**
- If you use volatile with a reference variable (like an object), the reference itself is guaranteed 
  to be visible across threads. However, the object's internal state (i.e., fields of the object) 
  is not automatically synchronized or visible unless explicitly synchronized or volatile at 
  the object level.

5.	**Can volatile be used for arrays or collections?**
- You can declare an array or collection as volatile, but this only guarantees visibility of the 
  reference to the array or collection object, not the contents of the array or the 
  state of the collection. 
  If the array or collection's state is modified (e.g., adding/removing elements), 
  you need additional synchronization to ensure thread-safety.


# 7.4 Transient keyword :

**Transient keyword** Used to indicate that a field should not be serialized

The transient keyword in Java is used in serialization to indicate that a specific 
field should not be serialized. It is primarily used when you want to exclude certain 
fields of an object from being written to a stream during the serialization process.

**Summary**
-	The transient keyword is used to prevent fields from being serialized.
-	transient is only applicable to instance variables (fields), not methods, classes, or blocks.
-	It is commonly used to exclude sensitive or non-essential data from serialization, such as passwords, session data, or cached information.
-	transient does not affect static fields, as static fields are not part of the serialization process.
-	You can combine transient with other keywords like final, volatile, and static based on the requirements of the field.

**What is the transient Keyword?**

The transient keyword is used in Java to mark fields of a class as non-serializable. 
When an object is serialized (i.e., converted into a byte stream for storage or transmission), 
the fields marked with transient will not be included in the serialization process. 
This is useful when you want to avoid serializing sensitive information (e.g., passwords) or 
derived values that can be recalculated.

**Key Features:**
-	**Prevents Serialization**: When you mark a variable as transient, it is not serialized when the 
    object is serialized.
-	**Serialization**: Serialization is the process of converting an object into a byte stream so 
    that it can be saved to a file, sent over a network, or persisted. transient helps exclude 
    unnecessary or sensitive data.
-	**Default Values for Transient Fields**: When deserialized, transient fields are assigned their 
    default values (null for reference types, 0 for numeric types, false for boolean, etc.), 
    unless explicitly restored during deserialization.

**Can We Apply transient to Methods, Blocks, or Classes?**

No, we can not apply transient to Methods, Blocks and Class.

**transient with Methods:**
-	No, the transient keyword cannot be applied to methods. It is only applicable to instance variables.
-	The purpose of transient is to indicate that a field should not be serialized, and methods do not 
    participate in the serialization process. Methods are not serialized.

**transient with Blocks:**
-	There is no concept of a transient block in Java. You can only use transient with fields (variables), 
 not blocks.

**transient with Classes:**
-	You cannot declare a class as transient.
-	You can have transient fields in a class, but you cannot mark the entire class as transient.


**Can We Overload or Override Methods with transient?**

No, the transient keyword cannot be applied to methods. It is only applicable to instance variables.
**Overloading a transient method is possible**, but the transient modifier does not apply to methods—only fields
**You cannot override a method based on transien**t because it's not part of the method signature.

**Can We Make a Class transient?**

No, you cannot apply transient to a class. 
The transient keyword is only for instance variables, not classes or methods. 
A class, by definition, is a template or blueprint for objects, and serialization concerns 
individual object fields, not the class itself.

**Can We Inherit a transient Class?**

the transient modifier applies to the fields of the parent class but is not 
inherited by the subclass fields.
You can inherit from a class with transient fields, 
but the transient keyword on the fields of the parent class will not affect 
the fields in the subclass.
If the subclass has fields marked transient, 
those fields will also not be serialized when the object is serialized.

**Can We Make an Interface transient?**

No, you cannot declare an interface as transient. 
The transient keyword applies only to fields (variables) in a class and not to 
classes or interfaces themselves.

**Can We Make an Abstract Class transient?**

No, you cannot declare an abstract class as transient. 
As mentioned, transient is only used to mark instance variables as non-serializable. 
You cannot use transient for the class itself, whether it's abstract or concrete.
However, an abstract class can have transient fields, which will not be serialized when 
objects of a subclass are serialized.

**When to Use the transient Keyword**

**When to Use transient with Variables:**
- **Sensitive Data**: Use transient to prevent sensitive information like passwords, 
  personal identification numbers (PINs), or credit card details from being serialized.
- **Derived/Calculated Fields**: If a field's value can be derived or recalculated when needed, 
  and doesn't need to be stored during serialization, mark it as transient.
- **Large Fields**: If a field contains a large object (e.g., a huge array, cache, or connection pool) 
  that you don't need to serialize, you can mark it as transient to reduce the size of the 
  serialized object.

**When Not to Use transient:**

When You Need the Field Serialized: If a field must be serialized for object restoration 
during deserialization, you should not mark it as transient.

**transient Keyword with Other Keywords :**

**transient and static**: A static transient variable does not make much sense because static 
variables are shared across all instances of the class and are not part of the instance 
serialization process. Serialization is for object state, and static variables do not belong to instances of a class but rather to the class itself.

**transient and volatile:**
The transient and volatile keywords can be used together, but they have distinct roles:

-	volatile ensures that changes to a variable are visible across all threads immediately.
-	transient ensures that a variable is not serialized.

**transient and final:**
-	final and transient can be used together.
-	A final transient variable can be useful when you want to ensure the field's value is not changed after initialization but should not be serialized.

**transient and synchronized:**
-	transient is unrelated to synchronization.
-	While transient affects the serialization of a field, synchronized affects thread safety by controlling access to shared resources.
-	These two keywords typically do not interact directly.

**Tricky Questions on transient**
1.	**What happens when a transient field is deserialized?**
- When an object is deserialized, transient fields are not restored to their original value. 
 Instead, they are initialized to their default values (e.g., null for reference types, 
0 for numeric types).

2.	**Can we serialize a transient field manually during deserialization?**
- Yes, you can manually restore the value of a transient field during the readObject method by 
implementing custom deserialization.
3.	**Does transient affect the deserialization of object graphs (fields of objects)?**
- No, transient only affects the field it is applied to. If an object is a field of another object, 
it will still be serialized unless its own fields are marked as transient.

4.	**What happens if you serialize an object with transient fields and the class structure changes?**
- If the class structure changes (e.g., fields are added or removed), and you try to deserialize 
an object that has transient fields, the default values for transient fields will be used. 
- If the class is incompatible (e.g., fields have been renamed or removed), it may lead to an 
**InvalidClassException.**

# 7.5 Constants 
**Constants** are typically defined using the final keyword to ensure the value cannot change

# 7.6 Inner Class and Outer Class in Java


**Outer Class**:
- An outer class is the main class that can contain inner classes. 
- It exists independently and can contain any other class, method, or variable.

**Inner Class:**
- An inner class is a class defined within another class. 
- It can access the members (including private) of its enclosing class.

~~~
class Outer {
    class Inner {
        
        void display() {
        System.out.println("Inside Inner class");
        
        }
    }
}
~~~

**The constructor of an outer class is invoked before the inner class constructor when 
creating an instance of a non-static inner class.**

In Java, inner classes are classes that are defined within another class, known as the outer class. 
These inner classes can access the members (fields, methods) of the outer class, including private members. 

Inner classes are used to logically group classes and increase the readability of the code, 
as well as to encapsulate the implementation of a class that 
doesn’t need to be exposed to the outside world.

**Types of Inner Classes in Java**
1.	Non-static Inner Class (Member Inner Class)
2.	Static Nested Class
3.	Local Inner Class
4.	Anonymous Inner Class

**Features and Properties of Inner and Outer Classes**
-	**Encapsulation**: Inner classes can encapsulate the logic of the outer class and can be used to 
    hide certain implementation details from the outer world.
-	**Access to Outer Class Members**: Non-static inner classes can access all the members 
    (private or public) of the outer class.
-	**Memory Efficiency**: Static nested classes do not need a reference to the outer class, 
    which makes them memory-efficient.
-	**Nested Classes and Object**-Oriented Design: Inner classes are useful for representing a part 
    of a class hierarchy or a behavior that naturally belongs to a specific outer class.
-	**Type Safety**: Inner classes are typically type-safe, meaning they can be used for specific 
    purposes like creating event handlers, comparators, etc.

**1. Non-static Inner Class (Member Inner Class)**

A non-static inner class is associated with an instance of the outer class. 
It can access all the members (including private members) of the outer class.

Key points:
- Cannot have static members.
- Needs an instance of the outer class to create an instance of the inner class.
~~~
class Outer {
    
    private int outerData = 10;

    class Inner {
        void display() {
            System.out.println("Outer data: " + outerData);
        }
    }
}
~~~

**2. Static Nested Class**

A static nested class is not associated with an instance of the outer class. 
It can only access static members of the outer class

Key points:
- Can have static members.
- Can be accessed without an instance of the outer class.
~~~
class Outer {
    
    static int outerData = 10;

    static class Inner {
        void display() {
            System.out.println("Outer data: " + outerData);
        }
    }
}
~~~

**3. Local Inner Class**

A local inner class is defined within a method or a block of code inside the outer class. 
It can access the local variables and parameters of the method but only if they are 
declared final or effectively final (**from Java 8 onwards**).
~~~
class Outer {

        void outerMethod() {
            final int num = 5;
    
            class LocalInner {
                void display() {
                    System.out.println("Number: " + num);
                }
            }
    
            LocalInner localInner = new LocalInner();
            localInner.display();
       }
}
~~~

**4. Anonymous Inner Class**

An anonymous inner class is a class without a name, defined and instantiated in a single statement. 
It is often used for implementing interfaces or extending classes on the fly.
~~~
class Outer {
    void display() {
        
            // Anonymous inner class implementing Runnable interface
            Runnable r = new Runnable() {
        
            public void run() {
                System.out.println("Running in anonymous class");
                }
           };
        r.run();
    }
}
~~~

**Keywords and Concepts Related to Inner and Outer Classes**

1.	**static Keyword:**
- Used for static nested classes that do not need an instance of the outer class to be instantiated.
2.	**this Keyword**:
- In the context of an inner class, this refers to the current instance of the inner class, 
  not the outer class.
- To access the outer class’s instance, use OuterClassName.this.
3.	**super Keyword**:
- Can be used to invoke the constructor or methods of the outer class from the inner class.
4.	**final Keyword (for local inner classes)**:
- Local variables and parameters must be final or effectively final to be used inside a local inner class.
5.	**abstract and interface with Inner Classes:**
- Inner classes can implement interfaces or extend abstract classes. 
  This is useful for creating specialized behavior tied to the outer class.
- 
6.	**private and protected Access Modifiers**:
- Inner classes can access all members of the outer class, even those marked private.

7.	**Constructor of Inner Classes:**
- Inner classes can have their own constructors, and non-static inner classes can have a 
reference to the outer class’s instance.

8.	**Inheritance with Inner Classes**:
- Inner classes can inherit from other classes or implement interfaces.

**Tricky and Complex Concepts**

1.	**Accessing Outer Class Members from Inner Class**:
- An inner class can access both the instance members and static members of the outer class. 
- However, a static nested class can only access static members of the outer class.

2.	**Memory Overhead with Inner Classes**:
- Non-static inner classes maintain an implicit reference to the outer class instance, which can increase memory overhead.
- Static nested classes do not have this overhead, making them more memory-efficient.

3.	**Serialization of Inner Classes:**
- Inner classes can be serialized, but if the outer class is not serializable, 
  the inner class may need to handle the serialization of the outer class reference.

4.	**Effectively Final Variables in Local Inner Classes:**
- Java 8 introduced the concept of effectively final variables, which means variables that 
  are not explicitly declared as final but are not reassigned after their initialization.

5.	**Anonymous Inner Classes and Lambdas:**
- Anonymous inner classes are often used for one-off implementations, but with Java 8 and beyond, 
lambdas provide a more concise and flexible way to handle functional interfaces.

6.	**Anonymous Inner Classes and Constructor Invocation:**
- Anonymous inner classes cannot have explicit constructors, 
so they must be instantiated with an initializer block or directly when creating an object.

**Interview Questions on Inner Classes and Outer Classes**

1.	**What is the difference between a non-static inner class and a static nested class?**
- A non-static inner class is associated with an instance of the outer class and can 
access instance members of the outer class. 
A static nested class is not associated with any outer class instance and 
can only access static members of the outer class.

2.	**Can an inner class access the private members of the outer class?**
- Yes, an inner class can access both private and public members of the outer class, 
whereas a static nested class can only access static members of the outer class.

3.	**What is an anonymous inner class and when would you use it?**
- An anonymous inner class is a class without a name that is defined and instantiated in one go. 
It is typically used for implementing interfaces or extending classes for short-lived objects, 
especially in event handling or concurrency contexts.

4.	**What is the difference between a local inner class and an anonymous inner class?**
- A local inner class is defined within a method and can have a name, while an anonymous 
inner class does not have a name and is used for one-off implementations.

5.	**Can an inner class be static? If yes, how does it differ from a regular inner class?**
- Yes, an inner class can be static. A static nested class can be instantiated without 
an instance of the outer class and can only access static members of the outer class. 
Regular (non-static) inner classes require an instance of the outer class and can access 
both instance and static members.

**6.	What is the significance of the this keyword in an inner class?**
- In a non-static inner class, this refers to the instance of the inner class. 
- To access the outer class's instance, we use OuterClassName.this.

**7.	What is the role of the final keyword in a local inner class?**
- Local variables and method parameters used within a local inner class must be 
final or effectively final, meaning they cannot be modified after they are initialized.

**8.	Can an interface be an inner class in Java?**
- Yes, an interface can be an inner class, and it can be static or non-static. 
- A static inner interface is independent of an instance of the outer class, 
while a non-static inner interface is tied to the instance of the outer class.

9.	**How can you prevent an inner class from accessing the outer class’s members?**
- By using access modifiers such as private for the outer class members, 
  or by designing the inner class as a static class that does not need access to instance members.

10.	**Can you use the super keyword in an inner class to refer to the outer class?**
- Yes, but the super keyword refers to the parent class of the inner class. 
To refer to the outer class, use OuterClassName.this



