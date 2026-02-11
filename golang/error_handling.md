# How to error  in go?

In Golang, Error isn't an exception that crashes program — it’s just a value. Go treats errors as "first-class citizens," meaning we handle like, as any other variable.


The most common way to handle errors is to check if the returned error value is nil (meaning success) or not nil (meaning failure), and then deal with the failure.


One of the most important concepts in Go is knowing when to return an error and when to panic. They may look similar at first, but they exist for completely different reasons by design.

### Errors: Expected Failures
Errors represent issues that can happen during normal program execution. They’re part of the flow, and program should be prepared for them. Errors should be handled gracefully. They should not crash your program.

### Panics: Unexpected Failures
A panic indicates something went terribly wrong, usually a programmer mistake or a critical, unrecoverable state.
Stop normal execution Crash the program

### recover:
Inside the deferred function, recover() is called. If a panic is active, it captures the panic value and stops the unwinding of the stack, allowing the program to continue running.







# Panic and Recover
# defer statement
# how create Custom Error type in go
