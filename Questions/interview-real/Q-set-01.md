# Go — Debugging and Design Questions

## Question 1

**What is the best practice for storing secrets in a Go application?**

### Options

- [ ] Database table
- [ ] Config file in repo
- [x] Environment variables or secrets manager
- [ ] Hardcode in source code

**Answer:** Environment variables or secrets manager

---

## Question 2

**Which HTTP status code should your Go API return for a bad request body?**

### Options

- [x] 400 Bad Request
- [ ] 500
- [ ] 200
- [ ] 404

**Answer:** 400 Bad Request

---

## Question 3

**How do you handle errors idiomatically in Go?**

### Options

- [ ] throw/catch blocks
- [ ] Log and ignore
- [x] Return error as last return value and check it
- [ ] Use panic always

**Answer:** Return error as last return value and check it

---

## Question 4

**Your Go HTTP server returns 500 intermittently. What is the first thing to check?**

### Options

- [ ] Memory usage
- [ ] Database connections
- [x] Application logs
- [ ] Network latency

**Answer:** Application logs

---

## Question 5

**Given the root of a BST and an integer `k`, the task is to find the kth smallest element in the BST. If there is no kth smallest element present, then return `-1`.**

### Function

```go
func kthSmallest(root Node, k int) int {
    // code here
}

```

---

## Question 6

**Given the root of a BST and an integer `k`, the task is to find the kth smallest element in the BST. If there is no kth smallest element present, then return `-1`.**

### Function

```go
func kthSmallest(root Node, k int) int {
    // code here
}

```
