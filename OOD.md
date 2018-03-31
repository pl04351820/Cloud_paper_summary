## Design pattern (OOD)
The only thing I learned from this is divide the software to changalbe part and inchangable part.

### OOD principle 
- SRP Single Responsiblity principle 
- OCP The open closed principle (Decorator)
- The Liskov Substitution principle 
- The interface segregation principle 
- THe dependency inversion principle

### OOD features
- Encapusulation
- Inherentence
- Polymorphism

### Creational Patterns
- Factory Pattern
- Singleton Pattern
- Builder Pattern
- Prototype Pattern
- Abstract Factiory Pattern

If language can pass type like variable, creational patterns could make no sense.
Ex: 
1. Prototype pattern
Java add a attribute like type in their classes, but in python, we can use type() to get the type of type. So prototype may not be so helpful.
2. Factory pattern
Solve the problem for interface. (Interface shape, outside we only need to use circle, square, rectangle to use it). In python, class name can be passed directly. So no need for factory pattern.
3. Singleton Pattern
Global variable.

### Structural Patterns
- Adapter Pattern
- Bridge Pattern 
- Filter, Criteria Pattern 
- Composite Pattern
- Decorator Pattern 
- Facade Pattern
- Flyweight Pattern
- Proxy Pattern

If language style can reject class hierachy, structural patterns could make no sense.

### Behavioral Patterns
- Chacin of Responsiblity Pattern 
- Command Pattern
- Interpreter Pattern
- Iterator Pattern 
- Mediator Pattern 
- Memento Pattern
- Observer Pattern 
- State Pattern
- Null Object Pattern 
- Strategy Pattern 
- Template Pattern
- Visitor Pattern 

If language can pass function like variable, behavioral patterns could make no sense.

Ex: 
1. Command Pattern/ Stategy Pattern
    Stategy +-= method. But this makes no sense if you can pass the function name.

2. Iterator Pattern
    Python, there is iterator embedded in language. 
