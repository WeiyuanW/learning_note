# Day 4 review note - Oct 17

two handlers are discuss in today’s lecture:

- **multi threading**

the knowledge points are as below:

jdk7

jdk8 -> 2014 (buggy) -> 2018 -> Spring framework booming

jdk11 -> release "flight recorder" -> free feature

jdk17 -> Spring6/SpringBoot3.0 ->

jdk19 -> virtual thread -> Loom project (java -jar --experimental main.jar) -> GO/GO routine

jdk21 -> virtual thread (normal object)

static codes                                                     execution routine of a process

program,            process,                                thread -> volatile

                           execution of a program

Thread lifecycle -> Six State : New, Runnable, Blocked, Waiting, Timed Waiting, Terminated

run() vs start() ： create new thread, 1 or multiple callable

Thread -> Creation -> 

1, Thread class

2, Runnable interface

3, Callable interface

4, Thread Pool -> (the only) -> (jdk21 - virtual threads )

CompletableFuture

Thread Pool 7 configurations : core pool size, maximum pool size, keep-alive time, time unit, work queue, thread factory, handler 

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