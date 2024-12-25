# Collection in JAVA

Collection in Java is a framework that provides an architecture to store and manipulate the group of objects.
Java Collections can achieve all the operations that you perform on a data such as 
**searching, sorting, insertion, manipulation, and deletion.** 

Java Collection means a single unit of objects.
Java Collection framework provides many interfaces and classes.  

**Interfaces : 	Set, List, Queue, Deque, SortedSet, Collection, Iterable, Iterator**

**Classes    : ArrayList, Vector, LinkedList, PriorityQueue, HashSet, LinkedHashSet, TreeSet**

# What is Collection in Java?
A Collection represents a single unit of objects, i.e., a group.

# What is a framework in Java?
A framework provides a ready-made structure of classes and interfaces for building software applications efficiently. 
It simplifies adding new features by offering reusable components that perform similar tasks, and eliminating the need 
to create a framework from scratch for each new project. 
This approach enhances object-oriented design, making development quicker, more consistent, and reliable.
-	It provides readymade architecture.
-	It represents a set of classes and interfaces.

# What is Collection framework ?
The Collection framework represents a unified architecture for storing and manipulating a group of objects. 
It enhances code efficiency and readability by offering various data structures, including arrays, linked lists, trees, 
and hash tables, tailored to different programming needs. 
It has:
1.	Interfaces and its implementations, i.e., classes
2.	Algorithm

# Why Collection Framework?

Before the Collection Framework was introduced in JDK 1.2, Java's approach to collections was using Arrays, Vectors, 
and Hash tables lacked a common interface. This meant each type of collection had its own set of methods, syntax, and 
constructors, with no standardization or correlation between them.

This made it difficult for users to remember the diverse functionalities of each collection type and hindered code 
consistency and reusability. The disparate nature of these collections highlighted the need for a unified 
Collection Framework to simplify and standardize collection operations in Java.

# Advantages of the Java Collection Framework
The Java Collections Framework offers significant advantages that enhance development practices, code quality, and 
application performance:
1.	Reusability
2.	Quality
3.	Speed.
4.	Maintenance
5.	Reduces Effort to Design New APIs

# Iterable Interface
The Iterable interface is the root interface for all the collection classes.
The Collection interface extends the Iterable interface and therefore all the subclasses of Collection interface also 
implement the Iterable interface.
It contains only one abstract method. i.e.,
~~~ 
Iterator<T> iterator() : It returns the iterator over the elements of type T. 
~~~  

# Iterator interface 
Iterator interface provides the facility of iterating the elements in a forward direction only.
There are only 3 methods in the Iterator interface.

~~~
public boolean hasNext() : It returns true if the iterator has more elements otherwise it returns false.

public Object next() : It returns the element and moves the cursor pointer to the next element.

public void remove() : It removes the last elements returned by the iterator. It is less used.
~~~


# Differences between Iterable and Iterator Interface

**Iterable:**  Allows an object to be traversed (iterated) using an Iterator. It defines a single method, iterator(), 
which returns an Iterator for the collection. It is typically implemented by collection classes (e.g., List, Set) and 
custom classes that need to provide iteration functionality.

**Iterator:** Provides the actual mechanism for traversing the collection. It has methods like hasNext(), next(), and 
remove() for accessing and manipulating elements during iteration. It is used explicitly to iterate through elements, 
either manually or within a loop.
In essence, Iterable gives the ability to iterate, while Iterator is the tool that performs the iteration.

# Collection Interface
The Collection interface is the interface which is implemented by all the classes in the collection framework. 
It declares the methods that every collection will have. In other words, we can say that the Collection interface builds
the foundation on which the collection framework depends.
Some of the methods of Collection interface are Boolean add (Object obj), Boolean addAll (Collection c), void clear(), 
etc. that are implemented by all the subclasses of Collection interface.

# List Interface
List interface is the child interface of Collection interface. It inhibits a list type data structure in which we can 
store the ordered collection of objects. It can have duplicate values.

List interface is implemented by the classes **ArrayList, LinkedList, Vector, and Stack.**

There are various methods in List interface that can be used to insert, delete, and access the elements from the list.
To instantiate the List interface, we must use:
~~~
1.	List <data-type> list1= new ArrayList();
2.	List <data-type> list2 = new LinkedList();
3.	List <data-type> list3 = new Vector();
4.	List <data-type> list4 = new Stack();  
~~~

# Queue Interface
Queue interface maintains the first-in-first-out order. It can be defined as an ordered list that is used to hold the 
elements which are about to be processed. There are various classes like **PriorityQueue, Deque, and ArrayDeque** which
implements the Queue interface.
~~~
Queue interface can be instantiated as:
1.	Queue<String> q1 = new PriorityQueue();
2.	Queue<String> q2 = new ArrayDeque();  
~~~     

# Set Interface
Set Interface in Java is present in java.util package. It extends the Collection interface. 
It represents the unordered set of elements which doesn't allow us to store the duplicate items. 
We can store at most one null value in Set. 

Set is implemented by **HashSet, LinkedHashSet, and TreeSet.**
Set can be instantiated as:
~~~
1.	Set<data-type> s1 = new HashSet<data-type>();
2.	Set<data-type> s2 = new LinkedHashSet<data-type>();
3.	Set<data-type> s3 = new TreeSet<data-type>(); 
~~~

# SortedSet Interface
SortedSet is the alternate of Set interface that provides a total ordering on its elements. 
The elements of the SortedSet are arranged in the increasing (ascending) order. 
The SortedSet provides the additional methods that inhibit the natural ordering of the elements.

The SortedSet can be instantiated as:
~~~
1.	SortedSet<data-type> set = new TreeSet();  
~~~


# Map Interface
The Map interface in Java is part of the Java Collections Framework. It represents a mapping between a set of keys and 
their corresponding values. A Map cannot contain duplicate keys; each key can map to at most one value. 
The Map interface is used to store key-value pairs, where each key is unique, and it provides an efficient way to 
retrieve, update, and manipulate data based on keys.

Syntax:
~~~
1.	Map<T, T> hm = new HashMap<>();
2.	Map<T, T> tm = new TreeMap<>();  
~~~

# 1. List Interface
List interface is the child interface of Collection interface. It inhibits a list type data structure in which we can 
store the ordered collection of objects. It can have duplicate values.
List interface is implemented by the **classes ArrayList, LinkedList, Vector, and Stack.**
~~~
1.	List <data-type> list1 = new ArrayList();  
2.	List <data-type> list2 = new LinkedList();  
3.	List <data-type> list3 = new Vector();  
4.	List <data-type> list4 = new Stack(); 
~~~

There are various methods in List interface that can be used to insert, delete, and access the elements from the list.

The classes that implement the List interface are given below :
**ArrayList	    LinkedList 	Vector 	Stack**
~~~
ArrayList<String> list  =   new ArrayList<String>();//Creating arraylist
LinkedList<String> al   =   new LinkedList<String>();  
Vector<String> v        =   new Vector<String>();
Stack<String> stack     =   new Stack<String>();
~~~

# 1.1 ArrayList Class.
The ArrayList class implements the List interface. It uses a dynamic array to store the duplicate element of different 
data types. The ArrayList class maintains the insertion order and is non-synchronized. 
The elements stored in the ArrayList class can be randomly accessed. 
~~~
import java.util.*;  
class Main 
{  
    public static void main(String args[])
    {  
        ArrayList<String> list=new ArrayList<String>();    //Creating arraylist  
        list.add("Rank");  //Adding object in arraylist  
        list.add("Kia");  
        list.add("Mack");  
        list.add("Alice");  
        
        //Traversing list through Iterator  
        Iterator itr=list.iterator();  
        while(itr.hasNext())
        {  
            System.out.println(itr.next());  
        }  
    }  
}  
~~~

# 1.2 LinkedList
LinkedList implements the Collection interface. It uses a doubly linked list internally to store the elements. 
It can store the duplicate elements. It maintains the insertion order and is not synchronized. 
In LinkedList, the manipulation is fast because no shifting is required.

~~~
import java.util.*;  
public class Main
{  
    public static void main(String args[])
    {  
        LinkedList<String> al=new LinkedList<String>();  
        al.add("abc");  
        al.add("pqe");  
        al.add("xyz");  
        al.add("jkl");  
        
        Iterator<String> itr=al.iterator();  
        while(itr.hasNext())
        {  
            System.out.println(itr.next());  
        }  
    }  
}  
~~~

# 1.3 Vector
Vector uses a dynamic array to store the data elements. It is similar to ArrayList. 
However, it is synchronized and contains many methods that are not the part of Collection framework.
~~~
import java.util.*;  
public class Main
{  
    public static void main(String args[])
    {  
        Vector<String> v=new Vector<String>();  
        v.add("Abc");  
        v.add("mno");  
        v.add("pqr");  
        v.add("xyz");  
        
        Iterator<String> itr=v.iterator();  
        while(itr.hasNext())
        {  
            System.out.println(itr.next());  
        }  
    }  
}
~~~

# 1.4 Stack
The stack is the subclass of Vector. It implements the last-in-first-out data structure, i.e., Stack. 
The stack contains all of the methods of Vector class and also provides its methods like boolean push(), boolean peek(), 
boolean push(object o), which defines its properties.
~~~
import java.util.*;  
public class Main
{  
    public static void main(String args[])
    {  
        Stack<String> stack = new Stack<String>();  
        
        stack.push("Ayush");  
        stack.push("Garvit");  
        stack.push("Amit");  
        stack.push("Ashish");  
        stack.push("Garima");  
        
        stack.pop();  
        
        Iterator<String> itr=stack.iterator();  
        while(itr.hasNext())
        {  
            System.out.println(itr.next());  
        }  
    }  
}  
~~~

# Difference between ArrayList, LinkedList and Vector and Stack

# ArrayList
- **Implementation**: Uses a dynamic array to store elements.
- **Performance**: Fast random access (O(1)) but slower insertion and deletion (O(n)) in the middle of the list due to 
shifting elements.
- **Use When**: You need fast access to elements by index and don’t frequently insert or remove elements from 
the middle of the list.
- **Thread safe & Synchronized** - No thread safe & Synchronized

# LinkedList
- **Implementation**: Uses a doubly linked list to store elements.
- **Performance**: Slower random access (O(n)) but faster insertion and deletion (O(1)) at both ends (head and tail) of the list.
- **Use When**: You frequently add or remove elements from the beginning or end of the list and don’t require fast random access.
- **Thread safe & Synchronized** - No thread safe & Synchronized

# Vector
- **Implementation**: Similar to ArrayList, but synchronized for thread safety.
- **Performance**: Slower than ArrayList due to synchronization overhead.
- **Use When**: You need a thread-safe list (synchronized) in a multi-threaded environment.
- **Thread safe & Synchronized** - Yes, thread safe & Synchronized

# Stack
- **Implementation**: Extends Vector and represents a last-in-first-out (LIFO) stack.
- **Performance**: Similar to Vector with additional methods for stack operations like push, pop, and peek.
- **Use When**: You need a LIFO stack structure, especially in a thread-safe environment.
- **Thread safe & Synchronized** - Yes, thread safe & Synchronized


# 2. Queue Interface

Queue interface maintains the first-in-first-out order. It can be defined as an ordered list that is used to hold 
the elements which are about to be processed. 
There are various classes like **PriorityQueue, ArrayDeque** which implements the Queue interface.

Queue interface can be instantiated as:
~~~
Queue<String> q1 = new PriorityQueue();  
Queue<String> q2 = new ArrayDeque();
~~~

There are various classes that implement the Queue interface, some of them are given below.

# 2.1 PriorityQueue class

The PriorityQueue class implements the Queue interface. It holds the elements or objects which are to be processed by 
their priorities. PriorityQueue doesn't allow null values to be stored in the queue.

# 2.2 ArrayDeque class
ArrayDeque class implements the Deque interface. It facilitates us to use the Deque. Unlike queue, we can add or 
delete the elements from both the ends. 
ArrayDeque is faster than ArrayList and Stack and has no capacity restrictions.
~~~
import java.util.*;  
public class Main
{  
    public static void main(String[] args)
    {  
        //Creating Deque and adding elements  
        Deque<String> deque = new ArrayDeque<String>();  
        deque.add("G");  
        deque.add("K");  
        deque.add("A");  
        
        //Traversing elements  
        for (String str : deque)
        {  
            System.out.println(str);   // order remain same
        }  
    }  
}
~~~

# 2.3 Deque Interface
Deque interface extends the Queue interface. In Deque, we can remove and add the elements from both the side. 
Deque stands for a double-ended queue which enables us to perform the operations at both the ends.

Deque can be instantiated as:
~~~
Deque d = new ArrayDeque(); 
~~~

# 3. Set Interface
Set Interface in Java is present in java.util package. It extends the Collection interface. 
It represents the unordered set of elements which doesn't allow us to store the duplicate items. 
We can store at most one null value in Set.

Set is implemented by **HashSet, LinkedHashSet, and TreeSet class.**
~~~
Set<data-type> s1 = new HashSet<data-type>();  
Set<data-type> s2 = new LinkedHashSet<data-type>();  
Set<data-type> s3 = new TreeSet<data-type>();
~~~

# 3.1 HashSet
HashSet class implements Set Interface. It represents the collection that uses a hash table for storage. 
Hashing is used to store the elements in the HashSet. It contains unique items.
~~~
HashSet<String> set=new HashSet<String>();
~~~

# 3.2 LinkedHashSet
LinkedHashSet class represents the LinkedList implementation of Set Interface. It extends the HashSet class 
and implements Set interface. 
Like HashSet, It also contains unique elements. It maintains the insertion order and permits null elements.
~~~
LinkedHashSet<String> set=new LinkedHashSet<String>();
~~~

# 3.3 TreeSet
Java TreeSet class implements the Set interface that uses a tree for storage. 
Like HashSet, TreeSet also contains unique elements. However, the access and retrieval time of TreeSet is quite fast. 
The elements in TreeSet stored in ascending order.

~~~
TreeSet<String> set=new TreeSet<String>();  
set.add("Ravi");
~~~

# 3.4 SortedSet Interface
SortedSet is the alternate of Set interface that provides a total ordering on its elements. 
The elements of the SortedSet are arranged in the increasing (ascending) order. 
The SortedSet provides the additional methods that inhibit the natural ordering of the elements.
The SortedSet can be instantiated as:
~~~
SortedSet<data-type> set  set= new TreeSet();
~~~

# 4 Map Interface
The Map interface in Java is part of the Java Collections Framework. 
It represents a mapping between a set of keys and their corresponding values. 
A Map cannot contain duplicate keys; each key can map to at most one value. 
The Map interface is used to store key-value pairs, where each key is unique, and it provides an efficient way to 
retrieve, update, and manipulate data based on keys.
~~~
1.	Map<T, T> hm = new HashMap<>();
2.	Map<T, T> tm = new TreeMap<>();
~~~

# 4.1 HashMap
HashMap in Java is a key-value data structure offering efficient data access via keys using hashing. 
Hashing converts large strings or other objects into smaller, consistent values for quick indexing and searching. 
HashMap implements the Map interface and is used for managing large datasets efficiently. 
Additionally, HashSet uses HashMap internally to store elements uniquely, demonstrating the utility of hashing 
in Java's collections framework for fast data retrieval and management.
~~~
Map<String, Integer> map = new HashMap<>();
~~~

# 4.2 TreeMap
TreeMap is another implementation of the Map interface, but it is based on a Red-Black tree 
(a type of self-balancing binary search tree). 
It stores key-value pairs in sorted order based on the natural ordering of the keys or by a custom comparator 
provided at map creation time. 
It does not allow null keys but it allows null values. 
Like HashMap, it is not synchronized by default and thus is not thread-safe.
~~~
TreeMap<String, Integer> map = new TreeMap<>();  
~~~

# Difference between HashMap and TreeMap

| Feature |         HashMap         | TreeMap |
| :---         |:-----------------------:|          ---: |
| Ordering  | No ordering (unordered) | Maintains sorted order of keys    |
| Performance     |        O(1) for most operations        | O(log n) for most operations      |
| Null Keys/Values     |        Allows one null key and null values        | No null keys, but allows null values      |
| Thread Safety     |        Not synchronized       | Not synchronized      |
| Use Case     |        When order doesn't matter and fast access is needed        | When you need sorted keys or range queries     |










