# Day 4 review note - Oct 17

two handlers are discuss in today’s lecture:

- **multi threading**

the knowledge points are as below:

jdk7

jdk8 -> 2014 (buggy) -> 2018 -> Spring framework booming
(Lambda Expressions, Stream API, Default Methods in interfaces, java.time, CompletableFuture)

jdk11 -> release "flight recorder" -> free feature
(HTTP Client, Flight Recorder…)

jdk17 -> Spring6/SpringBoot3.0 ->

(Sealed classes, Pattern Matching…)

jdk19 -> virtual thread -> Loom project (java -jar --experimental main.jar) -> GO/GO routine

jdk21 -> virtual thread (normal object)

(Virtual Threads (Loom), Record Patterns, Sequenced Collections…)

static codes                                                     execution routine of a process

program,            process,                                thread -> volatile

                           execution of a program

concurrent programming (limited CPU, switching) vs parallel programming 

working thread vs daemon thread

Thread lifecycle -> Six State : New, Runnable, Blocked, Waiting, Timed Waiting, Terminated

run() vs start() ： create new thread, only call once, "new" to "runnable" 

native → native method stack

Thread -> Creation -> 

1, Thread class (extends, only 1)

2, Runnable interface (implements, multiple)

3, Callable interface (return, throws exception)

4, Thread Pool -> (the only practice, not affecting the runtime app) -> (jdk21 - virtual threads )

CompletableFuture (asynchronous, chaining tasks, ~~blocking~~)

Thread Pool 7 configurations : core pool size, maximum pool size, keep-alive time, time unit, work queue, thread factory, handler. (bounded resources )

custom thread pools ⇒ ThreadPoolExecutor, multiple thread pools, priority 

Asynchronous Programming ⇒ CompletableFuture 

CompletableFuture.supplyAsync(TASK!).thenApply(task2).thenAccept(task3);

result1 = CallaableTask1.get() 
-> result2 = CallableTask2(result1).get() 
-> result3=CallablaeTask3(result2).get()

task1 ->                         task2 ->                         task3 
CompletableFuture      CompletableFuture      CompletableFuture

- resource:
    
    [lecture recording link.](https://drive.google.com/file/d/1dXVC_8FkQ1DbdhZ4NBqIyw6qsbwhsC9Q/view)
    [Meeting notes](https://docs.google.com/document/d/1Bnv12YTF2kaNAEyqPC2BHVHrX1N8odNKTXWLlG8-YVs/edit?tab=t.mdx4gv33wq4m).
    [Meeting Transcript](https://docs.google.com/document/d/1Bnv12YTF2kaNAEyqPC2BHVHrX1N8odNKTXWLlG8-YVs/edit?tab=t.hku7l8kvltgq).
    
- follow up:
    
    Talk about which version of Java you use? What’s those popular features that you use in your project? 
    - mention critical Java milestone releases and detail the new features used in their projects for each milestone
    
    code implementation of the multi threading.
    - extending `Thread`, implementing `Runnable`, and using `CompletableFuture`