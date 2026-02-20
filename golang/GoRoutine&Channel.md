# What is Go Routine
A Goroutine is a lightweight thread managed by the Go runtime, Used to run multiple function or method Concurrently.
While a traditional OS thread might take up 1MB of memory, a Goroutine starts with just 2KB.

Concurrency is not Parallelism.
Concurrency ability to handle many tasks at once. and Parallelism doing multiple things at the exact same time.

I will give small example:

Case 1: Concurrency 

I was writing something, then I get thirsty, so I stopped writing and drank some water, then started writing again.

Case 2: Parallelism.

I'm drinking eating Coke and pizza also watching TV at the same time.

Go is designed to be concurrent, which allows it to be parallel when have a processor with multiple cores.



# What is Go Channel | Type of Channel

A channel in Go is a communication mechanism used by goroutines.
It allows safe data sharing between goroutines without explicit locks.

Channels are reference types. zero value is nil. Initialize using the make() function.

We can send and receive values on channel with the channel operator, (<-)(->).

By default, channels are bidirectional, but for better API design and type safety, we often restrict them in function signatures:

Bidirectional: chan T (can send and receive).

Send-only: chan<- T (the arrow points into the chan).

Receive-only: <-chan T (the arrow points out of the chan).

Channel has been closed using close() function. No values can be sent after closing but  Receivers can still read remaining values after close .Channel close() Used to signal completion.

## Type of Channel 
Channels can be TWO type
1. Unbuffered Channel  2. Buffered Channel

Unbuffered : Capacity of 0. The sender blocks until a receiver is ready. Used for strict synchronization.

Buffered : Has a fixed capacity. The Sender only blocks when the buffer is full. receiver blocks when it's empty. its Allows asynchronous communication.

# Concurrency in go
# Difference between concurrency and parallelism in golang
# Go Memory Model | Thread Safety | Mutexes
# Data Race and Race Condition

## Race Conditions:
A Race Condition is a logic/design errors, not syntax errors in the program  when the correctness of the program depends on the order/timing of goroutines.
A Race condition happens when multiple goroutines access and modify shared data concurrently using goroutines without proper synchronization, that causing un-predictable results.

- Go makes detection easier with -race flag during run or test Go program to check unsynchronized memory access at runtime.

### 


## Data Race :

A Data Race is a specific type of race condition that happens at the memory level when Two or more goroutines access the same memory location concurrently. There is no synchronization used to coordinate the access.It is a low-level memory safety issue.

All data races are race conditions. Not all race conditions are data races


# Deadlocks


## sync.WaitGroup:

It's a fundamental tool for concurrency management.
Think of it as a counter that tells main program and wait till all goroutine finish. 
Without it, main function might finish and exit while goroutines are still halfway through their work. and that causing to Race Conditions.
It's also Standard Way to dill To prevent Race Conditions in Go.

- The sync.WaitGroup type exposes three core methods  1. Add(n int) 2. Done() 3. Wait()

### Add(int): 
Increments the counter by the number of goroutines you are starting.

### Done(): 
Decrements the counter by 1. Usually called via defer inside the goroutine.

### Wait(): 

Blocks the execution of the program (usually in main) until the counter reaches zero.
