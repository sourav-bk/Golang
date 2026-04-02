Go is not a traditional object-oriented programming (OOP) language but it supports most OOP concepts using structs, methods, and interfaces. 
Focusing on interfaces and composition rather than traditional class-based inheritance. This leads to a more flexible and modular design.



Core OOP Concepts in Go :

- ***Classes and Objects (Structs)***: Go uses structs instead of classes to define data structures. An "object" in Go is an instance of a struct.
- ***Encapsulation (Exported Identifiers)***: Access control is managed at the package level using naming conventions.
- ***Public***: Identifiers starting with an uppercase letter (e.g., ExportedField) are accessible from other packages.
- ***Private***: Identifiers starting with a lowercase letter (e.g., unexportedField) are restricted to their own package.
- ***Polymorphism (Interfaces)***: Go achieves polymorphism through implicit interfaces. A type satisfies an interface simply by implementing its required methods; there is no implements keyword.
- ***Inheritance (Composition & Embedding)***: Go does not support classical inheritance. Instead, it uses struct embedding (composition), where one struct is placed inside another to "inherit" its fields and methods
