# Conditional Statements in Java

Conditional statements (also known as decision-making statements) allow you to control the flow of execution in a Java program based on boolean conditions (`true` or `false`).

---

## Table of Contents
1. [Overview](#1-overview)
2. [if Statement](#2-if-statement)
3. [if-else Statement](#3-if-else-statement)
4. [if-else-if Ladder](#4-if-else-if-ladder)
5. [Nested if Statement](#5-nested-if-statement)
6. [Ternary Operator (? :)](#6-ternary-operator--)
7. [Switch Statement](#7-switch-statement)
   - [Traditional Switch](#traditional-switch)
   - [Enhanced Switch Expressions (Java 14+)](#enhanced-switch-expressions-java-14)
8. [Logical Operators in Conditions](#8-logical-operators-in-conditions)
9. [Best Practices & Common Pitfalls](#9-best-practices--common-pitfalls)

---

## 1. Overview

| Statement | Purpose |
| :--- | :--- |
| `if` | Executes a block of code only if the condition evaluates to `true`. |
| `if-else` | Executes one block if `true`, and another block if `false`. |
| `if-else-if` | Tests multiple conditions sequentially until one is `true`. |
| `nested if` | An `if` statement inside another `if` block. |
| `Ternary (? :)` | Compact inline shorthand for a simple `if-else` assignment or return. |
| `switch` | Selects one of many code blocks to execute based on an expression value. |

---

## 2. if Statement

The basic `if` statement executes the body only when the boolean condition is `true`.

### Syntax
```java
if (condition) {
    // block of code to execute if condition is true
}
```

### Example
```java
public class IfExample {
    public static void main(String[] args) {
        int age = 20;

        if (age >= 18) {
            System.out.println("You are eligible to vote.");
        }
    }
}
```

**Output:**
```text
You are eligible to vote.
```

---

## 3. if-else Statement

The `if-else` statement provides an alternative path when the condition evaluates to `false`.

### Syntax
```java
if (condition) {
    // code executed if condition is true
} else {
    // code executed if condition is false
}
```

### Example
```java
public class IfElseExample {
    public static void main(String[] args) {
        int number = 15;

        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }
    }
}
```

**Output:**
```text
15 is odd.
```

---

## 4. if-else-if Ladder

Used when you need to check multiple conditions sequentially. Execution stops as soon as one condition evaluates to `true`.

### Syntax
```java
if (condition1) {
    // executed if condition1 is true
} else if (condition2) {
    // executed if condition2 is true
} else if (condition3) {
    // executed if condition3 is true
} else {
    // executed if all conditions are false
}
```

### Example
```java
public class IfElseIfExample {
    public static void main(String[] args) {
        int score = 85;

        if (score >= 90) {
            System.out.println("Grade: A");
        } else if (score >= 80) {
            System.out.println("Grade: B");
        } else if (score >= 70) {
            System.out.println("Grade: C");
        } else if (score >= 60) {
            System.out.println("Grade: D");
        } else {
            System.out.println("Grade: F");
        }
    }
}
```

**Output:**
```text
Grade: B
```

---

## 5. Nested if Statement

An `if` or `if-else` block placed inside another `if` or `else` block.

### Syntax
```java
if (condition1) {
    if (condition2) {
        // executed if both condition1 and condition2 are true
    }
}
```

### Example
```java
public class NestedIfExample {
    public static void main(String[] args) {
        int age = 22;
        boolean hasValidID = true;

        if (age >= 18) {
            if (hasValidID) {
                System.out.println("Entry permitted.");
            } else {
                System.out.println("ID verification failed.");
            }
        } else {
            System.out.println("Underage: Entry denied.");
        }
    }
}
```

**Output:**
```text
Entry permitted.
```

---

## 6. Ternary Operator (`? :`)

A concise shorthand for simple `if-else` logic, often used in variable assignments or return statements.

### Syntax
```java
variable = (condition) ? expressionIfTrue : expressionIfFalse;
```

### Example
```java
public class TernaryExample {
    public static void main(String[] args) {
        int number = 7;
        
        String result = (number % 2 == 0) ? "Even" : "Odd";
        System.out.println(number + " is " + result);

        int max = (10 > 20) ? 10 : 20;
        System.out.println("Max value is: " + max);
    }
}
```

**Output:**
```text
7 is Odd
Max value is: 20
```

---

## 7. Switch Statement

The `switch` statement evaluates an expression and executes matching `case` blocks. Supported data types:
- `byte`, `short`, `char`, `int` (and their wrapper classes)
- `String` (since Java 7)
- `enum` types

### Traditional Switch

In traditional switch, each case requires a `break` statement to prevent fall-through.

```java
public class TraditionalSwitchExample {
    public static void main(String[] args) {
        int day = 3;
        String dayName;

        switch (day) {
            case 1:
                dayName = "Monday";
                break;
            case 2:
                dayName = "Tuesday";
                break;
            case 3:
                dayName = "Wednesday";
                break;
            case 4:
                dayName = "Thursday";
                break;
            case 5:
                dayName = "Friday";
                break;
            case 6:
                dayName = "Saturday";
                break;
            case 7:
                dayName = "Sunday";
                break;
            default:
                dayName = "Invalid day";
                break;
        }

        System.out.println("Day " + day + " is " + dayName);
    }
}
```

**Output:**
```text
Day 3 is Wednesday
```

---

### Enhanced Switch Expressions (Java 14+)

Modern Java allows arrow `->` syntax, eliminates fall-through bugs, and allows returning values directly.

```java
public class EnhancedSwitchExample {
    public static void main(String[] args) {
        String day = "SATURDAY";

        // Switch expression returning a value
        String dayType = switch (day) {
            case "MONDAY", "TUESDAY", "WEDNESDAY", "THURSDAY", "FRIDAY" -> "Weekday";
            case "SATURDAY", "SUNDAY" -> "Weekend";
            default -> {
                System.out.println("Validating unknown input...");
                yield "Unknown";
            }
        };

        System.out.println(day + " is a " + dayType);
    }
}
```

**Output:**
```text
SATURDAY is a Weekend
```

---

## 8. Logical Operators in Conditions

Combine multiple conditions inside conditional statements using logical operators:

| Operator | Name | Description | Example |
| :--- | :--- | :--- | :--- |
| `&&` | Logical AND (Short-circuit) | `true` only if both operands are `true` | `if (age >= 18 && hasTicket)` |
| `\|\|` | Logical OR (Short-circuit) | `true` if at least one operand is `true` | `if (isStudent \|\| isSenior)` |
| `!` | Logical NOT | Inverts the boolean value | `if (!isLoggedIn)` |

### Short-Circuit Evaluation Example
```java
public class ShortCircuitExample {
    public static void main(String[] args) {
        String text = null;

        // text != null is evaluated first.
        // If false, text.length() is skipped, avoiding NullPointerException.
        if (text != null && text.length() > 0) {
            System.out.println("Text is valid: " + text);
        } else {
            System.out.println("Text is null or empty.");
        }
    }
}
```

**Output:**
```text
Text is null or empty.
```

---

## 9. Best Practices & Common Pitfalls

### 1. Comparing Strings: Always use `.equals()`, not `==`
- `==` checks reference equality (memory location).
- `.equals()` checks value equality.

```java
// ❌ Avoid
if (role == "ADMIN") { ... }

// ✅ Correct
if ("ADMIN".equals(role)) { ... } // Prevents NullPointerException if role is null
```

### 2. Avoid Redundant Boolean Comparisons
```java
// ❌ Avoid
if (isActive == true) { ... }

// ✅ Clean & Idiomatic
if (isActive) { ... }
if (!isActive) { ... }
```

### 3. Beware of Accidental Assignment in `if`
```java
boolean flag = false;

// ❌ Accidental assignment (assigns true and evaluates to true)
if (flag = true) { ... }

// ✅ Comparison or direct check
if (flag) { ... }
```

### 4. Always use Curly Braces `{}`
Even for single-line statements, always use curly braces to prevent logic bugs when adding lines later.

```java
// ❌ Risky
if (isValid)
    doTask();
    logTask(); // Will execute unconditionally!

// ✅ Safe
if (isValid) {
    doTask();
    logTask();
}
```
