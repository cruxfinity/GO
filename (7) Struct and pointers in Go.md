A struct in Golang is a user-defined type that allows to group/combine items of possibly different types into a single type.
**Declaring a structure:**
```
 type Address struct {
      name string 
      street string
      city string
      state string
      Pincode int
}
```
In the above, the _**type**_ keyword introduces a new type. It is followed by the name of the type (_Address_) and the keyword _struct_ to illustrate that we’re defining a struct.

You can also _initialize a variable of a struct type using a struct literal_ as shown below:
```
var a = Address{"Akshay", "PremNagar", "Dehradun", "Uttarakhand", 252636}
```

**Note:**
- Always pass the field values in the same order in which they are declared in the struct. Also, you can’t initialize only a subset of fields with the above syntax.
- Go also supports the _name: value_ syntax for initializing a struct (the order of fields is irrelevant when using this syntax).
```
	var a = Address{Name:”Akshay”, street:”PremNagar”, state:”Uttarakhand”, Pincode:252636} //city:”” 
```
And this allows you to initialize only a subset of fields. All the uninitialized fields are set to their corresponding zero value.

___
```
package main
import "fmt"

type Address struct{
name string
city string
pincode int
}

func main(){
var a Address //here the struct field is initialized with 0 
fmt.Println(a) //{ 0}

a1:= Address{"abinash","delhi",12345}
fmt.Println("Address1:",a1) //Address1: {abinash delhi 12345}

a2=Address{"dash","kolkata",54321}
fmt.Println("Address2:",a2) //Address2: {dash kolkata 54321}
}
```

To access individual fields of a _struct_ you have to use dot ( . ) operator.
```
package main

import "fmt"

// defining the struct
type Car struct {
	Name, Model, Color string
	WeightInKg		 float64
}

// Main Function
func main() {
	c := Car{Name: "Ferrari", Model: "GTC4",
			Color: "Red", WeightInKg: 1920}

	// Accessing struct fields
	// using the dot operator
	fmt.Println("Car Name: ", c.Name)
	fmt.Println("Car Color: ", c.Color)

	// Assigning a new value
	// to a struct field
	c.Color = "Black"
	
	// Displaying the result
	fmt.Println("Car: ", c)
}

```

### Pointers to a struct

Pointers in Go is a variable which is used to store the memory address of another variable. You can also create a pointer to a struct as shown in the below example:
```
package main

import "fmt"

// defining a structure
type Employee struct {
	firstName, lastName string
	age, salary int
}

func main() {

	// passing the address of struct variable
	// emp8 is a pointer to the Employee struct
	emp8 := &Employee{"Sam", "Anderson", 55, 6000}

	// (*emp8).firstName is the syntax to access
	// the firstName field of the emp8 struct
	fmt.Println("First Name:", (*emp8).firstName)
	fmt.Println("Age:", (*emp8).age)
}
___________________________________________________________
Output
First Name: Sam
Age: 55
```

___
### Advantages of using structures in Go:

1. ==Encapsulation==: Structures allow you to encapsulate related data together, making it easier to manage and modify the data.

2. ==Type safety==: Structures provide type safety by allowing you to define   the type of each field, which helps to prevent errors caused by            assigning the wrong type of value.

3.  ==Efficiency==: Structures in Go are very efficient, both in terms of               memory usage and performance.

### Disadvantages of using structures in Go:

1. ==Complexity==: Structures can make code more complex, especially if the structures have a large number of fields or methods.

2. ==Boilerplate code==: When defining large structures with many fields, it can be time-consuming to write out all of the field names and types.

3. ==Immutability==: Go structures are mutable by default, which can make it more difficult to enforce immutability in your code.
___

# Pointers
In Go, pointers are variables that store the memory address of another variable. They are useful for referencing and manipulating data indirectly. Let's go over the basics of pointers in Go with an example:

1. **Declaring a Pointer:** You can declare a pointer using the `*` operator.
    
    
    
    ```
    var ptr *int // Declares a pointer to an integer
    ```
    
2. **Getting the Address of a Variable:** You can get the address of a variable using the `&` operator.
    
    
    
    ```
    var num int = 42
    var ptr = &num // ptr now holds the address of num
    ```
    
3. **Dereferencing a Pointer:** You can access the value stored at the address a pointer is pointing to using the `*` operator.
    
    
    
    ```
    var value = *ptr // value is now 42, the value of num
    ```
    

Here is a complete example:



```
package main

import "fmt"

func main() {
    // Declare an integer variable
    var num int = 42

    // Declare a pointer and assign the address of num to it
    var ptr *int = &num

    // Print the value of num using the pointer
    fmt.Println("Value of num:", *ptr)

    // Modify the value of num using the pointer
    *ptr = 100

    // Print the modified value of num
    fmt.Println("Modified value of num:", num)
}
```

In this example:

- We declare an integer variable `num` and assign it the value `42`.
    
- We declare a pointer `ptr` and assign it the address of `num`.
    
- We use the pointer to print the value of `num`.
    
- We modify the value of `num` using the pointer and print the modified value.
    

Pointers in Go are a powerful feature that allows you to work with memory addresses and manipulate data indirectly. They are especially useful when working with large data structures or when you need to modify a value within a function.

NEXT -> [[(8) Functions and methods in Go]]