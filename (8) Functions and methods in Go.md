In Go, functions are blocks of code that perform specific tasks, which can be reused throughout the program to save memory, improve readability, and save time. Functions may or may not return a value to the caller.

```
package main
import "fmt"

// multiply() multiplies two integers and returns the result
func multiply(a, b int) int {
    return a * b
}

func main() {
    result := multiply(5, 10)
    fmt.Printf("multiplication: %d", result)
}
```

### Call by Value
In call by value, values of the arguments are copied to the function parameters
```
package main
import "fmt"

func multiply(a, b int) int {
    a = a * 2 // modifying a inside the function
    return a * b
}

func main() {
    x := 5
    y := 10
    fmt.Printf("Before: x = %d, y = %d\n", x, y)
    result := multiply(x, y)
    fmt.Printf("multiplication: %d\n", result)
    fmt.Printf("After: x = %d, y = %d\n", x, y)
}
___________________________________________________________
Output
Before: x = 5, y = 10
multiplication: 100
After: x = 5, y = 10
```

### Call by Reference
In call by reference, pointers are used so that changes inside the function reflect in the caller’s variables.
```
package main
import "fmt"

func multiply(a, b *int) int {
    *a = *a * 2 // modifying a's value at its memory address
    return *a * *b
}

func main() {
    x := 5
    y := 10
    fmt.Printf("Before: x = %d, y = %d\n", x, y)
    result := multiply(&x, &y)
    fmt.Printf("multiplication: %d\n", result)
    fmt.Printf("After: x = %d, y = %d\n", x, y)
}
___________________________________________________________
Output
Before: x = 5, y = 10
multiplication: 100
After: x = 10, y = 10
```

___
# Variadic Functions in Go
Variadic functions in Go allow you to pass a variable number of arguments to a function.

```
package main
import "fmt"

// Variadic function to calculate sum
func sum(nums ...int) int {
    total := 0
    for _, n := range nums {
        total += n
    }
    return total
}

func main() {
    fmt.Println("Sum of 1, 2, 3:", sum(1, 2, 3))
    fmt.Println("Sum of 4, 5:", sum(4, 5))
    fmt.Println("Sum of no numbers:", sum())
}
___________________________________________________________
Output
Sum of 1, 2, 3: 6
Sum of 4, 5: 9
Sum of no numbers: 0
```
## Syntax
```
func functionName(parameters ...Type) ReturnType {  
    // Code  
}
```

## Variadic Functions with Other Parameters

You can also mix variadic parameters with regular parameters in a function. The variadic parameter must always be the last parameter.

```
package main
import "fmt"

// Variadic function to calculate sum
func sum(nums ...int) int {
    total := 0
    for _, n := range nums {
        total += n
    }
    return total
}

// Function with a regular parameter and a variadic parameter
func greet(prefix string, nums ...int) {
    fmt.Println(prefix)
    for _, n := range nums {
        fmt.Println("Number:", n)
    }
}
func main() {
    greet("Sum of numbers:", 1, 2, 3)
    greet("Another sum:", 4, 5)
    greet("No numbers sum:")
}
___________________________________________________________
Output
Sum of numbers:
Number: 1
Number: 2
Number: 3
Another sum:
Number: 4
Number: 5
No numbers sum:
```


# Anonymous function in Go Language
An anonymous function is a function that doesn’t have a name. It is useful when you want to create an inline function. In Go, an anonymous function can also form a closure.
```
package main
import "fmt"

func main() {
    // Anonymous function
    func() {
        fmt.Println("Hello, world!")
    }()
}
```

### Assigning to a Variable
You can assign an anonymous function to a variable. This variable can then be called like a regular function.
```
package main
import "fmt"

func main() {
    // Assigning an anonymous function to a variable
    value := func() {
        fmt.Println("Hello, world!")
    }
    value()
}
___________________________________________________________
Output
Hello, world!
```

### Passing Arguments
```
package main
import "fmt"

func main() {
    // Passing arguments in anonymous function
    func(ele string) {
        fmt.Println(ele)
    }("Hello, world!")
}
__________________________________________________________
Output
Hello, world!
```

### Passing as Arguments
```
package main
import "fmt"

// Passing anonymous function as an argument
func GFG(i func(p, q string) string) {
    fmt.Println(i("Geeks", "for"))
}
func main() {
    value := func(p, q string) string {
        return p + q + "Geeks"
    }
    GFG(value)
}
```

### Returning Anonymous Functions
```
package main

import "fmt"

// Function that returns an anonymous function
func getMultiplier(factor int) func(int) int {
    return func(val int) int {
        return val * factor
    }
}

func main() {
    // Get a function that multiplies by 2
    multiplyBy2 := getMultiplier(2)

    // Use the returned anonymous function
    fmt.Println(multiplyBy2(5)) // Output: 10
    fmt.Println(multiplyBy2(10)) // Output: 20
}

```

___
# main and init function in Golang
In Go, the `main` function is the entry point for any Go application, and the `init` function is a special function that can be used for setup tasks that need to happen before the `main` function runs. Here's a simple example to illustrate both:
```
package main

import (
    "fmt"
)

// init function
func init() {
    fmt.Println("Init function executed.")
}

// main function
func main() {
    fmt.Println("Main function executed.")
}

```
In this example:

- The `init` function gets executed first. It's called automatically when the program starts, before any other code in the package.
    
- The `main` function is the entry point for the application. After all the `init` functions have executed (if any), the `main` function runs.
    

You can have multiple `init` functions in different files within the same package, and they will be executed in the order they are compiled. The `init` function is typically used for tasks like initializing package-level variables or performing setup tasks that need to be done before the application starts running.

___
# Methods in Golang
In Go, methods are functions with a special receiver argument. They allow you to define functions that work with specific types. Here's an example to help you understand how methods work in Go:
```
package main

import (
    "fmt"
)

// Define a struct called Rectangle
type Rectangle struct {
    Width, Height float64
}

// Define a method with a receiver of type Rectangle
func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func main() {
    // Create an instance of Rectangle
    rect := Rectangle{Width: 10, Height: 5}

    // Call the Area method on the rect instance
    fmt.Println("Area of Rectangle:", rect.Area())
}

```
In this example:

- We define a struct called `Rectangle` with two fields: `Width` and `Height`.
    
- We define a method `Area` with a receiver of type `Rectangle`. The method calculates and returns the area of the rectangle.
    
- In the `main` function, we create an instance of `Rectangle` and call the `Area` method on it.
    

This is just a basic example. Methods can be more complex and can have pointer receivers for modifying the value of the receiver.

NEXT-> [[(9) Arrays and Slices in Go]]