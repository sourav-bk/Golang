# Data type in Go | Primitive / Non-Primitive

Go is a statically and strongly typed compiled language, that meaning every variable has a specific data type that cannot change after declaration. It makes Golang as Type safety to improve reliability and performance.

In Go, data types are broadly classified into two categories: Primitive and Non‑Primitive data types.

  ## - Primitive Data Types ::
Primitive data types, also known as basic or core types, are the fundamental building blocks of the Go language. They are used to store simple values.
Common primitive data types in Go include:

 Boolean: bool — stores true or false
 
 Integer Types: int, int8, int16, int32, int64, uint, uint8, uint16, uint32, uint64
 
 Floating‑Point Types: float32, float64
 
 String: string — used to store text data
 
 Numeric Types: complex types (complex64, complex128)

 note -- Go provides multiple  Primitive types based on bit size (8, 16, 32, and 64 bits).

 ## - Non‑Primitive Data Types ::
Non‑primitive data types are built using primitive data types. They are used to store collections of data, references to values, or more complex data structures.

Common non‑primitive data types in Go include:

Arrays
Fixed‑length collections of elements of the same primitive data type.

Slices
Dynamic‑length sequences of elements of the same primitive data type.

Structures (Structs)
Used to group multiple fields of different data types into a single unit.

Maps
Key‑value pairs where keys are unique and values can be duplicated.

Pointers
Store the memory address of another variable.

Channels
Used for communication between goroutines, allowing concurrent functions to exchange data safely.

 ## Variables && Constant

### Variable:
Variables are containers for storing data values.
Go is a statically and strongly typed compiled language, that meaning every variable have some specific data type that cannot change after declaration but value can be changed (or varied) during the execution of a program.

Variables are declared using the 'var' keyword or the shorthand ':=' operator. 


### Constants:
In Go, a constant is an immutable value that must be assigned at compile time and cannot be changed during the program's execution. They are useful for fixed values.

Constants, declared with the 'const' keyword, hold immutable values determined at compile time. 


## Zero Value of variable in GO

In Go, the Zero Value is a default value assigned to a variable when it is declared but not initialized that ensuring variables always hold a valid value, even without explicit initialization.

Each type has its own zero value.

Numeric types ( int, float64, byte, etc.) = 0 (or 0.0 for floats)
Boolean = false
String = "" (An empty string)
Pointers, Slices, Maps, Channels, Functions or Interfaces = nill

## Convert types in Golang

## Garbage collection 
## memory management in go
## Pointer ? how go handel  
## Handle memory leak 
## new() and make() keyword 
## manually trigger garbage collection 
## Function and method (variadic | anonymous )
## Closure
## Interfaces
## Generic  
## Method overloading 
