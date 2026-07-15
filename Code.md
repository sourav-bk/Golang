<details><summary><mark> </mark></summary>
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
  <summary><mark> </mark></summary>

</details>
