# Java Coding Practice: Basic Programs

This document contains 10 fundamental Java practice programs covering basic arithmetic, geometric calculations, unit conversions, number operations, and string manipulations.

---

## Table of Contents
1. [Basic Arithmetic](#1-basic-arithmetic)
2. [Area of Rectangle](#2-area-of-rectangle)
3. [Perimeter of Rectangle](#3-perimeter-of-rectangle)
4. [Kilometers to Meters](#4-kilometers-to-meters)
5. [Length of String](#5-length-of-string)
6. [First Three Characters](#6-first-three-characters)
7. [First & Last Digits of a Number](#7-first--last-digits-of-a-number)
8. [String Repetition](#8-string-repetition)
9. [Convert Days to Years, Weeks & Days](#9-convert-days-to-years-weeks--days)
10. [Half of a String](#10-half-of-a-string)

---

## 1. Basic Arithmetic

**Problem Statement:**  
Write a Java program to perform and display addition, subtraction, multiplication, division, and modulus operations on two numbers.

### Code
```java
import java.util.Scanner;

public class BasicArithmetic {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        double num1 = sc.nextDouble();

        System.out.print("Enter second number: ");
        double num2 = sc.nextDouble();

        System.out.println("\n--- Arithmetic Results ---");
        System.out.println("Addition (num1 + num2)       : " + (num1 + num2));
        System.out.println("Subtraction (num1 - num2)    : " + (num1 - num2));
        System.out.println("Multiplication (num1 * num2) : " + (num1 * num2));

        if (num2 != 0) {
            System.out.println("Division (num1 / num2)       : " + (num1 / num2));
            System.out.println("Modulus (num1 % num2)        : " + (num1 % num2));
        } else {
            System.out.println("Division & Modulus by zero are undefined.");
        }

        sc.close();
    }
}
```

### Sample Output
```text
Enter first number: 20
Enter second number: 6

--- Arithmetic Results ---
Addition (num1 + num2)       : 26.0
Subtraction (num1 - num2)    : 14.0
Multiplication (num1 * num2) : 120.0
Division (num1 / num2)       : 3.3333333333333335
Modulus (num1 % num2)        : 2.0
```

---

## 2. Area of Rectangle

**Problem Statement:**  
Write a Java program to calculate the area of a rectangle given its length and width.

$$\text{Area} = \text{length} \times \text{width}$$

### Code
```java
import java.util.Scanner;

public class AreaOfRectangle {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter length: ");
        double length = sc.nextDouble();

        System.out.print("Enter width: ");
        double width = sc.nextDouble();

        double area = length * width;

        System.out.println("Area of Rectangle: " + area);

        sc.close();
    }
}
```

### Sample Output
```text
Enter length: 12.5
Enter width: 4.0
Area of Rectangle: 50.0
```

---

## 3. Perimeter of Rectangle

**Problem Statement:**  
Write a Java program to calculate the perimeter of a rectangle given its length and width.

$$\text{Perimeter} = 2 \times (\text{length} + \text{width})$$

### Code
```java
import java.util.Scanner;

public class PerimeterOfRectangle {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter length: ");
        double length = sc.nextDouble();

        System.out.print("Enter width: ");
        double width = sc.nextDouble();

        double perimeter = 2 * (length + width);

        System.out.println("Perimeter of Rectangle: " + perimeter);

        sc.close();
    }
}
```

### Sample Output
```text
Enter length: 8.5
Enter width: 3.5
Perimeter of Rectangle: 24.0
```

---

## 4. Kilometers to Meters

**Problem Statement:**  
Write a Java program to convert distance in kilometers (km) to meters (m).

$$1 \text{ km} = 1000 \text{ meters}$$

### Code
```java
import java.util.Scanner;

public class KmToMeters {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter distance in kilometers: ");
        double km = sc.nextDouble();

        double meters = km * 1000;

        System.out.println(km + " km is equal to " + meters + " meters.");

        sc.close();
    }
}
```

### Sample Output
```text
Enter distance in kilometers: 5.75
5.75 km is equal to 5750.0 meters.
```

---

## 5. Length of String

**Problem Statement:**  
Write a Java program to read a string from the user and find its total length (number of characters) using `.length()`.

### Code
```java
import java.util.Scanner;

public class StringLength {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String text = sc.nextLine();

        int length = text.length();

        System.out.println("The string \"" + text + "\" has " + length + " characters.");

        sc.close();
    }
}
```

### Sample Output
```text
Enter a string: Java Programming
The string "Java Programming" has 16 characters.
```

---

## 6. First Three Characters

**Problem Statement:**  
Write a Java program to extract and display the first 3 characters of a string using `.substring()`.

### Code
```java
import java.util.Scanner;

public class FirstThreeChars {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String text = sc.nextLine();

        if (text.length() >= 3) {
            String firstThree = text.substring(0, 3);
            System.out.println("First 3 characters: " + firstThree);
        } else {
            System.out.println("The string is too short: " + text);
        }

        sc.close();
    }
}
```

### Sample Output
```text
Enter a string: Developer
First 3 characters: Dev
```

---

## 7. First & Last Digits of a Number

**Problem Statement:**  
Write a Java program to find the first digit and the last digit of a given integer.

### Code
```java
import java.util.Scanner;

public class FirstAndLastDigit {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter an integer: ");
        int num = sc.nextInt();

        int temp = Math.abs(num); // Handle negative numbers

        // Last digit is remainder when divided by 10
        int lastDigit = temp % 10;

        // First digit is obtained by repeatedly dividing by 10
        int firstDigit = temp;
        while (firstDigit >= 10) {
            firstDigit /= 10;
        }

        System.out.println("Given Number: " + num);
        System.out.println("First Digit : " + firstDigit);
        System.out.println("Last Digit  : " + lastDigit);

        sc.close();
    }
}
```

### Sample Output
```text
Enter an integer: 7492
Given Number: 7492
First Digit : 7
Last Digit  : 2
```

---

## 8. String Repetition

**Problem Statement:**  
Write a Java program to repeat a given string $N$ times.

### Code
```java
import java.util.Scanner;

public class StringRepetition {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        System.out.print("Enter number of repetitions: ");
        int count = sc.nextInt();

        // Method 1: Using Java 11+ .repeat()
        String repeatedJava11 = str.repeat(count);
        System.out.println("\nResult (using repeat): " + repeatedJava11);

        // Method 2: Using StringBuilder Loop (Compatible with all Java versions)
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < count; i++) {
            sb.append(str);
        }
        System.out.println("Result (using loop)  : " + sb.toString());

        sc.close();
    }
}
```

### Sample Output
```text
Enter a string: Java!
Enter number of repetitions: 4

Result (using repeat): Java!Java!Java!Java!
Result (using loop)  : Java!Java!Java!Java!
```

---

## 9. Convert Days to Years, Weeks & Days

**Problem Statement:**  
Write a Java program to convert a total number of days into equivalent years, weeks, and days (assuming 1 year = 365 days, 1 week = 7 days).

### Code
```java
import java.util.Scanner;

public class DaysConverter {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter total number of days: ");
        int totalDays = sc.nextInt();

        int years = totalDays / 365;
        int remainingDaysAfterYears = totalDays % 365;

        int weeks = remainingDaysAfterYears / 7;
        int days = remainingDaysAfterYears % 7;

        System.out.println("\n" + totalDays + " days is equivalent to:");
        System.out.println(years + " Year(s), " + weeks + " Week(s), and " + days + " Day(s).");

        sc.close();
    }
}
```

### Sample Output
```text
Enter total number of days: 400

400 days is equivalent to:
1 Year(s), 5 Week(s), and 0 Day(s).
```

---

## 10. Half of a String

**Problem Statement:**  
Write a Java program to print the first half of an input string.

### Code
```java
import java.util.Scanner;

public class HalfString {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String text = sc.nextLine();

        int halfLength = text.length() / 2;
        String firstHalf = text.substring(0, halfLength);

        System.out.println("Original String : " + text);
        System.out.println("First Half      : " + firstHalf);

        sc.close();
    }
}
```

### Sample Output
```text
Enter a string: HelloWorld
Original String : HelloWorld
First Half      : Hello
```
