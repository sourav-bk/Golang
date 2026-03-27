# Core GO :

<details><summary><h3><mark>What is GO? - Why Developers Choose Go?</mark></h3></summary>
  
Go (Golang) is a statically typed, compiled programming language designed by Google.
It is known for its simplicity, fast, and efficient, especially for building scalable backend systems.

Reasons for choosing Go---

<b>1. Performance and Efficiency : </b>
Go is very fast because it runs directly on machine code. It can handle many requests at the same time without slowing down, which makes applications more responsive.

<b>2. Cost Efficient : </b>
Go uses less memory and RAM, so applications need fewer servers. This helps companies reduce cloud and infrastructure costs, especially for high‑traffic systems.

<b>3. Fast Development & Deployment : </b>
Go is easy to write and understand, and it compiles very quickly. It creates a single executable file, which makes deployment simple and reliable.

<b>4. Strong Standard Library : </b>
Go comes with many built‑in features like HTTP servers, JSON handling, logging, and testing. This reduces the need for extra tools and saves development time.

<b>5. Cloud & Microservices Friendly : </b>
Go is well suited for cloud applications and microservices. It scales easily, works well with Docker and Kubernetes, and is widely used in modern systems.

We chose Go because it is fast, cost‑effective, easy to develop and deploy, and works very well for cloud‑based microservices.

</details>

<details><summary><h3><mark>How Run Go Code?</mark></h3></summary>
Running a Go application is simple because Go is a compiled language. When you build a Go program, it is compiled into a single static binary file. This means you do not need to install a Go runtime on the target machine — you only need the compiled file.

However, to compile Go code, you must install Go on your system (or download the Go compiler). You write your code in a file with the .go extension.

Every Go program starts from the main function. The main function is the entry point of the program, and execution always begins there.

To create an executable file, you use the go build command. By default, this command builds an executable for the current operating system and architecture.

If you want to build an executable for a different target system, you can specify the GOOS and GOARCH environment variables when running go build. This allows you to cross-compile for another operating system or CPU architecture.

Go also provides the go run command, which is used to quickly compile and run a Go program from the command line without creating a permanent executable file.

</details>

<details><summary><h3><mark>init() and main() function Role?</mark></h3></summary>  
  
  - <b>main() : </b> The main() function is the entry point of the executable application, determining the program's primary logic and flow. 
  
  - <b>init() : </b> In Go, the init() function is a special built‑in function that the Go runtime executes automatically once per package, before the main() function runs.

    It is commonly used for tasks such as initializing global variables, validating configuration, or setting up resources (for example, checking database connections).
    
</details>
  
<hr>
<details><summary><h3><mark>What is GOROOT | GOPATH</mark></h3></summary>
  
  - <b> GOROOT: </b> GOROOT points to the Go installation directory.
  This is where the Go compiler, standard library, and tools present.
  need to set GOROOT manually. The Go installer sets it automatically.

  - <b> GOPATH: </b> GOPATH is Where Go code dependencies, downloaded third‑party packages, and compiled binaries are stored.
    
    Before Go 1.11 version , all Go projects have to required to reside the $GOPATH/src directory.
  after introduced of stable production ready "'Go Modules'" on Go 1.16 version. GOPATH mode was effectively disabled by default. As a result, developers no longer need to place projects inside GOPATH, and Go projects can now live anywhere on the filesystem.
  However, GOPATH is still used internally by Go for purposes such as the module cache and installed binaries.

</details>
<details><summary><h3><mark>Go Packages || Go Modules || Go workspaces</mark></h3></summary>
  
  - <b>Go Packages :</b>
    A package is a collection of one or more Go source files (.go files) located in the same directory that are compiled together and share the same package name.

    Every Go source file must declare its package name at the very top of the file using a package declaration.

    Packages is fundamental unit for organizing and reusing code in Go, enabling related source files to be grouped logically while helping structure programs, control visibility, and promote modular, maintainable code.
   
  - <b>Go Modules :</b>
    Go Modules are the official dependency management system for Go projects. They were introduced in Go 1.11 and became the default behavior starting with Go 1.16. Go Modules allow projects to be developed and maintained outside of GOPATH, enabling better version control, dependency management, and reproducible builds.
    
#### Go Cli :

- <h6>go mod init :</h6>
To create a Go module, the go mod init command is used in the root directory of a Go project. This command initializes the project as a module and prepares it for dependency tracking.

- <h6>go.mod :</h6>
go mod init creates a go.mod file. This file defines the module’s import path, specifies the Go version the project supports, and lists all the direct dependencies required by the application.

- <h6>go.sum :</h6>
Go Modules also use a go.sum file. This file is not a lock file, but a security file that stores cryptographic checksums for all direct and indirect dependencies used in the project. These checksums ensure the integrity and authenticity of downloaded modules by verifying that the dependencies have not been tampered with

- <h6>go get :</h6>
The go get command is used to add, upgrade, or downgrade dependencies to a specific version. 

- <h6>go mod tidy :</h6>
The go mod tidy command is used to maintain module files. It adds any missing dependencies, removes unused ones, and cleans up both the go.mod and go.sum files to keep the dependency list accurate and minimal.

<br><br>
</details>

<details><summary><h3><mark>Access Modifiers in Go: Exported vs Unexported Identifiers</mark></h3></summary> 

  Go does not use traditional access‑control keywords such as public, private, or protected. Instead, access control is determined by the capitalization of an identifier’s name. This rule controls whether an identifier can be accessed outside the package in which it is defined.
  
  - <b>Exported Identifiers</b> :

    An identifier whose name starts with an uppercase letter is called an exported identifier. Exported identifiers are accessible from any other package that imports the defining package.
  
  - <b>Unexported Identifiers</b> :

    An identifier whose name starts with a lowercase letter is called an unexported identifier (also known as package‑private). Unexported identifiers are accessible only within the same package and cannot be accessed from outside it.

</details>

<hr>

<details><summary><h3><mark>Data type in Go? Primitive & Non-Primitive</mark></h3></summary>
  
  Go is a statically and strongly typed compiled language, that meaning every variable has a specific data type that cannot change after declaration. It makes Golang as Type safety to improve reliability and performance.
  
  In Go, data types are broadly classified into two categories: Primitive and Non‑Primitive data types.
  
  <ul>
    <li><details><summary><h5>Primitive Data Types</h5></summary>
    Primitive data types, also known as basic or core types, are the fundamental building blocks of the Go language. They are used to store simple values. 
  
  Common primitive data types in Go include:
    <ul>
    <li><h6>Boolean:</h6></li> bool — stores true or false
    <li><h6>Integer:</h6></li> int, int8, int16, int32, int64, uint, uint8, uint16, uint32, uint64
    <li><h6>Floating‑Point:</h6></li> float32, float64
    <li><h6>String:</h6></li> string — used to store text data
    <li><h6>Numeric Types:</h6></li> complex types (complex64, complex128)
    </ul><br>

  > NOTE:  Go provides multiple Primitive types based on bit size (8, 16, 32, and 64 bits). 
    </details>
    </li>
    <li><details><summary><h5>Non-Primitive Data Types</h5></summary>
    Non‑primitive data types are built using primitive data types. They are used to store collections of data, references to values, or more complex data structures.
  
  Common non‑primitive data types in Go include:
    <ul>
    <li><h6>Arrays:</h6></li> Fixed‑length collections of elements of the same primitive data type
    <li><h6>Slices:</h6></li> Dynamic‑length sequences of elements of the same primitive data type.
    <li><h6>Structures (Structs):</h6></li> Used to group multiple fields of different data types into a single unit.
    <li><h6>String:</h6></li> string — used to store text data
    <li><h6>Maps:</h6></li> Key‑value pairs where keys are unique and values can be duplicated.
    <li><h6>Pointers:</h6></li> Pointers Store the memory address of another variable.
    <li><h6>Channels:</h6></li> Channels Used for communication between goroutines, allowing concurrent functions to exchange data safely.
    </ul><br>
    </details>
    </li>
  </ul>
    <details><summary>Convert types in Golang</summary>
      
  In Go, type conversion is explicit, meaning you must manually convert a value from one type to another. Be aware about during type conversions between certain types can lead to data loss.
  
  - int -> float64 || var f float64 = float64(i)
  - float64 -> int || var i int = int(f)
  - int -> string || var stringValue string := strconv.Itoa(intValue)
  - string -> int || i, err := strconv.Atoi(str) // Atoi returns the integer value and a potential error
  - string -> []byte || b := []byte(s)
  - []byte -> string || s := string(b)
    
    </details>
</details>

<details><summary><h3><mark>Variables & Constant</mark></h3></summary>
  Variable:
  Variables are containers for storing data values. Go is a statically and strongly typed compiled language, that meaning every variable have some specific data type that cannot change after declaration but value can be changed (or varied) during the execution of a program.
  Variables are declared using the 'var' keyword or the shorthand ':=' operator.
  
  Constants:
  In Go, a constant is an immutable value that must be assigned at compile time and cannot be changed during the program's execution. They are useful for fixed values.
  
  Constants, declared with the 'const' keyword, hold immutable values determined at compile time.
</details>

<details><summary><h3><mark>Zero Value of variable in GO</mark></h3></summary>
  In Go, the Zero Value is a default value assigned to a variable when it is declared but not initialized that ensuring variables always hold a valid value, even without explicit initialization.
  
  Each type has its own zero value.
  
  Numeric types ( int, float64, byte, etc.) = 0 (or 0.0 for floats) Boolean = false String = "" (An empty string) Pointers, Slices, Maps, Channels, Functions or Interfaces = nill
</details>

<details><summary><h3><mark>Convert types in Golang</mark></h3></summary>
  
  In Go, type conversion is explicit, meaning you must manually convert a value from one type to another. Be aware about during type conversions between certain types can lead to data loss.
  

  - int -> float64 || var f float64 = float64(i)
  - float64 -> int || var i int = int(f)
  - int -> string || var stringValue string := strconv.Itoa(intValue)
  - string -> int || i, err := strconv.Atoi(str) // Atoi returns the integer value and a potential error
  - string -> []byte || b := []byte(s)
  - []byte -> string || s := string(b)
  
</details>
<hr>

<details><summary><h3><mark>Memory management and Garbage collection</mark></h3></summary>
  
  - **Memory management** : In Golang, its simple compared to other languages. Golang handles memory allocation and deallocation automatically. Go compiler is smart. it used escape analysis to decide, whether data is allocated on the stack or heap memory.

    The 2 main methods used for memory allocation in Golang.
    
    | **new()** | **make()** |
    |:---|:---|
    | Using new() we allocated memory but not initialize. new() give to Zero storage | and Using make() we allocated memory and it is initialize. make() give to non-Zero storage
<br>

  - **Garbage collection** :
    In Golang, GC automatically happens when objects are out of scope or nil. Go internally uses "Tricolor Mark-and-Sweep" algorithm for Garbage collection.
    Also, Golang provide limited excess to manipulate GC using GOGC and GOMEMLIMIT during go env setup.
  > Manually trigger garbage collection using `runtime.GC()` during go runtime
  
</details>

<details><summary><h3><mark>Pointer in go ? how go handle in Golang?</mark></h3></summary>
  
  In Go, a pointer is simply a variable that stores Memory address of another variable value.
  In pointer, There are 2 symbols need to know for Core Operators.
  
  - **Address-of operator (&)** This generates a pointer. It finds where value is sitting in memory.
  - **Dereference operator (*)** "follows" the pointer to the actual value stored at that address.
    
    
**How Go Handles Pointers:**

Go is memory-safe. Uninitialized pointers are nil. Go does not allow pointer arithmetic, so we can’t access random memory locations. Nil pointer is checked at runtime.
    
</details>

<details><summary><h3><mark>Function and method (variadic | anonymous )</mark></h3></summary>
  
  - ##### Function :
    A function is piece or blocks of code that does a specific task and called independently. Function help organize code, improve readability, and allow re-use.
  
  - ##### Methods :
    In Go, method is like function but associated with a special argument type called a receiver. The receiver binding the method to a specific type, which can be a struct or a non-struct type. Method is called on an instance of that type and is used to define behavior related to that structure.
    
  - ##### variadic Function :
    In Go, Function that can accept a variable number of arguments of any type. Variadic functions are declared with an ellipsis (...) before the type. Ex: fmt.Println().

  - ##### Anonymous Function :
    An anonymous function in Go is a function that does not have a name. It can be defined and used immediately by adding () at the end. Primary use of anonymous functions in Goroutine.

</details>

<details><summary><h3><mark>Closure | Interfaces | Generic</summary></mark></h3>
  
  - ##### Closure :
    A closure is an anonymous function that uses variables from outside its own body. In Go, a closure captures variables from its outer scope and remembers their values between calls.
  
  - ##### Interfaces :

    In Go, an interface is a collection of method signatures . It acts as a contract that type must fulfill by implementing all the methods declared in the interface.

    Interfaces can also be used as variable types. The empty interface (interface{}) can hold values of any type, such as integers, strings, or float.

  - ##### Generic :
    Generics introduced in Go 1.18. Generics in Go allow to write functions and types that work with multiple data types while maintaining type safety.

</details>
<br>

# Go Routine & Channel :


<br>

# Error Handling :
 <details><summary><h3><mark>Error in go? Panics | recover | defer </mark></h3></summary>
   
   In Golang, Error isn't an exception that crashes program — it’s just a value. Go treats errors as "first-class citizens," meaning we handle like, as any other variable.
   The most common way to handle errors is to check if the returned error value is nil (meaning success) or not nil (meaning failure), and then deal with the failure.
   
   One of the most important concepts in Go is knowing when to return an error and when to panic. They may look similar at first, but they exist for completely different reasons by design.
   
   - ##### Errors: Expected Failures

     Errors represent issues that can happen during normal program execution. They’re part of the flow, and program should be prepared for them. Errors should be handled gracefully. They should not crash your program.
   
   - ##### Panics: Unexpected Failures

     A panic indicates something went terribly wrong, usually a programmer mistake or a critical, unrecoverable state.
     Stop normal execution Crash the program.
   
   - ##### recover:

     Inside the deferred function, recover() is called. If a panic is active, it captures the panic value and stops the unwinding of the stack, allowing the program to continue running.
   <br><br>
- #### defer statement:
  
  The defer statement guarantees that, Any function method, or statement is executed at the end of the surrounding function.
  If a function contains multiple defer statements, they are pushed onto a stack and executed in reverse order, following Last-In, First-Out (LIFO) behavior.
  
 </details>

<br>

# OPPOS  

# Keyword
- Range
- Defer
- select
- [GO](#what-is-go---why-developers-choose-go)
