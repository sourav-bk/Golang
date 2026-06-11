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

  Polymorphism is one of the key concepts of object-oriented programming and means “many forms.” It refers to the ability of a single method, function, or interface to behave differently based on the context or the type of data it operates on. In simple terms, polymorphism allows the same operation to be performed in different ways.

  In traditional object-oriented languages, polymorphism is often achieved using method overloading or method overriding (same method name with different implementations or signatures).

  However, Go does not support classes, inheritance, or method overloading. Instead, polymorphism in Go is achieved using interfaces.

  Go interfaces are implemented implicitly. This means a type does not need to explicitly declare that it implements an interface; if it provides the required methods, it automatically satisfies that interface. Because of this, a variable of an interface type can hold values of any type that implements the interface.

  This flexibility allows Go to achieve polymorphism. Different types can implement the same interface in their own way, and the same method call can produce different behavior depending on the actual type of the value stored in the interface.

  Polymorphism in Go is primarily achieved through interfaces, enabling code to work with multiple types in a uniform and flexible manner without needing class-based inheritance.

    ```go
  package main

  import "fmt"

  type Animal interface {
	  Eat()
  }

  type Dog struct{}

  func (Dog) Eat() { fmt.Println("meat") }

  type Cat struct{}

  func (Cat) Eat() { fmt.Println("fish") }

  func main() {
	  var a Animal

	  a = Dog{}
	  a.Eat()   // meat

	  a = Cat{}
	  a.Eat()  // fish
  }

  ```

- ***Inheritance (Composition & Embedding)***:

  Go does not support classical inheritance. Instead, it uses struct embedding (composition), where one struct is placed inside another struct to "inherit" its fields and methods.


  
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

















|   | Explicit Fields | Implicit |
| --- | --- | --- |
| | An explicit field is a standard field declared with both a name and a data type. When accessing it, you must explicitly specify the field name in your code |n implicit field is created using anonymous embedding—where you specify only the type name (e.g., Address) without a designated variable name. Go automatically "promotes" the fields of the embedded struct into the parent struct, letting you access them implicitly without typing out the nested struct's name. |
| example | Row 2, Col 2 | Row 2, Col 3 |
