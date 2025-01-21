In Go, arrays are fixed-size sequences of elements of a single type. Here's a quick overview of arrays in Go, along with an example:

1. **Declaring an Array:** You can declare an array by specifying the size and the type of elements it will hold.
    
    
    
    ```
    var arr [5]int // Declares an array of 5 integers
    ```
    
2. **Initializing an Array:** You can initialize an array at the time of declaration.
    
    
    
    ```
    var arr = [5]int{1, 2, 3, 4, 5} // Initializes an array with values 1, 2, 3, 4, 5
    ```
    
3. **Accessing Elements:** You can access elements of an array using the index.
    
    
    
    ```
    fmt.Println(arr[0]) // Prints the first element of the array
    ```
    
4. **Modifying Elements:** You can modify elements of an array by assigning new values to specific indices.
    
    
    
    ```
    arr[0] = 10 // Sets the first element to 10
    ```
    

Here is a complete example:



```
package main

import "fmt"

func main() {
    // Declare and initialize an array
    var arr = [5]int{1, 2, 3, 4, 5}

    // Access and print elements of the array
    fmt.Println("First element:", arr[0])
    fmt.Println("Second element:", arr[1])

    // Modify an element
    arr[0] = 10

    // Print the modified array
    fmt.Println("Modified array:", arr)
}
```

In this example:

- We declare and initialize an array `arr` with 5 integers.
    
- We access and print the first and second elements.
    
- We modify the first element and print the modified array.
    

Remember, arrays in Go have a fixed size, so you can't change their size once they're defined. For more flexibility, you might want to use slices, which are like dynamically-sized arrays.

___

# Slices in Golang
Slices in Go are more flexible and powerful than arrays. They provide a dynamic array-like structure with additional functionality. Here's a quick overview of slices in Go, along with an example:

1. **Creating a Slice:** You can create a slice from an array or using the `make` function.
    
    
    
    ```
    var arr = [5]int{1, 2, 3, 4, 5}
    var slice = arr[1:4] // Creates a slice from elements 2, 3, and 4 of the array
    ```
    
2. **Appending to a Slice:** You can append elements to a slice using the `append` function.
    
    
    
    ```
    slice = append(slice, 6, 7) // Appends 6 and 7 to the slice
    ```
    
3. **Length and Capacity:** You can get the length and capacity of a slice using the `len` and `cap` functions.
    
    
    
    ```
    fmt.Println(len(slice)) // Prints the length of the slice
    fmt.Println(cap(slice)) // Prints the capacity of the slice
    ```
    

Here is a complete example:



```
package main

import "fmt"

func main() {
    // Create a slice from an array
    var arr = [5]int{1, 2, 3, 4, 5}
    var slice = arr[1:4] // Slice contains elements 2, 3, and 4

    // Print the slice
    fmt.Println("Slice:", slice)

    // Append elements to the slice
    slice = append(slice, 6, 7)

    // Print the modified slice
    fmt.Println("Modified slice:", slice)

    // Print the length and capacity of the slice
    fmt.Println("Length of slice:", len(slice))
    fmt.Println("Capacity of slice:", cap(slice))
}
```

In this example:

- We create a slice from an array `arr` that includes elements 2, 3, and 4.
    
- We append elements 6 and 7 to the slice.
    
- We print the modified slice, its length, and its capacity.
    

Slices are a powerful feature in Go, offering dynamic resizing and efficient memory management. They are widely used in Go programming for various tasks.

NEXT->[[(10) Strings in Golang]]