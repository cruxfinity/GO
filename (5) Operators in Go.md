Operators allow us to perform different kinds of operations on operands. In the **Go language**, operators Can be categorized based on their different functionality:

- [Arithmetic Operators](https://www.geeksforgeeks.org/go-operators/#Arithmetic%20Operators)
- [Relational Operators](https://www.geeksforgeeks.org/go-operators/#Relational%20Operators)
- [Logical Operators](https://www.geeksforgeeks.org/go-operators/#Logical%20Operators)
- [Bitwise Operators](https://www.geeksforgeeks.org/go-operators/#Bitwise%20Operators)
- [Assignment Operators](https://www.geeksforgeeks.org/go-operators/#Assignment%20Operators)
- [Misc Operators](https://www.geeksforgeeks.org/go-operators/#Misc%20Operators)

#### Arithmetic Operators
- **Addition:** The ‘+’ operator adds two operands. For example, x+y.
- **Subtraction:** The ‘-‘ operator subtracts two operands. For example, x-y.
- **Multiplication:** The ‘*’ operator multiplies two operands. For example, x*y.
- **Division:** The ‘/’ operator divides the first operand by the second. For example, x/y.
- **Modulus:** The ‘%’ operator returns the remainder when the first operand is divided by the second. For example, x%y.

**Note:** -, +, !, &, *, <-, and ^ are also known as unary operators and the precedence of unary operators is higher. ++ and — operators are from statements they are not expressions, so they are out from the operator hierarchy.

#### Relational Operators
- " == "(Equal To) operator checks whether the two given operands are equal or not. If so, it returns true. Otherwise, it returns false.
- **‘!='(Not Equal To)** operator checks whether the two given operands are equal or not. If not, it returns true. Otherwise, it returns false. It is the exact Boolean complement of the ‘ == ’ operator. 
- **‘>'(Greater Than)**operator checks whether the first operand is greater than the second operand. If so, it returns true. Otherwise, it returns false. 
- **‘<‘(Less Than)**operator checks whether the first operand is lesser than the second operand. If so, it returns true. Otherwise, it returns false. 
- **‘>='(Greater Than Equal To)**operator checks whether the first operand is greater than or equal to the second operand. If so, it returns true. Otherwise, it returns false. 
- **‘<='(Less Than Equal To)**operator checks whether the first operand is lesser than or equal to the second operand. If so, it returns true. Otherwise, it returns false. 

#### Logical Operators
- ==**Logical AND:** The ‘&&’ operator returns true when both the conditions in consideration are satisfied.== Otherwise it returns false. For example, a && b returns true when both a and b are true (i.e. non-zero).
- ==**Logical OR:** The ‘||’ operator returns true when one (or both) of the conditions in consideration is satisfied.== Otherwise it returns false. For example, a || b returns true if one of a or b is true (i.e. non-zero). Of course, it returns true when both a and b are true.
- ==**Logical NOT:** The ‘!’ operator returns true the condition in consideration is not satisfied==. Otherwise it returns false. For example, !a returns true if a is false, i.e. when a=0.

#### Bitwise Operators
In Go language, there are 6 bitwise operators which work at bit level or used to perform bit by bit operations.
- **& (bitwise AND):** Takes two numbers as operands and does AND on every bit of two numbers. The result of AND is 1 only if both bits are 1.
- **| (bitwise OR):** Takes two numbers as operands and does OR on every bit of two numbers. The result of OR is 1 any of the two bits is 1.
- **^ (bitwise XOR):** Takes two numbers as operands and does XOR on every bit of two numbers. The result of XOR is 1 if the two bits are different.
- **<< (left shift):** Takes two numbers, left shifts the bits of the first operand, the second operand decides the number of places to shift.
- **>> (right shift):** Takes two numbers, right shifts the bits of the first operand, the second operand decides the number of places to shift.
- **&^ (AND NOT):** This is a bit clear operator.

```
package main

import "fmt"

func main() {

   p:= 34

   q:= 20

   // & (bitwise AND)

   result1:= p & q

   fmt.Printf("Result of p & q = %d", result1)

   // | (bitwise OR)

   result2:= p | q

   fmt.Printf("\nResult of p | q = %d", result2)

   // ^ (bitwise XOR)

   result3:= p ^ q

   fmt.Printf("\nResult of p ^ q = %d", result3)

   // << (left shift)

   result4:= p << 1

   fmt.Printf("\nResult of p << 1 = %d", result4)

   // >> (right shift)

   result5:= p >> 1

   fmt.Printf("\nResult of p >> 1 = %d", result5)

   // &^ (AND NOT)
 
   result6:= p &^ q

   fmt.Printf("\nResult of p &^ q = %d", result6)

}
___________________________________________________________
```
```
**Output:** 

Result of p & q = 0
Result of p | q = 54
Result of p ^ q = 54
Result of p << 1 = 68
Result of p >> 1 = 17
Result of p &^ q = 34

```


#### Assignment Operators
Assignment operators are used to assigning a value to a variable.

- **“=”(Simple Assignment):** This is the simplest assignment operator. This operator is used to assign the value on the right to the variable on the left.
- **“+=”(Add Assignment):** This operator is a combination of ‘+’ and ‘=’ operators. This operator first adds the current value of the variable on left to the value on the right and then assigns the result to the variable on the left.
- **“-=”(Subtract Assignment):** This operator is a combination of ‘-‘ and ‘=’ operators. This operator first subtracts the current value of the variable on left from the value on the right and then assigns the result to the variable on the left.
- **“ * = ”(Multiply Assignment):** This operator is a combination of ‘*’ and ‘=’ operators. This operator first multiplies the current value of the variable on left to the value on the right and then assigns the result to the variable on the left.
- **“ /= ”(Division Assignment):** This operator is a combination of ‘/’ and ‘=’ operators. This operator first divides the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.
- **“%=”(Modulus Assignment):** This operator is a combination of ‘%’ and ‘=’ operators. This operator first modulo the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.
- **“&=”(Bitwise AND Assignment):** This operator is a combination of ‘&’ and ‘=’ operators. This operator first “Bitwise AND” the current value of the variable on the left by the value on the right and then assigns the result to the variable on the left.
- **“^=”(Bitwise Exclusive OR):** This operator is a combination of ‘^’ and ‘=’ operators. This operator first “Bitwise Exclusive OR” the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.
- **“|=”(Bitwise Inclusive OR):** This operator is a combination of ‘|’ and ‘=’ operators. This operator first “Bitwise Inclusive OR” the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.
- **“<<=”(Left shift AND assignment operator):** This operator is a combination of ‘<<’ and ‘=’ operators. This operator first “Left shift AND” the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.
- **“>>=”(Right shift AND assignment operator):** This operator is a combination of ‘>>’ and ‘=’ operators. This operator first “Right shift AND” the current value of the variable on left by the value on the right and then assigns the result to the variable on the left.

#### Misc Operators
- **& :** This operator returns the address of the variable.
- *  : This operator provides pointer to a variable.
- <- : **The name of this operator is receive. It is used to receive a value from the channel.
```
package main
import "fmt"

func main(){
a := 4
//using address of operator(&) and
//pointer indirection(*) operator

b:= &a
fmt.Println(*b)
*b = 7
fmt.Println(a)
}
___________________________________________________________

Output:

4
7
```

