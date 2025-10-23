# Day 5 review note - Oct 20

two handlers are discuss in today’s lecture:

- **thread safe**

the knowledge points are as below:

multiple threads -> running jvm

major concerns?

hardware resources limitations

thread safety -> concurrency issue -> read/write issue -> one thread reading

`while the other thread writing`

`on the same resource`

access the same resource -> not an issue if ???? ->

Lock -> Pessimistic vs Optimistic

synchronized -> scope(where???): method, block

essential -> Reentrantlock (Pessimisitc lock)

// thread safety -> (great things) -> trade off -> performance

Lock lock = new Reentrantlock(); --> Condition ---> Thread -> Six state -> 

before start() NEW

after start() Runnable

Lock + Condition -> thread1 execute first, then thread2 execute second, then come back to thread1 again

jvm -> stack, heap, method area, PC, native method stack

class MyRunnableTask implements Runnable {

public void run() {

Employee e1 = new Employee("David");

}

}

MyRunnableTask task = new MyRunnableTask();    -> .java -> .class -> 

(i)  find a space in heap
(ii) creation of object
(iii) assign reference to object

task1.start();        
task1.priority(10);

Pessimistic Lock ??? -> when to use

Optimistic Lock -> 
not locking before modification + Versioning (CAS -> Compare And Swap) (non-locking thread safety)

value1 -> version1 -> thread1 -> execution logics -> value1Updated2

value1Updated -> version2 -> thread2 -> update(very quick) -> return

valueUpdate

Java -> AtomicInteger/AtomicReference<T> AtomicReference<Employee>

                                AtomicReference<MYController>

                                AtomicTimeStampedReference

ABA ->

pessimistic

major(rw ww) vs major(rr) minor(rw ww)

minor(rr)      optimistic

monitoring

80% read / 20% write -> common pattern

----------------------------> 1 year

insurance system -> GEICO ->

- resource:
    
    [lecture recording link](https://drive.google.com/file/d/1xN3rOaxjsLRSdKzhsapQ2QV07yd3pxc3/view).
    [Meeting summary.](https://docs.google.com/document/d/1WS19giKSF39D2tEIjq794C7suoWjdPxsrcoVqCfHin0/edit?tab=t.jzrlj6nk0pq#heading=h.a3qlc327gb31)
    [Meeting Transcript](https://docs.google.com/document/d/1WS19giKSF39D2tEIjq794C7suoWjdPxsrcoVqCfHin0/edit?tab=t.2l1qx1uswtqn).
    
- HW:
    1. Thread safety -> r/w problem
    2. Pessimistic lock -> Synchronized vs Lock
    3. Thread priority -> execution order
    4. Optimistic lock -> Compare and Swap -> Version -> AtomicInteger/AtomicReference -> ABA problem -> timeStamp
    5. Optimistick s Pessimistic
    6. Singleton design pattern -> thread safe version