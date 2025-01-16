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