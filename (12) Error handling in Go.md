### Basics of Error Handling

Go's approach to error handling is different from many other programming languages. Instead of using exceptions, Go uses explicit error returns. This means that functions return errors as part of their result, and it's the caller's responsibility to handle them. This approach leads to clear, maintainable, and predictable code.

### The `error` Type

In Go, the `error` type is a built-in interface. An error is anything that implements this interface:



```
type error interface {
    Error() string
}
```

This means any type that has an `Error()` method with the appropriate signature satisfies the `error` interface.

### Creating and Returning Errors

You can create errors using the `errors` package. Here’s a simple way to create an error:



```
import "errors"

var err = errors.New("this is an error")
```

In functions, you often return an error as the second return value:



```
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

In the `divide` function, if `b` is zero, it returns an error indicating "division by zero". Otherwise, it returns the result of the division and `nil` for no error.

### Handling Errors

To handle an error, you check if the returned error is not `nil`:



```
result, err := divide(4, 0)
if err != nil {
    fmt.Println("Error:", err)
} else {
    fmt.Println("Result:", result)
}
```

This pattern is common in Go code. You frequently see functions returning a value and an error, and the caller immediately checks if the error is `nil`.

### Custom Error Types

Sometimes, you might want to provide more context with your errors. You can do this by defining a custom error type:



```
type DivideError struct {
    A, B float64
    Msg  string
}

func (e *DivideError) Error() string {
    return fmt.Sprintf("cannot divide %f by %f: %s", e.A, e.B, e.Msg)
}

func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, &DivideError{A: a, B: b, Msg: "division by zero"}
    }
    return a / b, nil
}

func main() {
    result, err := divide(4, 0)
    if err != nil {
        fmt.Println("Error:", err)
        if divErr, ok = err.(*DivideError); ok {
            fmt.Printf("Details: A=%f, B=%f\n", divErr.A, divErr.B)
        }
    } else {
        fmt.Println("Result:", result)
    }
}
```

In this example:

- We define a custom error type `DivideError` with fields for the operands and a message.
    
- The `Error` method formats a descriptive error message.
    
- The `divide` function returns a `DivideError` if there's an attempt to divide by zero.
    
- In `main`, we check the error and type-assert it to get more details.
    

### Wrapping Errors

The `fmt.Errorf` function can be used to wrap errors with additional context:



```
err := fmt.Errorf("failed to open file: %w", originalErr)
```

The `%w` verb is used to wrap the original error with the new message.

### Example Putting It All Together

Here’s a more comprehensive example incorporating everything we've discussed:



```
package main

import (
    "errors"
    "fmt"
)

// Custom error type
type DivideError struct {
    A, B float64
    Msg  string
}

func (e *DivideError) Error() string {
    return fmt.Sprintf("cannot divide %f by %f: %s", e.A, e.B, e.Msg)
}

// Function to divide two numbers
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, &DivideError{A: a, B: b, Msg: "division by zero"}
    }
    return a / b, nil
}

func main() {
    // Attempt to divide two numbers
    result, err := divide(4, 0)
    if err != nil {
        fmt.Println("Error:", err)
        if divErr, ok = err.(*DivideError); ok {
            fmt.Printf("Details: A=%f, B=%f\n", divErr.A, divErr.B)
        }
    } else {
        fmt.Println("Result:", result)
    }

    // Wrap the error with additional context
    _, originalErr := divide(4, 0)
    wrappedErr := fmt.Errorf("additional context: %w", originalErr)
    fmt.Println("Wrapped error:", wrappedErr)
}
```

This example demonstrates how to define custom errors, handle them, and wrap them with additional context.

Go's error handling approach encourages explicit error checking, making your code predictable and easier to maintain. It might seem verbose at first, but it leads to robust and clear code.

NEXT->[[(13) File handling in Go]]