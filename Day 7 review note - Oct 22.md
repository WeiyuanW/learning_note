# Day 7 review note - Oct 22

two handlers are discuss in today’s lecture:

- **Spring Framework**

the knowledge points are as below:

enum - data structures containing constant values that can be customized with different data types 

anotation - special interface types providing metadata and consist of four meta-annotations: `Target`, `Retention`, `Inherited`, and `Documented` 

Spring framework

> AOP ⇒ how to do it (where? anotations use for? )

> aspect oriented programming

> @Aspect

-> logics(what) -> (when) @Before(@annotaion(com.example.annotaiton.Cachable))

@After, @AfterReturning, @AfterThrowing(Exception UserNotExist.class), @Around

`@Before(`

`@Pointcut("execution(* com.example.controller.*)"),`

`throwing = "usernotexsit"`

`)`

`public void beforeUserValidation(JointPoint jointPoint, Exception usernotexsit) {`

`logger.info(jointpoint.getRequestId());`

`retry();`

`}`

// logging, login, Exception handling, retry, profiling ()

-> @Pointcut("execution(* com.example.service.UserService.processRequest(*))")

com.example.service.UserService.processRequest(String Id)

com.example.service.UserService.processRequest(Integer Id)

com.example.service.UserService.processRequest(Double Id)

-> logger user Id

`@AfterThrowing(Exception UserNotExist.class)`

`public void myPointCutExecution(){}`

Dependency Inversion principle => same idea as Inversion of Control (implements with Dependency injection)

Inversion of Control

> IOC -> Dependency injection -> loosely coupling your logics

          (ApplicationContext vs BeanFactory)

> new() -> Spring Container ->  spring beans -> scopes :  singleton, prototype, session, request, applciation

singleton design parttern ≠  spring beans singleton scope(java object + lifecycle controlled by Spring container)

Dependency injection -> (DI)

(i) field injection (Springboot1.0)

(ii) constructor injection -> (Springboot2.0) -> prevent null pointer exception during runtime, easier for testing [recommend]

(iii) setter injection

circular dependency issue -> bean A (bean B)

                                   bean B (bean C)

                             bean C (bean A)

 ⇒ @Lazy

- resource:
    
    [lecture recording link](https://drive.google.com/file/d/1gxETdc3Z6RpiYTMx6z5UqRcC11qml-xR/view).
    [Meeting summary.](https://docs.google.com/document/d/13NghrrdPXFT5eUlx6A0vBb3r-6LFEPzGQiP6KVAfg_0/edit?tab=t.ndv3nqlll7v4)
    [Meeting Transcript](https://docs.google.com/document/d/13NghrrdPXFT5eUlx6A0vBb3r-6LFEPzGQiP6KVAfg_0/edit?tab=t.54m3csnhdelb).
    
- HW:
    1. Create a spring project
    2. Implement a singleton class
    3. Implement AOP so that you log when the object has been accessed by different thread