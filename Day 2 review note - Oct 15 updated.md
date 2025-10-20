# Day 2 review note - Oct 15

three topics are discuss in today’s lecture:

- **Collections Framework and Hashmap implementation**
- Four Pillars of OOP
- SOLID Principle

the knowledge points are as below:

===== Collection framework graph 

list:

`- ArrayList`

`- LinkedList`

`- Vector + Stack`

Queue:

`- PriorityQueue`

`-> Comparator(between classes) vs Comparable(in class, compareTo)`

`- ArrayDeque`(circular,Queue/Stack) `vs LinkedList`(doubly,get/set) `as Deque`

`- BlockingQueue`(thread pool )

Set:

`- Hashset -> Hash Collision ->`

`- LinkedHashSet`

`- TreeSet<Employee> ? Comparator(sorting age) vs Comparable(sorting ID)`

Map: 

`- HashMap -> HashTable (safe,Deprecated) -> ConcurrentHashMap -> thread safety mechansim`

`- LinkedHashMap`

`- TreeMap<Key, Value> -> Sorting based on Key`
HashSet (HashMap): key1 -> null

Employee class into
HashMap<Employee, Profile> as key -> case 1
or just in HashSet<Employee> -> O(1) -> case 2
Set vs Map
Key-value map
single vluae + deduplicate -> set
hash collision
hashcode -> function
Employee e1                           unique hash-value
input         -> hashcode function -> output
Hash Collision
Employee e1 -> hash-value1
Employee e2 -> hash-value1
             vs
Normal update
Employee e1 -> hash-value1
Employee e1 -> hash-value1
override: hashcode + equals -> Employee extends Object -> e1.equals(e2) -> euqlas check each and every fields
employee -> id, age, name, contactInfo, email, phoneNumber
class template (Object) equals -> ==
                       key2                                                              hashvalue1
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
* always need to override both hash code method and equals method.

     OOP ->
     Inheritance -> interface + abstract class + final (limit Inheritance),(hide data)
     Encapsulation, -> access modifier
     Polymorphism, -> override vs overload
     Abstraction -> interface + abstract class (only show the function, hide the implementation)

     S -> single responsibility
     O -> Open/Closed (extension, modification)
     L -> Liskov Substitution (Subclasses replace base classes)
     I -> Interface segregation (no depend on not use interfaces)
     D -> Dependency Inversion (modules depend on abstractions , not high on low)

- resource:
    
    [lecture recording link.](https://drive.google.com/file/d/1URCBdQljjVsshBL56PPf39fDEngHwv9q/view)