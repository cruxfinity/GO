### if statement
```
if condition {

   // Statements to execute if
   // condition is true
}
```

### if…else Statement
```
if condition {

    // Executes this block if
    // condition is true
} else {

    // Executes this block if
    // condition is false
}
```

### Nested if Statement
```
if condition1 {

   // Executes when condition1 is true
   
   if condition2 {

      // Executes when condition2 is true
   }
}
```

### if..else..if ladder
```
if condition_1 {

     // this block will execute 
     // when condition_1 is true

} else if condition_2 {

    // this block will execute 
    // when condition2 is true
}
.
.
. else {

      // this block will execute when none
     // of the condition is true
}
```


# Loops
**1. As simple for loop**
```
for initialization; condition; post{
       // statements....
}
```

```
pacakage main
import "fmt"

func main(){

for i := 0; i<4; i++{

fmt.Println("hello world")

}
}

____________________________________________________________
Output

hello world
hello world
hello world
hello world

```

**2. For loop as Infinite Loop:**
```
for{
     // Statement...
}
```

```
package main
import "fmt"

func main(){

for{

fmt.Println("hello world")
}

}
___________________________________________________________
Output
hello world
hello world
hello world
hello world
.
.
.
```

**3. for loop as while Loop:**
```
for condition{
    // statement..
}
```

```
package main
import "fmt"

func main(){

i:= 0

for i<3{

i+=2 // loop executes till i<3 condition is true

}
fmt.Println(i)
}
___________________________________________________________
Output
4
```


**4. Simple range in for loop:**
```
for i, j:= range rvariable{
   // statement..
}
```

```
package main

import "fmt"

func main() {
    numbers := []int{1, 2, 3, 4, 5}

    // Using range to iterate over a slice
    // i stores the index number of individual number
    // num stores the individual number
    
    for i, num := range numbers {
        
        fmt.Printf("Index: %d, Value: %d\n", i, num)
    }
}

```


# Switch Statement
In Go, a `switch` statement is a multiway branch statement that efficiently directs execution based on the value (or type) of an expression. 
```
package main

import "fmt"

func main() {
    i := 2
    fmt.Print("Write ", i, " as ")
    switch i {
    case 1:
        fmt.Println("one")
    case 2:
        fmt.Println("two")
    case 3:
        fmt.Println("three")
    default:
        fmt.Println("unknown number")
    }
}

```

### Multiple expressions in case:

You can have multiple expressions in a single case:
package main
```
import "fmt"

func main() {
    char := 'a'
    switch char {
    case 'a', 'e', 'i', 'o', 'u':
        fmt.Println("Vowel")
    default:
        fmt.Println("Consonant")
    }
}
```

### Switch with no condition:

A switch statement with no condition is used as an alternative to `if-else`:
```
package main

import "fmt"

func main() {
    num := 75
    switch {
    case num > 100:
        fmt.Println("Greater than 100")
    case num > 50:
        fmt.Println("Greater than 50")
    default:
        fmt.Println("50 or less")
    }
}
```
___

In this example, we use the same `day` variable but wrapped in an `interface{}` to demonstrate the type switch.
```
package main
import "fmt"
func main() {
    var day interface{} = 4
    switch v := day.(type) {
    case int:
        switch v {
        case 1:
            fmt.Println("Monday")
        case 2:
            fmt.Println("Tuesday")
        case 3:
            fmt.Println("Wednesday")
        case 4:
            fmt.Println("Thursday")
        case 5:
            fmt.Println("Friday")
        default:
            fmt.Println("Invalid day")
        }
    default:
        fmt.Printf("Unknown type: %T\n", v)
    }
}
```

NEXT -> [[(7) Struct and pointers in Go]]