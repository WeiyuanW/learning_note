# Day 8 review note - Oct 24

two handlers are discuss in today’s lecture:

- **Spring Framework**

the knowledge points are as below:

Maven -  a project management and build tool. 

local vs central repository- 

setting.xml - used to configure the Maven runtime environment (repository, proxy, account, local cache).

pom.xml – used to configure Maven project dependencies and build logic.

dependency coordinates (groupId : artifactId : version)

maven lifecycle - clean, validate, compile, test, package, verify, install, site, deploy
*As you execute later stages, earlier stages will automatically run.

maven cmd(mvn clean, install, -Dmaven.test.skip=true)

Spring IOC
what - Object creation and dependency management handled by the Spring container.
why – Decoupling, Highly maintainable, Convenient testing, Flexible configuration
how – The implementation of IOC relies on IoC Container (Spring container), which scans, creates and manages beans.

DI - Dependency Injection (DI) is a specific implementation of IoC. It essentially means that the container injects the objects that an object depends on into it. @Autowired

1. Constructor Injection. (recommend)
2. Setter Injection.
3. Field Injection.

bean scope – singleton, prototype, request, session, application; @Scope("…")
spring container – Bean Factory + Lifecycle Manager

circular dependency - Two (or more) beans depend on each other.  

1. Use @Lazy instead (to lazy load one dependency)
2. Use Setter Injection instead of Constructor Injection
3. Refactor Dependency Design (Best Solution)

Spring bean lifecycle –
Container startup → Bean creation → Property injection → Initialization → Use → Destruction.

- resource:
    
    [lecture recording link.](https://drive.google.com/file/d/1RSct9fXOV3joyf119eOoGKo-3cWt85qD/view)
    [Meeting summary.](https://docs.google.com/document/d/1nhS7ymcwbGh_aRY2hG-QoCHmj6F_L_l-5-5CZkpy-HU/edit?tab=t.f32muxkn5dql#heading=h.ywr3p8hjwfpw)
    [Meeting Transcript.](https://docs.google.com/document/d/1nhS7ymcwbGh_aRY2hG-QoCHmj6F_L_l-5-5CZkpy-HU/edit?tab=t.g54f6uytlny2)
    
- HW:
    1. Redo Day 6 without change source code for singleton
    2. Maven review (local vs central, setting.xml, pom.xml, dependency coordinates, maven lifecycle, maven cmd(mvn clean, install, -Dmaven.test.skip=true)
    3. Spring IOC review (IOC what, why, how), DI(three style(trade offs), bean scope, spring container, circular dependency), Spring bean lifecycle
    4. Spring AOP review
