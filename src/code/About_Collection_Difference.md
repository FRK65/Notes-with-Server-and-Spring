
# 1. Array vs Vector in Java.

| Feature               | Array                                | Vector                                |
|-----------------------|--------------------------------------|---------------------------------------|
| **Size**              | Fixed size                          | Dynamic size (resizes automatically)  |
| **Type**              | Can store elements of a single type  | Can store objects of any type (since it stores `Object` type) |
| **Performance**       | Faster due to fixed size            | Slower due to dynamic resizing       |
| **Resizing**          | Cannot be resized after creation    | Resizes automatically when full      |
| **Memory Allocation** | Contiguous block of memory          | Allocates more memory to accommodate growth |
| **Thread Safety**     | Not thread-safe                     | Thread-safe (synchronized methods)    |
| **Default Capacity**  | N/A (size must be defined)          | Default capacity is 10               |
| **Access Method**     | Accessed using an index (array[i])  | Accessed using `get(index)` and `set(index, value)` methods |
| **Use Case**          | Suitable for fixed-size collections | Suitable for dynamic collections where resizing is needed |
| **Speed of Operations** | Faster access and manipulation      | Slower due to synchronization overhead |

# 2. Array vs ArrayList in Java

| Feature               | Array                                | ArrayList                             |
|-----------------------|--------------------------------------|---------------------------------------|
| **Size**              | Fixed size                          | Dynamic size (resizes automatically)  |
| **Type**              | Can store elements of a single type  | Can store objects of any type (since it stores `Object` type) |
| **Performance**       | Faster due to fixed size            | Slightly slower due to resizing and dynamic allocation |
| **Resizing**          | Cannot be resized after creation    | Resizes automatically when full      |
| **Memory Allocation** | Contiguous block of memory          | Resizes and reallocates memory when needed |
| **Thread Safety**     | Not thread-safe                     | Not thread-safe (can be synchronized externally) |
| **Default Capacity**  | N/A (size must be defined)          | Default capacity is 10               |
| **Access Method**     | Accessed using an index (array[i])  | Accessed using `get(index)` and `set(index, value)` methods |
| **Use Case**          | Suitable for fixed-size collections | Suitable for dynamic collections where resizing is needed |
| **Speed of Operations** | Faster access and manipulation      | Slower due to resizing and internal array adjustments |
| **Memory Efficiency** | More memory efficient (no overhead)  | Less memory efficient due to internal resizing and overhead |
