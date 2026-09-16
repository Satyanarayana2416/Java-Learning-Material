# Java Basics — Beginner-Friendly Notes

Welcome! 👋  
This README explains some of the **basic Java concepts** in simple English with easy examples.

---

## 1. What is Java?

**Java** is a high-level, object-oriented programming language used to build many types of applications.

Java is popular because:

- It is easy to learn for beginners.
- It is object-oriented.
- It is platform independent.
- It is widely used for web, mobile, desktop, and enterprise applications.
- Java code runs on the **JVM (Java Virtual Machine)**.

### Simple idea

You write Java code → Java compiler converts it into **bytecode** → JVM runs that bytecode.

```text
Java Source Code
       ↓
    Compiler
       ↓
    Bytecode
       ↓
      JVM
       ↓
    Output
```

### Example

```java
class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

---

# 2. Hello World Program in Java

The first program beginners usually write is **Hello World**.

```java
class Main {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

### Output

```text
Hello World
```

### Understanding the code

#### `class Main`

```java
class Main
```

This creates a class named `Main`.

#### `main()`

```java
public static void main(String[] args)
```

This is the **main method**. Java starts program execution from this method.

#### `System.out.println()`

```java
System.out.println("Hello World");
```

This prints text on the screen.

### Example

```java
System.out.println("My name is Purnith");
System.out.println("I am learning Java");
```

Output:

```text
My name is Purnith
I am learning Java
```

---

# 3. Arithmetic Operations in Java

Arithmetic operations are used to perform mathematical calculations.

Java provides these basic arithmetic operators:

| Operator | Operation | Example |
|---|---|---|
| `+` | Addition | `10 + 5` |
| `-` | Subtraction | `10 - 5` |
| `*` | Multiplication | `10 * 5` |
| `/` | Division | `10 / 5` |
| `%` | Modulo | `10 % 3` |

Let's understand each one.

---

## 3.1 Addition

The `+` operator is used to add two values.

```java
class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        int result = a + b;

        System.out.println(result);
    }
}
```

Output:

```text
15
```

### Short form

```java
int result = 10 + 5;
System.out.println(result);
```

Output:

```text
15
```

---

## 3.2 Subtraction

The `-` operator is used to subtract one value from another.

```java
class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        int result = a - b;

        System.out.println(result);
    }
}
```

Output:

```text
5
```

### Example

```java
int money = 100;
int spent = 30;

int remaining = money - spent;

System.out.println(remaining);
```

Output:

```text
70
```

---

## 3.3 Multiplication

The `*` operator is used to multiply values.

```java
class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        int result = a * b;

        System.out.println(result);
    }
}
```

Output:

```text
50
```

### Example

```java
int price = 100;
int quantity = 3;

int total = price * quantity;

System.out.println(total);
```

Output:

```text
300
```

---

## 3.4 Division

The `/` operator is used to divide one value by another.

```java
class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        int result = a / b;

        System.out.println(result);
    }
}
```

Output:

```text
2
```

### Important: Integer Division

When both numbers are integers, Java performs **integer division**.

```java
int result = 10 / 3;

System.out.println(result);
```

Output:

```text
3
```

It does **not** give `3.333...` because `result` is an `int`.

If you want a decimal result, use `double`:

```java
double result = 10.0 / 3.0;

System.out.println(result);
```

Output:

```text
3.3333333333333335
```

---

## 3.5 Modulo Operation

The `%` operator is called the **modulo operator**.

It gives the **remainder** after division.

```java
class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 3;

        int result = a % b;

        System.out.println(result);
    }
}
```

Output:

```text
1
```

Why?

```text
10 ÷ 3 = 3 remainder 1
```

Therefore:

```text
10 % 3 = 1
```

### Common use: Checking Even and Odd

```java
int number = 10;

if (number % 2 == 0) {
    System.out.println("Even");
} else {
    System.out.println("Odd");
}
```

Output:

```text
Even
```

---

# 4. Variables in Java

A **variable** is a named memory location used to store a value.

Think of a variable as a **box with a name**.

```text
age
 ↓
[ 20 ]
```

Here:

- `age` → variable name
- `20` → value
- `int` → data type

Example:

```java
int age = 20;
```

---

# 5. Declaring a Variable

**Declaration** means telling Java:

> "I want to create a variable of this type and with this name."

Syntax:

```java
dataType variableName;
```

Example:

```java
int age;
```

Here:

- `int` → data type
- `age` → variable name

Another example:

```java
double salary;
String name;
boolean isStudent;
```

At this point, we have declared the variables.

---

# 6. Initializing a Variable

**Initialization** means giving a value to a variable for the first time.

Example:

```java
int age;
age = 20;
```

Here:

```java
int age;
```

is declaration.

And:

```java
age = 20;
```

is initialization.

### Declaration + Initialization Together

You can also do both in one line:

```java
int age = 20;
```

This is very common in Java.

---

# 7. Defining a Variable

In beginner-level Java, **defining a variable** generally means creating the variable and assigning a value to it.

Example:

```java
int marks = 85;
```

Here:

- `int` → type
- `marks` → variable name
- `85` → value

Another example:

```java
String name = "Purnith";
```

Here:

- `String` → type
- `name` → variable name
- `"Purnith"` → value

---

# 8. Declaration vs Initialization vs Definition

These terms can be confusing at first.

### Declaration

```java
int age;
```

You are telling Java about the variable.

### Initialization

```java
age = 20;
```

You are assigning the first value to the variable.

### Declaration + Initialization

```java
int age = 20;
```

This creates the variable and gives it its first value.

For beginners, remember:

```text
Declaration    → Create/tell Java about the variable
Initialization → Give the variable its first value
```

---

# 9. Types of Variables in Java

Java variables can be understood in two common ways:

1. **Based on data type**
2. **Based on where the variable is declared**

---

## 9.1 Variables Based on Data Type

### Integer

Used for whole numbers.

```java
int age = 20;
```

### Decimal Number

Use `double` for decimal values.

```java
double price = 99.99;
```

### Character

Use `char` for a single character.

```java
char grade = 'A';
```

### Boolean

Used for `true` or `false`.

```java
boolean isStudent = true;
```

### String

Used for text.

```java
String name = "Purnith";
```

### Example

```java
class Main {
    public static void main(String[] args) {

        int age = 20;
        double price = 99.99;
        char grade = 'A';
        boolean isStudent = true;
        String name = "Purnith";

        System.out.println(name);
        System.out.println(age);
        System.out.println(price);
        System.out.println(grade);
        System.out.println(isStudent);
    }
}
```

Output:

```text
Purnith
20
99.99
A
true
```

---

# 10. Types of Variables Based on Location

Java commonly has three types of variables based on where they are declared:

### 1. Local Variable

Declared inside a method, constructor, or block.

```java
class Main {
    public static void main(String[] args) {

        int age = 20;  // local variable

        System.out.println(age);
    }
}
```

`age` is a local variable because it is declared inside `main()`.

---

### 2. Instance Variable

Declared inside a class but outside methods.

```java
class Student {

    String name;  // instance variable

    public static void main(String[] args) {

        Student s = new Student();

        s.name = "Purnith";

        System.out.println(s.name);
    }
}
```

`name` belongs to an object of the `Student` class.

---

### 3. Static Variable

Declared using the `static` keyword.

```java
class Student {

    static String college = "Pragati Engineering College";

    public static void main(String[] args) {

        System.out.println(college);
    }
}
```

A static variable belongs to the **class**, rather than to a particular object.

---

# 11. Simple Variable Example

Let's combine everything:

```java
class Main {
    public static void main(String[] args) {

        String name = "Purnith";
        int age = 20;
        int marks = 85;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Marks: " + marks);
    }
}
```

Output:

```text
Name: Purnith
Age: 20
Marks: 85
```

### Why is `+` used here?

In:

```java
"Name: " + name
```

the `+` operator joins text and the value of `name`.

This is called **string concatenation**.

---

# 12. Arithmetic Operations with Variables

We can perform calculations using variables.

```java
class Main {
    public static void main(String[] args) {

        int a = 20;
        int b = 10;

        int addition = a + b;
        int subtraction = a - b;
        int multiplication = a * b;
        int division = a / b;
        int remainder = a % b;

        System.out.println("Addition: " + addition);
        System.out.println("Subtraction: " + subtraction);
        System.out.println("Multiplication: " + multiplication);
        System.out.println("Division: " + division);
        System.out.println("Remainder: " + remainder);
    }
}
```

Output:

```text
Addition: 30
Subtraction: 10
Multiplication: 200
Division: 2
Remainder: 0
```

---

# 13. Quick Revision

### Java

Java is a high-level, object-oriented programming language.

### Print

```java
System.out.println("Hello");
```

### Addition

```java
int result = 10 + 5;
```

### Subtraction

```java
int result = 10 - 5;
```

### Multiplication

```java
int result = 10 * 5;
```

### Division

```java
int result = 10 / 5;
```

### Modulo

```java
int result = 10 % 3;
```

### Variable Declaration

```java
int age;
```

### Variable Initialization

```java
age = 20;
```

### Declaration + Initialization

```java
int age = 20;
```

---

# 14. Important Points to Remember

- Java is **case-sensitive**.
- Every Java statement usually ends with `;`.
- The program execution starts from the `main()` method.
- `int` stores whole numbers.
- `double` stores decimal numbers.
- `char` stores a single character.
- `boolean` stores `true` or `false`.
- `String` stores text.
- `+` can perform addition or string concatenation.
- `%` returns the remainder of a division.
- Variable names should be meaningful.

---

## Beginner Practice

Try writing programs for these:

### 1. Calculate the area of a rectangle

```text
length = 10
width = 5

area = length × width
```

### 2. Calculate the total price

```text
price = 100
quantity = 4

total = price × quantity
```

### 3. Check whether a number is even or odd

Hint:

```java
number % 2
```

### 4. Calculate the average of three numbers

```text
average = (a + b + c) / 3
```

---

## Final Takeaway

The basic structure you should remember is:

```java
class Main {
    public static void main(String[] args) {

        // Declare and initialize variables
        int a = 10;
        int b = 5;

        // Perform an operation
        int result = a + b;

        // Print the result
        System.out.println(result);
    }
}
```

Once you understand **variables + data types + operators + `main()` + `System.out.println()`**, you have a strong foundation for learning the next Java topics such as **if-else, loops, arrays, methods, OOP, and collections**.
