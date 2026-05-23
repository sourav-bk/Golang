## Object-oriented programming

Go is not a traditional object-oriented programming (OOP) language but it supports most OOP concepts using structs, methods, and interfaces. 
Focusing on interfaces and composition rather than traditional class-based inheritance. This leads to a more flexible and modular design.


Core OOP Concepts in Go :

- ***Classes and Objects (Structs)***: Go uses structs instead of classes to define data structures. An "object" in Go is an instance of a struct.
- ***Encapsulation (Exported Identifiers)***: Access control is managed at the package level using naming conventions.
  - ***Public***: Identifiers starting with an uppercase letter (e.g., ExportedField) are accessible from other packages.
  - ***Private***: Identifiers starting with a lowercase letter (e.g., unexportedField) are restricted to their own package.
- ***Polymorphism (Interfaces)***: Go achieves polymorphism through implicit interfaces. A type satisfies an interface simply by implementing its required methods; there is no implements keyword.
- ***Inheritance (Composition & Embedding)***: Go does not support classical inheritance. Instead, it uses struct embedding (composition), where one struct is placed inside another to "inherit" its fields and methods

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
