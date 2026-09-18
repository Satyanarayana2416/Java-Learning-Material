# Java 20 Days Challenge — Day 3 🚀

## Strings in Java

Welcome to **Day 3** of the Java learning journey! 👋

Today we will learn **Strings in Java** from the basics to practical and interview-relevant concepts.

### Topics Covered

- What is a String?
- Creating Strings
- String Literal
- String Object
- String Indexing
- `length()`
- `charAt()`
- `toUpperCase()` / `toLowerCase()`
- `trim()` / `strip()`
- `isEmpty()` / `isBlank()`
- `equals()` / `equalsIgnoreCase()`
- `==` vs `equals()`
- String Concatenation
- `concat()`
- `contains()`
- `startsWith()` / `endsWith()`
- `indexOf()` / `lastIndexOf()`
- `substring()`
- `replace()` / `replaceAll()`
- `split()`
- `toCharArray()`
- `compareTo()`
- `String.valueOf()`
- String to Number conversion
- String Immutability
- String Pool
- `StringBuilder`
- `StringBuffer`
- Escape Characters
- String Formatting
- Real-world examples
- Practice programs

---

## 1. What is a String?

A **String** is a sequence of characters.

```java
String name = "Purnith";
```

Here:

- `String` → data type
- `name` → variable
- `"Purnith"` → String value

Examples:

```java
String city = "Rajahmundry";
String phone = "9876543210";
String message = "Hello Java!";
```

A String can contain letters, numbers, spaces and special characters.

---

## 2. Creating a String

There are two common ways.

### String Literal

```java
String name = "Purnith";
```

### Using `new`

```java
String name = new String("Purnith");
```

For normal String creation, the literal form is commonly preferred.

---

## 3. String Indexing

String indexing starts from **0**.

For:

```java
String word = "JAVA";
```

```text
Character:  J   A   V   A
Index:      0   1   2   3
```

Example:

```java
System.out.println(word.charAt(0));
System.out.println(word.charAt(2));
```

Output:

```text
J
V
```

The last index is:

```java
word.length() - 1
```

---

## 4. `length()`

Returns the number of characters.

```java
String word = "Java";

System.out.println(word.length());
```

Output:

```text
4
```

---

## 5. `charAt()`

Returns the character at a particular index.

```java
String word = "Java";

System.out.println(word.charAt(0));
System.out.println(word.charAt(3));
```

Output:

```text
J
a
```

### First and Last Character

```java
String word = "Programming";

System.out.println("First: " + word.charAt(0));
System.out.println("Last: " + word.charAt(word.length() - 1));
```

Output:

```text
First: P
Last: g
```

---

## 6. `toUpperCase()`

Converts a String to uppercase.

```java
String text = "java";

System.out.println(text.toUpperCase());
```

Output:

```text
JAVA
```

---

## 7. `toLowerCase()`

Converts a String to lowercase.

```java
String text = "JAVA";

System.out.println(text.toLowerCase());
```

Output:

```text
java
```

Remember that Strings are immutable, so these methods return a new String.

---

## 8. `trim()`

Removes leading and trailing spaces.

```java
String name = "   Purnith   ";

System.out.println(name.trim());
```

Output:

```text
Purnith
```

It does not remove spaces between words.

---

## 9. `strip()`

`strip()` also removes leading and trailing whitespace and is more Unicode-aware than `trim()`.

```java
String text = "   Java   ";

System.out.println(text.strip());
```

Output:

```text
Java
```

`strip()` was introduced in Java 11.

---

## 10. `isEmpty()`

Checks whether a String contains zero characters.

```java
String text = "";

System.out.println(text.isEmpty());
```

Output:

```text
true
```

---

## 11. `isBlank()`

Checks whether a String is empty or contains only whitespace.

```java
String text = "   ";

System.out.println(text.isBlank());
```

Output:

```text
true
```

Difference:

```java
"".isEmpty();      // true
"   ".isEmpty();   // false

"".isBlank();      // true
"   ".isBlank();   // true
```

---

## 12. `equals()`

Use `equals()` to compare String contents.

```java
String a = "Java";
String b = "Java";

System.out.println(a.equals(b));
```

Output:

```text
true
```

Practical example:

```java
String username = "admin";

if (username.equals("admin")) {
    System.out.println("Login successful");
}
```

Output:

```text
Login successful
```

---

## 13. `equalsIgnoreCase()`

Compares Strings without considering uppercase/lowercase differences.

```java
String a = "Java";
String b = "JAVA";

System.out.println(a.equalsIgnoreCase(b));
```

Output:

```text
true
```

---

## 14. `==` vs `equals()`

This is an important Java interview concept.

For Strings:

```text
==        → compares references
equals()  → compares contents
```

Example:

```java
String a = new String("Java");
String b = new String("Java");

System.out.println(a == b);
System.out.println(a.equals(b));
```

Output:

```text
false
true
```

### Important Rule

When comparing String values, normally use:

```java
a.equals(b)
```

---

## 15. String Concatenation

We can join Strings using `+`.

```java
String firstName = "Purnith";
String lastName = "Kumar";

String fullName = firstName + " " + lastName;

System.out.println(fullName);
```

Output:

```text
Purnith Kumar
```

We can also combine Strings with numbers:

```java
String name = "Purnith";
int age = 20;

System.out.println("Name: " + name);
System.out.println("Age: " + age);
```

---

## 16. `concat()`

Joins Strings.

```java
String first = "Hello";
String second = " Java";

System.out.println(first.concat(second));
```

Output:

```text
Hello Java
```

For simple concatenation, `+` is usually easier to read.

---

## 17. `contains()`

Checks whether a String contains another sequence.

```java
String message = "I am learning Java";

System.out.println(message.contains("Java"));
```

Output:

```text
true
```

Practical example:

```java
String email = "student@gmail.com";

if (email.contains("@")) {
    System.out.println("Email contains @");
}
```

---

## 18. `startsWith()` and `endsWith()`

### `startsWith()`

```java
String name = "Purnith";

System.out.println(name.startsWith("Pur"));
```

Output:

```text
true
```

### `endsWith()`

```java
String fileName = "resume.pdf";

System.out.println(fileName.endsWith(".pdf"));
```

Output:

```text
true
```

This is useful for checking file extensions.

---

## 19. `indexOf()`

Finds the first occurrence of a character or String.

```java
String text = "Java Programming";

System.out.println(text.indexOf("Java"));
System.out.println(text.indexOf("Programming"));
```

Output:

```text
0
5
```

If the value is not found:

```java
System.out.println(text.indexOf("Python"));
```

Output:

```text
-1
```

Remember:

```text
Found     → index
Not found → -1
```

---

## 20. `lastIndexOf()`

Finds the last occurrence.

```java
String text = "Java Java";

System.out.println(text.lastIndexOf("Java"));
```

Output:

```text
5
```

---

## 21. `substring()`

Extracts part of a String.

### One Argument

```java
String text = "Programming";

System.out.println(text.substring(4));
```

Output:

```text
ramming
```

### Two Arguments

```java
String text = "Programming";

System.out.println(text.substring(0, 4));
```

Output:

```text
Prog
```

Important:

```text
substring(start, end)
```

`start` is included and `end` is excluded.

---

## 22. `replace()`

Replaces characters or text.

```java
String text = "I like Java";

String result = text.replace("Java", "Python");

System.out.println(result);
```

Output:

```text
I like Python
```

Example:

```java
String phone = "123-456-789";

System.out.println(phone.replace("-", ""));
```

Output:

```text
123456789
```

---

## 23. `replaceAll()`

Uses regular expressions for replacement.

```java
String text = "Java123";

String result = text.replaceAll("[0-9]", "");

System.out.println(result);
```

Output:

```text
Java
```

For simple replacement, `replace()` is easier.

---

## 24. `split()`

Splits a String into an array.

```java
String names = "Ram,Sam,Ravi";

String[] result = names.split(",");

for (String name : result) {
    System.out.println(name);
}
```

Output:

```text
Ram
Sam
Ravi
```

---

## 25. `toCharArray()`

Converts a String into a character array.

```java
String word = "Java";

char[] letters = word.toCharArray();

for (char ch : letters) {
    System.out.println(ch);
}
```

Output:

```text
J
a
v
a
```

This is useful when processing characters one by one.

---

## 26. `compareTo()`

Compares two Strings lexicographically.

```java
System.out.println("Java".compareTo("Java"));
```

Output:

```text
0
```

General rule:

```text
0        → equal
Negative → first String comes before second
Positive → first String comes after second
```

---

## 27. `String.valueOf()`

Converts a value into a String.

```java
int number = 100;

String text = String.valueOf(number);

System.out.println(text);
```

Output:

```text
100
```

---

## 28. String to Number Conversion

### String → int

```java
String text = "100";

int number = Integer.parseInt(text);

System.out.println(number + 50);
```

Output:

```text
150
```

### String → double

```java
String text = "99.50";

double price = Double.parseDouble(text);

System.out.println(price);
```

### String → long

```java
String text = "100000";

long number = Long.parseLong(text);

System.out.println(number);
```

---

## 29. Handling Invalid Number Conversion

Invalid numeric text causes `NumberFormatException`.

```java
String text = "abc";

try {
    int number = Integer.parseInt(text);
    System.out.println(number);
} catch (NumberFormatException e) {
    System.out.println("Invalid number");
}
```

Output:

```text
Invalid number
```

This is useful when processing user input.

---

## 30. String Immutability

Strings in Java are **immutable**.

That means the original String object cannot be modified.

```java
String name = "java";

name.toUpperCase();

System.out.println(name);
```

Output:

```text
java
```

To store the returned String:

```java
name = name.toUpperCase();

System.out.println(name);
```

Output:

```text
JAVA
```

---

## 31. String Pool

Java maintains a special **String Pool** for String literals.

Example:

```java
String a = "Java";
String b = "Java";

System.out.println(a == b);
```

Output:

```text
true
```

Java can reuse the same pooled String object.

Still, use:

```java
a.equals(b)
```

when comparing String contents.

---

## 32. `StringBuilder`

`StringBuilder` is mutable and useful when text needs frequent modifications.

```java
StringBuilder text = new StringBuilder("Hello");

text.append(" Java");
text.append(" World");

System.out.println(text);
```

Output:

```text
Hello Java World
```

### Common Methods

```java
append()
insert()
delete()
replace()
reverse()
```

### Reverse Example

```java
StringBuilder text = new StringBuilder("Java");

text.reverse();

System.out.println(text);
```

Output:

```text
avaJ
```

---

## 33. `StringBuffer`

`StringBuffer` is another mutable character sequence.

```java
StringBuffer text = new StringBuffer("Hello");

text.append(" Java");

System.out.println(text);
```

Output:

```text
Hello Java
```

### Difference

| Type | Mutable? | Typical Use |
|---|---|---|
| `String` | No | Normal text |
| `StringBuilder` | Yes | Frequent modifications |
| `StringBuffer` | Yes | Mutable text with synchronized methods |

---

## 34. Escape Characters

Escape characters allow special characters inside Strings.

| Escape | Meaning |
|---|---|
| `\n` | New line |
| `\t` | Tab |
| `\"` | Double quote |
| `\\` | Backslash |
| `\'` | Single quote |

Example:

```java
System.out.println("Hello\nJava");
```

Output:

```text
Hello
Java
```

Example:

```java
System.out.println("He said, \"Hello\"");
```

Output:

```text
He said, "Hello"
```

---

## 35. Text Blocks

Modern Java supports text blocks for multi-line Strings.

```java
String message = """
        Hello!
        Welcome to Java.
        This is Day 3.
        """;

System.out.println(message);
```

Output:

```text
Hello!
Welcome to Java.
This is Day 3.
```

Text blocks are useful for multi-line text, JSON, SQL and HTML.

---

## 36. String Formatting

`String.format()` creates formatted Strings.

```java
String name = "Purnith";
int age = 20;

String message = String.format(
        "My name is %s and I am %d years old.",
        name,
        age
);

System.out.println(message);
```

Output:

```text
My name is Purnith and I am 20 years old.
```

Common format specifiers:

```text
%s → String
%d → Integer
%f → Floating-point number
%c → Character
%b → Boolean
```

---

## 37. `repeat()`

Repeats a String a specified number of times.

```java
String star = "*";

System.out.println(star.repeat(5));
```

Output:

```text
*****
```

`repeat()` is available from Java 11.

---

# Real-World Examples

## 38. Username Validation

```java
String username = "  Purnith123  ";

username = username.trim();

if (username.length() >= 5 && username.length() <= 15) {
    System.out.println("Valid username length");
} else {
    System.out.println("Invalid username length");
}
```

Output:

```text
Valid username length
```

Concepts used:

```text
trim()
length()
if-else
```

---

## 39. Email Check

This is only a basic format check.

```java
String email = "purnith@gmail.com";

if (email.contains("@") && email.endsWith(".com")) {
    System.out.println("Email format looks valid");
} else {
    System.out.println("Invalid email format");
}
```

Output:

```text
Email format looks valid
```

---

## 40. File Extension Check

```java
String fileName = "Main.java";

if (fileName.endsWith(".java")) {
    System.out.println("This is a Java file");
} else {
    System.out.println("Not a Java file");
}
```

Output:

```text
This is a Java file
```

---

## 41. Extract Username from Email

```java
String email = "purnith@gmail.com";

int position = email.indexOf("@");

String username = email.substring(0, position);

System.out.println(username);
```

Output:

```text
purnith
```

---

## 42. Count Words

```java
String sentence = "Java is easy to learn";

String[] words = sentence.trim().split("\s+");

System.out.println("Number of words: " + words.length);
```

Output:

```text
Number of words: 5
```

---

## 43. Count Vowels

```java
String text = "education";

int count = 0;

for (int i = 0; i < text.length(); i++) {

    char ch = Character.toLowerCase(text.charAt(i));

    if (ch == 'a' || ch == 'e' || ch == 'i' ||
        ch == 'o' || ch == 'u') {
        count++;
    }
}

System.out.println("Vowels: " + count);
```

Output:

```text
Vowels: 5
```

---

## 44. Reverse a String

Using `StringBuilder`:

```java
String text = "Java";

String reversed = new StringBuilder(text)
        .reverse()
        .toString();

System.out.println(reversed);
```

Output:

```text
avaJ
```

---

## 45. Palindrome

A palindrome reads the same forward and backward.

```java
String text = "madam";

String reversed = new StringBuilder(text)
        .reverse()
        .toString();

if (text.equals(reversed)) {
    System.out.println("Palindrome");
} else {
    System.out.println("Not Palindrome");
}
```

Output:

```text
Palindrome
```

---

## 46. Remove Extra Spaces

```java
String text = "   Java    is    easy   ";

String result = text.trim().replaceAll("\s+", " ");

System.out.println(result);
```

Output:

```text
Java is easy
```

---

## 47. Character Frequency

Count how many times `a` appears.

```java
String text = "banana";

int count = 0;

for (int i = 0; i < text.length(); i++) {

    if (text.charAt(i) == 'a') {
        count++;
    }
}

System.out.println("a appears: " + count + " times");
```

Output:

```text
a appears: 3 times
```

---

## 48. Common String Methods — Quick Reference

| Method | Purpose |
|---|---|
| `length()` | Returns length |
| `charAt()` | Gets character |
| `toUpperCase()` | Converts to uppercase |
| `toLowerCase()` | Converts to lowercase |
| `trim()` | Removes leading/trailing spaces |
| `strip()` | Removes Unicode whitespace |
| `isEmpty()` | Checks zero length |
| `isBlank()` | Checks empty/whitespace |
| `equals()` | Compares contents |
| `equalsIgnoreCase()` | Compares ignoring case |
| `contains()` | Checks for sequence |
| `startsWith()` | Checks beginning |
| `endsWith()` | Checks ending |
| `indexOf()` | Finds first occurrence |
| `lastIndexOf()` | Finds last occurrence |
| `substring()` | Extracts part |
| `replace()` | Replaces text |
| `replaceAll()` | Regex replacement |
| `split()` | Splits into array |
| `concat()` | Joins Strings |
| `toCharArray()` | Converts to `char[]` |
| `compareTo()` | Lexicographic comparison |
| `String.valueOf()` | Converts value to String |
| `repeat()` | Repeats a String |

---

# 49. Complete String Program

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("Enter your full name: ");
        String name = input.nextLine();

        System.out.println("\n--- String Details ---");

        System.out.println("Original: " + name);
        System.out.println("Length: " + name.length());

        if (!name.isBlank()) {
            System.out.println("Uppercase: " + name.toUpperCase());
            System.out.println("Lowercase: " + name.toLowerCase());
            System.out.println("First character: " + name.charAt(0));
            System.out.println(
                    "Contains 'a': " +
                    name.toLowerCase().contains("a")
            );
        }

        input.close();
    }
}
```

Example:

```text
Enter your full name: Purnith Kumar

--- String Details ---
Original: Purnith Kumar
Length: 13
Uppercase: PURNITH KUMAR
Lowercase: purnith kumar
First character: P
Contains 'a': true
```

---

# 50. Day 3 Practice Programs 🧑‍💻

Try solving these yourself.

### Practice 1 — String Length

```text
Input: Java
Output: 4
```

### Practice 2 — First and Last Character

```text
Input: Programming

First: P
Last: g
```

### Practice 3 — Uppercase and Lowercase

Take a String and print both versions.

### Practice 4 — Count Vowels

```text
Input: education
Output: 5
```

### Practice 5 — Reverse a String

```text
Input: Java
Output: avaJ
```

### Practice 6 — Palindrome

```text
Input: madam
Output: Palindrome
```

### Practice 7 — Count a Character

```text
Input: banana
Character: a
Output: 3
```

### Practice 8 — Count Words

```text
Input: Java is easy to learn
Output: 5
```

### Practice 9 — Extract Email Username

```text
Input: purnith@gmail.com
Output: purnith
```

### Practice 10 — Remove Extra Spaces

```text
Input: "   Java    is    easy   "
Output: "Java is easy"
```

### Practice 11 — Anagram Check

Check whether two Strings contain the same characters.

```text
listen
silent

Output:
Anagram
```

### Practice 12 — Character Frequency

```text
Input: banana

b → 1
a → 3
n → 2
```

---

# 🎯 Day 3 Takeaway

```text
String
   ↓
Creating Strings
   ↓
String Literals & Objects
   ↓
Indexing
   ↓
String Methods
   ↓
Comparison
   ↓
Concatenation
   ↓
Searching
   ↓
Substring
   ↓
Replace & Split
   ↓
String Conversion
   ↓
Immutability
   ↓
String Pool
   ↓
StringBuilder
   ↓
Real-World String Processing
```

### Most Important Methods to Remember First

```java
length()
charAt()
toUpperCase()
toLowerCase()
trim()
isEmpty()
isBlank()
equals()
equalsIgnoreCase()
contains()
startsWith()
endsWith()
indexOf()
substring()
replace()
split()
```

---

## Day 3 Completed ✅

**Java Challenge Progress: 3/20 Days** 🚀

Keep learning. Keep coding. Keep building! 💻
