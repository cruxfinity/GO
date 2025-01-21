In Go, strings are a sequence of bytes used to represent text. They are immutable, meaning their content cannot be changed after they are created. Here are some common operations you can perform with strings in Go:

1. **Creating a String:** You can create a string using double quotes.
    
    
    
    ```
    var str = "Hello, World!"
    ```
    
2. **String Length:** You can get the length of a string using the `len` function.
    
    
    
    ```
    fmt.Println(len(str)) // Prints the length of the string
    ```
    
3. **Accessing Characters:** You can access individual characters of a string using indices. Note that this gives you the byte at the given index, not necessarily a full character.
    
    
    
    ```
    fmt.Println(str[0]) // Prints the first byte of the string
    ```
    
4. **String Concatenation:** You can concatenate strings using the `+` operator.
    
    
    
    ```
    var greeting = "Hello, " + "World!"
    ```
    
5. **Substring:** You can extract a substring using slicing.
    
    
    
    ```
    var sub = str[7:12] // Extracts "World" from the string
    ```
    
6. **Iterating Over a String:** You can iterate over a string using a `for` loop with the `range` keyword.
    
    
    
    ```
    for i, c := range str {
        fmt.Printf("Character %d: %c\n", i, c)
    }
    ```
    

Here is a complete example demonstrating these operations:



```
package main

import "fmt"

func main() {
    // Create a string
    var str = "Hello, World!"

    // Get and print the length of the string
    fmt.Println("Length of string:", len(str))

    // Access and print the first character (byte) of the string
    fmt.Printf("First character (byte): %c\n", str[0])

    // Concatenate and print strings
    var greeting = "Hello, " + "Gophers!"
    fmt.Println("Concatenated string:", greeting)

    // Extract and print a substring
    var sub = str[7:12]
    fmt.Println("Substring:", sub)

    // Iterate over and print characters of the string
    for i, c := range str {
        fmt.Printf("Character %d: %c\n", i, c)
    }
}
```

In this example:

- We create a string `str` with the value "Hello, World!".
    
- We get and print the length of the string.
    
- We access and print the first character (byte) of the string.
    
- We concatenate and print strings.
    
- We extract and print a substring.
    
- We iterate over and print characters of the string.
    

Strings in Go are versatile and come with a variety of useful functions in the `strings` package for manipulation and analysis.

NEXT->[[(12) Error handling in Go]]