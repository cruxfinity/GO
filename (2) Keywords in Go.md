Keywords or Reserved words are the words in a language that are used for some internal process or represent some predefined actions.

There are **_total 25 keywords present_** in the Go language as follows:

|  break   |   default   |  func  | interface | select |
| :------: | :---------: | :----: | :-------: | ------ |
|   case   |    defer    |   go   |    map    | struct |
|   chan   |    else     |  goto  |  package  | switch |
|  const   | fallthrough |   if   |   range   | type   |
| continue |     for     | import |  return   | var    |
Examples of some of the above keywords :-

#break
```
package main
import (
    "fmt"
)

func main() {
    for i := 0; i < 10; i++ {
        if i == 5 {
            break // Exit the loop when i is 5
        }
        fmt.Println(i)
    }
    fmt.Println("Loop exited")
}
```

#defer
```
package main

import (
    "fmt"
)

func main() {
    fmt.Println("Start")
    
    // The deferred function call 
    defer fmt.Println("Deferred")
    
    fmt.Println("End")
}
```
The `defer` keyword in Go is used to ensure that a function call is performed later in a program's execution, usually for purposes of cleanup.

#func
```
package main

import (
    "fmt"
)

// Function declaration
func greet(name string) string {
    return "Hello, " + name + "!"
}

func main() {
    // Function call
    message := greet("Alice")
    fmt.Println(message)
}
```
- The `func` keyword declares a function named `greet`.
    
- The function takes a single parameter of type `string` named `name`.
    
- The function returns a `string`, which is the concatenated greeting message.
    
- In the `main` function, the `greet` function is called with the argument `"Alice"`, and the returned message is printed.

#struct
```
package main

import (
    "fmt"
)

// Define a struct type named Person
type Person struct {
    Name string
    Age  int
}

func main() {
    // Create an instance of the Person struct
    p := Person{Name: "Alice", Age: 30}
    
    // Access and modify struct fields
    fmt.Println(p.Name) // Output: Alice
    fmt.Println(p.Age)  // Output: 30

    p.Age = 31
    fmt.Println(p.Age)  // Output: 31
}
```
- The `Person` struct is defined with two fields: `Name` (a string) and `Age` (an int).
    
- An instance of `Person` is created and initialized.
    
- The fields of the struct are accessed and modified using dot notation (`p.Name` and `p.Age`).
-In Go, the `struct` keyword is used to define a structure, which is a composite data type that groups together variables under a single name. Each variable within a struct is called a field.

#range
```
package main

import (
    "fmt"
)

func main() {
    numbers := []int{1, 2, 3, 4, 5}

    for index, value := range numbers {
        fmt.Printf("Index: %d, Value: %d\n", index, value)
    }
}
```
In this example, `range` returns both the index and value for each element in the `numbers` slice.

#chan
```
package main

import (
    "fmt"
)

func main() {
    // Declare a channel of type int
    ch := make(chan int)

    // Start a goroutine to send a value into the channel
    go func() {
        ch <- 42
    }()

    // Receive the value from the channel
    value := <-ch
    fmt.Println(value) // Output: 42
}
```
- The `ch` channel is created using `make(chan int)`.
    
- A goroutine is started to send the value `42` into the channel `ch` using the send operator (`<-`).
    
- The main function receives the value from the channel using the receive operator (`<-ch`).
	https://www.scaler.com/topics/golang/channels-in-golang/

***NOTE***: All keywords will be explained later in the topic as i progress
yet feel free to check other resources :
https://go.dev/tour/welcome/1
https://www.geeksforgeeks.org/go-keywords/?ref=lbp

NEXT -> [[(3) Data Types in Go]]
