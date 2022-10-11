# Operators

Operators in TorqueScript behave very similarly to operators in real-world math and other programming languages. You should recognize quite a few of these from math classes you took in school, but with small syntactical changes. The rest of this section will explain the syntax and show a brief example, but we will cover these in depth in later guides.

### Arithmetic Operators

These are your basic math operators.

| Operator | Name                                        | Example   | Explanation                        |
| -------- | ------------------------------------------- | --------- | ---------------------------------- |
| `*`      | multiplication                              | `$a * $b` | Multiply `$a` and `$b`.            |
| `/`      | division                                    | `$a / $b` | Divide `$a` by `$b`.               |
| `%`      | modulo                                      | `$a % $b` | Remainder of `$a` divided by `$b`. |
| `+`      | addition                                    | `$a + $b` | Add `$a` and `$b`.                 |
| `-`      | subtraction                                 | `$a - $b` | Subtract `$b` from `$a`.           |
| `++`     | <p>auto-increment</p><p>(post-fix only)</p> | `$a++`    | Increment `$a`.                    |
| `--`     | <p>auto-decrement</p><p>(post-fix only)</p> | `$b--`    | Decrement `$b`.                    |

<mark style="color:orange;">Note:</mark>

<mark style="color:orange;">`++$a`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">is illegal. The value of</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`$a++`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">is that of the incremented variable: auto-increment is post-fix in syntax, but pre-increment in semantics (the variable is incremented before the return value is calculated). This behavior is unlike that of C and C++.</mark>

<mark style="color:orange;">`--$b`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">is illegal. The value of</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`$a--`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">is that of the decremented variable: auto-decrement is post-fix in syntax, but pre-decrement in semantics (the variable is decremented before the return value is calculated). This behavior is unlike that of C and C++.</mark>

### Relational Operators

Used in comparing values and variables against each other.

| Operator | Name                  | Example      | Explanation                                |
| -------- | --------------------- | ------------ | ------------------------------------------ |
| `<`      | Less than             | `$a < $b`    | 1 if `$a` is less than `$b`                |
| `>`      | More than             | `$a > $b`    | 1 if `$a` is greater than `$b`             |
| `<=`     | Less than or Equal to | `$a <= $b`   | 1 if `$a` is less than or equal to `$b`    |
| `>=`     | More than or Equal to | `$a >= $b`   | 1 if `$a` is greater than or equal to `$b` |
| `==`     | Equal to              | `$a == $b`   | 1 if `$a` is equal to `$b`                 |
| `!=`     | Not equal to          | `$a != $b`   | 1 if `$a` is not equal to `$b`             |
| `!`      | Logical NOT           | `!$a`        | 1 if `$a` is 0                             |
| `&&`     | Logical AND           | `$a && $b`   | 1 if `$a` and `$b` are both non-zero       |
| `\|\|`   | Logical OR            | `$a \|\| $b` | 1 if either `$a` or `$b` is non-zero       |
| `$=`     | String equal to       | `$c $= $d`   | 1 if `$c` equal to `$d`.                   |
| `!$=`    | String not equal to   | `$c !$= $d`  | 1 if `$c` not equal to `$d`.               |

### Bitwise Operators

Used for comparing and shifting bits.

| Operator | Name               | Example    | Explanation                                                      |
| -------- | ------------------ | ---------- | ---------------------------------------------------------------- |
| `~`      | Bitwise complement | `~$a`      | flip bits 1 to 0 and 0 to 1                                      |
| `&`      | Bitwise AND        | `$a & $b`  | composite of elements where bits in same position are 1          |
| `\|`     | Bitwise OR         | `$a \| $b` | composite of elements where bits 1 in either of the two elements |
| `^`      | Bitwise XOR        | `$a ^ $b`  | composite of elements where bits in same position are opposite   |
| `<<`     | Left Shift         | `$a << 3`  | element shifted left by 3 and padded with zeros                  |
| `>>`     | Right Shift        | `$a >> 3`  | element shifted right by 3 and padded with zeros                 |

### Assignment Operators

Used for setting the value of variables.

| Operator | Name                 | Example      | Explanation                                                                    |
| -------- | -------------------- | ------------ | ------------------------------------------------------------------------------ |
| `=`      | Assignment           | `$a = $b;`   | Assign value of `$b` to `$a`                                                   |
| `op=`    | Assignment Operators | `$a op= $b;` | Equivalent to `$a = $a op $b`, where op can be any of: \* / % + - & \| ^ << >> |

> Note
>
> The value of an assignment is the value being assigned, so `$a = $b = $c` is legal.

### String Operators

There are special values you can use to concatenate strings and variables. Concatenation refers to the joining of multiple values into a single variable. The following is the basic syntax:

```
"string 1" operation "string 2"
```

You can use string operators similarly to how you use mathematical operators (=, +, -, \*). You have four operators at your disposal:

| Operator | Name                 | Example     | Explanation                                                                                                                 |
| -------- | -------------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------- |
| `@`      | String concatenation | `$c @ $d`   | Concatenates strings $c and $d into a single string. Numeric literals/variables convert to strings.                         |
| `NL`     | New Line             | `$c NL $d`  | Concatenates strings $c and $d into a single string separated by new-line. Such a string can be decomposed with getRecord() |
| `TAB`    | Tab                  | `$c TAB $d` | Concatenates strings $c and $d into a single string separated by tab. Such a string can be decomposed with getField()       |
| `SPC`    | Space                | `$c SPC $d` | Concatenates strings $c and $d into a single string separated by space. Such a string can be decomposed with getWord()      |

### Miscellaneous Operators

General programming operators.

| Operator | Name                   | Example                                                                                                     | Explanation                                                                                                                       |
| -------- | ---------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `? :`    | Conditional            | `x ? y : z`                                                                                                 | Evaluates to `y` if `x` equal to 1, else evaluates to `z`                                                                         |
| `[]`     | Array element          | `$a[5]`                                                                                                     | Synonymous with `$a5`                                                                                                             |
| `( )`    | Delimiting, Grouping   | <p><code>t2dGetMin(%a, %b)</code></p><p><code>if ( $a == $b )</code></p><p><code>($a+$b)*($c-$d)</code></p> | <p>Argument list for function call</p><p>Used with if, for, while, switch keywords</p><p>Control associativity in expressions</p> |
| `{}`     | Compound statement     | <p><code>if (1) {$a = 1; $b = 2;}</code></p><p><code>function foo() {$a = 1;}</code></p>                    | <p>Delimit multiple statements, optional for if, else, for, while</p><p>Required for switch, datablock, new, function</p>         |
| `,`      | Listing                | <p><code>t2dGetMin(%a, %b)</code></p><p><code>%M[1,2]</code></p>                                            | Delimiter for arguments                                                                                                           |
| `::`     | Namespace              | `Item::onCollision()`                                                                                       | This definition of the `onCollision()` function is in the `Item` namespace                                                        |
| `.`      | Field/Method selection | <p><code>%obj.field</code></p><p><code>%obj.method()</code></p>                                             | Select a console method or field                                                                                                  |
| `//`     | Single-line comment    | `// This is a comment`                                                                                      | Used to comment out a single line of code                                                                                         |
| `/* */`  | Multi-line comment     | <p><code>/*This is a a</code></p><p><code>multi-line</code></p><p><code>comment*/</code></p>                | <p>Used to comment out multiple consecutive lines</p><p><code>/*</code> opens the comment, and <code>*/</code> closes it</p>      |

<mark style="color:orange;">NOTE: There is no “comma operator”, as defined in C/C++;</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`$a = 1, $b = 2;`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">is a parse error.</mark>
