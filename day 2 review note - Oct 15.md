# day 2 note - Oct 15

three topics are discuss in today’s lecture:

- **Collections Framework and Hashmap implementation**
- Four Pillars of OOP
- SOLID Principle

the knowledge points are as below:

===== Collection framework graph 

1. **LinkedList & ArrayDeque:**
LinkedList is implemented in doubly linked list, in ; 
array deck implements in a circular list, better for queue or stack, head and tail
Use ArrayDeque for deque operations, LinkedList for middle insertions/deletions, and ArrayList for random access.
2. PriorityQueue
comparable and comparater
comparable - compare another object with itself 
comparater - an interface, take two objects 
3. BlockingQueue
use in thread pool customized for the waiting queue.
4. Set
HashSet - no order, hash function
LinkedHashSet - keeping insertion order.
SortedSet - order by value?
list & set diff: no duplicate elements allow in set.
5. Map 
HashMap - 
LinkedHashMap - keeping insertion order.
HashTable - Thread safe version of HashMap. —> ConcurrentHashMap
6. HashSet and hashMap relationship, hashset implement with a value null hashmap in java.
HashMap
key1 -> value1
key2 -> value2
key3 -> value3
key4 -> value4
key5 -> value5

HashSet
key1 -> null
key2 -> null
key3 -> null
key4 -> null
key5 -> null
7. Employee class into
HashMap<Employee, Profile> as key -> case 1
or just in HashSet<Employee> -> O(1) -> case 2
Set vs Map
Key-value map
single vluae + deduplicate -> set
8. hash collision
hashcode -> function
Employee e1                           unique hash-value
input         -> hashcode function -> output
Hash Collision???
Employee e1 -> hash-value1
Employee e2 -> hash-value1
             vs
Normal update???
Employee e1 -> hash-value1
Employee e1 -> hash-value1
9. hashcode + equals -> Employee extends Object -> e1.equals(e2) -> euqlas check each and every fields
employee -> id, age, name, contactInfo, email, phoneNumber
class template (Object) equals -> ==
                       key2                         hashvalue1
HashMap key1-value1 :  key1 -> hashcode function -> hashvalue1
______________________________ Bucket(array)
            |
            V
          value1
            |
            V
          value2
            |
            V
          vluae3
            |
            V
            .... * 1m records O(1) -> O(n)
        java 8 -> 8/16 -> linkedlist -> black and red tree data structure
10.      OOP Four Pillars ->
     Inheritance -> interface + abstract class + final(limit Inheritance),(hide data)
     Encapsulation, -> access modifier (private, protected, public, default)
     Polymorphism, -> override(Runtime) vs overload(Compile-time)
     Abstraction -> interface + abstract class (only show the function, hide the implementation)
11. SOLID Principle
     S -> single responsibility 
- Each class should have only one responsibility.

     O -> Open/Closed 
- Software entities (classes, modules, functions) should be **open for extension but closed for modification**.

     L -> Liskov Substitution principle
- Subclasses should be replaceable for their base classes without affecting program correctness.

     I -> Interface Segregation
- A class should not be forced to depend on interfaces it does not use.

     D -> Dependency Inversion
- High-level modules should not depend on low-level modules; both should depend on abstractions. (Dependency injection is just one way to implement this principle.)

- resource:
    
    [lecture recording link.](https://drive.google.com/file/d/1URCBdQljjVsshBL56PPf39fDEngHwv9q/view)
    
- code
    
    Singleton.java - singleton design pattern (access modifiers, template types, the static keyword, immutability with the final keyword, and the differences between method overloading and overriding)
    
    ```java
    package org.example;
    class Singleton {
        private static final Singleton instance = new Singleton();
        private Singleton() {}
        public static Singleton getInstance() {
            return instance;
        }
    }
    
    /*
    HashMap
    key1 -> value1
    key2 -> value2
    key3 -> value3
    key4 -> value4
    key5 -> value5
    
    HashSet
    key1 -> null
    key2 -> null
    key3 -> null
    key4 -> null
    key5 -> null
    
    Employee class into
    HashMap<Employee, Profile> as key -> case 1
    or just in HashSet<Employee> -> O(1) -> case 2
    Set vs Map
    Key-value map
    single vluae + deduplicate -> set
    ????
    hash collision
    hashcode -> function
    Employee e1                           unique hash-value
    input         -> hashcode function -> output
    Hash Collision???
    Employee e1 -> hash-value1
    Employee e2 -> hash-value1
                 vs
    Normal update???
    Employee e1 -> hash-value1
    Employee e1 -> hash-value1
    hashcode + equals -> Employee extends Object -> e1.equals(e2) -> euqlas check each and every fields
    employee -> id, age, name, contactInfo, email, phoneNumber
    class template (Object) equals -> ==
                           key2                         hashvalue1
    HashMap key1-value1 :  key1 -> hashcode function -> hashvalue1
    ______________________________ Bucket(array)
                |
                V
              value1
                |
                V
              value2
                |
                V
              vluae3
                |
                V
                .... * 1m records O(1) -> O(n)
            java 8 -> 8/16 -> linkedlist -> black and red tree data structure
    
         OOP ->
    
         Inheritance -> interface + abstract class + final
    
         Encapsulation, -> access modifier
    
         Polymorphism, -> override vs overload
    
         Abstraction -> interface + abstract class
    
         +
    
         S -> single responsibility
         O -> Open/Closed
         L -> Loskov principle
         I -> Interface segeration
         D -> Dependency injection
    
    */
    
    ```