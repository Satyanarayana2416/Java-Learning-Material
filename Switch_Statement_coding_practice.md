# Java Switch Statement Coding Practice

Switch statements are used when we want to check one variable against many possible values. They make code cleaner than a long chain of `if-else` statements.

In this practice file, we will learn and try:

- Weekday
- Days in a month
- Vowel or Consonant
- Shapes

---

## 1. Weekday

### Problem
Write a Java program to print the day name for a number from 1 to 7.

### Code
```java
import java.util.Scanner;

public class WeekdaySwitch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number from 1 to 7: ");
        int day = sc.nextInt();

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            case 3:
                System.out.println("Wednesday");
                break;
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day number. Please enter a number from 1 to 7.");
        }

        sc.close();
    }
}
```

### Sample Output
```text
Enter a number from 1 to 7: 5
Friday
```

---

## 2. Days in a Month

### Problem
Write a Java program to display the number of days in a month.

### Code
```java
import java.util.Scanner;

public class DaysInMonthSwitch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter month number (1-12): ");
        int month = sc.nextInt();

        switch (month) {
            case 1:
            case 3:
            case 5:
            case 7:
            case 8:
            case 10:
            case 12:
                System.out.println("This month has 31 days.");
                break;
            case 4:
            case 6:
            case 9:
            case 11:
                System.out.println("This month has 30 days.");
                break;
            case 2:
                System.out.println("February has 28 days in a common year and 29 days in a leap year.");
                break;
            default:
                System.out.println("Invalid month number. Please enter a number from 1 to 12.");
        }

        sc.close();
    }
}
```

### Sample Output
```text
Enter month number (1-12): 4
This month has 30 days.
```

---

## 3. Vowel or Consonant

### Problem
Write a Java program to check whether a character is a vowel or a consonant.

### Code
```java
import java.util.Scanner;

public class VowelConsonantSwitch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a character: ");
        char ch = sc.next().charAt(0);

        switch (Character.toLowerCase(ch)) {
            case 'a':
            case 'e':
            case 'i':
            case 'o':
            case 'u':
                System.out.println(ch + " is a vowel.");
                break;
            default:
                if ((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z')) {
                    System.out.println(ch + " is a consonant.");
                } else {
                    System.out.println("Invalid input. Please enter a letter.");
                }
        }

        sc.close();
    }
}
```

### Sample Output
```text
Enter a character: e
 e is a vowel.
```

---

## 4. Shapes

### Problem
Write a Java program to calculate the area of different shapes using a `switch` statement.

### Code
```java
import java.util.Scanner;

public class ShapeAreaSwitch {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Choose a shape:");
        System.out.println("1. Circle");
        System.out.println("2. Rectangle");
        System.out.println("3. Triangle");

        int choice = sc.nextInt();

        switch (choice) {
            case 1:
                System.out.print("Enter radius: ");
                double r = sc.nextDouble();
                double circleArea = 3.14 * r * r;
                System.out.println("Area of Circle = " + circleArea);
                break;

            case 2:
                System.out.print("Enter length: ");
                double length = sc.nextDouble();
                System.out.print("Enter width: ");
                double width = sc.nextDouble();
                double rectangleArea = length * width;
                System.out.println("Area of Rectangle = " + rectangleArea);
                break;

            case 3:
                System.out.print("Enter base: ");
                double base = sc.nextDouble();
                System.out.print("Enter height: ");
                double height = sc.nextDouble();
                double triangleArea = 0.5 * base * height;
                System.out.println("Area of Triangle = " + triangleArea);
                break;

            default:
                System.out.println("Invalid choice.");
        }

        sc.close();
    }
}
```

### Sample Output
```text
Choose a shape:
1. Circle
2. Rectangle
3. Triangle
2
Enter length: 6
Enter width: 4
Area of Rectangle = 24.0
```

---

## Quick Notes

- `switch` is best when there are multiple fixed choices.
- Every `case` should usually end with `break;`.
- `default` handles all values not matched by any case.

---

## Practice Questions

Try these on your own:

1. Write a Java program using `switch` to display the month name from a number.
2. Write a switch program to check if a number is even or odd.
3. Create a menu-driven switch program for calculator operations: add, subtract, multiply, divide.
4. Write a switch program to print the grade based on marks.

---

## Summary

The `switch` statement helps us write cleaner and simpler code when many conditions are checked. It is very useful for programs like:

- day names
- month names
- menu selection
- grade checking
- vowel/consonant checks
- shape selection

This is a great beginner-level Java concept for practicing logic building.
