# Day 1 review note - Oct 14

two handlers are discuss in today’s lecture:

- **Singleton Design Pattern and its Modes**
- **Factory Design Pattern**

the knowledge points are as below:

singleton design partern

access modifiers - public, private(class), default(package), protected(default+child to parent)

object/instance vs template  -> new instantiation

template: class vs interface vs abstract class vs enum vs annotation (@interface)

class MyClass implements interface1, 2, 3 extends AbstractClass

static -> field, method, class, block

template -> access elements from template

JVM -> Java Virtual Machine -> type of virtual machine (Process Virtual machine) 

stack, heap, PC(program counter), method area, native method stack

final -> field, method, class                             finalize vs finally

immutable class:

1. final -> class
2. private final fields
3. getter only, no setter
4. in getter, given referenced data type field, always return deep copy dummies

final keyword on field ⇒ cannot be changed

mode: lazy -> eager loading

override vs overload difference 
-> runtime vs compile time polymorphism
 → in-between classes vs within same class

factory design pattern

paypal, credit card -> payment methods -> pay API
expose checkout API for cross function team

double vs Double -> primitive vs referenced data type ->  8 primitive data type
       byte < short < int < long，float < double，boolean，char
（1 byte < 2 byte < 4 byte < 8 byte，4 byte < 8 byte，1 bit{1 byte}，2 byte）

auto boxing (primitive type to its wrapper class)

auto unboxing

runtime exception(Unchecked) vs compile time exception(Checked)

extends RuntimeException vs extend Exception

throw vs throws

try… catch… finally…; 

Throwable: Exception vs Error

status code ---> HTTP status 100, 200, 300, 400, 500

                                           `HR, Sales, Account`

Exception status code ----> 101                000 1 -->

                                           `DEparmetn`

                                                 `HR -> CandadietNotExist 100`

                                                        `MissCellPhoneInfo 101`

                                                        `ContractUnSigned 202`

Exception messages

- resource:
    
    [lecture recording link](https://drive.google.com/file/d/1V8Bxxz56w7bLv86Ey2NPEjlh4mlfYKtk/view).
    [Meeting notes](https://docs.google.com/document/d/13ZpNWEorLM1NjHMQ2JRzYf_QkbFZR29-pxzPOiCheSo/edit?tab=t.2oet7imt5097#heading=h.k710r67ocdvf).
    [Meeting Transcript](https://docs.google.com/document/d/13ZpNWEorLM1NjHMQ2JRzYf_QkbFZR29-pxzPOiCheSo/edit?tab=t.o39y6laelyt7#heading=h.81cbgjgmdhli).