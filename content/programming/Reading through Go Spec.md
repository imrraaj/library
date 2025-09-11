Allows _ in numbers 100_000 is valid number
p = > 2<sup>n</sup>
0x2.p10 = 2 * 2<sup>10</sup>
Supports imaginary numbers 0i
Rune => not a char rather a unicode code point  
**rune**        alias for int32
\U930u5390u034 whatever unicode code point is there
\`\` means row strings and will not be evaluated \n \r \t wont work 
"" means interpreted string, \n \r \t will work



Maps cant have these as keys
thus the key type must not be a function, map, or slice
The initial capacity does not bound its size: maps grow to accommodate the number of items stored in them, with the exception of `nil` maps. A `nil` map is equivalent to an empty map except that no elements may be added.

### Channel
ChannelType = ( "chan" | "chan" "<-" | "<-" "chan" ) ElementType



can create a variable of interface type, if you call interface methods it will panic if not implemented

type a b 
creates two different types a and b so you can do 
```go
// this doensnt work creates two different types at and b
type at = int
type b at
var A at = 34
var B b = 35
A = B
fmt.Println(A, B)



// will work as it creats alis for at as b
type at = int
type b =  at
var A at = 34
var B b = 35
A = B
fmt.Println(A, B)
	```


2^^2 =  2 XOR (neg of 2)
************************
This behavior is consistent across all signed integer types in Go (`int`, `int8`, `int16`, `int32`, `int64`). `^x` will always evaluate to `-(x + 1)`.
```go
^1         // untyped integer constant, equal to -2
uint8(^1)  // illegal: same as uint8(-2), -2 cannot be represented as a uint8
^uint8(1)  // typed uint8 constant, same as 0xFF ^ uint8(1) = uint8(0xFE)
int8(^1)   // same as int8(-2)
^int8(1)   // same as -1 ^ int8(1) = -2
```

## Channels ==blocks== the execution when called
After they receive the value they continue the execution, else wait on the statement

Someone has to be waiting on receiving end if you are sending from select statement

in select
fires receive if it receives first the value
fires send if somewhere the channel receiver is waiting

IF YOU SEND INTO A CHANNEL WITHOUT FIRST LISTING THAT SOMEONE IS THERE ON THE RECEIVER END IT WILL PANIC

