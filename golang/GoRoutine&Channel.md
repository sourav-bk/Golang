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
# Data Race | Race Condition
# Deadlocks
