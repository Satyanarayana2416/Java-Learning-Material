# Relational Operators in Java

Relational operators (also known as **comparison operators**) are used to check the relationship between two operands. They compare values and always return a `boolean` result: either `true` or `false`.

---

## Table of Contents
1. [Overview Table](#1-overview-table)
2. [Detailed Operator Breakdown](#2-detailed-operator-breakdown)
   - [Equal To (`==`)](#equal-to-)
   - [Not Equal To (`!=`)](#not-equal-to-)
   - [Greater Than (`>`)](#greater-than-)
   - [Less Than (`<`)](#less-than-)
   - [Greater Than or Equal To (`>=`)](#greater-than-or-equal-to-)
   - [Less Than or Equal To (`<=`)](#less-than-or-equal-to-)
3. [Comprehensive Code Example](#3-comprehensive-code-example)
4. [Relational Operators with Different Data Types](#4-relational-operators-with-different-data-types)
   - [Primitive Numeric Types](#primitive-numeric-types)
   - [Character Comparisons (`char`)](#character-comparisons-char)
   - [Floating-Point Comparisons (`float` & `double`)](#floating-point-comparisons-float--double)
5. [Primitives vs. Objects: `==` vs `.equals()`](#5-primitives-vs-objects--vs-equals)
6. [Using Relational Operators in Control Flow](#6-using-relational-operators-in-control-flow)
7. [Best Practices & Common Pitfalls](#7-best-practices--common-pitfalls)

---

## 1. Overview Table

| Operator | Name | Description | Example (`a = 10, b = 20`) | Result |
| :---: | :--- | :--- | :---: | :---: |
| `==` | Equal to | Checks if two values are equal | `a == b` | `false` |
| `!=` | Not equal to | Checks if two values are NOT equal | `a != b` | `true` |
| `>` | Greater than | Checks if left operand is strictly greater | `a > b` | `false` |
| `<` | Less than | Checks if left operand is strictly smaller | `a < b` | `true` |
| `>=` | Greater than or equal to | Checks if left operand is greater or equal | `a >= 10` | `true` |
| `<=` | Less than or equal to | Checks if left operand is less or equal | `b <= 20` | `true` |

---

## 2. Detailed Operator Breakdown

### Equal To (`==`)
Returns `true` if both operands have the same value.
```java
int x = 5;
int y = 5;
System.out.println(x == y); // true
```

### Not Equal To (`!=`)
Returns `true` if operands have different values.
```java
int x = 5;
int y = 10;
System.out.println(x != y); // true
```

### Greater Than (`>`)
Returns `true` if the left operand is strictly greater than the right operand.
```java
int x = 15;
int y = 10;
System.out.println(x > y); // true
```

### Less Than (`<`)
Returns `true` if the left operand is strictly smaller than the right operand.
```java
int x = 8;
int y = 12;
System.out.println(x < y); // true
```

### Greater Than or Equal To (`>=`)
Returns `true` if the left operand is greater than OR equal to the right operand.
```java
int score = 50;
System.out.println(score >= 50); // true
```

### Less Than or Equal To (`<=`)
Returns `true` if the left operand is less than OR equal to the right operand.
```java
int speed = 60;
System.out.println(speed <= 60); // true
```

---

## 3. Comprehensive Code Example

```java
public class RelationalOperatorsDemo {
    public static void main(String[] args) {
        int a = 25;
        int b = 15;

        System.out.println("a = " + a + ", b = " + b);
        System.out.println("-------------------------");
        System.out.println("a == b  : " + (a == b));   // false
        System.out.println("a != b  : " + (a != b));   // true
        System.out.println("a > b   : " + (a > b));    // true
        System.out.println("a < b   : " + (a < b));    // false
        System.out.println("a >= b  : " + (a >= b));   // true
        System.out.println("a <= b  : " + (a <= b));   // false
    }
}
```

**Output:**
```text
a = 25, b = 15
-------------------------
a == b  : false
a != b  : true
a > b   : true
a < b   : false
a >= b  : true
a <= b  : false
```

---

## 4. Relational Operators with Different Data Types

### Primitive Numeric Types
Operands of different numeric types are automatically widened before comparison:
```java
int intVal = 10;
double doubleVal = 10.0;

// intVal (10) is promoted to double (10.0)
System.out.println(intVal == doubleVal); // true
```

### Character Comparisons (`char`)
Characters in Java are stored as Unicode numerical values (ASCII values), so they can be compared with relational operators:
```java
char ch1 = 'A'; // Unicode value 65
char ch2 = 'B'; // Unicode value 66

System.out.println(ch1 < ch2);  // true (65 < 66)
System.out.println('a' > 'A');  // true (97 > 65)
```

### Floating-Point Comparisons (`float` & `double`)
Due to floating-point rounding errors in binary representations, comparing floating-point numbers with `==` can be risky.

```java
double a = 0.1 + 0.2;
double b = 0.3;

System.out.println(a == b); // false! (a is 0.30000000000000004)

// ✅ Best practice: Compare with a small tolerance (epsilon)
double epsilon = 1e-9;
boolean isEqual = Math.abs(a - b) < epsilon;
System.out.println("Practically equal: " + isEqual); // true
```

---

## 5. Primitives vs. Objects: `==` vs `.equals()`

> [!IMPORTANT]
> - `==` on **primitives** compares their **values**.
> - `==` on **objects/references** compares their **memory addresses (references)**.
> - `.equals()` compares the **actual content/values** of objects.

### Example with Strings:
```java
public class StringComparison {
    public static void main(String[] args) {
        String s1 = new String("Java");
        String s2 = new String("Java");
        String s3 = "Java";
        String s4 = "Java";

        // Reference comparison
        System.out.println(s1 == s2);      // false (different objects in heap)
        System.out.println(s3 == s4);      // true (same string pool reference)

        // Content/Value comparison
        System.out.println(s1.equals(s2)); // true (same content)
    }
}
```

---

## 6. Using Relational Operators in Control Flow

Relational operators are the foundation of decision making and looping in Java.

### In `if-else` Conditions
```java
int temperature = 32;

if (temperature > 30) {
    System.out.println("It's hot outside.");
} else if (temperature >= 15) {
    System.out.println("The weather is pleasant.");
} else {
    System.out.println("It's cold outside.");
}
```

### In `while` and `for` Loops
```java
// Using <= in a loop condition
for (int i = 1; i <= 5; i++) {
    System.out.print(i + " ");
}
// Output: 1 2 3 4 5
```

---

## 7. Best Practices & Common Pitfalls

### 1. Don't confuse `=` (Assignment) with `==` (Equality)
```java
int count = 5;

// ❌ Syntax Error for non-boolean types:
// if (count = 10) { ... }

// ✅ Correct Comparison:
if (count == 10) {
    System.out.println("Count is 10");
}
```

### 2. Watch out for Wrapper Object Caching (`Integer`, `Long`, etc.)
Java caches `Integer` objects between `-128` and `127`.
```java
Integer num1 = 100;
Integer num2 = 100;
System.out.println(num1 == num2); // true (cached)

Integer num3 = 200;
Integer num4 = 200;
System.out.println(num3 == num4); // false (outside cache, different objects!)
System.out.println(num3.equals(num4)); // true (always use .equals() for objects)
```

### 3. Chaining Comparisons
In math, you can write `10 < x < 20`. In Java, you must split them with logical operators:
```java
int x = 15;

// ❌ Syntax Error in Java:
// if (10 < x < 20) { ... }

// ✅ Correct:
if (10 < x && x < 20) {
    System.out.println("x is between 10 and 20");
}
```
