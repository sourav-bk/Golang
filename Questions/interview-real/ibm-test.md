# Go HackerRank Questions

## Question 1

**Which of the following are true for arrays and slices in Go?**\
*(Choose multiple options, as applicable.)*

1.  Arrays have fixed length and slices have dynamic length.
2.  When assigned to other variables, arrays and slices are both copied
    by value.
3.  When assigned to other variables, copy of array is made while
    reference to slice is passed.
4.  Arrays have length while slices have length and capacity.

------------------------------------------------------------------------

## Question 2

**In Go, which of the following are valid ways to define a function that
takes two integer arguments and returns their sum?**\
*(Choose multiple options, as applicable.)*

1.  `add(x, y int) int { return x + y }`
2.  `func add(x, y int) int { return x + y }`
3.  `func add(x, y int) { return x + y }`
4.  `func add(x, y int) { return x + y }`

------------------------------------------------------------------------

## Question 3

**What will be output of below code?**

``` go
package main

import (
    "fmt"
    "strings"
)

func main() {
    text := "This is a sample string with multiple words"
    words := strings.Fields(text)
    fmt.Println(len(words))
}
```

### Options

1.  The code counts the number of letters in the text. The output will
    be the letter count.
2.  The code splits the text into individual words and counts the number
    of words. The output will be the word count.
3.  The code counts the number of spaces in the text. The output will be
    the space count.
4.  The code extracts the first word from the text. The output will be
    the first word.

------------------------------------------------------------------------

## Question 4

**In Go, what is the primary use case for the `context.Context` API,
particularly in the context of concurrent programming?**

### Options

1.  To define global configuration settings for a Go program.
2.  To create a new goroutine for executing background tasks.
3.  To carry request-scoped deadlines, cancellations, and other values
    across API boundaries and between goroutines.
4.  To encapsulate and serialize data structures for safe communication
    between goroutines.

------------------------------------------------------------------------

## Question 5

**In the Go strings package, which function is used to find the index of
the first occurrence of a substring within a given string?**

### Options

1.  `IndexOf`
2.  `FindIndex`
3.  `FindString`
4.  `Index`

------------------------------------------------------------------------

## Question 6

**What will be output of below code?**

``` go
package main

import (
    "encoding/json"
    "fmt"
)

func main() {
    data := `{"name":"Alice","age":30,"email":null}`

    var person map[string]interface{}

    err := json.Unmarshal([]byte(data), &person)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }

    fmt.Println("Name:", person["name"])
    fmt.Println("Age:", person["age"])
    fmt.Println("Email:", person["email"])
}
```

### Options

1.  Compilation Error
2.  

``` text
Name: Alice
Age: 30
Email: <nil>
```

3.  

``` text
Name: Alice
Age: 30
Email: null
```

4.  

``` text
Name: Alice
Age: 30
```

------------------------------------------------------------------------

## Question 7

**What will be output of below code?**

``` go
package main

import (
    "fmt"
    "io"
    "strings"
)

func main() {
    data := "Hello, world"
    reader := strings.NewReader(data)

    buffer := make([]byte, 5)
    _, err := reader.Read(buffer)

    if err != nil && err != io.EOF {
        fmt.Println("Error:", err)
        return
    }

    fmt.Println("Data Read:", string(buffer))
}
```

### Options

1.  Compilation Error
2.  `Data Read: Hello`
3.  `Data Read: Hello, world`
4.  `Data Read:`

------------------------------------------------------------------------

## Question 8

**In Go, what is the purpose of a `sync.WaitGroup`?**

### Options

1.  To create concurrent functions.
2.  To wait for goroutines to finish.
3.  To synchronize the execution of channels.
4.  To define custom concurrency primitives.

------------------------------------------------------------------------

## Question 9

**What will be output of below code?**

``` go
package main

import (
    "fmt"
    "time"
)

func main() {
    ch1 := make(chan int)
    ch2 := make(chan int)

    go func() {
        time.Sleep(1 * time.Second)
        ch1 <- 1
    }()

    go func() {
        time.Sleep(1 * time.Second)
        ch2 <- 2
    }()

    select {
    case val := <-ch1:
        fmt.Printf("Received from ch1: %d\n", val)
    case val := <-ch2:
        fmt.Printf("Received from ch2: %d\n", val)
    }

    fmt.Println("Done.")
}
```

### Options

1.  The `select` statement waits for data from both `ch1` and `ch2`. The
    output will be `Received from ch1: 1`.
2.  The `select` statement waits for data from either `ch1` or `ch2`,
    whichever sends data first. The output can be either
    `Received from ch1: 1` or `Received from ch2: 2`.
3.  The `select` statement synchronizes the two goroutines. The output
    will be `Received from ch2: 2`.
4.  The program will not compile due to a syntax error.




---

## Question 10
**What is the standard naming convention for test functions in Go?**

### Options
- **A.** `TestFunctionName`
- **B.** `FunctionName_Test`
- **C.** `Test_FunctionName`
- **D.** `testName`

---

## Question 11
**What is the purpose of table-driven tests in Go?**

### Options
- **A.** To test tables and databases used in the application.
- **B.** To verify that the testing framework is functioning correctly.
- **C.** To create a test suite with multiple test cases for a function by using a data-driven approach.
- **D.** To benchmark the performance of a function.

---

## Question 12
**In Go, what is the primary purpose of the `errors.Is` function?**

### Options
- **A.** To create custom error types.
- **B.** To check if two error values are equal.
- **C.** To check if an error is of a specific type.
- **D.** To format error messages for display.

---

## Question 13
**Which Go function is used to start an HTTP server for incoming requests on a specified network address?**

### Options
- **A.** `http.ListenAndServe`
- **B.** `http.Handle`
- **C.** `http.Serve`
- **D.** `http.NewServer`

---

## Question 14
**What is connection pooling in the context of Go's HTTP client, and why is it important when making multiple HTTP requests to the same server?**

### Options
- **A.** Connection pooling is a technique for limiting the maximum number of concurrent HTTP requests to a server. It is important for preventing overloading the server.
- **B.** Connection pooling is a mechanism for sharing HTTP connections among different clients. It is important to save memory and reduce resource consumption.
- **C.** Connection pooling is the process of reusing and maintaining open HTTP connections to a server. It is important for reducing connection overhead and improving efficiency when making multiple requests to the same server.
- **D.** Connection pooling is a security feature that prevents unauthorized clients from making HTTP requests to a server. It is important for protecting the server.

---

## Question 15
**What command is used to initialize a Go module in a project?**

### Options
- **A.** `go build`
- **B.** `go get`
- **C.** `go mod init`
- **D.** `go mod start`




---

<img width="627" height="721" alt="image" src="https://github.com/user-attachments/assets/3143ecce-12e4-4021-9e09-3d8043979f43" />



