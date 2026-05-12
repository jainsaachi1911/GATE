___
# Basics of C Programming
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
> **It is called formatted print. It allows `\n, \t` etc.**

---
##   Precedence & Associativity of All Operators

| Group              | Operator                                                     | Category                                                                                       | Associativity     | Precedence |
| ------------------ | ------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | ----------------- | ---------- |
| **Parenthesis**    | `()` `[]` `->` `.`                                           | Function call, Array subscript, Arrow, Dot                                                     | Left to right     | Highest 14 |
| ==**Unary**==      | ==`++` `--` `!` `~` `(type)` `&` `*` `sizeof`==              | ==Increment, Decrement, Logical NOT, One's complement, Cast, Address of, Indirection, Sizeof== | ==Right to left== | ==13==     |
| **Multiplicative** | `*` `/` `%`                                                  | Multiplication, Division, Modulus                                                              | Left to right     | 12         |
| **Additive**       | `+` `-`                                                      | Addition, Subtraction                                                                          | Right to left     | 11         |
| **Shift**          | `<<` `>>`                                                    | Left Shift, Right Shift                                                                        | Left to right     | 10         |
| **Relational**     | `<` `<=` `>` `>=`                                            | Less than, Less than or Equal to, Greater than, Greater than or Equal to                       | Left to right     | 8          |
| **Equal To**       | `==` `!=`                                                    | Equal to, Not equal to                                                                         | Right to left     | 8          |
| **Bitwise AND**    | `&`                                                          | Bitwise AND                                                                                    | Left to right     | 7          |
| **Bitwise XOR**    | `^`                                                          | Bitwise XOR                                                                                    | Left to right     | 6          |
| **Bitwise OR**     | `\|`                                                         | Bitwise OR                                                                                     | Right to left     | 5          |
| **Logical AND**    | `&&`                                                         | Logical AND                                                                                    | Left to right     | 4          |
| **Logical OR**     | `\|\|`                                                       | Logical OR                                                                                     | Left to right     | 3          |
| ==**Ternary**==    | ==`? :`==                                                    | ==Conditional==                                                                                | ==Right to left== | ==2==      |
| ==**Assignment**== | ==`=` `+=` `-=` `*=` `/=` `%=` `>>=` `<<=` `&=` `^=` `\|=`== | ==Assignment operators==                                                                       | ==Right to left== | ==1==      |
| **Comma**          | `,`                                                          | Comma                                                                                          | Left to right     | Lowest 0   |


![[Pasted image 20260511172159.png]]


> [!NOTE] Associativity
> **Check Highlighted Ones: Unary, Ternary and Assignment.** TAU is always Right

---
### Arithmetic Operators

| Operation  | Sign | Code                                                   |
| ---------- | ---- | ------------------------------------------------------ |
| Sum        | `+`  | `x+y`                                                  |
| Difference | `-`  | `x-y`                                                  |
| Product    | `*`  | `x*y`                                                  |
| Quotient   | `/`  | `x/y` (ignores no. after point eg: 2.52. will print 2) |
| Remainder  | `%`  | `x%y`                                                  |
##### Integer

```c
int main() 
{
	int x = 6, y = 5;
	printf("Sum = %d\n",x + y); // 11
	printf("Difference = %d\n",x - y); // 1
	printf("Product = %d\n",x * y); // 30
	printf("Quotient = %d\n",x / y); // 1 (1.2 not possible)
	printf("Remainder = %d\n",x % y); // 1
	return 0;
}
```

##### Float
``` c
int main() 
{
	float x = 5.8, y = 2.3;
	printf("Sum = %f\n",x + y); // 8.1
	printf("Difference = %f\n",x - y); // 3.5
	printf("Product = %f\n",x * y); // 13.34
	printf("Quotient = %.3f\n",x / y); // 2.521
	// Remainder x % y does not exist
}
```

> [!NOTE] Never do %f in Int/Int
> The result will be invalid
#### Increment and Decrement Operator

`a = 5`

| Operator            | Internal Working   | Final Answer                 |
| ------------------- | ------------------ | ---------------------------- |
| `printf("%d",a);`   |                    | 5                            |
| `printf("%d",++a);` | a = a+1<br>Use a   | 6                            |
| `printf("%d",--a);` | a = a - 1<br>Use a | 4                            |
| `printf("%d",a++);` | Use a<br>a = a + 1 | 5<br>// internally a = 6 now |
| `printf("%d",a--);` | Use a<br>a = a - 1 | 5<br>// internally a = 4 now |
#### Comma Operator

1. Separator
2. Operator

``` c
int main()
{
	int a, b;
	a = (2, 3, 4); // Operator (Ans: 4)
	b = 2, 3, 4; // Seperator (Ans: 2)
	printf("%d, %d", a, b); // 4, 2
	return 0;
}
```

#### Ternary Operator

`___ ? ___ : ____`

``` c
int main()
{
	int x, y, max;
	scanf("%d%d", &x, &y);
	max = x>y ? x : y
	printf("Max = %d\n",max);
	return 0;
}
```

`max = x>y ? x : y`

if (x > y)
	True: x
	False: y

`z = (x == 3 ? (y == 4 ? 6 : 8) : 0);`

if (x == 3)
	True: if (y == 4)
		True: 6
		False: 8
	False: 0

#### Sizeof Operator 

**No. of bytes required to store**

> [!NOTE] Is Sizeof a function in C?
> No, Sizeof is not a function, Its an Operator.

| Data Type           | Bytes |
| ------------------- | ----- |
| int x;<br>sizeof(x) | 4     |
| sizeof(int)         | 4     |
| sizeof(5)           | 4     |
| sizeof(char)        | 1     |
| sizeof(short int)   | 2     |
| sizeof(float)       | 4     |
| sizeof(double)      | 8     |
| sizeof(long double) | 16    |

#### TypeCasting

**Types**
1. Implicit Typecasting
	- Done by compiler
	- No loss of information
	- Eg: x (8 bit) + y (16 bit) = Ans (Automatically converts x into 16 bit)
2. Explicit Typecasting
	- Done by programmer
	- Will be loss of information
	- Eg: float x; int(x)

**Important Case**

**Case 1:**

`int a = 10, b = 3;`
`float c = a / b;`
Ans:  3.0 (not 3.3333)

**Case 2: Precedence**

`int a = 10, b = 3;`
`float c = (float)a/b;` //  float a / int b 
Ans: 3.33333

**Case 3: Associativity**

`int a = 10, b = 3;`
`float c = (float)(a/b)` // first will solve a/b R -> L
Ans: 3.0
____
# Control Statements

### If Else Statements
``` c
int main()
{
	int n1=1, n2=2;
	if(n1 > n2) 
	{
		printf("%d", n1)
	}
	else 
	{
		printf("%d", n2)
	}
}
```

``` c
enum Fruit { Apple, Mango };

int main()
{
    int n = Mango;
    if (n == Apple)
    {
        printf("Apple");
    }
    else if (n == Mango)
    {
        printf("Mango");
    }
    else
    {
        printf("Not a fruit");
    }

    return 0;
}

```


> [!NOTE] Can you write without Else or Else Ifs?
> Yes, I can consecutively write multiple Ifs and skip Else
### While Loop

``` c
int main()
{
	int n = 1;
	while(n <= 5)
	{
		printf("%d", n); // 1 2 3 4 5
		n = n + 1;
	}
}
```

``` c
int main()
{
	int n = 1;
	while(n <= 5)
	{
		n = n + 1;
	}
	printf("%d", n); // 6
}
```

### Do While Loop

The body of the loop is executed atleast once before the test expression is evaluated.

