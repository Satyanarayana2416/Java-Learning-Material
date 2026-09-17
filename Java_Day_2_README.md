# Java 20 Days Challenge — Day 2 🚀

## Data Types, Packages, Input/Output & Type Conversion

Welcome to **Day 2 of the Java learning journey!** 👋

Today we will learn how Java stores different kinds of data, how to take input from users, how packages work, and how to convert one data type into another.

---

## 1. Data Types

A **data type** tells Java what kind of value a variable can store.

```java
int age = 20;
```

Here:
- `int` → data type
- `age` → variable
- `20` → value

Java data types are mainly divided into:

```text
Data Types
│
├── Primitive Data Types
│
└── Non-Primitive Data Types
```

---

## 2. Primitive Data Types

Primitive data types are the **basic built-in data types** provided by Java.

Java has **8 primitive data types**:

| Data Type | Used For | Example |
|---|---|---|
| `byte` | Small whole numbers | `byte age = 20;` |
| `short` | Whole numbers | `short year = 2026;` |
| `int` | Whole numbers | `int marks = 90;` |
| `long` | Large whole numbers | `long population = 1400000000L;` |
| `float` | Decimal numbers | `float price = 99.5f;` |
| `double` | Decimal numbers | `double pi = 3.14159;` |
| `char` | Single character | `char grade = 'A';` |
| `boolean` | True or false | `boolean passed = true;` |

### Example

```java
class Main {
    public static void main(String[] args) {

        byte age = 20;
        short year = 2026;
        int marks = 90;
        long population = 1400000000L;
        float price = 99.5f;
        double pi = 3.14159;
        char grade = 'A';
        boolean passed = true;

        System.out.println(age);
        System.out.println(year);
        System.out.println(marks);
        System.out.println(population);
        System.out.println(price);
        System.out.println(pi);
        System.out.println(grade);
        System.out.println(passed);
    }
}
```

### Important

For `long`, use `L`:

```java
long number = 10000000000L;
```

For `float`, use `f`:

```java
float value = 10.5f;
```

---

## 3. Non-Primitive Data Types

Non-primitive data types are also called **reference types**.

Examples:

- `String`
- Arrays
- Classes
- Objects
- Interfaces

### String Example

```java
String name = "Purnith";

System.out.println(name);
```

Output:

```text
Purnith
```

### Array Example

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers[0]);
```

Output:

```text
10
```

### Easy Difference

```text
Primitive     → Basic value
Non-Primitive → Reference to an object
```

---

## 4. Primitive vs Non-Primitive

| Primitive | Non-Primitive |
|---|---|
| Basic data types | Reference types |
| 8 types | Many types |
| `int`, `double`, `char`, etc. | `String`, arrays, classes, etc. |
| Stores a value | Refers to an object |
| Fixed-size primitive values | Can represent objects and references |

---

## 5. Packages

A **package** in Java is used to organize related classes and interfaces.

Think of a package like a **folder** on your computer.

```text
Package
   │
   ├── Class 1
   ├── Class 2
   └── Class 3
```

Java provides many built-in packages.

For example:

```java
java.util
```

contains useful classes such as:

- `Scanner`
- `ArrayList`
- `HashMap`
- `HashSet`

---

## 6. Importing a Package

We can import accessible classes from a package using `*`.

```java
import java.util.*;
```

### Example

```java
import java.util.*;

class Main {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = input.nextLine();

        System.out.println("Hello " + name);
    }
}
```

Output:

```text
Enter your name: Purnith
Hello Purnith
```

---

## 7. Importing a Class

Instead of importing the complete package, we can import only the class we need.

```java
import java.util.Scanner;
```

### Example

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("Enter your age: ");
        int age = input.nextInt();

        System.out.println("Your age is " + age);
    }
}
```

Output:

```text
Enter your age: 20
Your age is 20
```

### Difference

Import complete package:

```java
import java.util.*;
```

Import one class:

```java
import java.util.Scanner;
```

---

## 8. Input and Output

A Java program commonly needs to:

1. Take input from the user.
2. Process the input.
3. Display output.

```text
User Input
    ↓
Java Program
    ↓
Output
```

---

## 9. Reading User Input Using Scanner

The `Scanner` class is commonly used to read input from the keyboard.

First, import it:

```java
import java.util.Scanner;
```

Then create a Scanner object:

```java
Scanner input = new Scanner(System.in);
```

### Reading an Integer

Use:

```java
nextInt()
```

Example:

```java
int age = input.nextInt();
```

### Reading a Decimal

Use:

```java
double price = input.nextDouble();
```

### Reading One Word

Use:

```java
String name = input.next();
```

### Reading a Complete Line

Use:

```java
String fullName = input.nextLine();
```

If the user enters:

```text
Purnith Kumar
```

`nextLine()` reads the complete line.

---

## 10. Scanner Input Methods

| Method | Reads |
|---|---|
| `nextInt()` | Integer |
| `nextDouble()` | Double |
| `nextFloat()` | Float |
| `nextLong()` | Long |
| `next()` | One word |
| `nextLine()` | Complete line |
| `nextBoolean()` | `true` or `false` |
| `next().charAt(0)` | One character |

### Complete Example

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = input.nextLine();

        System.out.print("Enter your age: ");
        int age = input.nextInt();

        System.out.print("Enter your percentage: ");
        double percentage = input.nextDouble();

        System.out.println("\n--- Student Details ---");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Percentage: " + percentage);

        input.close();
    }
}
```

Example Output:

```text
Enter your name: Purnith
Enter your age: 20
Enter your percentage: 85.5

--- Student Details ---
Name: Purnith
Age: 20
Percentage: 85.5
```

---

## 11. Printing Output

Java provides two commonly used methods.

### `System.out.print()`

Prints without moving to a new line.

```java
System.out.print("Hello ");
System.out.print("Java");
```

Output:

```text
Hello Java
```

### `System.out.println()`

Prints and moves to the next line.

```java
System.out.println("Hello");
System.out.println("Java");
```

Output:

```text
Hello
Java
```

### Easy Difference

```text
print   → Same line
println → New line
```

---

## 12. Checking the Data Type

For **non-primitive/reference types**, we can use `getClass()`.

### Non-Primitive Example

```java
String name = "Purnith";

System.out.println(name.getClass().getSimpleName());
```

Output:

```text
String
```

Another example:

```java
Integer number = 100;

System.out.println(number.getClass().getSimpleName());
```

Output:

```text
Integer
```

### What about primitives?

Primitive variables such as `int`, `double`, and `char` do not have `getClass()` methods.

For example, this is not valid:

```java
int age = 20;

// age.getClass();  // ❌ Not allowed
```

Instead, Java provides **wrapper classes**:

| Primitive | Wrapper Class |
|---|---|
| `byte` | `Byte` |
| `short` | `Short` |
| `int` | `Integer` |
| `long` | `Long` |
| `float` | `Float` |
| `double` | `Double` |
| `char` | `Character` |
| `boolean` | `Boolean` |

Example:

```java
int age = 20;

Integer boxedAge = age;

System.out.println(boxedAge.getClass().getSimpleName());
```

Output:

```text
Integer
```

The automatic conversion from `int` to `Integer` is called **autoboxing**.

---

## 13. Type Conversion and Type Casting

**Type conversion** means changing a value from one data type to another.

For example:

```text
int → double
```

or:

```text
double → int
```

There are two important forms:

```text
Type Conversion
│
├── Implicit Type Conversion
│
└── Explicit Type Conversion (Type Casting)
```

---

## 14. Implicit Type Conversion

Implicit conversion happens **automatically** when Java converts a compatible smaller numeric type into a larger numeric type.

Example:

```java
int number = 10;

double value = number;

System.out.println(value);
```

Output:

```text
10.0
```

Java automatically performs:

```text
int → double
```

This is also called **widening conversion**.

### Example

```java
int marks = 90;

long bigMarks = marks;
double decimalMarks = marks;

System.out.println(bigMarks);
System.out.println(decimalMarks);
```

Output:

```text
90
90.0
```

---

## 15. Explicit Type Conversion (Type Casting)

Sometimes we need to manually tell Java to convert a value.

Syntax:

```java
targetType variable = (targetType) value;
```

### Example

```java
double price = 99.99;

int result = (int) price;

System.out.println(result);
```

Output:

```text
99
```

The decimal part is removed:

```text
99.99
 ↓
 99
```

This is called **explicit type casting** or **narrowing conversion**.

---

## 16. Widening vs Narrowing

### Widening

Usually automatic:

```java
int a = 10;
double b = a;
```

```text
int → double
```

### Narrowing

Usually requires casting:

```java
double a = 10.99;
int b = (int) a;
```

```text
double → int
```

### Easy Way to Remember

```text
Smaller → Larger
Automatic → Widening

Larger → Smaller
Manual cast → Narrowing
```

---

## 17. Type Conversion Using Methods

Java also provides methods for converting values.

These are especially useful when converting **Strings into numbers**.

### String → Integer

Use:

```java
Integer.parseInt()
```

Example:

```java
String number = "100";

int value = Integer.parseInt(number);

System.out.println(value + 50);
```

Output:

```text
150
```

---

### String → Double

Use:

```java
Double.parseDouble()
```

Example:

```java
String price = "99.50";

double value = Double.parseDouble(price);

System.out.println(value);
```

Output:

```text
99.5
```

---

### String → Float

```java
String value = "10.5";

float number = Float.parseFloat(value);

System.out.println(number);
```

---

### String → Long

```java
String value = "100000";

long number = Long.parseLong(value);

System.out.println(number);
```

---

## 18. Number → String

We can convert numbers into Strings using:

```java
String.valueOf()
```

Example:

```java
int number = 100;

String text = String.valueOf(number);

System.out.println(text);
```

Another method:

```java
int number = 100;

String text = Integer.toString(number);

System.out.println(text);
```

Now:

```text
number → int
text   → String
```

---

## 19. Complete Type Conversion Example

```java
class Main {
    public static void main(String[] args) {

        // Implicit conversion
        int number = 10;
        double decimalNumber = number;

        System.out.println("Implicit conversion: " + decimalNumber);

        // Explicit casting
        double price = 99.99;
        int wholePrice = (int) price;

        System.out.println("Explicit casting: " + wholePrice);

        // String to int
        String textNumber = "50";
        int convertedNumber = Integer.parseInt(textNumber);

        System.out.println("String to int: " + convertedNumber);

        // int to String
        int marks = 90;
        String textMarks = String.valueOf(marks);

        System.out.println("int to String: " + textMarks);
    }
}
```

Output:

```text
Implicit conversion: 10.0
Explicit casting: 99
String to int: 50
int to String: 90
```

---

## 20. Quick Revision

### Primitive Data Types

```java
int age = 20;
double price = 99.99;
char grade = 'A';
boolean passed = true;
```

### Non-Primitive

```java
String name = "Purnith";
int[] numbers = {10, 20, 30};
```

### Import a Class

```java
import java.util.Scanner;
```

### Import a Package

```java
import java.util.*;
```

### Scanner

```java
Scanner input = new Scanner(System.in);
```

### Read Integer

```java
int age = input.nextInt();
```

### Read String

```java
String name = input.nextLine();
```

### Print

```java
System.out.println("Hello");
```

### Implicit Conversion

```java
int a = 10;
double b = a;
```

### Explicit Casting

```java
double a = 10.5;
int b = (int) a;
```

### String → int

```java
int number = Integer.parseInt("100");
```

### String → double

```java
double number = Double.parseDouble("10.5");
```

### Number → String

```java
String text = String.valueOf(100);
```

---

## 21. Day 2 Practice Programs 🧑‍💻

Try solving these without looking at the examples above.

### Practice 1 — Student Details

Take the following from the user:

- Name
- Age
- Marks

Then print all the details.

### Practice 2 — Addition

Take two numbers from the user and print their sum.

Example:

```text
Enter first number: 10
Enter second number: 20

Sum: 30
```

### Practice 3 — Type Casting

Create:

```java
double number = 25.75;
```

Convert it into an `int`.

Expected output:

```text
25
```

### Practice 4 — String Conversion

Convert:

```java
String number = "500";
```

into an integer and add `100`.

Expected output:

```text
600
```

### Practice 5 — User Input + Conversion

Take a number as a String from the user:

```text
Enter a number: 100
```

Convert it into an integer and multiply it by `2`.

Expected output:

```text
200
```

---

## 🎯 Day 2 Takeaway

Today you learned:

```text
Data Types
    ↓
Primitive & Non-Primitive
    ↓
Packages
    ↓
Importing Classes
    ↓
Scanner Input
    ↓
Printing Output
    ↓
Checking Types
    ↓
Type Conversion
    ↓
Type Casting
    ↓
Conversion Using Methods
```

These concepts are important because almost every Java program uses **data types, input, output, and type conversion**.

---

## Day 2 Completed ✅

**Java Challenge Progress: 2/20 Days** 🚀
