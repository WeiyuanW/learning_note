# day 1 note - Oct 14

three handlers are discuss in today’s lecture:

- **Singleton Design Pattern and its Modes**
- **Factory Design Pattern**
- **Collections Framework**

the knowledge points are as below:

===== cover in Singleton.java 

1. **Singleton Design Pattern and its Modes:**
its purpose is to ensure a class instance is created only once throughout the Java program's lifecycle. 
the two primary modes of implementation are lazy loading and eager loading.
lazy loading instantiates the object only when needed, while eager loading instantiates it at the start.
2. **Access Modifiers and Keywords are `public private default protected`.** 
`public` provides the widest access (any class), `private` the narrowest (current class), and `default` and `protected` offer access based on package and inheritance, respectively.
`default -> protected (default + child access parent)`
3. the `class` keyword as defining a template, which becomes an `object` or `instance` only upon instantiation with the `new` keyword.
 `object/instance vs template  -> new instantiation`
4. **Template Types in Java** including `class`, `interface`, and `abstract class`, along with `enum` and `annotations(@interface)` 
`abstract classes` can contain abstract methods without implementation bodies and that inheriting from them requires overriding. 
`abstract classes` allow only single inheritance, whereas `interfaces` permit multiple implementations
`class MyClass implmeent interface1, 2, 3 extends AbstractClass`
5. **Static Keyword and JVM Memory Areas**    
`static -> field, method, class, block`
the `static` keyword allows access to elements directly from the class template without needing an object instance.   
6. five key areas in JVM memory architecture: stack, heap, program counter, method area, and native method stack. 
`static` elements, including class templates and source code, are stored in the method area, while object instances reside in the heap.
static blocks are executed once during program loading and are used for bootstrap logic.
`template -> access elements from template`
Each object accesses class-level elements from the class template stored in the Method Area.
`JVM -> Java Virtual Machine -> type of virtual machine(Process Virtual Machine)`
7. **Immutability and the Final Keyword.**
`final -> field, method, class`
for method, `final` means prevents overriding.
for class, `final` means prevents inheritance. cannot be subclassed.
for fields, `final` means the reference cannot be reassigned, distinguishing it from an immutable object. 
(final→reference cannot be reassigned; immutable→object's content can not be changed.)
between eager and lazy loading in singleton patterns, noting `final` cannot be used with lazy loading because the instance is assigned later.
using getter methods to control access and maintain immutability; deep copies for reference data types in getters to prevent unintended modifications 
**`finalize`**: A method called by the garbage collector before an object is destroyed, typically used (though not recommended) to release resources.
**`finally`**: A block of code that always executes after a `try` block, regardless of whether an exception occurs, usually for cleanup tasks.
8. immutable class means **instances cannot be modified after they are created**. Once you create an object of an immutable class, its state (its fields) cannot change.
The class is declared `final` (so it cannot be subclassed).
All fields are `private` and `final`.
No setter methods are provided.
All fields are initialized via the constructor.
If a field is mutable (like a `Date` or a `List`), the class makes a **defensive copy** when setting or returning it.
9. **Overloading vs. Overriding** 
both are forms of polymorphism. 
**overriding** occurs between parent and child classes, maintaining the same method signature but changing implementation. `runtime time polymorphism`（dynamic polymorphism）;`in-between classes`
**overloading** happens within the same class using the same method name but different parameter signatures. `compile-time polymorphism`（static polymorphism）;`within same class`

===== cover in PaymentService.java  
10.     **Factory Design Pattern**    
The Factory Design Pattern is a **creational pattern** that abstracts the process of creating objects. Instead of the client instantiating objects directly, a factory class or method is responsible for creating them.
We use it when object creation is complex, or we want to decouple clients from concrete classes, or decide the type of object at runtime.
`// paypal, credit card -> payment methods -> pay API`
`// expose checkout API for cross function team`
11.     **Exception Handling: Throw vs. Throws**    
`throw` is the action of throwing an exception and `throws` is an indication that a method might throw a certain type of exception. 
Exceptions can be handled using `try-catch-finally` blocks or by using `throws` to delegate handling to an upper layer, which is a common strategy in frameworks like Spring.
12.     **Types of Exceptions and Customization**    
There are two types of exceptions: **runtime exceptions(Unchecked Exceptions)** and **compile-time exceptions(Checked Exceptions)**.
compile-time exceptions must be handled while compile.
All exceptions and errors inherit from the `Throwable` class, with exceptions being handleable by `try-catch` blocks, unlike errors which represent unrecoverable issues.
customizing exceptions by categorizing them, choosing the correct superclass to inherit from, and designing appropriate status codes and messages.
`// IllegalAccessException -> runtime exception vs compile time exception`
`// extends RuntimeException vs extend Exception`
`// Throwable`
`// Exception vs Error`
13. `8 primitive data type`:byte < short < int < long，float < double，char，boolean
（1 byte < 2 byte < 4 byte < 8 byte，4 byte < 8 byte，2 byte，1 byte/1 bit）
`auto boxing`Automatic conversion from a **primitive type** to its **wrapper class**.
`auto unboxing`Automatic conversion from a **wrapper class** back to its **primitive type**.
Useful when working with **collections** or **arithmetic operations**.
`// double vs Double -> primitive vs referenced data type ->  8 primitive data type`
`// List<Double> list = new ArraYList();`
`// double d = 2.0; -> Double d1 = new Double (d); -> auto boxing`
`// list.add(d);    -> list.add(d1);`
`// double d = list.get(0);`
`// List<double>`

==== Collection framework graph
14.     **Collections Framework and Interview Strategy**    
the Collections Framework contains various data structures like `ArrayList`, `LinkedList`, and `HashSet`, but  `Map` is a separate system. 
rather than detailing implementation specifics, it is more effective to demonstrate experience by explaining "when to use which" data structure 
15. map implementation?
    
    
    | Implementation | Features | Thread-safe | Allows null? |
    | --- | --- | --- | --- |
    | **HashMap** | Based on hash table; fast lookup and insertion | ❌ No | Key: ✅ (only one null), Value: ✅ |
    | **LinkedHashMap** | Maintains insertion order or access order | ❌ No | Key: ✅, Value: ✅ |
    | **TreeMap** | Based on red-black tree; keys are sorted | ❌ No | Key: ❌, Value: ✅ |
    | **Hashtable** | Legacy implementation; synchronized methods | ✅ Yes | Key: ❌, Value: ❌ |
    | **ConcurrentHashMap** | Optimized for concurrent access; thread-safe | ✅ Yes | Key: ❌, Value: ✅ |

- resource:
    
    [lecture recording link](https://drive.google.com/file/d/1V8Bxxz56w7bLv86Ey2NPEjlh4mlfYKtk/view).
    [Meeting notes](https://docs.google.com/document/d/13ZpNWEorLM1NjHMQ2JRzYf_QkbFZR29-pxzPOiCheSo/edit?tab=t.2oet7imt5097#heading=h.k710r67ocdvf).
    [Meeting Transcript](https://docs.google.com/document/d/13ZpNWEorLM1NjHMQ2JRzYf_QkbFZR29-pxzPOiCheSo/edit?tab=t.o39y6laelyt7#heading=h.81cbgjgmdhli).
    

- code
    
    Singleton.java - singleton design pattern (access modifiers, template types, the static keyword, immutability with the final keyword, and the differences between method overloading and overriding)
    
    ```java
    package org.example;
    // public private default protected
    // default -> protected (default + parent/child access)
    // object/instance vs template  -> new instantiation
    // class vs interface vs abstract class vs enum vs annotation (@interface)
    // class MyClass implmeent interface1, 2, 3 extends AbstractClass
    // static -> field, method, class, ??? (block)
    // template -> access elements from template
    // why?
    // JVM -> Java Virtual Machine -> type of virtual machine
    // stack, heap, PC, method area, native method stack
    // final -> field, method, class                             finalize vs finally
    // ---> Employee class -> immutable class????
    // final -> class
    // private final fields
    // getter only, no setter
    // in getter, given referenced data type field, always return deep copy dummies
    /**
     * Profile -> CellPhone, IDCard,
     *  public final Employee {
     *      final int age;
     *      final string name;
     *      final List<Friend> friends;
     *      final Profile
     *
     *      // Getter method for age. name, friends
     *      // no setter
     *  }
     *  Employee e1 = new Employee(52, "David", new ArraYLsit());
     *  e1.getFriends().add(new Employee("Rogor"XXXXX));
     *
     */
    // if you put the final keyword on field,
    // it cannot be changed
    // Employee e1 = new Employee("David", 52, "male", "Senior SDE");
    // e1 = new Employee("Kyra", XX, "female", "Senior SDE");
    
    // mode? lazy -> eager loading
    public class Singleton {
    //    static {
    //        System.out.println("hello world");
    //    }
    //
    //    static class MyStaticClass {
    //
    //    }
        private static Singleton instance = new Singleton();
        private Singleton() {
        }
        public static Singleton getInstance() {
    //        if (instance == null) {
    //            instance = new Singleton();
    //        }
            return instance;
        }
    //    String s1 = new String("a");
    }
    
    // override vs overload difference
    // -> runtime vs compile time polymorphism
    // in-between classes vs within same class
    
    ```
    
    PaymentService.java - Factory Design Pattern (exception handling, `throw` vs. `throws`)
    
    ```java
    package org.example;
    
    // factory design pattern
    // paypal, credit card -> payment methods -> pay API
    // expose checkout API for cross function team
    // double vs Double -> primitive vs referenced data type ->  8 primitive data type
    // List<Double> list = new ArraYList();
    // double d = 2.0; -> Double d1 = new Double (d); -> auto boxing
    // list.add(d);    -> list.add(d1);
    // double d = list.get(0);
    // List<double>
    
    // IllegalAccessException -> runtime exception vs compile time exception
    // extends RuntimeException vs extend Exception
    // Throwable
    // Exception vs Error
    
    interface Payment {
        void pay(double money);
    }
    
    class PayPalPayment implements Payment{
        public void pay(double money){
            System.out.println("Pay pal");
        }
    }
    
    class CreditCardPayment implements Payment{
        public void pay(double money){
            System.out.println("credit card payment");
        }
    }
    
    class PaymentFactory {
        public static Payment createPayment(String type)  {
            switch(type.toLowerCase()) {
                case "paypal": return new PayPalPayment();
                case "creditcard": return new CreditCardPayment();
                default:
                    try {
                        throw new IllegalAccessException("unknown type" + type);
                    } catch (IllegalAccessException e) {
                        System.out.println(e.getMessage());
                        // logger.debug();
                        // loger.info();
                    } finally {
    
                    }
            }
        }
    }
    
    public class PaymentService {
        public void checkout(double amount, String paymentType) throws IllegalAccessException {
            Payment payment = PaymentFactory.createPayment(paymentType);
            payment.pay(amount );
    
        }
    }
    
    ```