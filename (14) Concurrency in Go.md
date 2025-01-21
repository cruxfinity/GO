Concurrency is a fundamental part of Go's design, enabling programs to perform multiple tasks simultaneously. Go's concurrency model is built around goroutines and channels, making it easier to write concurrent programs. Let's dive into the details:

### Goroutines

Goroutines are lightweight threads managed by the Go runtime. They are much cheaper than traditional threads in terms of memory and scheduling overhead.

**Creating a Goroutine:** You can start a new goroutine using the `go` keyword followed by a function call.

go

```
package main

import (
    "fmt"
    "time"
)

func say(s string) {
    for i := 0; i < 5; i++ {
        time.Sleep(100 * time.Millisecond)
        fmt.Println(s)
    }
}

func main() {
    go say("world") // Starts a new goroutine
    say("hello")    // This runs in the main goroutine
}
```

In this example:

- The `say` function is run concurrently in a new goroutine, while the `main` function continues executing.
    

### Channels

Channels provide a way for goroutines to communicate and synchronize by sending and receiving values. They can be thought of as typed conduits through which you can send and receive values.

**Creating a Channel:** You can create a channel using the `make` function.

go

```
ch := make(chan int)
```

**Sending and Receiving:** You use the `<-` operator to send and receive values from a channel.

go

```
ch <- 42   // Send value 42 to channel ch
x := <-ch  // Receive a value from channel ch and assign it to x
```

### Example: Goroutines and Channels

Here’s an example that demonstrates how to use goroutines and channels together:

go

```
package main

import (
    "fmt"
    "time"
)

// Function that sends numbers to a channel
func generateNumbers(ch chan int) {
    for i := 0; i < 5; i++ {
        time.Sleep(100 * time.Millisecond)
        ch <- i // Send number to channel
    }
    close(ch) // Close the channel when done
}

func main() {
    ch := make(chan int) // Create a channel

    go generateNumbers(ch) // Start a goroutine

    // Receive and print values from the channel
    for num := range ch {
        fmt.Println(num)
    }
}
```

In this example:

- The `generateNumbers` function sends numbers to the channel `ch`.
    
- The `main` function receives and prints values from the channel.
    

### Buffered Channels

Buffered channels allow you to specify the capacity of the channel buffer. Sending to a buffered channel only blocks when the buffer is full, and receiving blocks only when the buffer is empty.

**Creating a Buffered Channel:**

go

```
ch := make(chan int, 2) // Create a buffered channel with a capacity of 2
```

### Select Statement

The `select` statement allows a goroutine to wait on multiple communication operations. It blocks until one of its cases can proceed, then it executes that case.

**Using** `select`**:**

go

```
package main

import (
    "fmt"
    "time"
)

func main() {
    ch1 := make(chan string)
    ch2 := make(chan string)

    go func() {
        time.Sleep(1 * time.Second)
        ch1 <- "one"
    }()
    go func() {
        time.Sleep(2 * time.Second)
        ch2 <- "two"
    }()

    for i := 0; i < 2; i++ {
        select {
        case msg1 := <-ch1:
            fmt.Println("Received", msg1)
        case msg2 := <-ch2:
            fmt.Println("Received", msg2)
        }
    }
}
```

In this example:

- The `select` statement waits for messages from `ch1` or `ch2` and prints the received message.
    

### Synchronization

Go provides synchronization primitives like `sync.Mutex` and `sync.WaitGroup` for more complex synchronization needs.

**Using** `sync.Mutex`**:**

go

```
package main

import (
    "fmt"
    "sync"
)

type SafeCounter struct {
    v   map[string]int
    mux sync.Mutex
}

func (c *SafeCounter) Inc(key string) {
    c.mux.Lock()
    c.v[key]++
    c.mux.Unlock()
}

func (c *SafeCounter) Value(key string) int {
    c.mux.Lock()
    defer c.mux.Unlock()
    return c.v[key]
}

func main() {
    c := SafeCounter{v: make(map[string]int)}
    for i := 0; i < 1000; i++ {
        go c.Inc("somekey")
    }

    // Allow goroutines to finish
    fmt.Println(c.Value("somekey"))
}
```

In this example:

- `sync.Mutex` is used to ensure that only one goroutine at a time can access the map `v`.
    

**Using** `sync.WaitGroup`**:**

go

```
package main

import (
    "fmt"
    "sync"
)

func worker(id int, wg *sync.WaitGroup) {
    fmt.Printf("Worker %d starting\n", id)
    wg.Done()
}

func main() {
    var wg sync.WaitGroup

    for i := 1; i <= 5; i++ {
        wg.Add(1)
        go worker(i, &wg)
    }

    wg.Wait() // Wait for all goroutines to finish
}
```

In this example:

- `sync.WaitGroup` is used to wait for multiple goroutines to finish.
    

### Conclusion

Go's concurrency model is powerful yet simple to use. Goroutines and channels provide a clear and efficient way to write concurrent programs. With synchronization primitives like `sync.Mutex` and `sync.WaitGroup`, you can handle more complex concurrency patterns.

NEXT-> [[(15) REVISION]]