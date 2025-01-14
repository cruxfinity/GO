Variable is a placeholder of the information which can be changed at runtime. Variables allow to Retrieve and Manipulate the stored information.
	1. Variable names must begin with a letter or an underscore(_). And the names may contain the letters ‘a-z’ or ’A-Z’ or digits 0-9 as well as the character ‘_’.
	2. A variable name should not start with a digit.
	3. Keywords is not allowed to use as a variable name.

# Declaring a Variable

**Using ==var== keyword**
	 `var variable_name type = expression
	 In the above syntax, either _type_ or _=_ expression can be omitted, but not both.

*note* : If the expression is removed, then the variable holds zero-value for the type like zero for the number, false for Booleans, **“”** for strings, and nil for interface and reference type. So, there is ==_**no such concept of an uninitialized variable in Go language.**_== 

**Using short variable declaration**
	 `variable_name:= expression 
	 The local variables which are initialized in the functions are declared by using short variable declaration ( := ).
```
package main

import "fmt"

func main() {

// Using short variable declaration
// Multiple variables of same types
// are declared and initialized in 
// the single line

myvar1, myvar2, myvar3 := 800, 34, 56

fmt.println( myvar1 , myvar2 , myvar3)

}
```

`In a short variable declaration, you are allowed to initialize a set of variables by the calling function that returns multiple values.
==i, j := os.Open(name)==

`Using short variable declaration you are allowed to declare multiple variables of different types in the single declaration.
==a, b, c := "hello",123,"world==


# Constants

Once the value of constant is defined, it cannot be modified further.
***Constants are declared like variables but in using a const keyword as a prefix to declare a constant with a specific type. It cannot be declared using “:=” syntax.***

```
package main

import "fmt"

const PI = 3.14

func main(){

const A = 10
fmt.println("The value of A is ",a)
fmt.println(PI)
}
```

For reference : https://www.geeksforgeeks.org/constants-go-language/?ref=lbp

NEXT -> [[(5) Operators in Go]]
