<details><summary><h2><mark>Go Routine and Channel? Type of Channel? </mark></h3></summary>
 
## ***Go Routine*** :
A Goroutine is a lightweight thread managed by the Go runtime, Used to run multiple function or method Concurrently.
While a traditional OS thread might take up 1MB of memory, a Goroutine starts with just 2KB.

***Concurrency***

Go follow Concurrency. Concurrency is the ability to run multiple things at once.
When we normally write code, that code runs sequentially, meaning that each job is run back to back. 
In concurrent code, those jobs are run simultaneously.

- #### Concurrency vs. Parallelism
Concurrency is not Parallelism.

Concurrency is ability to handle many tasks at once. and Parallelism doing multiple things at the exact same time.

I will give small example:

- Case 1: ***Concurrency*** - I was writing something, then I get thirsty, so I stopped writing and drank some water, then started writing again.

- Case 2: ***Parallelism*** - I'm drinking eating Coke and pizza also watching TV at the same time. 

Go is designed to be concurrent, which allows it to be parallel when have a processor with multiple cores.

A Go program can be concurrent even on a single core machine, but it achieves true parallelism when running on a multi-core system, as the Go runtime efficiently distributes goroutines across available cores.


## ***Channel*** :

A channel in Go is a communication mechanism used by goroutines. It allows safe data sharing between goroutines without explicit locks.

Go channels use the FIFO (First-In, First-Out) method and Values sent to a channel are received in the same order they were sent. 

If multiple goroutines are sending/receiving, the order of operations is preserved as they are processed through the channel's internal buffer.

Channels are reference types. zero value is nil. Initialize using the make() function.

We can send and receive values on channel with the channel operator, (<-)(->).

By default, channels are bidirectional, but for better API design and type safety, we often restrict them in function signatures:

- ***Bidirectional:*** chan T (can send and receive).

- ***Send-only:*** chan<- T (the arrow points into the chan).

- ***Receive-only:*** <-chan T (the arrow points out of the chan).

Channel has been closed using close() function. No values can be sent after closing  but  Receivers can still read remaining values after close. Channel close() Used to signal completion.

- ### Type of Channel 

Channels can be TWO type -- 1. Unbuffered Channel   2. Buffered Channel

- ***Unbuffered*** : Capacity of 0. The sender blocks until a receiver is ready. Used for strict synchronization. Since they have no capacity, they act as direct synchronization points.

- ***Buffered*** : Has a fixed capacity. The Sender only blocks when the buffer is full. receiver blocks when it's empty. its Allows asynchronous communication. Act as FIFO queues. The first value added to the buffer is the first one removed.

 
</details>

<details><summary><h2><mark>Concurrency in go</mark></h3></summary>
</details>

<details><summary><h2><mark>Data Race and Race Condition</mark></h3></summary>

## ***Race Conditions***:
A Race Condition is a logic/design errors, not syntax errors in the program when the correctness of the program depends on the order/timing of goroutines. A Race condition happens when multiple goroutines access and modify shared data concurrently using goroutines without proper synchronization, that causing un-predictable results.

Go makes detection easier with -race flag during run or test Go program to check unsynchronized memory access at runtime.
## ***Data Race*** :
A Data Race is a specific type of race condition that happens at the memory level when Two or more goroutines access the same memory location concurrently. There is no synchronization used to coordinate the access. It is a low-level memory safety issue.

All data races are race conditions. Not all race conditions are data races.
 
</details>


<details><summary><h2><mark>Deadlocks</mark></h3></summary>
 
A deadlock occurs when two or more goroutines are permanently blocked. Its waiting for each other to release resources or send/receive data — so no progress is possible.

In simple Deadlock is a state where goroutines wait indefinitely for resources or communication, causing the program to stop executing.

In Go, deadlocks usually happen due to incorrect use of channels, mutexes, or wait groups.

- ***Channels*** :: Common Deadlock Scenarios in Go. Unbuffered Channel Blocking


- ***Circular Wait (Mutexes)*** :: This occurs when Goroutine A holds Lock 1 and waits for Lock 2, while Goroutine B holds Lock 2 and waits for Lock 1.

- ***Resource Leak / WaitGroup Misuse*** :: If  increment a sync.WaitGroup but a goroutine crashes or returns before calling .Done(), the wg.Wait() call will block forever.


## sync.WaitGroup:

It's a fundamental tool for concurrency management.
Think of it as a counter that tells main program and wait till all goroutine finish. 
Without it, main function might finish and exit while goroutines are still halfway through their work. and that causing to Race Conditions.
It's also Standard Way to dill To prevent Race Conditions in Go.

sync.WaitGroup operates on  internal counter using three main methods:

- ***Add(int)***: Increments the counter by the number of goroutines you are starting.

- ***Done()***: Decrements the counter by 1. Usually called via defer inside the goroutine.

- ***Wait()***: Blocks the execution of the program (usually in main) until the counter reaches zero.


## sync.Mutex && Mutexes ::

In Go, when multiple goroutines try to access the same piece of data at the same time, its end up with a Date race. To prevent Date race , we use "Mutual Exclusion" locks, or Mutexes.

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
