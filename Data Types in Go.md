Data types specify the type of data that a valid [Go variable](https://www.geeksforgeeks.org/go-variables/) can hold.
1. **Basic type:** Numbers, strings, and Booleans come under this category.
2. **Aggregate type:** Array and structs come under this category.
3. **Reference type:** Pointers, slices, maps, functions, and channels come under this category.
4. **Interface type**
---
*In Go language, numbers are divided into _three_ sub-categories that are:
**==Integers==:** In Go language, both signed and unsigned integers are available in four different sizes

| Data Type   | Description                                                                                                 |
| ----------- | ----------------------------------------------------------------------------------------------------------- |
| **int8**    | 8-bit signed integer                                                                                        |
| **int16**   | 16-bit signed integer                                                                                       |
| **int32**   | 32-bit signed integer                                                                                       |
| **int64**   | 64-bit signed integer                                                                                       |
| **uint8**   | 8-bit unsigned integer                                                                                      |
| **uint16**  | 16-bit unsigned integer                                                                                     |
| **uint32**  | 32-bit unsigned integer                                                                                     |
| **uint64**  | 64-bit unsigned integer                                                                                     |
| **int**     | Both int and uint contain same size, either 32 or 64 bit.                                                   |
| **uint**    | Both int and uint contain same size, either 32 or 64 bit.                                                   |
| **rune**    | It is a synonym of int32 and also represent Unicode code points.                                            |
| **byte**    | It is a synonym of uint8.                                                                                   |
| **uintptr** | It is an unsigned integer type. Its width is not defined, but its can hold all the bits of a pointer value. |

**==Floating-Point Numbers==:** In Go language, floating-point numbers are divided into **two** categories

|Data Type|Description|
|---|---|
|**float32**|32-bit IEEE 754 floating-point number|
|**float64**|64-bit IEEE 754 floating-point number|

==**Complex Numbers==:** The complex numbers are divided into two parts are shown in the below table.

|Data Type|Description|
|---|---|
|**complex64**|Complex numbers which contain float32 as a real and imaginary component.|
|**complex128**|Complex numbers which contain float64 as a real and imaginary component.|

**==Booleans==** : The Boolean data type represents only one bit of information either **true** or **false**.

**==Strings==** : The string data type represents a sequence of Unicode code points.

NEXT -> [[Variables in Go]]