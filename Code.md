<details>
	<summary><mark> two numbers concurrently </mark></summary>
	
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
