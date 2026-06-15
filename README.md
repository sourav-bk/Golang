# Core GO :

<details><summary><h3><mark>What is GO? - Why Developers Choose Go?</mark></h3></summary>
  
Go (Golang) is a statically typed, compiled programming language designed by Google.
It is known for its simplicity, fast, and efficient, specially for building scalable backend systems.

Reasons for choosing Go---

<b>1. Performance and Efficiency : </b>
Go is very fast because it runs directly on machine code. It can handle many requests at the same time without slowing down, which makes applications more responsive.

<b>2. Cost Efficient : </b>
Go uses less memory and RAM, so applications need fewer servers. This helps companies reduce cloud and infrastructure costs, specially for high‑traffic systems.

<b>3. Fast Development & Deployment : </b>
Go is easy to write and understand, and it compiles very quickly. It creates a single executable file, which makes deployment simple and reliable.

<b>4. Strong Standard Library : </b>
Go comes with many built‑in features like HTTP servers, JSON handling, logging, and testing. This reduces the need for extra tools and saves development time.

<b>5. Cloud & Microservices Friendly : </b>
Go is well suited for cloud applications and microservices. It scales easily, works well with Docker and Kubernetes, and is widely used in modern systems.

We chose Go because it is fast, cost‑effective, easy to develop and deploy, and works very well for cloud‑based microservices.

</details>

<details><summary><h3><mark>How Run Go Code?</mark></h3></summary>
Running a Go application is simple because Go is a compiled language. When build a Go program, it is compiled into a single static binary file. This means we do not need to install a Go runtime on the target machine — only need the compiled file.

However, to compile Go code, must install Go on system (or download the Go compiler). we write code in a file with the .go extension.

Every Go program starts from the main function. The main function is the entry point of the program, and execution always begins there.

To create an executable file, we use the go build command. By default, this command builds an executable for the current operating system and architecture.

If we want to build an executable for a different target system, we can specify the GOOS and GOARCH environment variables when running go build. This allows we to cross-compile for another operating system or CPU architecture.

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


- **go fmt — Code Formatter**

  Automatically formats Go source code to follow the official Go style. It Fix indentation Align, spacing, Organizes code layout consistently and Remove unnecessary parentheses or formatting issues.
  - CMD:
    - `go fmt main.go` (format single file)
    - `go fmt ./...` (format an entire package)
    - 

  
- **go vet — Static Analyzer (Bug Detector)**

  Analyzes Go code to identify suspicious constructs that may indicate potential bugs, even though the code compiles successfully. It uses heuristic checks, which means not all reported issues are guaranteed to be real problems, but it helps uncover mistakes that the compiler does not detect.

  Its check Incorrect Printf format strings, Un-used variables or assignments, Mis-used of struct tags, Un-reachable code, Possible nil dereferences
  - CMD:
    - `go vet main.go` (format single file)
    - `go vet ./...` (format an entire package)
    - `go vet` (Current Package)
  
- **go doc — Documentation Tool**
  
  Displays documentation for Go packages, functions, types, and methods. Its Shows comments written above functions/types and Helps explore APIs Doc from terminal.
  - CMD
    - `go doc module/package.Func`
      
<br><br>
</details>

<details><summary><h3><mark>Access Modifiers in Go: Exported vs Unexported Identifiers</mark></h3></summary> 

  Go does not use traditional access‑control keywords such as public, private, or protected. Instead, access control is determined by the capitalization of an identifier’s name. This rule controls whether an identifier can be accessed outside the package in which it is defined.
  
  - <b>Exported Identifiers</b> :

    An identifier whose name starts with an uppercase letter is called an exported identifier. Exported identifiers are accessible from any other package that imports the defining package.
  
  - <b>Unexported Identifiers</b> :

    An identifier whose name starts with a lowercase letter is called an unexported identifier (also known as package‑private). Unexported identifiers are accessible only within the same package and cannot be accessed from outside it.

</details>

<details><summary><h3><mark> Context Package </mark></h3></summary>

 The context package is one of the most important built-in packages in Go.

 It provides a standard way to manage the lifecycle of goroutines, handle timeouts and deadlines, and pass request-scoped data across API boundaries.

 - **Why Do We Need Context?**

 When a client sends an HTTP request, the server creates one or more goroutines to handle the request efficiently. These goroutines may execute database queries, communicate with external APIs, and launch additional goroutines for parallel processing. All of these operations work together to generate the final response sent back to the client.

 If the user cancels the initial request OR if it times-out OR want all those downstream goroutines to stop working immediately to free up resources. The context package halps how we orchestrate/manage that goroutines .
	
 - **Core Concepts**
   
 The context.Context is an immutable interface with four core methods.
  - Done() <-chan struct{}: Returns a channel that closes when the context is canceled or times out.
  - Err() error: Explains why the context was closed (e.g., context.Canceled or context.DeadlineExceeded).
  - Deadline() (deadline time.Time, ok bool): Returns the execution end time if one is set.
  - Value(key any) any: Fetches request-scoped metadata associated with a key.		
	
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
      
  In Go, type conversion is explicit, meaning we must manually convert a value from one type to another. Be aware about during type conversions between certain types can lead to data loss.
  
  - int -> float64 || var f float64 = float64(i)
  - float64 -> int || var i int = int(f)
  - int -> string || var stringValue string := strconv.Itoa(intValue)
  - string -> int || i, err := strconv.Atoi(str) // Atoi returns the integer value and a potential error
  - string -> []byte || b := []byte(s)
  - []byte -> string || s := string(b)
    
    </details>
</details>

<details><summary><h3><mark> Character | byte - rune | alias | Enums </mark></h3></summary>

  
</details>

<details><summary><h3><mark>Variables & Constant</mark></h3></summary>
  
  - ***Variable:***
  
  Variables are containers for storing data values. Go is a statically and strongly typed compiled language, that meaning every variable have some specific data type that cannot change after declaration but value can be changed (or varied) during the execution of a program.
  Variables are declared using the 'var' keyword or the shorthand ':=' operator.
  
  - ***Constants:***
  
  In Go, a constant is an immutable value that must be assigned at compile time and cannot be changed during the program's execution. They are useful for fixed values.
  
  Constants, declared with the 'const' keyword, hold immutable values determined at compile time.
  
</details>

<details><summary><h3><mark>Zero Value of variable in GO</mark></h3></summary>
  In Go, the Zero Value is a default value assigned to a variable when it is declared but not initialized that ensuring variables always hold a valid value, even without explicit initialization.
  
  Each type has its own zero value.
  
  Numeric types ( int, float64, byte, etc.) = 0 (or 0.0 for floats) Boolean = false String = "" (An empty string) Pointers, Slices, Maps, Channels, Functions or Interfaces = nill
</details>

<details><summary><h3><mark>Convert types in Golang</mark></h3></summary>
  
  In Go, type conversion is explicit, meaning we must manually convert a value from one type to another. Be aware about during type conversions between certain types can lead to data loss.
  

  - int -> float64 || var f float64 = float64(i)
  - float64 -> int || var i int = int(f)
  - int -> string || var stringValue string := strconv.Itoa(intValue)
  - string -> int || i, err := strconv.Atoi(str) // Atoi returns the integer value and a potential error
  - string -> []byte || b := []byte(s)
  - []byte -> string || s := string(b)
  
</details>
<hr>

<details><summary><h3><mark>Memory management and Garbage collection (GC) | Memory Leaks </mark></h3></summary>
  
  - **Memory management** : In Golang, its simple compared to other languages. Golang handles memory allocation and deallocation automatically. Go compiler is smart. it used escape analysis to decide, whether data is allocated on the stack or heap memory.

    The 2 main methods used for memory allocation in Golang.
    
    | **new()** | **make()** |
    |:---|:---|
    | Using new() we allocated memory but not initialize. new() give to Zero storage | and Using make() we allocated memory and it is initialize. make() give to non-Zero storage
<br>

  - **Garbage collection (GC) ** :
    In Golang, GC automatically happens when objects are out of scope or nil. Go internally uses "Tricolor Mark-and-Sweep" algorithm for Garbage collection.
    Also, Golang provide limited excess to manipulate GC using GOGC and GOMEMLIMIT during go env setup.
  > Manually trigger garbage collection using `runtime.GC()` during go runtime.

  - ** Memory leaks ** :
    
    Go has automatic Garbage Collection. so, traditional memory leaks are un-common.

    Memory leaks can still happen when memory remains referenced, even the application no longer requires them and therefore cannot be reclaimed by the GC.

    Common causes include goroutine leaks, Active pointers,un-bounded caches or maps, slices retaining large backing arrays, missing context cancellations, global variables holding references and unclosed resources keep unwanted data alive.

    Most Go memory leaks are caused by logical errors that keep un-used objects alive rather than by manual memory management issues.
    
  
</details>

<details><summary><h3><mark>Pointer in go ? how go handle in Golang?</mark></h3></summary>
  
  In Go, a pointer is simply a variable that stores Memory address of another variable value.
  In pointer, There are 2 symbols need to know for Core Operators.
  
  - **Address-of operator (&)** This generates a pointer. It finds where value is sitting in memory.
  - **Dereference operator (*)** "follows" the pointer to the actual value stored at that address.
    
    
**How Go Handles Pointers:**

Go is memory-safe. Uninitialized pointers are nil. Go does not allow pointer arithmetic, so we can’t access random memory locations. Nil pointer is checked at runtime.
    
</details>

<details><summary><h3><mark>Function and method ( variadic | anonymous )</mark></h3></summary>
  
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
    A closure is an anonymous function., that uses variables from outside.. its own body. In Go, Closure captures variables., from its outer scope and remembers their values between calls.
  
  - ##### Interfaces :

    In Go, an interface is a collection of method signatures. It acts as a contract., that type must ful-fill by implementing all the methods., which declared in the interface.

    Interfaces can also be used as variable types. The empty interface (interface{}) can hold values of any type, such as integers, strings, or float.

    **Embedding Interfaces:** We can combining multiple smaller interfaces into one larger interface. Instead of creating a big interface from scratch, you can reuse existing small interfaces and join them together. This makes your code cleaner, easier to manage, and more reusable. It follows Go’s idea of composition over inheritance by building bigger functionality from smaller pieces.

  - ##### Generic :
    Generics introduced in Go 1.18 . Generics in Go, allow to write functions and types.., that work with multiple data types.., while maintaining type safety.

</details>

<details><summary><h3><mark> Range, switch, default, select </summary></mark></h3>
  
  - ##### Range :
    In Golang, Range keyword used in different kinds of data structures., in-order to iterates over elements. The range keyword is mainly used in.., <mark>For</mark> loops in-order to iterate over all the elements.., of a map, slice, channel, or an array.
  
  - ##### switch, default  :
    - switch :

      A switch statement is a shorter way to write a sequence of if - else statements. It runs the first case whose value is equal to the condition expression.

      Go provides automatic break statements after each case.
      
    - default :

      The default case in a select is run if no other case is ready.

      
    - select :

      The select statement lets a goroutine wait on multiple channel operations simultaneously.
      
      It blocks until one of its cases is ready to execute, making it essential for managing concurrency.
      If, multiple channels are ready at the same time, Go picks one at random to ensure fairness.
      
      It functions like a switch statement, but instead of checking values, each case is a communication operation.

</details>
<br><br>

# Error Handling :
 <details><summary><h3><mark>Error in go? Panics | recover | defer </mark></h3></summary>
   
   In Golang, Error isn't an exception that crashes program — it’s just a value. Go treats errors as "first-class citizens," meaning we handle like, as any other variable.
   
   Most common way to handle errors is to check, if the returned error value is nil (meaning success) or not nil (meaning failure), and then deal with the failure.
   
   One of the most important concepts in Go is knowing., when to return an error.., and when to panic. They may look similar at first, but they exist for completely different reasons by design.
   
   - ##### Errors: Expected Failures

     Errors re-present issues, that can happen during normal program execution. They’re part of the flow, and program should be prepared for them.

     Errors should be handled gracefully and should not crash program.
   
   - ##### Panics: Unexpected Failures

     Panic Indicates, something terribly wrong, usually a programmer mistake or a critical, unrecoverable state..,  that Stop normal execution and Crash the program.
   
   - ##### recover:

     Inside the deferred function, recover() is called. If a panic is active, it captures the panic value and stops the un-winding of the stack, that allowing the program to continue running.
     
   <br><br>
   
- #### defer statement:
  
  The defer statement guarantees that, Any function method, or statement is executed at the end of the surrounding function.
  If a function contains multiple defer statements, they are pushed onto a stack and executed in reverse order, following Last-In, First-Out (LIFO) behavior.
  
 </details>

<br>


# Goroutine, Channel, Concurrency, Deadlock :
<details><summary><h3><mark>Go Routine and Channel? Type of Channel? </mark></h3></summary>
 
## ***Go Routine*** :
A Goroutine is a lightweight thread managed by the Go runtime, Used to run multiple function or method Concurrently.
While traditional OS thread might take up 1MB of memory, a Goroutine starts with just 2KB.

---
#### Difference between Goroutine and Thread 
# Goroutines vs OS Threads

| Feature             | Goroutine                                                                | OS Thread                                                                |
|---------------------|--------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Management          | Managed entirely by the Go runtime                                       | Managed by the Operating System Kernel                                   |
| Memory Footprint    | Starts small (~2 KB) and dynamically grows                               | Usually reserves a fixed, large size (~1+ MB) per thread                 |
| Creation Cost       | Extremely low – creates a lightweight state machine in user space        | High – requires expensive system calls and kernel-level bookkeeping      |
| Maximum Capacity    | Millions can run concurrently                                            | Typically thousands at most before performance degrades                  |
| Communication       | Uses channels for safe communication without explicit locks              | Requires shared memory, mutexes, and locks to prevent race conditions    |
| Context Switching   | Fast – handled in user space by the Go scheduler                         | Slower – involves kernel mode switching and CPU register save/restore    |

---
***Concurrency***

Go follow Concurrency. Concurrency is the ability to run multiple things at once.
When we normally write code, that code runs sequentially, meaning that each job is run back to back. 
In concurrent code, those jobs are running simultaneously.

- #### Concurrency vs. Parallelism
Concurrency is not Parallelism.

Concurrency is ability to handle many tasks at once. and Parallelism doing multiple things at the exact same time.

I will give small example:

- Case 1: ***Concurrency*** - I was writing something, then I get thirsty, so I stopped writing and drank some water, then started writing again.

- Case 2: ***Parallelism*** - I'm drinking and eating, Coke and pizza also watching TV at the same time. 

Go is designed to be concurrent, which allows., it to be parallel, when have processor with multiple cores.

Go program can be concurrent, even on a single core machine, but it achieves true parallelism, when running on a multi-core system, 

And Go runtime efficiently distributes goroutines, across all available CPU cores.


## ***Channel*** :

***Channel*** in Go, is a communication mechanism used by goroutines. It allows safe data sharing between goroutines without locks.

Think of it as a pipe., through which.., goroutines send/receive values.

Go channels use the FIFO (First-In, First-Out) method.

If multiple goroutines are sending/receiving value, the order of operations is preserved, as they are processed., through the channel's internal buffer.

Channels are reference types. zero value is nil. Initialize using the make() function.

We can send and receive values on channel., with the channel operator, (<-)(->). ( receive operator && arrow operator )

By default, channels are bidirectional, but for better API design and type safety, we restrict them in function signatures:

- ***Bidirectional:*** chan T (can send and receive).

- ***Send-only:*** chan<- T (the arrow points into the chan).

- ***Receive-only:*** <-chan T (the arrow points out of the chan).

Channel has been closed using close() function. No values can be sent after closing., but Receivers can still read existing/buffered values after close. Channel close() Used to signal completion.

- ### Type of Channel 

Channels can be TWO type -- 1. Unbuffered Channel   2. Buffered Channel

- ***Unbuffered*** : Capacity of 0. The sender blocks until a receiver is ready. Used for strict synchronization. Since they have no capacity, they act as direct synchronization points.

- ***Buffered*** : Has a fixed capacity. The Sender only blocks when the buffer is full. receiver blocks when it's empty. its Allows asynchronous communication. Act as FIFO queues. The first value added to the buffer is the first one removed.

 
</details>

<details><summary><h3><mark>Concurrency in go</mark></h3></summary>
 
 Go follow Concurrency. Concurrency in Golang is one of most powerful features.
 
 Concurrency is the ability to run multiple tasks simultaneously.
 Its allows Go programs to make progress on independent operations by rapidly switching context between them, optimizing resource utilization and keeping applications responsive. 
 
 Concurrency is not Parallelism., although it enables parallelism.
 
 Concurrency is ability to handle many tasks at once. (not necessarily running at the exact same time — that’s parallelism)
 and Parallelism doing multiple things at the exact same time.
 
 
 I will give small example:
 
 - Case 1: Concurrency - I was writing something, then I get thirsty, so I stopped writing and drank some water, then started writing again.
 
 - Case 2: Parallelism - I'm drinking and eating, Coke and pizza also watching TV at the same time.
 
 If have only one processor, Go program can still be concurrent but it cannot be parallel.
 
 On the other hand, a well-written concurrent program might run efficiently in parallel on a multiprocessor system.

 Go program can be concurrent, even on the single core machine, but it achieves true parallelism, when running on a multi-core system.

 --- --- ---

 Go handles concurrency using the CSP(Communicating Sequential Processes) model.
 
 CSP model is formal mathematical model/theory for describing collection of independent sequential processes, how data will share in the concurrent systems. 
 
 Its follow that, do not share memory directly, share memory by Communicating.
 
 Managing concurrent in a program is a nightmare So CSP was designed precisely to solve in Managing concurrent, privent locks, race conditions, and unpredictable result or  crashes in concurrent go program.
 
 Go manage or makes concurrency using 
 
 1. Goroutines 2. Channels 3. select 4. Sync primitives like WaitGroup, Mutex, Once, etc.
    
 - ***1. Goroutines:***

   Goroutine is a lightweight thread managed by the Go runtime.
   
 - ***2. Channels:***

   Channel is used for communication between goroutines. Think of it as a pipe through which goroutines send and receive values.
   
 - ***3. Select:***
   
   The select statement lets a goroutine wait on multiple channel operations simultaneously.
   
   It blocks until one of its cases is ready to execute, making it essential for managing concurrency. If, multiple channels are ready at the same time, Go picks one at random to ensure fairness.

   It functions like a switch statement, but instead of checking values, each case is a communication operation.
   
 - ***4. Sync primitives like WaitGroup, Mutex, Once, etc.***

   In the Go programming language, WaitGroup, Mutex, and Once are essential tools in the sync package used for managing concurrent code.
   - WaitGroup: Waits for the collection of goroutines to finish executing.
   - Mutex: Locks shared data to prevent race-conditions. When, multiple goroutines read/write simultaneously.
   - Once: Guarantees a block of code runs exactly once (like for lazy initialization or singletons)

</details>

<details><summary><h3><mark>Data Race and Race Condition</mark></h3></summary>

## ***Race Conditions***:
A Race Condition is a logic/design errors, not syntax errors in the program when the correctness of the program depends on the order/timing of goroutines. A Race condition happens when multiple goroutines access and modify shared data concurrently using goroutines without proper synchronization, that causing un-predictable results.

Go makes detection easier with -race flag during run or test Go program to check unsynchronized memory access at runtime.
## ***Data Race*** :
A Data Race is a specific type of race condition that happens at the memory level when Two or more goroutines access the same memory location concurrently. There is no synchronization used to coordinate the access. It is a low-level memory safety issue.

All data races are race conditions. Not all race conditions are data races.
 
</details>


<details><summary><h3><mark>Deadlocks | WaitGroup | Mutex </mark></h3></summary>
 
Deadlock occurs when two or more goroutines are permanently blocked and waiting for each other to release resources or send/receive data — so no progress is possible.

In simple, Deadlock is a state where goroutines wait indefinitely for resources or communication, that causing the program to be stop executing.

In Go, deadlocks usually happen due to incorrect use of channels, mutexes, or wait groups.

- ***Channels*** :: Common Deadlock Scenarios in Go. Unbuffered Channel Blocking


- ***Circular Wait (Mutexes)*** :: This occurs when Goroutine A holds Lock 1 and waits for Lock 2, while Goroutine B holds Lock 2 and waits for Lock 1.

- ***Resource Leak / WaitGroup Misuse*** :: If increment a sync.WaitGroup but a goroutine crashes or returns before calling .Done(), the wg.Wait() call will block forever.


## sync.WaitGroup:

It's a fundamental tool for concurrency management.
Think of it as a counter that tells main program and wait till all goroutine finish. 
Without it, main function might finish and exit while goroutines are still halfway through their work. and that causing to Race Conditions.
It's also Standard Way to dill To prevent Race Conditions in Go.

sync.WaitGroup operates on  internal counter using three main methods:

- ***Add(int)***: Increments the counter by the number of goroutines we are starting.

- ***Done()***: Decrements the counter by 1. Usually called via defer inside the goroutine.

- ***Wait()***: Blocks the execution of the program (usually in main) until the counter reaches zero.


## sync.Mutex && Mutexes ::

In Go, when multiple goroutines try to access the same piece of data at the same time on the memory, its end up with a Date race. To prevent Date race , we use "Mutual Exclusion" locks, or Mutexes.

The standard Mutex is "exclusive." If one goroutine has the lock, nobody else can access the protected code until the lock is released.

For simple lock we use The sync.Mutex (The Simple Lock) or more specialized, "smart" lock we used sync.RWMutex.


- Mutexes have two methods
   - ####  Lock() :
     Blocks both new Readers and new Writers
  
   - #### Unlock() :
     Releases the lock for everyone.
  

- Also RWMutex have two methods for Read Lock and Read Unlock
   - #### RLock()
     Blocks new Writers, but allows other Readers.
  
   - #### RUnlock()
     Releases one reader's hold on the lock.
  
</details>


<details><summary><h3><mark> Worker pool </mark></h3></summary>
 Worker-pool in Go, is The concurrency pattern.
 Which is also known as thread pool.., it is the pattern used to achieve concurrency.
 
 Where fixed number of goroutines  — called workers.
 to process many jobs/task in background, from the shared queue.
 
 That pattern/design Clean the queue of jobs/task., using fixed number of goroutines/workers.,  which running in background concurrently and sent via a channel.


 This pattern limits the usage of resource, prevents system from being over-loaded by too many concurrent goroutines, and optimizes CPU utilization

</details>
<br>

# Oops :
 <details><summary><h3><mark> Object-oriented programming </mark></h3></summary>
	 
 Go is not a traditional object-oriented programming (OOP) language but it supports most OOP concepts using structs, methods, and interfaces. 
Focusing on interfaces and composition rather than traditional class-based inheritance. This make more flexible and modular design.

It achieves OOP concepts using structs (to represent class/objects), methods (functions attached to structs), interfaces (for polymorphism), and composition (for reuse).


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


 </details>

 <details><summary><h3><mark> Struct embedding </mark></h3></summary>
 In Go, struct embedding is a powerful way to build complex types through composition rather than inheritance. Since Go does not support classes or traditional inheritance, it achieves code reuse by allowing one struct to be embedded within another.

When a struct is embedded, its fields and methods are automatically promoted to the outer struct. This means the outer struct can access them directly, as if they were its own, without needing explicit qualification.

Struct embedding enables developers to create flexible, reusable, and maintainable designs. Instead of inheriting behavior, Go encourages composing smaller, focused structs into larger ones, resulting in cleaner and more modular code.

**Key Behaviors:**


- Field & Method Promotion :

  In Go, field and method promotion occurs when we embed an anonymous struct type( means specify only the type name without a designated variable name ) into another struct, that allowing the inner struct's fields and methods to be accessed directly from the outer struct.
  
  ```go
	package main

	import "fmt"

	type Address struct {
		City  string
		State string
	}

	func (a Address) PrintAddress() {
		fmt.Println(a.City, a.State)
	}

	type Person struct {
		Name    string
		Age     int
		Address // embedded struct (no field name)
	}

	func main() {
		p := Person{
			Name: "Sourav",
			Age:  27,
			Address: Address{
				City:  "Kolkata",
				State: "WB",
			},
		}

		fmt.Println(p.City) // works directly
		p.PrintAddress()    // works directly
		p.Address.PrintAddress()

	}

 	```
  
- Shadowing (Overriding):

  When the outer struct and an embedded struct define a field or method with the same name, the outer struct takes priorities —this is known as shadowing. By default, the compiler resolves references to the outer struct’s member. However, the embedded struct’s member can still be accessed explicitly using the embedded type’s name.

  	```go

  	package main

	import "fmt"

	// define A struct
	type A struct {
		Value int
	}

	func (a A) GetData() {
		fmt.Println("Print GetData() from A")
	}

	// define B struct
	type B struct {
		A
		Value int
	}

	func (b B) GetData() {
		fmt.Println("Print GetData() from B")
	}

	func main() {

		b := B{
			A: A{
				Value: 10,
			},
			Value: 20,
		}

	fmt.Println(b.Value)   // 20 (outer one)
	fmt.Println(b.A.Value) // 10 (inner one)

	b.GetData()   // Print GetData() from B || call outer struct (B) GetData() method
	b.A.GetData() // Print GetData() from A || call inner struct (A) GetData() method

	}

  	```
  
 </details>

 <details><summary><h3><mark> Composition | Composition over Inheritance | Composition vs Inheritance) </mark></h3></summary>
	 
 #### Composition over Inheritance ::	 
 
 In Go, the concept of inheritance does not exist as it does in traditional object-oriented languages; instead, Go strongly promotes composition over inheritance. 
	 This means that rather than creating complex class hierarchies, developers build larger, more capable types by combining smaller, reusable components using struct embedding and interfaces.
 (follow "has-a" relationships rather than "is-a" relationships)

 With composition..,

 Struct can embed another struct and automatically gain access to its fields and methods, a feature known as fields/method promotion. This approach keeps the design simple, flexible, and loosely coupled, making the code easier to maintain and test. 

 Unlike inheritance, where behavior is tightly bound in a hierarchy, composition allows developers to mix and match functionality as needed. 

Additionally.., 

 Go’s interfaces enable a form of polymorphism without requiring explicit declarations, as any type implementing the required methods satisfies the interface. Overall, Go favors composition because it avoids the complexity of deep inheritance chains while encouraging modular and reusable code design.

 #### Composition and Inheritance ::	
 Composition and inheritance are two different approaches to code reuse and design in programming. 
- **Inheritance ::**
Inheritance is based on an “is-a” relationship, where a child class derives from a parent class and inherits its properties and behavior, often leading to tightly coupled and rigid hierarchies. This can make systems harder to modify as changes in the parent can affect all derived classes. 

In contrast, 
- **Composition ::**
Composition is based on a “has-a” relationship, where a type is built by combining smaller, independent components. This approach promotes flexibility, as behaviors can be added, modified, or replaced without affecting the entire structure. Composition results in loosely coupled systems that are easier to maintain, extend, and test. Because of these advantages, languages like Go favor composition over inheritance, using struct embedding and interfaces to achieve reuse and polymorphism without relying on deep class hierarchies.

| Feature / Dimension | Composition ("Has-A") | Inheritance ("Is-A") |
| :--- | :--- | :--- |
| **Core Concept** | "A Dog **has-a** barking behavior"<br>"A Car **has-an** Engine" | "A Dog **is-an** Animal"<br>"A Car **is-a** Vehicle" |
| **Mechanism** | Struct embeds other structs / references components | Subclass extends a base class |
| **Reuse Direction** | **Horizontal:** Mix-and-match independent features | **Vertical:** Deep hierarchical inheritance tree |
| **Coupling** | **Loose:** Components are decoupled, isolated modules | **Tight:** Child class depends heavily on parent state |
| **Flexibility** | **High:** Easy to swap or modify pieces at runtime | **Rigid:** Hard-coded and fixed at compile time |
| **Encapsulation** | **Strong:** Inner details stay hidden inside components | **Weak:** Breaks parent encapsulation (via `protected`) |
| **Testing** | **Easy:** Straightforward to mock isolated dependencies | **Harder:** Tests must manage complex parent states |
 
 </details>

<br>


# Keyword
- Range
- Defer
- select
- [GO](#what-is-go---why-developers-choose-go)
