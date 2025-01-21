Operators allow us to perform different kinds of operations on operands. In the **Go language**, operators Can be categorized based on their different functionality:

- [Arithmetic Operators](https://www.geeksforgeeks.org/go-operators/#Arithmetic%20Operators)
- [Relational Operators](https://www.geeksforgeeks.org/go-operators/#Relational%20Operators)
- [Logical Operators](https://www.geeksforgeeks.org/go-operators/#Logical%20Operators)
- [Bitwise Operators](https://www.geeksforgeeks.org/go-operators/#Bitwise%20Operators)
- [Assignment Operators](https://www.geeksforgeeks.org/go-operators/#Assignment%20Operators)
- [Misc Operators](https://www.geeksforgeeks.org/go-operators/#Misc%20Operators)

Go has a rich set of operators that you can use in various contexts like arithmetic, comparisons, logical operations, and more. Let's dive into the details of these operators with examples:

### Arithmetic Operators

Arithmetic operators are used to perform mathematical operations.

- **Addition (+):**
    
    
    
    ```
    sum := 5 + 3 // sum is 8
    ```
    
- **Subtraction (-):**
    
    
    
    ```
    difference := 10 - 4 // difference is 6
    ```
    
- _Multiplication (_):*
    
    
    
    ```
    product := 7 * 6 // product is 42
    ```
    
- **Division (/):**
    
    
    
    ```
    quotient := 9 / 3 // quotient is 3
    // Note: Integer division truncates towards zero
    ```
    
- **Modulus (%):**
    
    
    
    ```
    remainder := 10 % 3 // remainder is 1
    ```
    

### Comparison Operators

Comparison operators are used to compare two values and return a boolean result.

- **Equal to ( == ):**
    
    
    
    ```
    equal := (5 == 5) // equal is true
    ```
    
- **Not equal to (!=):**
    
    
    
    ```
    notEqual := (5 != 3) // notEqual is true
    ```
    
- **Greater than (>):**
    
    
    
    ```
    greater := (7 > 4) // greater is true
    ```
    
- **Less than (<):**
    
    
    
    ```
    less := (3 < 5) // less is true
    ```
    
- **Greater than or equal to (>=):**
    
    
    
    ```
    greaterOrEqual := (7 >= 7) // greaterOrEqual is true
    ```
    
- **Less than or equal to (<=):**
    
    
    
    ```
    lessOrEqual := (4 <= 5) // lessOrEqual is true
    ```
    

### Logical Operators

Logical operators are used to combine multiple conditions.

- **Logical AND (&&):**
    
    
    
    ```
    and := (true && false) // and is false
    ```
    
- **Logical OR (||):**
    
    
    
    ```
    or := (true || false) // or is true
    ```
    
- **Logical NOT (!):**
    
    
    
    ```
    not := !true // not is false
    ```
    

### Bitwise Operators

Bitwise operators perform operations on individual bits of integer values.

- **Bitwise AND (&):**
    
    
    
    ```
    bitwiseAnd := 6 & 3 // bitwiseAnd is 2 (0110 & 0011 is 0010)
    ```
    
- **Bitwise OR (|):**
    
    
    
    ```
    bitwiseOr := 6 | 3 // bitwiseOr is 7 (0110 | 0011 is 0111)
    ```
    
- **Bitwise XOR (^):**
    
    
    
    ```
    bitwiseXor := 6 ^ 3 // bitwiseXor is 5 (0110 ^ 0011 is 0101)
    ```
    
- **Bitwise NOT (^):**
    
    
    
    ```
    bitwiseNot := ^6 // bitwiseNot is -7 (In two's complement, the bitwise NOT of 0110 is 1001)
    ```
    
- **Left shift (<<):**
    
    
    
    ```
    leftShift := 3 << 2 // leftShift is 12 (0011 shifted left by 2 positions is 1100)
    ```
    
- **Right shift (>>):**
    
    
    
    ```
    rightShift := 8 >> 2 // rightShift is 2 (1000 shifted right by 2 positions is 0010)
    ```
    

### Assignment Operators

Assignment operators are used to assign values to variables.

- **Assignment (=):**
    
    
    
    ```
    var x int = 10 // Assigns 10 to x
    ```
    
- **Addition assignment (+=):**
    
    
    
    ```
    x += 5 // x is now 15
    ```
    
- **Subtraction assignment (-=):**
    
    
    
    ```
    x -= 3 // x is now 12
    ```
    
- _Multiplication assignment (_=):*
    
    
    
    ```
    x *= 2 // x is now 24
    ```
    
- **Division assignment (/=):**
    
    
    
    ```
    x /= 4 // x is now 6
    ```
    
- **Modulus assignment (%=):**
    
    
    
    ```
    x %= 4 // x is now 2
    ```
    
- **Bitwise AND assignment (&=):**
    
    
    
    ```
    x &= 3 // x is now 2 (0010 & 0011 is 0010)
    ```
    
- **Bitwise OR assignment (|=):**
    
    
    
    ```
    x |= 1 // x is now 3 (0010 | 0001 is 0011)
    ```
    
- **Bitwise XOR assignment (^=):**
    
    
    
    ```
    x ^= 2 // x is now 1 (0011 ^ 0010 is 0001)
    ```
    
- **Left shift assignment (<<=):**
    
    
    
    ```
    x <<= 1 // x is now 2 (0001 shifted left by 1 position is 0010)
    ```
    
- **Right shift assignment (>>=):**
    
    
    
    ```
    x >>= 1 // x is now 1 (0010 shifted right by 1 position is 0001)
    ```
    

### Other Operators

- **Address-of (&):**
    
    
    
    ```
    y := 10
    ptr := &y // ptr is a pointer to y
    ```
    
- _Dereference (_):*
    
    
    
    ```
    z := *ptr // z is 10, the value of y
    ```
    

### Example: Using Different Operators

Here's a complete example that demonstrates the use of various operators in Go:



```
package main

import "fmt"

func main() {
    // Arithmetic operators
    a, b := 5, 3
    fmt.Println("Sum:", a+b)
    fmt.Println("Difference:", a-b)
    fmt.Println("Product:", a*b)
    fmt.Println("Quotient:", a/b)
    fmt.Println("Remainder:", a%b)

    // Comparison operators
    fmt.Println("Equal:", a == b)
    fmt.Println("Not Equal:", a != b)
    fmt.Println("Greater than:", a > b)
    fmt.Println("Less than:", a < b)
    fmt.Println("Greater or Equal:", a >= b)
    fmt.Println("Less or Equal:", a <= b)

    // Logical operators
    p, q := true, false
    fmt.Println("Logical AND:", p && q)
    fmt.Println("Logical OR:", p || q)
    fmt.Println("Logical NOT:", !p)

    // Bitwise operators
    fmt.Println("Bitwise AND:", a&b)
    fmt.Println("Bitwise OR:", a|b)
    fmt.Println("Bitwise XOR:", a^b)
    fmt.Println("Left Shift:", a<<1)
    fmt.Println("Right Shift:", a>>1)

    // Assignment operators
    x := 10
    x += 5
    fmt.Println("Addition Assignment:", x)
    x -= 3
    fmt.Println("Subtraction Assignment:", x)
    x *= 2
    fmt.Println("Multiplication Assignment:", x)
    x /= 4
    fmt.Println("Division Assignment:", x)
    x %= 3
    fmt.Println("Modulus Assignment:", x)

    // Address-of and Dereference operators
    y := 20
    ptr := &y
    fmt.Println("Address-of:", ptr)
    fmt.Println("Dereference:", *ptr)
}
```

In this example:

- We use different arithmetic, comparison, logical, bitwise, and assignment operators.
    
- We demonstrate the use of address-of (`&`) and dereference (`*`) operators with pointers.

NEXT -> [[(6) Control statements in Go]]