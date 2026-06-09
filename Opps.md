## Object-oriented programming

Go is not a traditional object-oriented programming (OOP) language but it supports most OOP concepts using structs, methods, and interfaces. 
Focusing on interfaces and composition rather than traditional class-based inheritance. This make more flexible and modular design.

it achieves OOP concepts using structs (to represent class/objects), methods (functions attached to structs), interfaces (for polymorphism), and composition (for reuse).


Core OOP Concepts in Go :

- ***Classes and Objects (Structs)***:
  Go uses structs instead of classes., to define data structures. An "object" in Go is an instance of a struct.
  
- ***Encapsulation (Exported Identifiers)***:

  Encapsulation is one of the core principles of object-oriented programming. It refers to the concept of wrapping data and the methods that operate on that data into a single unit, while also restricting direct access to some of the object's components. In simple terms, encapsulation acts as a protective shield that prevents external code from directly accessing and modifying internal data.

  In traditional object-oriented languages, encapsulation is achieved using classes, where data members are kept private and can only be accessed through public methods defined within the same class. However, Go does not support classes in the conventional sense. Instead, encapsulation in Go is achieved using packages and visibility rules.

  Go provides two types of identifiers:
  - Exported identifiers (public) :: Identifiers starting with an uppercase letter (e.g., ExportedField) are accessible from other packages.
  - Unexported identifiers (private) :: Identifiers starting with a lowercase letter (e.g., unexportedField) are restricted to their own package.


  Access control is managed at the package level using naming conventions.
  
- ***Polymorphism (Interfaces)***:
  
  Go achieves polymorphism through implicit interfaces. A type satisfies an interface simply by implementing its required methods; there is no implements keyword.


  Polymorphism is the ability of a message to be displayed in more than one form. Polymorphism is considered one of the important features of Object-Oriented Programming and can be achieved during either runtime or compile time. Golang is a light-object-oriented language and supports polymorphism through interfaces only.
  
  
- ***Inheritance (Composition & Embedding)***:

  Go does not support classical inheritance. Instead, it uses struct embedding (composition), where one struct is placed inside another to "inherit" its fields and methods
  
---

## Struct embedding : 

Go doesn't have classes or inheritance. Instead, it uses struct embedding to embed one struct inside another struct, to re-use struct attributes (fields and methods).

## Composition :

Go does not support inheritance and Instead of, it relies on composition. The idea that .., The larger object is built by combining smaller and focused objects (follow "has-a" relationships rather than "is-a" relationships).

## Composition over Inheritance

| Feature / Dimension | Composition ("Has-A") | Inheritance ("Is-A") |
| :--- | :--- | :--- |
| **Core Concept** | "A Dog **has-a** barking behavior"<br>"A Car **has-an** Engine" | "A Dog **is-an** Animal"<br>"A Car **is-a** Vehicle" |
| **Mechanism** | Struct embeds other structs / references components | Subclass extends a base class |
| **Reuse Direction** | **Horizontal:** Mix-and-match independent features | **Vertical:** Deep hierarchical inheritance tree |
| **Coupling** | **Loose:** Components are decoupled, isolated modules | **Tight:** Child class depends heavily on parent state |
| **Flexibility** | **High:** Easy to swap or modify pieces at runtime | **Rigid:** Hard-coded and fixed at compile time |
| **Encapsulation** | **Strong:** Inner details stay hidden inside components | **Weak:** Breaks parent encapsulation (via `protected`) |
| **Testing** | **Easy:** Straightforward to mock isolated dependencies | **Harder:** Tests must manage complex parent states |
