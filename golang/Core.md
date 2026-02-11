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
In Go, type conversion is explicit, meaning you must manually convert a value from one type to another.
Be aware about during type conversions between certain types can lead to data loss.

int	-> float64   || var f float64 = float64(i)

float64	-> int || var i int = int(f)	

int -> string ||  var stringValue string := strconv.Itoa(intValue)

string -> int || i, err := strconv.Atoi(str) // Atoi returns the integer value and a potential error

string -> []byte || b := []byte(s)

[]byte -> string || s := string(b)

## Memory management and Garbage collection 

### Memory management :

memory management in Golang, its simple compared to other languages. Golang handles memory allocation and deallocation automatically. Go compiler is smart. it used escape analysis to decide, whether data is allocated on the stack or heap memory.



The 2 main methods used for memory allocation in Golang. 

1. new() 

Using new() we allocated memory but not initialize.
new() give to Zero storage


2. make()

and Using make() we allocated memory and it is initialize.
make() give to non-Zero storage




### Garbage collection :

In Golang, GC automatically happens when objects are out of scope or nil. Go internally uses "Tricolor Mark-and-Sweep" algorithm for Garbage collection.

also, Golang provide limited excess to manipulate GC using GOGC and GOMEMLIMIT during go env setup.

#### Manually trigger garbage collection using 
== runtime.GC() during go runtime.

## Pointer in go ? how go handle in Golang ?

In Go, a pointer is simply a variable that stores Memory address of another variable value.

In pointer, There are 2 symbols need to know for Core Operators.

1. Address-of operator (&) 
This generates a pointer. It finds where value is sitting in memory.

2. Dereference operator (*)
"follows" the pointer to the actual value stored at that address.


### How Go Handles Pointers:

Go is memory-safe. Uninitialized pointers are nil.
Go does not allow pointer arithmetic, so we can’t access random memory locations.
Nil pointer is checked at runtime.

 

## Function and method (variadic | anonymous )

### Function

A function is piece or blocks of code that does a specific task and called independently.
Function help organize code, improve readability, and allow re-use.

### Methods:

In Go, method is like function but associated with a special argument type called a receiver. 
The receiver binding the method to a specific type, which can be a struct or a non-struct type.
Method is called on an instance of that type and is used to define behavior related to that structure.


### variadic Function:: 

In Go, Function that can accept a variable number of arguments of any type.
Variadic functions are declared with an ellipsis (...) before the type.
Ex: fmt.Println()

### Anonymous Function

An anonymous function in Go is a function that does not have a name. It can be defined and used immediately by adding () at the end.
Primary use of anonymous functions in Goroutine.


## Closure
## Interfaces
## Generic  
## Method overloading 
