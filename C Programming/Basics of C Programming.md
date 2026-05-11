___
## Sample Code

```c
# include<stdio.h>
main()
{
	printf("Hello World");
}
```

`include<stdio.h>`
- Its a header
- standard input output header file
	`printf`
	`scanf`


> [!NOTE] What is f in printf?
> It is called formatted print. It allows `\n, \t` etc.

---
##   Precedence & Associativity of All Operators

| Group              | Operator                                                 | Category                                                                                   | Associativity | Precedence |
| ------------------ | -------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ------------- | ---------- |
| **Parenthesis**    | `()` `[]` `->` `.`                                       | Function call, Array subscript, Arrow, Dot                                                 | Left to right | Highest 14 |
| **Unary**          | `++` `--` `!` `~` `(type)` `&` `*` `sizeof`              | Increment, Decrement, Logical NOT, One's complement, Cast, Address of, Indirection, Sizeof | Right to left | 13         |
| **Multiplicative** | `*` `/` `%`                                              | Multiplication, Division, Modulus                                                          | Left to right | 12         |
| **Additive**       | `+` `-`                                                  | Addition, Subtraction                                                                      | Right to left | 11         |
| **Shift**          | `<<` `>>`                                                | Left Shift, Right Shift                                                                    | Left to right | 10         |
| **Relational**     | `<` `<=` `>` `>=`                                        | Less than, Less than or Equal to, Greater than, Greater than or Equal to                   | Left to right | 8          |
| **Equal To**       | `==` `!=`                                                | Equal to, Not equal to                                                                     | Right to left | 8          |
| **Bitwise AND**    | `&`                                                      | Bitwise AND                                                                                | Left to right | 7          |
| **Bitwise XOR**    | `^`                                                      | Bitwise XOR                                                                                | Left to right | 6          |
| **Bitwise OR**     | `\|`                                                     | Bitwise OR                                                                                 | Right to left | 5          |
| **Logical AND**    | `&&`                                                     | Logical AND                                                                                | Left to right | 4          |
| **Logical OR**     | `\|\|`                                                   | Logical OR                                                                                 | Left to right | 3          |
| **Ternary**        | `? :`                                                    | Conditional                                                                                | Right to left | 2          |
| **Assignment**     | `=` `+=` `-=` `*=` `/=` `%=` `>>=` `<<=` `&=` `^=` `\|=` | Assignment operators                                                                       | Right to left | 1          |
| **Comma**          | `,`                                                      | Comma                                                                                      | Left to right | Lowest 0   |


![[Pasted image 20260511172159.png]]

