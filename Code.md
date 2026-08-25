<details>
	<summary><mark> Example </mark></summary>
	
```go
  package main

  import "fmt"

  func add(resultChan chan int, nums ...int) {
	  total := 0
	  // nums is treated as a slice ([]int)
	  for _, num := range nums {
		  total += num
	  }
    resultChan <- total
  }

  func main() {
	  resultChan := make(chan int)
	  // 1. Pass multiple individual arguments
	  go add(resultChan, 10, 20, 30)
	  fmt.Println("Result 1:", <-resultChan) // Output: 60
	  // 2. Pass a different number of arguments
	  go add(resultChan, 5, 5)
	  fmt.Println("Result 2:", <-resultChan) // Output: 10
  }
```
</details>

<details>
	<summary><mark> Add Two numbers concurrently </mark></summary>
	
```go
  package main

  import "fmt"

  func add(resultChan chan int, nums ...int) {
	  total := 0
	  // nums is treated as a slice ([]int)
	  for _, num := range nums {
		  total += num
	  }
    resultChan <- total
  }

  func main() {
	  resultChan := make(chan int)
	  // 1. Pass multiple individual arguments
	  go add(resultChan, 10, 20, 30)
	  fmt.Println("Result 1:", <-resultChan) // Output: 60
	  // 2. Pass a different number of arguments
	  go add(resultChan, 5, 5)
	  fmt.Println("Result 2:", <-resultChan) // Output: 10
  }
```
</details>

<details>
  <summary><mark> Check Palindrome String | Number  </mark></summary>
	
```go

package main

import "fmt"

func isPalindromeStr(s string) bool {

	left, right := 0, len(s)-1

	for left < right {
		if s[left] != s[right] {
			return false
		}
		left++
		right--
	}

	return true
}

func isPalindromeNum(n int) bool {

	// Negative numbers are not palindromes
	if n < 0 {
		return false
	}

	original := n
	reversed := 0

	for n > 0 {
		digit := n % 10
		reversed = reversed*10 + digit
		n /= 10
	}

	return original == reversed
}

func main() {

	// check Palindrome String
	str := "madam"
	if isPalindromeStr(str) {
		fmt.Printf("%q is a palindrome\n", str)
	} else {
		fmt.Printf("%q is not a palindrome\n", str)
	}

	// check Palindrome number

	num := 1212
	if isPalindromeNum(num) {
		fmt.Printf("%d is a palindrome\n", num)
	} else {
		fmt.Printf("%d is not a palindrome\n", num)
	}
}

```
</details>

<details>
  <summary><mark> Using routines and channels print even and odd numbers up to X.  </mark></summary>
	
```go

package main

import (
	"fmt"
	"sync"
)

func main() {
	X := 10 // Set your upper limit here

	// Create unbuffered channels for signaling turns
	oddChan := make(chan bool)
	evenChan := make(chan bool)

	var wg sync.WaitGroup
	wg.Add(2)

	// Goroutine for Odd numbers
	go func() {
		defer wg.Done()
		for i := 1; i <= X; i += 2 {
			<-oddChan // Wait for turn
			fmt.Printf("Odd: %d\n", i)
			evenChan <- true // Signal even goroutine
		}
	}()

	// Goroutine for Even numbers
	go func() {
		defer wg.Done()
		for i := 2; i <= X; i += 2 {
			<-evenChan // Wait for turn
			fmt.Printf("Even: %d\n", i)
			if i < X {
				oddChan <- true // Signal odd goroutine
			}
		}
	}()

	// Kickstart the sequence by signaling the odd goroutine
	oddChan <- true

	// Wait for both goroutines to finish
	wg.Wait()
}


/*

   Check if the remainder is 0 when divided by 2
    if number%2 == 0 {
        fmt.Printf("%d is an even number.\n", number)
    } else {
        fmt.Printf("%d is an odd number.\n", number)
    }

*/



```
</details>


<details>
  <summary><mark> Print numbers from 1 to x using Go routines and channels.</mark></summary>
	
```go

package main

import (
	"fmt"
)

func generateNumbers(x int, ch chan<- int) {
	// Loop from 1 to x and send each number to the channel
	for i := 1; i <= x; i++ {
		ch <- i
	}
	// Always close the channel to notify the receiver that data is finished
	close(ch) 
}

func main() {
	x := 10 // Change this to your desired value
	ch := make(chan int)

	// Start the producer goroutine
	go generateNumbers(x, ch)

	// Consumer: Read and print values from the channel sequentially
	for num := range ch {
		fmt.Println(num)
	}
}


```
</details>





<details>
	<summary><mark> Generate the Fibonacci series using Go routines. </mark></summary>
	
```go

package main

import (
	"fmt"
)

func main() {
	// Define how many numbers you want in the series
	const terms = 3

	// Create an unbuffered channel to communicate between goroutines
	ch := make(chan int)

	// Launch the fibonacci generator as a background Go routine
	go fibonacci(terms, ch)

	fmt.Printf("First %d terms of Fibonacci series:\n", terms)

	// The main goroutine blocks and reads numbers as they are sent.
	// The loop terminates automatically when the channel is closed.
	for num := range ch {
		fmt.Printf("%d ", num)
	}
	fmt.Println()
}

// fibonacci is a producer function that calculates numbers
// and sends them through a write-only channel.
func fibonacci(n int, ch chan<- int) {
	x, y := 0, 1
	for i := 0; i < n; i++ {
		ch <- x
		x, y = y, x+y
	}
	// Crucial: Close the channel so the receiver knows when to stop reading
	close(ch)
}

```
</details>


<details>
	<summary><mark> Key-value store concurrency </mark></summary>
	
```go

package main
import "fmt"
import "sync"
 
type kvStore struct {
    data sync.Map
}

func NewKVStore() *kvStore {
	return &kvStore{}
}
 
func (k *kvStore) Set(key string, value any) {
    k.data.Store(key, value)
}
 
func (k *kvStore) Get(key string) (any, bool) {
    return k.data.Load(key)
}
 
func (k *kvStore) Delete(key string) {
    k.data.Delete(key)
}
 
func (k *kvStore) GetOrCreate(key string, value any) (any, bool) {
    return k.data.LoadOrStore(key, value)
}
 
 
func main() {
    fmt.Println("::__KVStore__::");
	
    store := NewKVStore()            //store := &KVStore{}
    store.Set("name", "Sourav")
    store.Set("key-01", "value-01")

    value, ok := store.GetOrCreate("key-01","value-update")
    if ok {
        fmt.Println(value)
    }

}

```
</details>
