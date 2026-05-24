# Section 1: Java + DSA for Complete Beginners

> **Who is this for?** Someone who has NEVER written code before. We'll explain everything like we're teaching a 10-year-old. Each line of code has a comment explaining what it does. Every concept has working Java programs you can compile and run.

---

# PART 1: JAVA BASICS

---

## 1.1 Variables & Data Types

### Concept Explanation

Think of variables as **labeled boxes** where you store things. Just like you have a box labeled "toys" for toys and a box labeled "books" for books, in Java each variable has a **type** that says what kind of data it can hold.

**Data Types are like different kinds of containers:**
- `int` → stores whole numbers (like 5, -3, 1000) — like a box for counting
- `float` / `double` → stores decimal numbers (like 3.14, -0.5) — like a box for precise measurement
- `char` → stores a SINGLE character (like 'A', '$', '7') — like a tiny box for one letter
- `boolean` → stores true/false — like a light switch that's either ON or OFF
- `long` → stores HUGE whole numbers (bigger than int can hold)
- `short` → stores small whole numbers (smaller range than int)
- `byte` → stores very tiny whole numbers (-128 to 127)

### Code Example 1: Declaring and Using Variables

```java
public class Variables {
    public static void main(String[] args) {

        // ===== INTEGER TYPES (whole numbers) =====

        // byte: very small numbers, -128 to 127
        byte myByte = 100;
        System.out.println("byte value: " + myByte);

        // short: small numbers, -32,768 to 32,767
        short myShort = 30000;
        System.out.println("short value: " + myShort);

        // int: most common for whole numbers
        int myInt = 999999;
        System.out.println("int value: " + myInt);

        // long: for huge numbers, needs 'L' at the end
        long myLong = 1234567890123L;
        System.out.println("long value: " + myLong);

        // ===== DECIMAL TYPES =====

        // float: decimal up to 6-7 digits, needs 'f' at the end
        float myFloat = 3.14f;
        System.out.println("float value: " + myFloat);

        // double: decimal up to 15 digits (more common)
        double myDouble = 3.141592653589793;
        System.out.println("double value: " + myDouble);

        // ===== OTHER TYPES =====

        // char: stores ONE character, uses SINGLE quotes ''
        char myChar = 'A';
        System.out.println("char value: " + myChar);

        char symbolChar = '@';
        System.out.println("Symbol char: " + symbolChar);

        // boolean: only true or false
        boolean isSunny = true;
        System.out.println("Is it sunny? " + isSunny);
    }
}
```

### Code Example 2: Student Report Card

```java
public class ReportCard {
    public static void main(String[] args) {

        String studentName = "Alice Johnson";
        int rollNumber = 101;
        char grade = 'A';
        float percentage = 95.5f;
        boolean hasPassed = true;
        long studentId = 2024001L;
        byte classSection = 5;

        System.out.println("======= STUDENT REPORT CARD =======");
        System.out.println("Name: " + studentName);
        System.out.println("Roll Number: " + rollNumber);
        System.out.println("Grade: " + grade);
        System.out.println("Percentage: " + percentage + "%");
        System.out.println("Passed: " + hasPassed);
        System.out.println("Student ID: " + studentId);
        System.out.println("Class Section: " + classSection);

        int englishMarks = 85;
        int mathMarks = 95;
        int scienceMarks = 90;
        int totalMarks = englishMarks + mathMarks + scienceMarks;
        int average = totalMarks / 3;

        System.out.println("\n--- Subject Breakdown ---");
        System.out.println("English: " + englishMarks);
        System.out.println("Math: " + mathMarks);
        System.out.println("Science: " + scienceMarks);
        System.out.println("Total: " + totalMarks);
        System.out.println("Average: " + average);
    }
}
```

### Code Example 3: Variable Naming Rules

```java
public class NamingRules {
    public static void main(String[] args) {

        // RULE 1: letters, numbers, $, and _
        int myVariable = 10;
        int myVariable2 = 20;

        // RULE 2: Can NOT start with a number
        // int 2myVariable = 50;  // ERROR!

        // RULE 3: Can NOT use reserved keywords
        // int class = 60;  // ERROR!
        // int int = 70;    // ERROR!

        // RULE 4: Java is CASE-SENSITIVE
        int age = 16;
        int Age = 17;
        int AGE = 18;
        System.out.println("age=" + age + ", Age=" + Age + ", AGE=" + AGE);

        // RULE 5: Use camelCase
        int myAgeInYears = 25;
        String myFirstName = "John";

        System.out.println("Age: " + myAgeInYears + ", Name: " + myFirstName);
    }
}
```

---

## 1.2 Type Conversion & Casting

### Concept Explanation

**Widening (automatic):** Going from smaller container to bigger. Like pouring water from a small cup into a big jug — it just fits. Java does this for you automatically.

byte → short → int → long → float → double

**Narrowing (explicit casting):** Going from bigger container to smaller. Like trying to pour a big jug into a small cup — you MIGHT spill! You MUST write the cast manually.

double → float → long → int → short → byte

### Code Example 1: Widening (Automatic)

```java
public class WideningConversion {
    public static void main(String[] args) {

        byte myByte = 42;
        System.out.println("byte value: " + myByte);

        // byte to short: automatic
        short myShort = myByte;
        System.out.println("short from byte: " + myShort);

        // short to int: automatic
        int myInt = myShort;
        System.out.println("int from short: " + myInt);

        // int to long: automatic
        long myLong = myInt;
        System.out.println("long from int: " + myLong);

        // long to float: automatic
        float myFloat = myLong;
        System.out.println("float from long: " + myFloat);

        // float to double: automatic
        double myDouble = myFloat;
        System.out.println("double from float: " + myDouble);

        // Practical: mixing types in calculation
        int apples = 5;
        double pricePerApple = 0.75;
        double totalCost = apples * pricePerApple;  // int * double = double
        System.out.println("\nTotal cost: $" + totalCost);
    }
}
```

### Code Example 2: Narrowing (Explicit Casting)

```java
public class NarrowingCasting {
    public static void main(String[] args) {

        double myDouble = 99.99;
        System.out.println("Original double: " + myDouble);

        // Put target type in parentheses
        float myFloat = (float) myDouble;
        System.out.println("Casted to float: " + myFloat);

        // Data loss: double to int TRUNCATES the decimal
        int myInt = (int) myDouble;
        System.out.println("Casted to int: " + myInt);  // 99 (lost .99!)

        // More data loss: int to byte
        int bigNumber = 1000;
        byte smallByte = (byte) bigNumber;
        System.out.println("\nOriginal int: " + bigNumber);
        System.out.println("Casted to byte: " + smallByte);  // -24 (wrapped!)

        // char and int relationship
        char letter = 'A';
        int asciiValue = (int) letter;
        System.out.println("\nCharacter '" + letter + "' has ASCII value: " + asciiValue);

        int number = 66;
        char charFromNumber = (char) number;
        System.out.println("Number " + number + " is character: '" + charFromNumber + "'");
    }
}
```

### Code Example 3: Type Promotion

```java
public class TypePromotion {
    public static void main(String[] args) {

        // RULE 1: byte, short, char are promoted to int in expressions
        byte a = 10;
        byte b = 20;
        int sum = a + b;  // a + b becomes int
        System.out.println("Sum of bytes: " + sum);

        // RULE 2: If any operand is long, everything becomes long
        int x = 5;
        long y = 10L;
        long result = x + y;
        System.out.println("int + long = long: " + result);

        // RULE 3: If any operand is float/double, everything becomes that
        int p = 3;
        float q = 2.5f;
        float result2 = p * q;
        System.out.println("int * float = float: " + result2);

        // Integer division surprise!
        int num1 = 5;
        int num2 = 2;
        int intDivision = num1 / num2;
        System.out.println("\nInteger 5/2: " + intDivision);  // 2, not 2.5!

        // Fix: cast to double
        double correctDivision = (double) num1 / num2;
        System.out.println("Double 5/2: " + correctDivision);  // 2.5
    }
}
```

---

## 1.3 Operators

### Concept Explanation

Operators are the **action words** in programming — they tell Java WHAT TO DO with values.

- **Arithmetic** → math (+, -, *, /, %)
- **Relational** → comparing (>, <, >=, <=, ==, !=)
- **Logical** → true/false combinations (&&, ||, !)
- **Assignment** → putting values (=, +=, -=, etc.)
- **Unary** → single value work (++, --, -)
- **Ternary** → shortcut if-else (? :)

### Code Example 1: Arithmetic Operators

```java
public class ArithmeticOperators {
    public static void main(String[] args) {

        int a = 15, b = 4;

        int sum = a + b;
        System.out.println(a + " + " + b + " = " + sum);

        int diff = a - b;
        System.out.println(a + " - " + b + " = " + diff);

        int product = a * b;
        System.out.println(a + " * " + b + " = " + product);

        int quotient = a / b;
        System.out.println(a + " / " + b + " = " + quotient);  // 3 (not 3.75!)

        int remainder = a % b;
        System.out.println(a + " % " + b + " = " + remainder);  // 3

        // Modulus for even/odd check
        int num = 7;
        boolean isEven = num % 2 == 0;
        System.out.println("\n" + num + " is even? " + isEven);

        // Operator precedence
        int result = 5 + 3 * 2;       // 5 + 6 = 11
        System.out.println("5 + 3 * 2 = " + result);

        int withParens = (5 + 3) * 2;  // 8 * 2 = 16
        System.out.println("(5 + 3) * 2 = " + withParens);
    }
}
```

### Code Example 2: Relational (Comparison) Operators

```java
public class RelationalOperators {
    public static void main(String[] args) {

        int x = 10, y = 20;

        System.out.println("x = " + x + ", y = " + y + "\n");

        System.out.println("x == y: " + (x == y));  // false
        System.out.println("x != y: " + (x != y));  // true
        System.out.println("x > y: " + (x > y));    // false
        System.out.println("x < y: " + (x < y));    // true
        System.out.println("x >= y: " + (x >= y));  // false
        System.out.println("x <= y: " + (x <= y));  // true

        int p = 5, q = 5;
        System.out.println("\n" + p + " >= " + q + ": " + (p >= q));  // true

        // Practical use
        int age = 18;
        boolean canVote = age >= 18;
        System.out.println("\nAge " + age + ", Can vote? " + canVote);
    }
}
```

### Code Example 3: Logical Operators

```java
public class LogicalOperators {
    public static void main(String[] args) {

        boolean isSunny = true;
        boolean isWarm = false;

        // && (AND): BOTH must be true
        boolean goToBeach = isSunny && isWarm;
        System.out.println("Go to beach? " + goToBeach);  // false

        // || (OR): AT LEAST ONE must be true
        boolean playOutside = isSunny || isWarm;
        System.out.println("Play outside? " + playOutside);  // true

        // ! (NOT): flips the value
        System.out.println("Not sunny? " + !isSunny);  // false

        // TRUTH TABLE
        System.out.println("\ntrue && true = " + (true && true));
        System.out.println("true && false = " + (true && false));
        System.out.println("false && true = " + (false && true));
        System.out.println("false && false = " + (false && false));

        System.out.println("\ntrue || true = " + (true || true));
        System.out.println("true || false = " + (true || false));
        System.out.println("false || true = " + (false || true));
        System.out.println("false || false = " + (false || false));

        System.out.println("\n!true = " + (!true));
        System.out.println("!false = " + (!false));
    }
}
```

### Code Example 4: Assignment Operators

```java
public class AssignmentOperators {
    public static void main(String[] args) {

        int x = 10;
        System.out.println("x = " + x);

        x += 5;       // x = x + 5
        System.out.println("x += 5: " + x);

        x -= 3;       // x = x - 3
        System.out.println("x -= 3: " + x);

        x *= 2;       // x = x * 2
        System.out.println("x *= 2: " + x);

        x /= 4;       // x = x / 4
        System.out.println("x /= 4: " + x);

        x %= 5;       // x = x % 5
        System.out.println("x %= 5: " + x);

        // Real-life: restaurant bill
        double total = 0;
        total += 25.50;   // burger
        total += 8.99;    // fries
        total += 3.50;    // drink
        total *= 0.9;     // 10% discount
        System.out.println("\nTotal after discount: $" + total);
    }
}
```

### Code Example 5: Unary Operators

```java
public class UnaryOperators {
    public static void main(String[] args) {

        int x = 10;
        System.out.println("-x = " + (-x));  // -10

        // POST-INCREMENT: use FIRST, then increment
        int a = 5;
        int result = a++;
        System.out.println("\nPost-increment:");
        System.out.println("result = a++: " + result);  // 5 (used first)
        System.out.println("a after: " + a);             // 6

        // PRE-INCREMENT: increment FIRST, then use
        int b = 5;
        int result2 = ++b;
        System.out.println("\nPre-increment:");
        System.out.println("result2 = ++b: " + result2); // 6 (incremented first)
        System.out.println("b after: " + b);              // 6

        // Decrement works the same way
        int c = 5;
        System.out.println("\nc-- returns: " + (c--));   // 5
        System.out.println("c is now: " + c);             // 4

        int d = 5;
        System.out.println("--d returns: " + (--d));     // 4
        System.out.println("d is now: " + d);             // 4
    }
}
```

### Code Example 6: Ternary Operator

```java
public class TernaryOperator {
    public static void main(String[] args) {

        // Structure: condition ? valueIfTrue : valueIfFalse

        int age = 20;
        String message = (age >= 18) ? "Can vote!" : "Too young";
        System.out.println("Age " + age + ": " + message);

        // Find larger number
        int a = 15, b = 20;
        int max = (a > b) ? a : b;
        System.out.println("\nLarger of " + a + " and " + b + " is: " + max);

        // Even or odd
        int num = 7;
        String evenOdd = (num % 2 == 0) ? "Even" : "Odd";
        System.out.println(num + " is: " + evenOdd);

        // Absolute value
        int value = -5;
        int abs = (value < 0) ? -value : value;
        System.out.println("Absolute of " + value + " is: " + abs);

        // Nested ternary (grade calculator)
        int marks = 75;
        String grade = (marks >= 90) ? "A" :
                       (marks >= 80) ? "B" :
                       (marks >= 70) ? "C" :
                       (marks >= 60) ? "D" : "F";
        System.out.println("\nMarks: " + marks + ", Grade: " + grade);
    }
}
```

---

## 1.4 Conditional Statements

### Concept Explanation

Your program needs to **make decisions**, just like you do:

- **if**: "If it's raining, take an umbrella."
- **if-else**: "If raining → umbrella, otherwise → sunglasses."
- **else-if ladder**: Check MULTIPLE conditions in order.
- **switch**: Check ONE variable against MANY possible values.

### Code Example 1: If Statement

```java
public class IfStatement {
    public static void main(String[] args) {

        int age = 16;
        System.out.println("Age: " + age);

        if (age >= 18) {
            System.out.println("You can vote!");
        }
        // This line runs no matter what:
        System.out.println("This always prints.");

        // With multiple conditions
        int marks = 85;
        boolean isAttentive = true;

        if (marks >= 80 && isAttentive) {
            System.out.println("\nExcellent student!");
        }
    }
}
```

### Code Example 2: If-Else

```java
public class IfElseStatement {
    public static void main(String[] args) {

        int number = 7;

        if (number % 2 == 0) {
            System.out.println(number + " is EVEN.");
        } else {
            System.out.println(number + " is ODD.");
        }

        // Practical: grade check
        int marks = 45;
        if (marks >= 40) {
            System.out.println("\nYou PASSED! Keep it up!");
        } else {
            System.out.println("\nYou FAILED. Try harder next time.");
        }
    }
}
```

### Code Example 3: Else-If Ladder

```java
public class ElseIfLadder {
    public static void main(String[] args) {

        int marks = 85;
        System.out.println("Marks: " + marks);

        if (marks >= 90) {
            System.out.println("Grade: A - Excellent!");
        } else if (marks >= 80) {
            System.out.println("Grade: B - Great!");
        } else if (marks >= 70) {
            System.out.println("Grade: C - Good!");
        } else if (marks >= 60) {
            System.out.println("Grade: D - Passing.");
        } else if (marks >= 50) {
            System.out.println("Grade: E - Barely passed.");
        } else {
            System.out.println("Grade: F - Failed.");
        }

        // Number classifier
        int num = -5;
        System.out.println("\nNumber: " + num);
        if (num > 0) {
            System.out.println("POSITIVE");
        } else if (num < 0) {
            System.out.println("NEGATIVE");
        } else {
            System.out.println("ZERO");
        }

        // Largest of 3 numbers
        int a = 45, b = 78, c = 32;
        System.out.println("\nNumbers: " + a + ", " + b + ", " + c);
        if (a >= b && a >= c) {
            System.out.println("Largest: " + a);
        } else if (b >= a && b >= c) {
            System.out.println("Largest: " + b);
        } else {
            System.out.println("Largest: " + c);
        }
    }
}
```

### Code Example 4: Nested If-Else

```java
public class NestedIfElse {
    public static void main(String[] args) {

        boolean isRaining = true;
        int temperature = 15;

        if (isRaining) {
            System.out.print("Wear a raincoat. ");
            if (temperature < 20) {
                System.out.println("Also wear a sweater.");
            } else {
                System.out.println("Just the raincoat is fine.");
            }
        } else {
            System.out.print("No raincoat. ");
            if (temperature > 25) {
                System.out.println("Wear shorts!");
            } else if (temperature > 15) {
                System.out.println("Wear a light jacket.");
            } else {
                System.out.println("Wear a warm coat!");
            }
        }
    }
}
```

### Code Example 5: Switch Statement

```java
public class SwitchStatement {
    public static void main(String[] args) {

        // Check ONE variable against MANY values
        int dayNumber = 3;
        String dayName;

        switch (dayNumber) {
            case 1:
                dayName = "Monday";
                break;  // break exits the switch
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
            default:  // like else — runs if nothing matched
                dayName = "Invalid day!";
                break;
        }
        System.out.println("Day " + dayNumber + " is: " + dayName);

        // Fall-through: multiple cases, one action
        int month = 1;
        System.out.println("\nMonth: " + month);
        switch (month) {
            case 1: case 3: case 5: case 7: case 8: case 10: case 12:
                System.out.println("31 days");
                break;
            case 4: case 6: case 9: case 11:
                System.out.println("30 days");
                break;
            case 2:
                System.out.println("28 or 29 days");
                break;
            default:
                System.out.println("Invalid!");
        }

        // Switch with Strings
        String fruit = "Apple";
        String color;
        switch (fruit.toLowerCase()) {
            case "apple":
                color = "Red or Green"; break;
            case "banana":
                color = "Yellow"; break;
            case "orange":
                color = "Orange"; break;
            default:
                color = "Unknown";
        }
        System.out.println("\n" + fruit + " is: " + color);

        // Calculator using switch
        int num1 = 20, num2 = 4;
        char op = '/';
        int result = 0;

        switch (op) {
            case '+': result = num1 + num2; break;
            case '-': result = num1 - num2; break;
            case '*': result = num1 * num2; break;
            case '/':
                if (num2 != 0) result = num1 / num2;
                else System.out.println("Can't divide by 0!");
                break;
            default: System.out.println("Invalid operator!");
        }
        if (op == '/' && num2 == 0) {}
        else System.out.println(num1 + " " + op + " " + num2 + " = " + result);
    }
}
```

---

---

## 1.5 Loops

### Concept Explanation

Loops let you **repeat code** without writing it over and over.

- **for**: "I know exactly how many times" (count 1 to 10)
- **while**: "Keep going WHILE condition is true"
- **do-while**: "Do it ONCE, then check if I should repeat"

### Code Example 1: For Loop

```java
public class ForLoop {
    public static void main(String[] args) {

        // for (initialization; condition; update)
        System.out.println("=== Count 1 to 10 ===");
        for (int i = 1; i <= 10; i++) {
            System.out.print(i + " ");
        }
        System.out.println();

        System.out.println("\n=== Count down 10 to 1 ===");
        for (int i = 10; i >= 1; i--) {
            System.out.print(i + " ");
        }
        System.out.println();

        System.out.println("\n=== Count by 2s ===");
        for (int i = 2; i <= 20; i += 2) {
            System.out.print(i + " ");
        }
        System.out.println();

        // Sum of first 10 numbers
        int sum = 0;
        for (int i = 1; i <= 10; i++) {
            sum += i;  // sum = sum + i
        }
        System.out.println("\nSum 1 to 10 = " + sum);  // 55

        // Multiplication table
        int table = 5;
        System.out.println("\n=== Table of " + table + " ===");
        for (int i = 1; i <= 10; i++) {
            System.out.println(table + " x " + i + " = " + (table * i));
        }

        // Factorial: 5! = 5*4*3*2*1
        int fact = 1;
        for (int i = 5; i >= 1; i--) {
            fact *= i;
        }
        System.out.println("\n5! = " + fact);  // 120

        // BREAK: exit the loop immediately
        System.out.println("\n=== Break at 5 ===");
        for (int i = 1; i <= 10; i++) {
            if (i == 5) {
                System.out.println("Reached 5! Breaking!");
                break;
            }
            System.out.print(i + " ");
        }
        System.out.println("\n(Loop ended early)");

        // CONTINUE: skip current iteration
        System.out.println("\n=== Skip 5 ===");
        for (int i = 1; i <= 10; i++) {
            if (i == 5) {
                System.out.println("Skipping 5...");
                continue;
            }
            System.out.print(i + " ");
        }
        System.out.println("\n(5 is missing)");
    }
}
```

### Code Example 2: While Loop

```java
public class WhileLoop {
    public static void main(String[] args) {

        // Use when you DON'T know how many times, just the CONDITION
        System.out.println("=== Count 1 to 10 ===");
        int i = 1;
        while (i <= 10) {
            System.out.print(i + " ");
            i++;  // DON'T forget this, or it runs forever!
        }
        System.out.println();

        // Keep halving until we reach 1
        System.out.println("\n=== Halve 100 until 1 ===");
        int num = 100;
        while (num > 1) {
            System.out.print(num + " -> ");
            num /= 2;
        }
        System.out.println("1");

        // Extract digits of a number
        int number = 12345;
        System.out.print("\nDigits of " + number + ": ");
        while (number > 0) {
            int digit = number % 10;    // get last digit
            System.out.print(digit + " ");
            number = number / 10;        // remove last digit
        }
        System.out.println();

        // Reverse a number
        int original = 1234;
        int temp = original;
        int reversed = 0;
        while (temp > 0) {
            int digit = temp % 10;
            reversed = reversed * 10 + digit;
            temp /= 10;
        }
        System.out.println("\nReverse of " + original + " is: " + reversed);

        // Palindrome check
        int checkNum = 1221;
        temp = checkNum;
        reversed = 0;
        while (temp > 0) {
            reversed = reversed * 10 + (temp % 10);
            temp /= 10;
        }
        if (checkNum == reversed) {
            System.out.println(checkNum + " IS a palindrome!");
        } else {
            System.out.println(checkNum + " is NOT a palindrome.");
        }
    }
}
```

### Code Example 3: Do-While Loop

```java
public class DoWhileLoop {
    public static void main(String[] args) {

        // Do-while: runs AT LEAST ONCE, then checks condition
        System.out.println("=== Count 1 to 5 ===");
        int i = 1;
        do {
            System.out.print(i + " ");
            i++;
        } while (i <= 5);
        System.out.println();

        // KEY DIFFERENCE: do-while runs even if condition is false
        System.out.println("\n=== While vs Do-While ===");
        int x = 100;

        System.out.print("While (x > 200): ");
        while (x > 200) {
            System.out.print("never prints");
        }
        System.out.println("(nothing - condition false from start)");

        System.out.print("Do-while (x > 200): ");
        do {
            System.out.println("prints ONCE even though condition is false!");
            x++;
        } while (x > 200);

        // Menu system
        System.out.println("\n=== Menu Simulation ===");
        int choice = 1;
        do {
            System.out.println("\n--- MENU ---");
            System.out.println("1. Say Hello");
            System.out.println("2. Say Goodbye");
            System.out.println("3. Exit");
            System.out.println("Choice: " + choice);

            if (choice == 1) System.out.println("Hello!");
            else if (choice == 2) System.out.println("Goodbye!");
            else if (choice == 3) System.out.println("Exiting...");
            else System.out.println("Invalid!");

            choice++;
            if (choice > 3) choice = 3;
        } while (choice != 3);
    }
}
```

### Code Example 4: Nested Loops & Pattern Basics

```java
public class NestedLoops {
    public static void main(String[] args) {

        // Outer loop = rows, Inner loop = columns
        System.out.println("=== Times Table (1 to 5) ===");
        for (int row = 1; row <= 5; row++) {
            for (int col = 1; col <= 5; col++) {
                System.out.print((row * col) + "\t");
            }
            System.out.println();
        }

        // Print a rectangle
        System.out.println("\n=== Rectangle (5x3) ===");
        for (int i = 0; i < 3; i++) {          // rows
            for (int j = 0; j < 5; j++) {      // columns
                System.out.print("* ");
            }
            System.out.println();
        }

        // Right triangle
        System.out.println("\n=== Right Triangle ===");
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {     // j goes up to i
                System.out.print("* ");
            }
            System.out.println();
        }

        // Number triangle
        System.out.println("\n=== Number Triangle ===");
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");     // column number
            }
            System.out.println();
        }
        // 1
        // 1 2
        // 1 2 3
        // 1 2 3 4
        // 1 2 3 4 5

        // Row number triangle
        System.out.println("\n=== Row Number Triangle ===");
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(i + " ");     // ROW number
            }
            System.out.println();
        }
        // 1
        // 2 2
        // 3 3 3
        // 4 4 4 4
        // 5 5 5 5 5

        // Inverted triangle
        System.out.println("\n=== Inverted Triangle ===");
        for (int i = 5; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

---

## 1.6 Functions (Methods)

### Concept Explanation

A **function** is a reusable block of code that does ONE specific task. Like a recipe:
- **Name** = recipe name (makeToast)
- **Parameters** = ingredients (bread, butter)
- **Return type** = what it produces (Toast)
- **Body** = steps to follow

### Code Example 1: Simple Functions

```java
public class SimpleFunctions {

    public static void main(String[] args) {
        System.out.println("=== main() starts ===");

        // Call a function - execution jumps there and comes back
        greetUser();
        showWelcome();

        System.out.println("Back in main()! Program ending.");
    }

    // void means this function doesn't RETURN anything
    public static void greetUser() {
        System.out.println("  Hello! Welcome to Java!");
        // Execution returns to where this was called from
    }

    public static void showWelcome() {
        System.out.println("  Let's learn Java functions!");
    }
}
```

### Code Example 2: Functions with Parameters

```java
public class FunctionParameters {

    public static void main(String[] args) {

        greetPerson("Alice");
        greetPerson("Bob");
        greetPerson("Charlie");

        System.out.println("\n--- Adding Numbers ---");
        addAndPrint(5, 10);
        addAndPrint(100, 200);

        System.out.println("\n--- Print a Box ---");
        printBox(3, 5, '#');
        printBox(2, 4, '@');
    }

    // Parameter: a String called 'name'
    public static void greetPerson(String name) {
        System.out.println("Hello, " + name + "!");
    }

    // Two int parameters
    public static void addAndPrint(int a, int b) {
        System.out.println(a + " + " + b + " = " + (a + b));
    }

    // Three parameters
    public static void printBox(int rows, int cols, char symbol) {
        System.out.println(rows + "x" + cols + " box of '" + symbol + "':");
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.print(symbol + " ");
            }
            System.out.println();
        }
    }
}
```

### Code Example 3: Functions with Return Values

```java
public class ReturnValues {

    public static void main(String[] args) {

        // Store the returned value
        int result = add(10, 25);
        System.out.println("10 + 25 = " + result);

        // Use returned value in an expression
        int doubled = add(5, 3) * 2;
        System.out.println("(5+3) x 2 = " + doubled);

        // More examples
        int x = 10, y = 3;
        System.out.println("\n" + x + " - " + y + " = " + subtract(x, y));
        System.out.println(x + " x " + y + " = " + multiply(x, y));
        System.out.println(x + " / " + y + " = " + divide(x, y));

        // Boolean return
        int age = 20;
        if (isAdult(age)) {
            System.out.println("\nAge " + age + ": You are an adult.");
        }

        // Prime check
        int num = 17;
        System.out.println(num + " is prime? " + isPrime(num));
    }

    public static int add(int a, int b) {
        return a + b;  // the 'return' keyword sends the value back
    }

    public static int subtract(int a, int b) {
        return a - b;
    }

    public static int multiply(int a, int b) {
        return a * b;
    }

    public static int divide(int a, int b) {
        if (b == 0) {
            System.out.println("ERROR: Division by zero!");
            return 0;
        }
        return a / b;
    }

    public static boolean isAdult(int age) {
        return age >= 18;
    }

    public static boolean isPrime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i <= n / 2; i++) {
            if (n % i == 0) return false;
        }
        return true;
    }
}
```

### Code Example 4: Functions Calling Functions (Call Stack)

```java
public class FunctionChaining {

    public static void main(String[] args) {
        System.out.println("main() starts");

        double area = calculateRoomArea(10.5, 7.2);
        System.out.println("\nRoom area: " + area + " sq meters");

        System.out.println("main() ends");
    }

    public static double calculateRoomArea(double length, double width) {
        System.out.println("  calculateRoomArea() called");
        double area = multiply(length, width);  // calls another function!
        System.out.println("  calculateRoomArea() returning: " + area);
        return area;
    }

    public static double multiply(double a, double b) {
        System.out.println("    multiply() called with " + a + " x " + b);
        return a * b;
    }

    // CALL STACK:
    // 1. main() pushes onto stack
    // 2. calculateRoomArea() pushes on top
    // 3. multiply() pushes on top
    // 4. multiply() completes -> pops off
    // 5. calculateRoomArea() completes -> pops off
    // 6. main() completes -> pops off (stack empty)
}
```

### Code Example 5: Method Overloading

```java
public class MethodOverloading {

    // SAME name, DIFFERENT parameters. Java picks the right one!

    public static void main(String[] args) {

        System.out.println("add(2, 3) = " + add(2, 3));           // 2 ints
        System.out.println("add(2, 3, 4) = " + add(2, 3, 4));    // 3 ints
        System.out.println("add(2.5, 3.7) = " + add(2.5, 3.7));  // 2 doubles

        // Overloaded print
        print(42);
        print(3.14);
        print("Hello!");
        print(3, "Java");
    }

    public static int add(int a, int b) {
        System.out.println("  -> add(int, int)");
        return a + b;
    }

    public static int add(int a, int b, int c) {
        System.out.println("  -> add(int, int, int)");
        return a + b + c;
    }

    public static double add(double a, double b) {
        System.out.println("  -> add(double, double)");
        return a + b;
    }

    public static void print(int value) {
        System.out.println("  print(int): " + value);
    }

    public static void print(double value) {
        System.out.println("  print(double): " + value);
    }

    public static void print(String value) {
        System.out.println("  print(String): \"" + value + "\"");
    }

    public static void print(int times, String value) {
        for (int i = 0; i < times; i++) {
            System.out.println("  print(int, String): " + value);
        }
    }
}
```

### Code Example 6: Variable Scope

```java
public class VariableScope {

    static int classVar = 100;  // visible everywhere in this class

    public static void main(String[] args) {

        int mainLocal = 50;  // only in main()

        System.out.println("classVar: " + classVar);
        System.out.println("mainLocal: " + mainLocal);

        someFunction();

        // System.out.println(functionLocal);  // ERROR! Doesn't exist here

        // BLOCK SCOPE
        if (true) {
            int insideBlock = 20;
            System.out.println("Inside if: " + insideBlock);
        }
        // System.out.println(insideBlock);  // ERROR! Doesn't exist here

        for (int i = 0; i < 3; i++) {
            System.out.println("i = " + i);  // 'i' only exists in this loop
        }
        // System.out.println(i);  // ERROR!
    }

    public static void someFunction() {
        int functionLocal = 75;
        System.out.println("someFunction() - classVar: " + classVar);
        System.out.println("someFunction() - functionLocal: " + functionLocal);
        // System.out.println(mainLocal);  // ERROR! Don't have access
    }
}
```

---

# PART 2: PATTERNS (Part 1 - Basic)

---

## 2.1 Star Patterns - Square, Triangle, Pyramid, Diamond

### Concept Explanation

Pattern printing is the BEST way to master nested loops. The **outer loop** = rows, **inner loop** = columns. What you print (star, space, number) fills each cell.

### Code Example 1: Square and Triangle Patterns

```java
public class BasicStarPatterns {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== PATTERN 1: Solid Square ===");
        // *****
        // *****
        // *****
        // *****
        // *****
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 2: Hollow Square ===");
        // *****
        // *   *
        // *   *
        // *   *
        // *****
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                // Print star on edges only
                if (i == 1 || i == n || j == 1 || j == n) {
                    System.out.print("* ");
                } else {
                    System.out.print("  ");
                }
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 3: Right Triangle ===");
        // *
        // **
        // ***
        // ****
        // *****
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {     // stars increase with row
                System.out.print("*");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 4: Inverted Right Triangle ===");
        // *****
        // ****
        // ***
        // **
        // *
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 5: Mirrored Right Triangle ===");
        //     *
        //    **
        //   ***
        //  ****
        // *****
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) {  // spaces
                System.out.print(" ");
            }
            for (int j = 1; j <= i; j++) {      // stars
                System.out.print("*");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 6: Inverted Mirrored ===");
        // *****
        //  ****
        //   ***
        //    **
        //     *
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) {
                System.out.print(" ");
            }
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

### Code Example 2: Pyramid and Diamond

```java
public class PyramidDiamondPatterns {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== PATTERN 7: Pyramid ===");
        //     *
        //    ***
        //   *****
        //  *******
        // *********
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) {
                System.out.print(" ");
            }
            for (int j = 1; j <= 2 * i - 1; j++) {  // 1, 3, 5, 7, 9 stars
                System.out.print("*");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 8: Inverted Pyramid ===");
        // *********
        //  *******
        //   *****
        //    ***
        //     *
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) {
                System.out.print(" ");
            }
            for (int j = 1; j <= 2 * i - 1; j++) {
                System.out.print("*");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 9: Diamond ===");
        //     *
        //    ***
        //   *****
        //  *******
        // *********
        //  *******
        //   *****
        //    ***
        //     *
        // Upper half (pyramid)
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) System.out.print("*");
            System.out.println();
        }
        // Lower half (inverted, minus middle row to avoid duplication)
        for (int i = n - 1; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) System.out.print("*");
            System.out.println();
        }

        System.out.println("\n=== PATTERN 10: Hollow Pyramid ===");
        //     *
        //    * *
        //   *   *
        //  *     *
        // *********
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) {
                // Star only on edges, space inside
                if (i == 1 || i == n || j == 1 || j == 2 * i - 1) {
                    System.out.print("*");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 11: Hollow Diamond ===");
        //     *
        //    * *
        //   *   *
        //  *     *
        // *       *
        //  *     *
        //   *   *
        //    * *
        //     *
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) {
                if (j == 1 || j == 2 * i - 1) System.out.print("*");
                else System.out.print(" ");
            }
            System.out.println();
        }
        for (int i = n - 1; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) {
                if (j == 1 || j == 2 * i - 1) System.out.print("*");
                else System.out.print(" ");
            }
            System.out.println();
        }
    }
}
```

### Code Example 3: Butterfly Pattern

```java
public class ButterflyPattern {

    public static void main(String[] args) {

        int n = 4;

        System.out.println("=== BUTTERFLY PATTERN ===");
        // *      *
        // **    **
        // ***  ***
        // ********
        // ********
        // ***  ***
        // **    **
        // *      *

        // Upper half
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) System.out.print("*");      // left
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" "); // middle
            for (int j = 1; j <= i; j++) System.out.print("*");      // right
            System.out.println();
        }
        // Lower half
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= i; j++) System.out.print("*");
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) System.out.print("*");
            System.out.println();
        }

        System.out.println("\n=== HOLLOW BUTTERFLY ===");
        // *      *
        // **    **
        // * *  * *
        // *  **  *
        // *  **  *
        // * *  * *
        // **    **
        // *      *
        n = 5;
        // (pattern with hollow wings - only print * at edges of each wing)
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                if (j == 1 || j == i) System.out.print("*");
                else System.out.print(" ");
            }
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) {
                if (j == 1 || j == i) System.out.print("*");
                else System.out.print(" ");
            }
            System.out.println();
        }
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                if (j == 1 || j == i) System.out.print("*");
                else System.out.print(" ");
            }
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) {
                if (j == 1 || j == i) System.out.print("*");
                else System.out.print(" ");
            }
            System.out.println();
        }
    }
}
```

---

## 2.2 Number Patterns

### Code Example 1: Basic Number Patterns

```java
public class NumberPatterns {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== PATTERN 1: 1, 12, 123... ===");
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 2: 1, 22, 333... ===");
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(i + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 3: Increasing count ===");
        // 1
        // 2 3
        // 4 5 6
        // 7 8 9 10
        int counter = 1;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(counter++ + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 4: Inverted number ===");
        // 1 2 3 4 5
        // 1 2 3 4
        // 1 2 3
        // 1 2
        // 1
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 5: Palindromic pyramid ===");
        //     1
        //    212
        //   32123
        //  4321234
        // 543212345
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = i; j >= 1; j--) System.out.print(j);
            for (int j = 2; j <= i; j++) System.out.print(j);
            System.out.println();
        }

        System.out.println("\n=== PATTERN 6: Binary triangle ===");
        // 1
        // 0 1
        // 1 0 1
        // 0 1 0 1
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(((i + j) % 2 == 0 ? 1 : 0) + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 7: Number pyramid ===");
        //     1
        //    123
        //   12345
        //  1234567
        // 123456789
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) System.out.print(j);
            System.out.println();
        }
    }
}
```

### Code Example 2: Floyd's Triangle and 0-1 Triangle

```java
public class SpecialTriangles {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== FLOYD'S TRIANGLE ===");
        // 1
        // 2  3
        // 4  5  6
        // 7  8  9  10
        // 11 12 13 14 15
        int number = 1;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(number++ + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== 0-1 TRIANGLE ===");
        // 1
        // 0 1
        // 1 0 1
        // 0 1 0 1
        // 1 0 1 0 1
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(((i + j) % 2 == 0 ? 1 : 0) + " ");
            }
            System.out.println();
        }

        // Alternative approach to 0-1 triangle
        System.out.println("\n=== 0-1 Triangle (toggle method) ===");
        int start;
        for (int i = 0; i < n; i++) {
            start = (i % 2 == 0) ? 1 : 0;
            for (int j = 0; j <= i; j++) {
                System.out.print(start + " ");
                start = 1 - start;  // toggle between 0 and 1
            }
            System.out.println();
        }
    }
}
```

---

## 2.3 Character Patterns

### Code Example 1: Character Patterns

```java
public class CharacterPatterns {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== PATTERN 1: A, AB, ABC... ===");
        for (int i = 1; i <= n; i++) {
            char ch = 'A';
            for (int j = 1; j <= i; j++) {
                System.out.print(ch++ + " ");  // increment ASCII value
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 2: A, BB, CCC... ===");
        for (int i = 1; i <= n; i++) {
            char ch = (char) ('A' + i - 1);  // 'A' + 0 = 'A', +1 = 'B', etc.
            for (int j = 1; j <= i; j++) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 3: A, BC, DEF... ===");
        // A
        // B C
        // D E F
        // G H I J
        char ch = 'A';
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(ch++ + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 4: Inverted characters ===");
        // A B C D E
        // A B C D
        // A B C
        // A B
        // A
        for (int i = n; i >= 1; i--) {
            ch = 'A';
            for (int j = 1; j <= i; j++) {
                System.out.print(ch++ + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 5: Character pyramid ===");
        //     A
        //    A B
        //   A B C
        //  A B C D
        // A B C D E
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            ch = 'A';
            for (int j = 1; j <= i; j++) {
                System.out.print(ch++ + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 6: A, ABA, ABCBA... ===");
        //     A
        //    ABA
        //   ABCBA
        //  ABCDCBA
        // ABCDEDCBA
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            ch = 'A';
            for (int j = 1; j <= i; j++) System.out.print(ch++);
            ch = (char) ('A' + i - 2);
            for (int j = 1; j <= i - 1; j++) System.out.print(ch--);
            System.out.println();
        }
    }
}
```

---

---

# PART 3: PATTERNS (Part 2 - Advanced)

---

## 3.1 Advanced Number Patterns & Pascal's Triangle

### Code Example 1: Advanced Number Patterns

```java
public class AdvancedNumberPatterns {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== PATTERN 1: Number Diamond ===");
        //     1
        //    212
        //   32123
        //  4321234
        // 543212345
        //  4321234
        //   32123
        //    212
        //     1
        // Upper
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = i; j >= 1; j--) System.out.print(j);
            for (int j = 2; j <= i; j++) System.out.print(j);
            System.out.println();
        }
        // Lower
        for (int i = n - 1; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = i; j >= 1; j--) System.out.print(j);
            for (int j = 2; j <= i; j++) System.out.print(j);
            System.out.println();
        }

        System.out.println("\n=== PATTERN 2: Number Spiral Square ===");
        // 1 1 1 1 1
        // 1 2 2 2 1
        // 1 2 3 2 1
        // 1 2 2 2 1
        // 1 1 1 1 1
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                // Minimum distance from any edge
                int dist = Math.min(Math.min(i, j), Math.min(n - i + 1, n - j + 1));
                System.out.print(dist + " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 3: Number Pyramid with gaps ===");
        //         1
        //       2 3 2
        //     3 4 5 4 3
        //   4 5 6 7 6 5 4
        // 5 6 7 8 9 8 7 6 5
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print("  ");
            int num = i;
            for (int j = 1; j <= i; j++) System.out.print(num++ + " ");
            num -= 2;
            for (int j = 1; j <= i - 1; j++) System.out.print(num-- + " ");
            System.out.println();
        }

        System.out.println("\n=== PATTERN 4: Hollow Number Diamond ===");
        //     1
        //    2 2
        //   3   3
        //  4     4
        // 5       5
        //  4     4
        //   3   3
        //    2 2
        //     1
        // Upper
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) {
                System.out.print((j == 1 || j == 2 * i - 1) ? i : " ");
            }
            System.out.println();
        }
        // Lower
        for (int i = n - 1; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            for (int j = 1; j <= 2 * i - 1; j++) {
                System.out.print((j == 1 || j == 2 * i - 1) ? i : " ");
            }
            System.out.println();
        }

        System.out.println("\n=== PATTERN 5: Hollow Number Square ===");
        // 1 2 3 4 5
        // 1       5
        // 1       5
        // 1       5
        // 1 2 3 4 5
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                if (i == 1 || i == n || j == 1 || j == n) {
                    System.out.print(j + " ");
                } else {
                    System.out.print("  ");
                }
            }
            System.out.println();
        }
    }
}
```

### Code Example 2: Pascal's Triangle

```java
public class PascalsTriangle {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== PASCAL'S TRIANGLE ===");
        //     1
        //    1 1
        //   1 2 1
        //  1 3 3 1
        // 1 4 6 4 1
        //
        // Each number = sum of two numbers above it.
        // First and last of each row = 1.

        for (int i = 0; i < n; i++) {
            // Spaces for alignment
            for (int j = 0; j < n - i - 1; j++) {
                System.out.print(" ");
            }

            int num = 1;  // first number is always 1
            for (int j = 0; j <= i; j++) {
                System.out.print(num + " ");

                // Calculate next: num * (i - j) / (j + 1)
                num = num * (i - j) / (j + 1);
            }
            System.out.println();
        }

        // Explanation:
        // Row 0: 1
        // Row 1: 1, 1
        // Row 2: 1, 2, 1
        // Row 3: 1, 3, 3, 1
        // Row 4: 1, 4, 6, 4, 1
        // Formula: C(n,k) = n! / (k! * (n-k)!)

        System.out.println("\n=== PASCAL'S TRIANGLE (Array method) ===");
        int[][] pascal = new int[n][n];

        for (int i = 0; i < n; i++) {
            pascal[i][0] = 1;      // first element = 1
            pascal[i][i] = 1;      // last element = 1

            for (int j = 1; j < i; j++) {
                // Sum of two numbers above: pascal[i-1][j-1] + pascal[i-1][j]
                pascal[i][j] = pascal[i-1][j-1] + pascal[i-1][j];
            }
        }

        // Print the triangle
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i - 1; j++) System.out.print(" ");
            for (int j = 0; j <= i; j++) {
                System.out.print(pascal[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

### Code Example 3: Advanced Star Patterns

```java
public class AdvancedStarPatterns {

    public static void main(String[] args) {

        int n = 5;

        System.out.println("=== DOUBLE DIAMOND (Sandglass) ===");
        // * * * * * * * * *
        //   * * * * * * *
        //     * * * * *
        //       * * *
        //         *
        //       * * *
        //     * * * * *
        //   * * * * * * *
        // * * * * * * * * *
        // Upper half (inverted pyramid)
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) System.out.print("  ");
            for (int j = 1; j <= 2 * i - 1; j++) System.out.print("* ");
            System.out.println();
        }
        // Lower half
        for (int i = 2; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) System.out.print("  ");
            for (int j = 1; j <= 2 * i - 1; j++) System.out.print("* ");
            System.out.println();
        }

        System.out.println("\n=== DIAMOND INSIDE SQUARE ===");
        // *********
        // **** ****
        // ***   ***
        // **     **
        // *       *
        // **     **
        // ***   ***
        // **** ****
        // *********
        // Upper
        for (int i = n; i >= 1; i--) {
            for (int j = 1; j <= i; j++) System.out.print("*");
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) System.out.print("*");
            System.out.println();
        }
        // Lower
        for (int i = 2; i <= n; i++) {
            for (int j = 1; j <= i; j++) System.out.print("*");
            for (int j = 1; j <= 2 * (n - i); j++) System.out.print(" ");
            for (int j = 1; j <= i; j++) System.out.print("*");
            System.out.println();
        }

        System.out.println("\n=== PLUS PATTERN ===");
        //     *
        //     *
        //   *****
        //     *
        //     *
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                // Middle row (horizontal line) or middle column (vertical line)
                if (i == n / 2 + 1 || j == n / 2 + 1) {
                    System.out.print("* ");
                } else {
                    System.out.print("  ");
                }
            }
            System.out.println();
        }

        System.out.println("\n=== X PATTERN ===");
        // *   *
        //  * *
        //   *
        //  * *
        // *   *
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                // Primary diagonal (i == j) or secondary diagonal (i + j == n + 1)
                if (i == j || i + j == n + 1) {
                    System.out.print("* ");
                } else {
                    System.out.print("  ");
                }
            }
            System.out.println();
        }

        System.out.println("\n=== HOLLOW RHOMBUS ===");
        //     *****
        //    *   *
        //   *   *
        //  *   *
        // *****
        for (int i = 1; i <= n; i++) {
            // Leading spaces create slant
            for (int j = 1; j <= n - i; j++) System.out.print(" ");
            // Stars: only on edges
            for (int j = 1; j <= n; j++) {
                if (i == 1 || i == n || j == 1 || j == n) {
                    System.out.print("*");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println();
        }
    }
}
```

---

# PART 4: ARRAYS

---

## 4.1 Arrays - Creation, Traversal, Memory Concept

### Concept Explanation

An **array** is like a **row of lockers** in a school hallway:
- Each locker has a **number** (index 0, 1, 2, ...)
- All lockers hold the **same type** of item
- Once you build the row, you can't change its **length**
- You access items using `arrayName[index]`

**Memory:** When you create `int[] arr = new int[5]`, Java finds 5 consecutive parking spots in memory. `arr` stores the address of the first spot. `arr[2]` means "skip 2 spots from the first."

### Code Example 1: Creating and Using Arrays

```java
import java.util.Arrays;

public class ArrayBasics {

    public static void main(String[] args) {

        // Method 1: Declare and allocate (default values: 0)
        int[] numbers = new int[5];
        System.out.println("Array of 5 ints: " + Arrays.toString(numbers));

        // Assign values
        numbers[0] = 10;
        numbers[1] = 20;
        numbers[2] = 30;
        numbers[3] = 40;
        numbers[4] = 50;
        // numbers[5] = 60;  // ERROR! Out of bounds

        System.out.println("After assignment: " + Arrays.toString(numbers));

        // Method 2: Declare and initialize
        int[] scores = {95, 87, 92, 78, 88};
        System.out.println("\nScores: " + Arrays.toString(scores));

        // Access individual elements
        System.out.println("First score: " + scores[0]);      // 95
        System.out.println("Last score: " + scores[scores.length - 1]); // 88

        // Array length
        System.out.println("\nLength of scores: " + scores.length);

        // Different array types
        String[] names = {"Alice", "Bob", "Charlie"};
        double[] temps = {98.6, 100.2, 97.8};
        char[] letters = {'J', 'A', 'V', 'A'};
        boolean[] flags = {true, false, true};

        System.out.println("\nNames: " + Arrays.toString(names));
        System.out.println("Temps: " + Arrays.toString(temps));
        System.out.println("Letters: " + Arrays.toString(letters));
        System.out.println("Flags: " + Arrays.toString(flags));
    }
}
```

### Code Example 2: Array Traversal

```java
import java.util.Arrays;

public class ArrayTraversal {

    public static void main(String[] args) {

        int[] arr = {10, 20, 30, 40, 50};

        // Method 1: for loop with index
        System.out.println("For loop:");
        for (int i = 0; i < arr.length; i++) {
            System.out.println("  arr[" + i + "] = " + arr[i]);
        }

        // Method 2: Enhanced for-each (no index)
        System.out.println("\nFor-each loop:");
        for (int element : arr) {
            System.out.println("  Value: " + element);
        }

        // Method 3: While loop
        System.out.println("\nWhile loop:");
        int i = 0;
        while (i < arr.length) {
            System.out.println("  arr[" + i + "] = " + arr[i]);
            i++;
        }

        // Common operations
        // Sum
        int sum = 0;
        for (int val : arr) sum += val;
        System.out.println("\nSum: " + sum);

        // Average
        double avg = (double) sum / arr.length;
        System.out.println("Average: " + avg);

        // Count elements > 25
        int count = 0;
        for (int val : arr) {
            if (val > 25) count++;
        }
        System.out.println("Elements > 25: " + count);

        // Reverse print
        System.out.print("Reverse: ");
        for (int j = arr.length - 1; j >= 0; j--) {
            System.out.print(arr[j] + " ");
        }
        System.out.println();

        // Copy array
        int[] copy = new int[arr.length];
        for (int j = 0; j < arr.length; j++) {
            copy[j] = arr[j];
        }
        System.out.println("Copy: " + Arrays.toString(copy));

        // Fill with a value
        int[] filled = new int[5];
        Arrays.fill(filled, 42);
        System.out.println("Filled: " + Arrays.toString(filled));
    }
}
```

### Code Example 3: Array Memory Concept

```java
public class ArrayMemory {

    public static void main(String[] args) {

        // arr1 and arr2 point to the SAME array
        int[] arr1 = {1, 2, 3};
        int[] arr2 = arr1;  // arr2 = same memory address!

        System.out.println("arr1: " + java.util.Arrays.toString(arr1));
        System.out.println("arr2: " + java.util.Arrays.toString(arr2));

        arr2[0] = 99;  // modifies the SAME array

        System.out.println("\nAfter arr2[0] = 99:");
        System.out.println("arr1[0] = " + arr1[0]);  // 99 (changed!)
        System.out.println("Same object? " + (arr1 == arr2));  // true

        // To make an actual COPY:
        int[] arr3 = new int[arr1.length];
        for (int i = 0; i < arr1.length; i++) {
            arr3[i] = arr1[i];
        }
        // Or: int[] arr3 = arr1.clone();

        arr3[1] = 777;
        System.out.println("\nAfter arr3[1] = 777 (real copy):");
        System.out.println("arr1[1] = " + arr1[1]);  // 2 (unchanged!)
        System.out.println("arr3[1] = " + arr3[1]);  // 777
        System.out.println("Same object? " + (arr1 == arr3));  // false

        // Memory diagram:
        // arr1 ──────→ [1, 2, 3]   (heap)
        // arr2 ──────→ [1, 2, 3]   (same object!)
        // arr3 ──────→ [1, 2, 3]   (different copy!)
    }
}
```

---

## 4.2 Linear Search & Binary Search

### Concept Explanation

**Linear Search:** Check each element one by one (like looking at every book on a shelf). Works on ANY data. Slow for large data.

**Binary Search:** Divide and conquer! Look at the middle, decide which half to search next. MUCH faster but array MUST be sorted.

### Code Example 1: Linear Search

```java
public class LinearSearch {

    public static void main(String[] args) {

        int[] arr = {5, 2, 8, 1, 9, 3, 7, 4, 6};
        int target = 7;

        System.out.print("Array: ");
        printArray(arr);
        System.out.println("Searching for: " + target);

        int index = linearSearch(arr, target);
        if (index != -1) {
            System.out.println("Found at index: " + index);
        } else {
            System.out.println("Not found.");
        }

        // Search for something not present
        System.out.println("\nSearching for 99: " +
                          (linearSearch(arr, 99) == -1 ? "Not found" : "Found"));

        // String linear search
        String[] names = {"Alice", "Bob", "Charlie", "Diana"};
        String searchName = "Charlie";
        int nameIdx = linearSearchString(names, searchName);
        System.out.println("\nSearching for '" + searchName + "': Index " + nameIdx);

        // Find ALL occurrences
        int[] arr2 = {3, 1, 4, 1, 5, 9, 2, 6, 1};
        System.out.print("\nAll indices of 1 in ");
        printArray(arr2);
        System.out.print(": ");
        findAllOccurrences(arr2, 1);
    }

    public static int linearSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) return i;
        }
        return -1;
    }

    public static int linearSearchString(String[] arr, String target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i].equals(target)) return i;
        }
        return -1;
    }

    public static void findAllOccurrences(int[] arr, int target) {
        boolean found = false;
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                System.out.print(i + " ");
                found = true;
            }
        }
        if (!found) System.out.print("None");
        System.out.println();
    }

    public static void printArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i]);
            if (i < arr.length - 1) System.out.print(", ");
        }
        System.out.println();
    }
}
```

### Code Example 2: Binary Search

```java
import java.util.Arrays;

public class BinarySearchDemo {

    public static void main(String[] args) {

        // MUST be sorted!
        int[] arr = {2, 5, 8, 12, 16, 23, 38, 45, 56, 72};

        System.out.println("Sorted array: " + Arrays.toString(arr));

        int[] targets = {23, 2, 72, 99, 16};
        for (int t : targets) {
            int idx = binarySearch(arr, t);
            if (idx != -1) {
                System.out.println("Found " + t + " at index " + idx);
            } else {
                System.out.println(t + " not found");
            }
        }

        System.out.println("\n=== Step-by-Step ===");
        binarySearchDetailed(arr, 38);
    }

    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;  // middle index

            if (arr[mid] == target) {
                return mid;                        // found!
            } else if (arr[mid] < target) {
                left = mid + 1;                    // search right half
            } else {
                right = mid - 1;                   // search left half
            }
        }
        return -1;
    }

    public static void binarySearchDetailed(int[] arr, int target) {
        int left = 0, right = arr.length - 1;
        int step = 0;

        while (left <= right) {
            int mid = left + (right - left) / 2;
            step++;

            System.out.println("Step " + step + ": left=" + left +
                             "(" + arr[left] + "), right=" + right +
                             "(" + arr[right] + "), mid=" + mid +
                             "(" + arr[mid] + ")");

            if (arr[mid] == target) {
                System.out.println("Found at index " + mid + "!");
                return;
            } else if (arr[mid] < target) {
                System.out.println("  " + arr[mid] + " < " + target + " -> right half");
                left = mid + 1;
            } else {
                System.out.println("  " + arr[mid] + " > " + target + " -> left half");
                right = mid - 1;
            }
        }
        System.out.println("Not found.");
    }
}
```

---

## 4.3 Array Operations

### Code Example 1: Largest/Smallest, Reverse, Pairs

```java
public class ArrayOperations {

    public static void main(String[] args) {

        int[] arr = {5, 2, 8, 1, 9, 3, 7, 4, 6};

        System.out.print("Array: ");
        printArray(arr);

        // Find largest
        int largest = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > largest) largest = arr[i];
        }
        System.out.println("Largest: " + largest);

        // Find smallest
        int smallest = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] < smallest) smallest = arr[i];
        }
        System.out.println("Smallest: " + smallest);

        // Find largest and second largest
        int max1 = Integer.MIN_VALUE, max2 = Integer.MIN_VALUE;
        for (int num : arr) {
            if (num > max1) {
                max2 = max1;
                max1 = num;
            } else if (num > max2 && num != max1) {
                max2 = num;
            }
        }
        System.out.println("Largest: " + max1 + ", Second largest: " + max2);

        // Reverse the array
        System.out.println("\n=== Reverse ===");
        reverseArray(arr);
        System.out.print("Reversed: ");
        printArray(arr);
        reverseArray(arr);  // reverse back

        // Pairs in array
        System.out.println("\n=== All Pairs ===");
        printPairs(arr);
        System.out.println("Total pairs: " + (arr.length * (arr.length - 1) / 2));

        // Subarrays
        System.out.println("\n=== Subarrays of {1, 2, 3} ===");
        int[] smallArr = {1, 2, 3};
        printSubarrays(smallArr);
    }

    public static void reverseArray(int[] arr) {
        int i = 0, j = arr.length - 1;
        while (i < j) {
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
            i++;
            j--;
        }
    }

    public static void printPairs(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            for (int j = i + 1; j < arr.length; j++) {
                System.out.println("(" + arr[i] + ", " + arr[j] + ")");
            }
        }
    }

    public static void printSubarrays(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            for (int j = i; j < arr.length; j++) {
                System.out.print("[");
                for (int k = i; k <= j; k++) {
                    System.out.print(arr[k]);
                    if (k < j) System.out.print(", ");
                }
                System.out.println("]");
            }
        }
    }

    public static void printArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
}
```

### Code Example 2: Max Subarray Sum (Brute Force, Prefix Sum, Kadane's)

```java
public class MaxSubarraySum {

    public static void main(String[] args) {

        int[] arr = {1, -2, 6, -1, 3};
        System.out.print("Array: ");
        for (int n : arr) System.out.print(n + " ");
        System.out.println();

        // Method 1: Brute Force - O(n)
        int maxSum = bruteForce(arr);
        System.out.println("\nBrute Force: Max subarray sum = " + maxSum);

        // Method 2: Prefix Sum - O(n)
        maxSum = prefixSumMethod(arr);
        System.out.println("Prefix Sum: Max subarray sum = " + maxSum);

        // Method 3: Kadane's Algorithm - O(n) [BEST!]
        maxSum = kadane(arr);
        System.out.println("Kadane's: Max subarray sum = " + maxSum);

        // Edge case: all negative numbers
        int[] allNeg = {-3, -1, -7, -2};
        System.out.print("\nAll negative: ");
        for (int n : allNeg) System.out.print(n + " ");
        System.out.println("\nKadane's (modified): " + kadaneModified(allNeg));
    }

    // BRUTE FORCE: Check every possible subarray - O(n)
    public static int bruteForce(int[] arr) {
        int maxSum = Integer.MIN_VALUE;

        for (int i = 0; i < arr.length; i++) {
            for (int j = i; j < arr.length; j++) {
                int sum = 0;
                for (int k = i; k <= j; k++) {
                    sum += arr[k];  // sum from i to j
                }
                if (sum > maxSum) maxSum = sum;
            }
        }
        return maxSum;
    }

    // PREFIX SUM: Precompute sums to avoid inner loop - O(n)
    public static int prefixSumMethod(int[] arr) {
        int n = arr.length;

        // Create prefix sum array
        int[] prefix = new int[n];
        prefix[0] = arr[0];
        for (int i = 1; i < n; i++) {
            prefix[i] = prefix[i - 1] + arr[i];
        }

        int maxSum = Integer.MIN_VALUE;
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) {
                // Sum from i to j = prefix[j] - prefix[i-1]
                int sum = (i == 0) ? prefix[j] : prefix[j] - prefix[i - 1];
                if (sum > maxSum) maxSum = sum;
            }
        }
        return maxSum;
    }

    // KADANE'S ALGORITHM: O(n) - the BEST approach!
    // At each position, decide: extend current subarray or start fresh
    public static int kadane(int[] arr) {
        int maxSoFar = arr[0];      // best sum seen so far
        int maxEndingHere = arr[0];  // best sum ending at current position

        for (int i = 1; i < arr.length; i++) {
            // Either extend the subarray (maxEndingHere + arr[i])
            // or start a new subarray (arr[i])
            maxEndingHere = Math.max(arr[i], maxEndingHere + arr[i]);
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }
        return maxSoFar;
    }

    // Kadane's for ALL NEGATIVE numbers (returns the largest negative)
    public static int kadaneModified(int[] arr) {
        int maxSoFar = arr[0];
        int maxEndingHere = arr[0];

        for (int i = 1; i < arr.length; i++) {
            maxEndingHere = Math.max(arr[i], maxEndingHere + arr[i]);
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }
        return maxSoFar;
    }
}
```

### Code Example 3: Trapping Rainwater

```java
public class TrappingRainwater {

    public static void main(String[] args) {

        int[] height = {4, 2, 0, 6, 3, 2, 5};
        System.out.print("Heights: ");
        for (int h : height) System.out.print(h + " ");
        System.out.println();

        int water = trapRainwater(height);
        System.out.println("Trapped rainwater: " + water + " units");
    }

    // At each position, water trapped = min(maxLeft, maxRight) - height[i]
    // You need the tallest bar on the LEFT and RIGHT of current position
    public static int trapRainwater(int[] height) {
        int n = height.length;
        if (n <= 2) return 0;  // can't trap water with < 3 bars

        // Precompute max height from left for each position
        int[] leftMax = new int[n];
        leftMax[0] = height[0];
        for (int i = 1; i < n; i++) {
            leftMax[i] = Math.max(height[i], leftMax[i - 1]);
        }

        // Precompute max height from right for each position
        int[] rightMax = new int[n];
        rightMax[n - 1] = height[n - 1];
        for (int i = n - 2; i >= 0; i--) {
            rightMax[i] = Math.max(height[i], rightMax[i + 1]);
        }

        // Calculate trapped water
        int trappedWater = 0;
        for (int i = 0; i < n; i++) {
            int waterLevel = Math.min(leftMax[i], rightMax[i]);
            trappedWater += waterLevel - height[i];
        }

        return trappedWater;
    }

    // Two-pointer approach (more efficient, O(n) time, O(1) space)
    public static int trapRainwaterOptimized(int[] height) {
        int n = height.length;
        if (n <= 2) return 0;

        int left = 0, right = n - 1;
        int leftMax = 0, rightMax = 0;
        int water = 0;

        while (left < right) {
            if (height[left] < height[right]) {
                if (height[left] >= leftMax) {
                    leftMax = height[left];
                } else {
                    water += leftMax - height[left];
                }
                left++;
            } else {
                if (height[right] >= rightMax) {
                    rightMax = height[right];
                } else {
                    water += rightMax - height[right];
                }
                right--;
            }
        }
        return water;
    }
}
```

### Code Example 4: Buy and Sell Stocks

```java
public class BuySellStocks {

    public static void main(String[] args) {

        int[] prices = {7, 1, 5, 3, 6, 4};
        System.out.print("Stock prices: ");
        for (int p : prices) System.out.print(p + " ");
        System.out.println();

        int maxProfit = maxProfit(prices);
        System.out.println("Max profit: " + maxProfit);

        // Buy at day 2 (price=1), sell at day 5 (price=6) => profit = 5

        int[] prices2 = {7, 6, 4, 3, 1};
        System.out.print("\nFalling prices: ");
        for (int p : prices2) System.out.print(p + " ");
        System.out.println("\nMax profit: " + maxProfit(prices2));  // 0
    }

    // At each day, we know the LOWEST price seen so far.
    // Sell today: profit = today's price - lowest price seen so far.
    // Keep track of max profit.
    public static int maxProfit(int[] prices) {
        int buyPrice = Integer.MAX_VALUE;  // smallest price seen so far
        int maxProfit = 0;                  // best profit

        for (int i = 0; i < prices.length; i++) {
            if (prices[i] < buyPrice) {
                buyPrice = prices[i];       // found a better day to buy
            } else {
                int profit = prices[i] - buyPrice;  // profit if we sell today
                if (profit > maxProfit) {
                    maxProfit = profit;     // update best profit
                }
            }
        }
        return maxProfit;
    }
}
```

---

## 4.4 Basic Sorting Algorithms

### Concept Explanation

Sorting puts elements in order (smallest to largest). Like arranging books by height.

- **Bubble Sort:** Repeatedly swap adjacent elements if they're in wrong order. Bigger elements "bubble up" to the end.
- **Selection Sort:** Find the smallest element, put it at the front. Repeat.
- **Insertion Sort:** Take elements one by one and insert them in the correct position. Like sorting cards in your hand.
- **Arrays.sort():** Java's built-in sort (uses Dual-Pivot QuickSort). FASTEST — use this in real life!

### Code Example 1: Bubble Sort

```java
import java.util.Arrays;

public class BubbleSort {

    public static void main(String[] args) {

        int[] arr = {5, 2, 8, 1, 3};
        System.out.println("Original: " + Arrays.toString(arr));

        bubbleSort(arr);
        System.out.println("Sorted: " + Arrays.toString(arr));

        // With optimization (stops early if already sorted)
        int[] arr2 = {3, 1, 4, 2, 5};
        System.out.println("\nOriginal: " + Arrays.toString(arr2));
        bubbleSortOptimized(arr2);
        System.out.println("Sorted: " + Arrays.toString(arr2));
    }

    // Basic bubble sort
    public static void bubbleSort(int[] arr) {
        int n = arr.length;

        // Outer loop: number of passes (n-1 passes needed)
        for (int i = 0; i < n - 1; i++) {
            // Inner loop: compare adjacent elements
            // After each pass, the largest element settles at the end
            for (int j = 0; j < n - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap: wrong order!
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    // Optimized: stop if no swaps happened (already sorted)
    public static void bubbleSortOptimized(int[] arr) {
        int n = arr.length;

        for (int i = 0; i < n - 1; i++) {
            boolean swapped = false;

            for (int j = 0; j < n - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

            // If no swaps, array is already sorted!
            if (!swapped) {
                System.out.println("Already sorted! Stopped early at pass " + (i + 1));
                break;
            }
        }
    }
}
```

### Code Example 2: Selection Sort

```java
import java.util.Arrays;

public class SelectionSort {

    public static void main(String[] args) {

        int[] arr = {5, 2, 8, 1, 3};
        System.out.println("Original: " + Arrays.toString(arr));

        selectionSort(arr);
        System.out.println("Sorted:   " + Arrays.toString(arr));
    }

    // Find the smallest element, swap it with position 0
    // Then find the next smallest, swap with position 1
    // Continue until sorted
    public static void selectionSort(int[] arr) {
        int n = arr.length;

        for (int i = 0; i < n - 1; i++) {
            // Assume current position has the smallest element
            int minIdx = i;

            // Find the actual smallest in the remaining unsorted part
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIdx]) {
                    minIdx = j;  // found a smaller element
                }
            }

            // Swap the smallest element with position i
            int temp = arr[i];
            arr[i] = arr[minIdx];
            arr[minIdx] = temp;
        }
    }
}
```

### Code Example 3: Insertion Sort

```java
import java.util.Arrays;

public class InsertionSort {

    public static void main(String[] args) {

        int[] arr = {5, 2, 8, 1, 3};
        System.out.println("Original: " + Arrays.toString(arr));

        insertionSort(arr);
        System.out.println("Sorted:   " + Arrays.toString(arr));
    }

    // Pick an element from unsorted part, insert it at correct position
    // in the sorted part. Like sorting playing cards in your hand.
    public static void insertionSort(int[] arr) {
        int n = arr.length;

        // Start from index 1 (first element is trivially "sorted")
        for (int i = 1; i < n; i++) {
            int current = arr[i];      // the element we need to place
            int j = i - 1;             // last element of sorted part

            // Shift elements right until we find the right spot
            while (j >= 0 && arr[j] > current) {
                arr[j + 1] = arr[j];   // shift right
                j--;
            }

            // Place current element in its correct position
            arr[j + 1] = current;
        }
    }
}
```

### Code Example 4: Inbuilt Sort & Counting Sort

```java
import java.util.Arrays;
import java.util.Collections;

public class InbuiltSorting {

    public static void main(String[] args) {

        // Arrays.sort() - Java's built-in sort (FAST!)
        int[] arr = {5, 2, 8, 1, 3, 6, 7, 4};
        System.out.println("Original: " + Arrays.toString(arr));

        Arrays.sort(arr);  // sorts in ascending order
        System.out.println("Sorted:   " + Arrays.toString(arr));

        // Sort in descending order (need Integer[] not int[])
        Integer[] arrDesc = {5, 2, 8, 1, 3};
        Arrays.sort(arrDesc, Collections.reverseOrder());
        System.out.println("\nDescending: " + Arrays.toString(arrDesc));

        // Sort a specific range
        int[] arr2 = {9, 3, 7, 1, 5, 8, 2, 4, 6};
        Arrays.sort(arr2, 2, 6);  // sort from index 2 to 5 (exclusive of 6)
        System.out.println("\nRange sorted (2 to 5): " + Arrays.toString(arr2));

        // Sort strings
        String[] names = {"Charlie", "Alice", "Bob"};
        Arrays.sort(names);
        System.out.println("\nSorted names: " + Arrays.toString(names));
    }
}

// COUNTING SORT: For when you know the range of values (e.g., 0-100)
// Count how many times each value appears, then reconstruct sorted array
class CountingSort {

    public static void main(String[] args) {

        int[] arr = {4, 2, 2, 8, 3, 3, 1};
        System.out.println("Original: " + Arrays.toString(arr));

        countingSort(arr);
        System.out.println("Sorted:   " + Arrays.toString(arr));
    }

    public static void countingSort(int[] arr) {
        // Find the range (largest element)
        int largest = Integer.MIN_VALUE;
        for (int num : arr) {
            if (num > largest) largest = num;
        }

        // Count array: size = largest + 1 (for 0 to largest)
        int[] count = new int[largest + 1];

        // Count occurrences
        for (int num : arr) {
            count[num]++;
        }

        // Reconstruct sorted array
        int idx = 0;
        for (int i = 0; i < count.length; i++) {
            while (count[i] > 0) {
                arr[idx] = i;     // place value i
                idx++;
                count[i]--;       // decrease count
            }
        }
    }
}
```

---

## 4.5 2D Arrays

### Concept Explanation

A 2D array is like a **grid** or **spreadsheet** with rows and columns. Think of it as an array OF arrays (each row is itself an array).

- `int[][] matrix = new int[3][4]` → 3 rows, 4 columns
- `matrix[row][col]` to access a cell
- **Row-major:** Process row by row (outer loop = rows)
- **Column-major:** Process column by column (outer loop = columns)

### Code Example 1: Creating and Traversing 2D Arrays

```java
import java.util.Arrays;

public class TwoDArrays {

    public static void main(String[] args) {

        // Method 1: declare and allocate
        int[][] matrix = new int[3][4];  // 3 rows, 4 columns
        System.out.println("3x4 matrix created (default 0s):");

        // Fill with values
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 4; j++) {
                matrix[i][j] = i * 4 + j + 1;  // 1 to 12
            }
        }

        // Print: row-major traversal (outer loop = rows)
        System.out.println("\nRow-major traversal:");
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + "\t");
            }
            System.out.println();
        }

        // Method 2: initialize directly
        int[][] arr = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        System.out.println("\n3x3 matrix:");
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr[i].length; j++) {
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

        // Column-major traversal (outer loop = columns)
        System.out.println("\nColumn-major traversal:");
        for (int j = 0; j < arr[0].length; j++) {
            for (int i = 0; i < arr.length; i++) {
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }

        // Jagged array (rows have different lengths)
        int[][] jagged = new int[3][];
        jagged[0] = new int[2];  // row 0: 2 columns
        jagged[1] = new int[4];  // row 1: 4 columns
        jagged[2] = new int[3];  // row 2: 3 columns

        System.out.println("\nJagged array lengths: " +
                          jagged[0].length + ", " +
                          jagged[1].length + ", " +
                          jagged[2].length);

        // Length of 2D array
        System.out.println("\nNumber of rows: " + arr.length);
        System.out.println("Number of columns: " + arr[0].length);
    }
}
```

### Code Example 2: Spiral Matrix

```java
public class SpiralMatrix {

    public static void main(String[] args) {

        int[][] matrix = {
            {1,  2,  3,  4},
            {5,  6,  7,  8},
            {9, 10, 11, 12},
            {13, 14, 15, 16}
        };

        System.out.println("Original matrix:");
        printMatrix(matrix);

        System.out.println("\nSpiral order:");
        printSpiral(matrix);
    }

    // Traverse matrix in spiral order: right -> down -> left -> up -> repeat
    public static void printSpiral(int[][] matrix) {
        int startRow = 0;
        int endRow = matrix.length - 1;
        int startCol = 0;
        int endCol = matrix[0].length - 1;

        while (startRow <= endRow && startCol <= endCol) {
            // 1. Go RIGHT (top row, left to right)
            for (int j = startCol; j <= endCol; j++) {
                System.out.print(matrix[startRow][j] + " ");
            }
            startRow++;  // move top boundary down

            // 2. Go DOWN (right column, top to bottom)
            for (int i = startRow; i <= endRow; i++) {
                System.out.print(matrix[i][endCol] + " ");
            }
            endCol--;  // move right boundary left

            // 3. Go LEFT (bottom row, right to left)
            if (startRow <= endRow) {  // still have rows?
                for (int j = endCol; j >= startCol; j--) {
                    System.out.print(matrix[endRow][j] + " ");
                }
                endRow--;  // move bottom boundary up
            }

            // 4. Go UP (left column, bottom to top)
            if (startCol <= endCol) {  // still have columns?
                for (int i = endRow; i >= startRow; i--) {
                    System.out.print(matrix[i][startCol] + " ");
                }
                startCol++;  // move left boundary right
            }
        }
        System.out.println();
    }

    public static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int val : row) {
                System.out.print(val + "\t");
            }
            System.out.println();
        }
    }
}
```

### Code Example 3: Diagonal Sum

```java
public class DiagonalSum {

    public static void main(String[] args) {

        int[][] matrix = {
            {1, 2, 3, 4},
            {5, 6, 7, 8},
            {9, 10, 11, 12},
            {13, 14, 15, 16}
        };

        System.out.println("Matrix:");
        for (int[] row : matrix) {
            for (int val : row) System.out.print(val + "\t");
            System.out.println();
        }

        int sum = diagonalSum(matrix);
        System.out.println("\nSum of both diagonals: " + sum);
    }

    // Sum primary diagonal (top-left to bottom-right) +
    // secondary diagonal (top-right to bottom-left)
    // Avoid double-counting the center element for odd-sized matrices
    public static int diagonalSum(int[][] matrix) {
        int sum = 0;
        int n = matrix.length;

        for (int i = 0; i < n; i++) {
            // Primary diagonal: row = col (matrix[i][i])
            sum += matrix[i][i];

            // Secondary diagonal: row + col = n - 1 (matrix[i][n-1-i])
            // Don't double-count the middle element when n is odd
            if (i != n - 1 - i) {  // not the center element
                sum += matrix[i][n - 1 - i];
            }
        }
        return sum;
    }
}
```

### Code Example 4: Search in Sorted Matrix (Staircase Search)

```java
public class StaircaseSearch {

    public static void main(String[] args) {

        // Matrix sorted: each row & column is in ascending order
        int[][] matrix = {
            {10, 20, 30, 40},
            {15, 25, 35, 45},
            {27, 29, 37, 48},
            {32, 33, 39, 50}
        };

        System.out.println("Matrix:");
        for (int[] row : matrix) {
            for (int val : row) System.out.print(val + "\t");
            System.out.println();
        }

        int target = 37;
        System.out.println("\nSearching for: " + target);
        System.out.println(search(matrix, target));

        target = 100;
        System.out.println("\nSearching for: " + target);
        System.out.println(search(matrix, target));
    }

    // Start from top-right corner. If current > target, go left.
    // If current < target, go down. This creates a "staircase" path.
    // O(n + m) time.
    public static boolean search(int[][] matrix, int target) {
        int row = 0;
        int col = matrix[0].length - 1;  // start at top-right

        while (row < matrix.length && col >= 0) {
            int current = matrix[row][col];

            System.out.println("  at (" + row + "," + col + ") = " + current);

            if (current == target) {
                System.out.println("Found at (" + row + "," + col + ")!");
                return true;
            } else if (current > target) {
                col--;  // go LEFT (values decrease going left)
            } else {
                row++;  // go DOWN (values increase going down)
            }
        }

        System.out.println("Not found.");
        return false;
    }
}
```

---

# PART 5: STRINGS

---

## 5.1 String Basics

### Concept Explanation

A **String** is a sequence of characters. Think of it as a necklace of beads where each bead is a character.

- Strings are **immutable** — you can't change a string once created. Any "change" creates a NEW string.
- `StringBuilder` and `StringBuffer` are **mutable** — you can modify them without creating new objects.
- Use `StringBuilder` for efficiency when doing lots of string operations.

### Code Example 1: String Creation and Methods

```java
import java.util.Arrays;

public class StringBasics {

    public static void main(String[] args) {

        // Method 1: String literal (stored in String pool)
        String str1 = "Hello";

        // Method 2: Using new keyword (stored in heap)
        String str2 = new String("World");

        // Method 3: From char array
        char[] chars = {'J', 'a', 'v', 'a'};
        String str3 = new String(chars);

        System.out.println("str1: " + str1);
        System.out.println("str2: " + str2);
        System.out.println("str3: " + str3);

        // Common String methods
        String s = "  Hello World!  ";

        System.out.println("\n=== String Methods ===");
        System.out.println("Original: '" + s + "'");
        System.out.println("Length: " + s.length());
        System.out.println("Char at 1: " + s.charAt(1));
        System.out.println("To uppercase: " + s.toUpperCase());
        System.out.println("To lowercase: " + s.toLowerCase());
        System.out.println("Trim: '" + s.trim() + "'");
        System.out.println("Substring (0,5): '" + s.substring(0, 5) + "'");
        System.out.println("Substring (8): '" + s.substring(8) + "'");
        System.out.println("Replace 'l' with 'x': " + s.replace('l', 'x'));
        System.out.println("Contains 'World': " + s.contains("World"));
        System.out.println("Starts with '  He': " + s.startsWith("  He"));
        System.out.println("Ends with '!  ': " + s.endsWith("!  "));

        // Index of
        System.out.println("\nIndex of 'o': " + s.indexOf('o'));
        System.out.println("Index of 'o' (from 5): " + s.indexOf('o', 5));
        System.out.println("Last index of 'l': " + s.lastIndexOf('l'));

        // Convert to char array
        char[] charArr = s.toCharArray();
        System.out.println("\nChar array: " + Arrays.toString(charArr));

        // Split
        String sentence = "apple,banana,orange";
        String[] fruits = sentence.split(",");
        System.out.println("Split by comma: " + Arrays.toString(fruits));

        // Join
        String joined = String.join(" - ", fruits);
        System.out.println("Joined: " + joined);

        // isEmpty / isBlank
        System.out.println("\n'  '.isEmpty(): " + "  ".isEmpty());
        System.out.println("'  '.isBlank(): " + "  ".isBlank());
    }
}
```

### Code Example 2: String Comparison

```java
public class StringComparison {

    public static void main(String[] args) {

        // == compares REFERENCES (memory addresses), NOT the actual text!
        // .equals() compares the actual TEXT

        String s1 = "Hello";
        String s2 = "Hello";      // same literal - points to same object in pool
        String s3 = new String("Hello");  // different object in heap

        System.out.println("s1 = \"" + s1 + "\"");
        System.out.println("s2 = \"" + s2 + "\"");
        System.out.println("s3 = new String(\"Hello\")\n");

        System.out.println("s1 == s2: " + (s1 == s2));     // true (same pool object)
        System.out.println("s1 == s3: " + (s1 == s3));     // false (different objects!)
        System.out.println("s1.equals(s2): " + s1.equals(s2)); // true
        System.out.println("s1.equals(s3): " + s1.equals(s3)); // true (compares text!)

        // Case-insensitive comparison
        String s4 = "hello";
        System.out.println("\ns4 = \"hello\"");
        System.out.println("s1.equalsIgnoreCase(s4): " + s1.equalsIgnoreCase(s4));

        // compareTo: compares lexicographically
        System.out.println("\n\"Apple\".compareTo(\"Banana\"): " + "Apple".compareTo("Banana"));
        System.out.println("\"Banana\".compareTo(\"Apple\"): " + "Banana".compareTo("Apple"));
        System.out.println("\"Hello\".compareTo(\"Hello\"): " + "Hello".compareTo("Hello"));
        // Negative: first string comes before second
        // Positive: first string comes after second
        // Zero: equal

        // IMPORTANT RULE: ALWAYS use .equals() for Strings, never == !
        // == only works for literals, but fails for new String() or dynamic strings
    }
}
```

### Code Example 3: StringBuilder and StringBuffer

```java
public class StringBuilderDemo {

    public static void main(String[] args) {

        // StringBuilder is MUTABLE - you can modify it without creating new objects
        // Much more efficient than String when doing lots of concatenations

        System.out.println("=== StringBuilder ===");

        // Create
        StringBuilder sb = new StringBuilder("Hello");

        System.out.println("Initial: " + sb);
        System.out.println("Length: " + sb.length());

        // Append (add to end) - MODIFIES the same object!
        sb.append(" World");
        System.out.println("\nAfter append: " + sb);

        sb.append("!").append(" How").append(" are").append(" you?");
        System.out.println("Chained append: " + sb);

        // Insert at index
        sb.insert(5, " Beautiful");
        System.out.println("\nAfter insert at 5: " + sb);

        // Replace
        sb.replace(6, 15, "Amazing");
        System.out.println("After replace: " + sb);

        // Delete
        sb.delete(6, 13);
        System.out.println("After delete: " + sb);

        // Reverse
        sb.reverse();
        System.out.println("Reversed: " + sb);
        sb.reverse();  // reverse back

        // Char operations
        System.out.println("\nChar at 0: " + sb.charAt(0));
        sb.setCharAt(0, 'h');
        System.out.println("After setCharAt: " + sb);

        // Convert to String
        String finalStr = sb.toString();
        System.out.println("As String: " + finalStr);

        // Performance comparison
        System.out.println("\n=== Performance Comparison ===");
        long start, end;

        // String (slow)
        start = System.nanoTime();
        String str = "";
        for (int i = 0; i < 10000; i++) {
            str += "a";  // creates a NEW object EVERY TIME!
        }
        end = System.nanoTime();
        System.out.println("String concat: " + (end - start) / 1000000 + "ms");

        // StringBuilder (fast)
        start = System.nanoTime();
        StringBuilder sb2 = new StringBuilder();
        for (int i = 0; i < 10000; i++) {
            sb2.append("a");  // modifies the SAME object
        }
        end = System.nanoTime();
        System.out.println("StringBuilder: " + (end - start) / 1000000 + "ms");
    }
}
```

---

## 5.2 String Problems

### Code Example 1: Shortest Path, Palindrome, Anagram

```java
public class StringProblems1 {

    public static void main(String[] args) {

        // === PROBLEM 1: Shortest Path ===
        // Given directions: N, S, E, W, find the shortest path to destination
        System.out.println("=== Shortest Path ===");
        String path = "WNEENESENNN";
        System.out.println("Path: " + path);
        String shortest = shortestPath(path);
        System.out.println("Shortest path: " + shortest);

        // === PROBLEM 2: Palindrome Check ===
        System.out.println("\n=== Palindrome Check ===");
        String[] tests = {"racecar", "noon", "hello", "madam", "A man a plan a canal Panama"};
        for (String test : tests) {
            System.out.println("\"" + test + "\" is palindrome? " +
                             isPalindrome(test));
        }

        // === PROBLEM 3: Anagram Check ===
        System.out.println("\n=== Anagram Check ===");
        String a1 = "race", a2 = "care";
        System.out.println("\"" + a1 + "\" and \"" + a2 + "\" are anagrams? " +
                          areAnagrams(a1, a2));

        String b1 = "hello", b2 = "world";
        System.out.println("\"" + b1 + "\" and \"" + b2 + "\" are anagrams? " +
                          areAnagrams(b1, b2));
    }

    // Shortest path: count N, S, E, W, then compute displacement
    public static String shortestPath(String path) {
        int x = 0, y = 0;

        // Count movements
        for (int i = 0; i < path.length(); i++) {
            char dir = path.charAt(i);
            if (dir == 'N') y++;
            else if (dir == 'S') y--;
            else if (dir == 'E') x++;
            else if (dir == 'W') x--;
        }

        // Now we need to go from (0,0) to (x,y)
        // Build the shortest path: first N/S, then E/W (or vice versa)
        StringBuilder sb = new StringBuilder();

        // Going North? (y > 0) or South? (y < 0)
        if (y > 0) {
            for (int i = 0; i < y; i++) sb.append('N');
        } else {
            for (int i = 0; i < -y; i++) sb.append('S');
        }

        // Going East? (x > 0) or West? (x < 0)
        if (x > 0) {
            for (int i = 0; i < x; i++) sb.append('E');
        } else {
            for (int i = 0; i < -x; i++) sb.append('W');
        }

        return sb.toString();
    }

    // Palindrome: string reads the same forwards and backwards
    public static boolean isPalindrome(String s) {
        // Normalize: remove spaces and convert to lowercase
        s = s.toLowerCase().replaceAll(" ", "");

        int i = 0, j = s.length() - 1;

        while (i < j) {
            if (s.charAt(i) != s.charAt(j)) {
                return false;  // mismatch found
            }
            i++;
            j--;
        }
        return true;  // all characters matched
    }

    // Anagrams: two strings that use the same characters (same frequency)
    public static boolean areAnagrams(String s1, String s2) {
        if (s1.length() != s2.length()) return false;

        // Count frequency of each character (assume lowercase letters)
        int[] freq = new int[26];

        for (int i = 0; i < s1.length(); i++) {
            freq[s1.charAt(i) - 'a']++;   // count in s1
            freq[s2.charAt(i) - 'a']--;   // uncount in s2
        }

        // If all counts are 0, they're anagrams
        for (int count : freq) {
            if (count != 0) return false;
        }
        return true;
    }
}
```

### Code Example 2: String Compression

```java
public class StringProblems2 {

    public static void main(String[] args) {

        // === PROBLEM 4: Uppercase First Letter of Each Word ===
        System.out.println("=== Uppercase First Letter ===");
        String sentence = "hi, i am learning java";
        System.out.println("Original: " + sentence);
        System.out.println("Converted: " + toUpperCase(sentence));

        // === PROBLEM 5: String Compression ===
        System.out.println("\n=== String Compression ===");
        String s1 = "aaabbcccdd";
        System.out.println("Original: " + s1);
        System.out.println("Compressed: " + compress(s1));

        String s2 = "abc";
        System.out.println("Original: " + s2);
        System.out.println("Compressed: " + compress(s2));  // "abc" (not "a1b1c1")
    }

    // Convert first letter of each word to uppercase
    public static String toUpperCase(String str) {
        StringBuilder sb = new StringBuilder();
        boolean nextUpper = true;  // next char should be uppercase

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);

            if (ch == ' ') {
                nextUpper = true;    // next letter should be uppercase
                sb.append(ch);       // keep the space
            } else if (nextUpper) {
                sb.append(Character.toUpperCase(ch));  // capitalize
                nextUpper = false;                      // reset
            } else {
                sb.append(ch);       // keep as is
            }
        }

        return sb.toString();
    }

    // Compress string: "aaabbc" -> "a3b2c1"
    // If compressed isn't shorter, return original
    public static String compress(String str) {
        StringBuilder sb = new StringBuilder();

        for (int i = 0; i < str.length(); i++) {
            int count = 1;

            // Count consecutive same characters
            while (i + 1 < str.length() && str.charAt(i) == str.charAt(i + 1)) {
                count++;
                i++;
            }

            // Append character
            sb.append(str.charAt(i));

            // Append count (only if > 1)
            if (count > 1) {
                sb.append(count);
            }
        }

        // Return whichever is shorter
        String compressed = sb.toString();
        return compressed.length() < str.length() ? compressed : str;
    }

    // Alternative: check if character is a vowel
    public static boolean isVowel(char ch) {
        ch = Character.toLowerCase(ch);
        return ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u';
    }

    // Count vowels in a string
    public static int countVowels(String str) {
        int count = 0;
        for (int i = 0; i < str.length(); i++) {
            if (isVowel(str.charAt(i))) count++;
        }
        return count;
    }
}
```

---

# PART 6: BIT MANIPULATION

---

## 6.1 Binary Number System & Bitwise Operators

### Concept Explanation

Computers work with **binary** (0s and 1s). Bit manipulation lets you operate directly on those bits — it's incredibly fast and memory-efficient.

**Binary:** Base-2 number system. Each position is a power of 2.
- Decimal 5 = Binary 101 (1*4 + 0*2 + 1*1)
- Decimal 10 = Binary 1010 (1*8 + 0*4 + 1*2 + 0*1)

**Bitwise operators** work on individual bits:
- `&` (AND): 1 if BOTH bits are 1
- `|` (OR): 1 if AT LEAST ONE bit is 1
- `^` (XOR): 1 if bits are DIFFERENT
- `~` (NOT): flips ALL bits
- `<<` (LEFT SHIFT): shifts bits left (multiply by 2)
- `>>` (RIGHT SHIFT): shifts bits right (divide by 2)

### Code Example 1: Binary Basics & Bitwise Operators

```java
public class BitwiseBasics {

    public static void main(String[] args) {

        System.out.println("=== Binary Number System ===");

        // Convert decimal to binary string
        int a = 5;   // binary: 101
        int b = 3;   // binary: 011

        System.out.println("a = " + a + " (binary: " + Integer.toBinaryString(a) + ")");
        System.out.println("b = " + b + " (binary: " + Integer.toBinaryString(b) + ")");

        // Bitwise AND (&)
        // 101 & 011 = 001 (which is decimal 1)
        System.out.println("\n=== Bitwise AND (&) ===");
        System.out.println(a + " & " + b + " = " + (a & b));
        System.out.println("  101");
        System.out.println("& 011");
        System.out.println("  ---");
        System.out.println("  001 = " + (a & b));
        // Truth table: 1&1=1, 1&0=0, 0&1=0, 0&0=0

        // Bitwise OR (|)
        // 101 | 011 = 111 (decimal 7)
        System.out.println("\n=== Bitwise OR (|) ===");
        System.out.println(a + " | " + b + " = " + (a | b));
        System.out.println("  101");
        System.out.println("| 011");
        System.out.println("  ---");
        System.out.println("  111 = " + (a | b));
        // Truth table: 1|1=1, 1|0=1, 0|1=1, 0|0=0

        // Bitwise XOR (^)
        // 101 ^ 011 = 110 (decimal 6)
        System.out.println("\n=== Bitwise XOR (^) ===");
        System.out.println(a + " ^ " + b + " = " + (a ^ b));
        System.out.println("  101");
        System.out.println("^ 011");
        System.out.println("  ---");
        System.out.println("  110 = " + (a ^ b));
        // Truth table: 1^1=0, 1^0=1, 0^1=1, 0^0=0
        // XOR is like "does this bit differ?"

        // Bitwise NOT (~)
        // ~5 = ~0101 = ...11111010 (infinite leading 1s in 2's complement)
        System.out.println("\n=== Bitwise NOT (~) ===");
        System.out.println("~" + a + " = " + (~a));
        System.out.println("  ~101 = ...11111010 (flips ALL bits)");

        // Left Shift (<<)
        // Shifts bits left, fills with 0 on right. Each shift = multiply by 2
        System.out.println("\n=== Left Shift (<<) ===");
        System.out.println(a + " << 1 = " + (a << 1));  // 5*2 = 10
        System.out.println(a + " << 2 = " + (a << 2));  // 5*4 = 20
        System.out.println("  101 << 1 = 1010 (which is 10)");

        // Right Shift (>>)
        // Shifts bits right, fills with sign bit. Each shift = divide by 2
        System.out.println("\n=== Right Shift (>>) ===");
        System.out.println(a + " >> 1 = " + (a >> 1));  // 5/2 = 2
        System.out.println("  101 >> 1 = 10 (which is 2)");

        // Unsigned Right Shift (>>>)
        // Always fills with 0 (doesn't preserve sign)
        int negative = -5;
        System.out.println("\n" + negative + " >> 1 = " + (negative >> 1));
        System.out.println(negative + " >>> 1 = " + (negative >>> 1));
    }
}
```

### Code Example 2: Get, Set, Clear, Update Bit

```java
public class BitOperations {

    public static void main(String[] args) {

        int num = 5;  // binary: 101

        System.out.println("Number: " + num + " (" + Integer.toBinaryString(num) + ")\n");

        // === GET BIT: Check if the bit at position i is 0 or 1 ===
        // Create a mask: 1 << i (put 1 at position i)
        // AND with mask: if result is 0, bit is 0; if non-zero, bit is 1
        int position = 2;  // check bit at position 2 (0-indexed from right)

        int bitMask = 1 << position;           // 1 << 2 = 100 (binary)
        int result = num & bitMask;            // 101 & 100 = 100 (non-zero!)

        System.out.println("=== GET BIT at position " + position + " ===");
        System.out.println("Bit mask: " + Integer.toBinaryString(bitMask) + " (1<<" + position + ")");
        System.out.println(num + " & " + bitMask + " = " + result);
        System.out.println("Bit at " + position + " is: " + (result == 0 ? "0" : "1"));

        // === SET BIT: Set the bit at position i to 1 ===
        // Create mask: 1 << i, OR with number
        position = 1;
        bitMask = 1 << position;               // 1 << 1 = 010
        int setResult = num | bitMask;          // 101 | 010 = 111 (7)

        System.out.println("\n=== SET BIT at position " + position + " ===");
        System.out.println("Before: " + num + " (" + Integer.toBinaryString(num) + ")");
        System.out.println("After:  " + setResult + " (" + Integer.toBinaryString(setResult) + ")");

        // === CLEAR BIT: Set the bit at position i to 0 ===
        // Create mask: 1 << i, NOT it, AND with number
        num = 7;  // 111
        position = 2;
        bitMask = 1 << position;               // 100
        int notMask = ~bitMask;                // ...11111011
        int clearResult = num & notMask;        // 111 & ...11111011 = 011 (3)

        System.out.println("\n=== CLEAR BIT at position " + position + " ===");
        System.out.println("Before: " + num + " (" + Integer.toBinaryString(num) + ")");
        System.out.println("After:  " + clearResult + " (" + Integer.toBinaryString(clearResult) + ")");

        // === UPDATE BIT: Set bit to 0 or 1 at position i ===
        // Clear the bit first (make it 0), then set it to desired value
        num = 5;  // 101
        position = 1;
        int setTo = 1;  // we want to set this bit to 1

        // Step 1: Clear the bit
        bitMask = 1 << position;
        num = num & (~bitMask);                // clear the bit

        // Step 2: Set to desired value
        int newMask = (setTo << position);
        num = num | newMask;

        System.out.println("\n=== UPDATE BIT at position " + position + " to " + setTo + " ===");
        System.out.println("Result: " + num + " (" + Integer.toBinaryString(num) + ")");

        // PRACTICAL: Check if a number is even or odd
        System.out.println("\n=== Even/Odd using bitwise ===");
        // Last bit (position 0) is 1 for odd, 0 for even
        int testNum = 7;
        System.out.println(testNum + " is " +
                          ((testNum & 1) == 0 ? "Even" : "Odd"));
    }
}
```

### Code Example 3: Power of 2, Count Set Bits, Fast Exponentiation

```java
public class BitAlgorithms {

    public static void main(String[] args) {

        // === CHECK IF NUMBER IS POWER OF 2 ===
        // A power of 2 has exactly ONE bit set (e.g., 1, 2, 4, 8, 16)
        // Trick: n & (n-1) will be 0 for powers of 2
        System.out.println("=== Power of 2 ===");
        int[] nums = {1, 2, 3, 4, 5, 8, 16, 32, 63, 64};
        for (int n : nums) {
            System.out.println(n + " is power of 2? " + isPowerOfTwo(n));
        }

        // === COUNT SET BITS (count number of 1s in binary) ===
        System.out.println("\n=== Count Set Bits ===");
        int[] testNums = {5, 7, 15, 31, 63};
        for (int n : testNums) {
            System.out.println(n + " (" + Integer.toBinaryString(n) +
                             ") has " + countSetBits(n) + " set bits");
        }

        // === FAST EXPONENTIATION (a^b in O(log b)) ===
        System.out.println("\n=== Fast Exponentiation ===");
        int base = 3;
        int exp = 5;
        System.out.println(base + "^" + exp + " = " + fastExpo(base, exp));
        System.out.println("Expected: " + (int)Math.pow(base, exp));

        // === CLEAR RANGE OF BITS ===
        System.out.println("\n=== Clear Range of Bits ===");
        int num = 63;  // 111111
        int start = 1, end = 4;  // clear bits 1 through 4
        System.out.println("Before: " + num + " (" + Integer.toBinaryString(num) + ")");
        int result = clearBitsInRange(num, start, end);
        System.out.println("After:  " + result + " (" + Integer.toBinaryString(result) + ")");
    }

    // Check if n is a power of 2
    // Example: n=8 (1000), n-1=7 (0111), 1000 & 0111 = 0000 = 0
    public static boolean isPowerOfTwo(int n) {
        if (n <= 0) return false;        // 0 and negative can't be power of 2
        return (n & (n - 1)) == 0;        // KEY property of powers of 2!
    }

    // Count number of 1 bits in binary representation
    // Brian Kernighan's algorithm: n & (n-1) removes the rightmost set bit
    public static int countSetBits(int n) {
        int count = 0;
        while (n > 0) {
            n = n & (n - 1);  // remove the rightmost set bit
            count++;          // one more bit counted
        }
        return count;
    }

    // Fast exponentiation: compute a^b using binary exponentiation
    // 3^5 = 3^101 = 3^4 * 3^1 = 81 * 3 = 243
    public static int fastExpo(int a, int b) {
        int result = 1;

        while (b > 0) {
            if ((b & 1) == 1) {        // if current bit of b is 1
                result = result * a;    // multiply result by a^power
            }
            a = a * a;                  // square a (a^1, a^2, a^4, a^8...)
            b = b >> 1;                 // shift b right (next bit)
        }

        return result;
    }

    // Clear bits from position 'start' to 'end' (inclusive)
    public static int clearBitsInRange(int n, int start, int end) {
        // Create a mask with 0s from start to end, 1s elsewhere
        int leftMask = (~0) << (end + 1);     // 1s to the left of range
        int rightMask = (1 << start) - 1;      // 1s to the right of range
        int mask = leftMask | rightMask;        // combine

        return n & mask;                        // clear the range
    }
}
```

---

# PART 7: OBJECT-ORIENTED PROGRAMMING (OOPs)

---

## 7.1 Classes & Objects

### Concept Explanation

A **class** is a **blueprint** or **recipe**. An **object** is the actual thing you build from that blueprint.

Think of a class "CookieCutter" and an object as the actual cookie. The class defines what a cookie IS (shape, size, ingredients), and objects are the real cookies you can eat!

### Code Example 1: Creating a Class and Objects

```java
// A class is a blueprint for creating objects
// This file should be saved as Student.java

class Student {
    // === ATTRIBUTES (data / fields / properties) ===
    // These describe what a Student HAS

    String name;       // student's name
    int rollNumber;    // roll number
    double marks;      // marks scored
    String section;    // class section

    // === METHODS (behavior) ===
    // These describe what a Student CAN DO

    // Display student info
    void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Roll: " + rollNumber);
        System.out.println("Marks: " + marks);
        System.out.println("Section: " + section);
    }

    // Check if student passed
    boolean hasPassed() {
        return marks >= 40;  // returns true if marks >= 40
    }

    // Update marks
    void updateMarks(double newMarks) {
        marks = newMarks;
        System.out.println(name + "'s marks updated to " + marks);
    }
}

// Main class to test the Student class
public class ClassAndObjects {

    public static void main(String[] args) {

        // Create an object: new Student() creates the actual Student
        // s1 is a REFERENCE variable that points to the Student object
        Student s1 = new Student();

        // Set attributes using dot (.) operator
        s1.name = "Alice";
        s1.rollNumber = 101;
        s1.marks = 85.5;
        s1.section = "A";

        // Call methods
        System.out.println("=== Student 1 ===");
        s1.displayInfo();
        System.out.println("Passed? " + s1.hasPassed());

        // Create another Student object
        Student s2 = new Student();
        s2.name = "Bob";
        s2.rollNumber = 102;
        s2.marks = 35.0;
        s2.section = "B";

        System.out.println("\n=== Student 2 ===");
        s2.displayInfo();
        System.out.println("Passed? " + s2.hasPassed());

        // Update marks
        s2.updateMarks(45.0);
        System.out.println("Now passed? " + s2.hasPassed());
    }
}
```

### Code Example 2: Constructors

```java
// Constructors: special methods that run when object is created

class Car {
    String brand;
    String model;
    int year;
    double price;

    // === CONSTRUCTOR TYPES ===

    // 1. DEFAULT CONSTRUCTOR (provided free if you don't write any)
    // But once you write ANY constructor, the default is NOT provided

    // 2. NO-ARG CONSTRUCTOR (constructor with no parameters)
    Car() {
        System.out.println("  Car created with default values");
        brand = "Unknown";
        model = "Unknown";
        year = 2000;
        price = 0.0;
    }

    // 3. PARAMETERIZED CONSTRUCTOR
    Car(String brand, String model, int year, double price) {
        System.out.println("  Car created with parameters");
        this.brand = brand;    // 'this.brand' refers to the object's field
        this.model = model;    // 'model' (without this) is the parameter
        this.year = year;
        this.price = price;
    }

    // 4. COPY CONSTRUCTOR
    Car(Car other) {
        System.out.println("  Car created by copying another car");
        this.brand = other.brand;
        this.model = other.model;
        this.year = other.year;
        this.price = other.price;
    }

    void display() {
        System.out.println("  " + year + " " + brand + " " + model + " - $" + price);
    }
}

public class ConstructorsDemo {

    public static void main(String[] args) {

        System.out.println("=== No-Arg Constructor ===");
        Car c1 = new Car();          // calls no-arg constructor
        c1.display();

        System.out.println("\n=== Parameterized Constructor ===");
        Car c2 = new Car("Toyota", "Camry", 2023, 28000);
        c2.display();

        Car c3 = new Car("Honda", "Civic", 2024, 25000);
        c3.display();

        System.out.println("\n=== Copy Constructor ===");
        Car c4 = new Car(c2);        // copy of c2
        c4.display();

        // Prove it's an independent copy
        c2.price = 30000;
        System.out.println("\nAfter changing c2's price:");
        c2.display();
        c4.display();  // unaffected (it's a separate object)
    }
}
```

### Code Example 3: 'this' Keyword

```java
class Employee {
    String name;
    int id;
    double salary;

    // 'this' refers to the CURRENT object
    // It's used to distinguish between parameters and fields

    // 1. this.field - when parameter has same name as field
    Employee(String name, int id) {
        this.name = name;    // this.name = field, name = parameter
        this.id = id;        // this.id = field, id = parameter
    }

    // 2. this() - calling another constructor from a constructor
    Employee() {
        this("Unknown", 0);  // calls the above constructor!
        System.out.println("  No-arg constructor called this()");
    }

    // 3. Returning the current object
    Employee setSalary(double salary) {
        this.salary = salary;
        return this;  // return the object itself (method chaining)
    }

    Employee display() {
        System.out.println("  Employee: " + name + " (ID: " + id + ", Salary: $" + salary + ")");
        return this;
    }
}

public class ThisKeyword {

    public static void main(String[] args) {

        System.out.println("=== 'this' keyword ===");

        Employee e1 = new Employee("Alice", 101);
        e1.setSalary(50000);
        e1.display();

        // Method chaining: each method returns 'this'
        System.out.println("\nMethod chaining:");
        Employee e2 = new Employee("Bob", 102);
        e2.setSalary(60000).display();  // setSalary returns 'this', then display()

        // Using this() in constructor
        System.out.println("\nUsing this() in constructor:");
        Employee e3 = new Employee();  // calls no-arg, which calls parameterized
        e3.display();
    }
}
```

---

## 7.2 Inheritance

### Concept Explanation

**Inheritance** is like a child inheriting traits from parents. A child class (subclass) gets all the properties and methods of the parent class (superclass), and can add its own.

- **Single:** One child, one parent (like you and your parent)
- **Multilevel:** Grandparent -> Parent -> Child
- **Hierarchical:** One parent, multiple children

### Code Example 1: Single Inheritance

```java
// Parent class (superclass, base class)
class Animal {
    String name;
    String sound;

    Animal(String name) {
        this.name = name;
    }

    void makeSound() {
        System.out.println(name + " makes a sound");
    }

    void eat() {
        System.out.println(name + " is eating");
    }

    void sleep() {
        System.out.println(name + " is sleeping");
    }
}

// Child class (subclass, derived class) - INHERITS from Animal
// 'extends' means Dog gets everything Animal has
class Dog extends Animal {

    // Dog's own additional attribute
    String breed;

    Dog(String name, String breed) {
        super(name);           // call the parent's constructor!
        this.breed = breed;
    }

    // OVERRIDE the parent's method (provide own version)
    @Override
    void makeSound() {
        System.out.println(name + " barks: Woof! Woof!");
    }

    // Dog's own method (not in parent)
    void wagTail() {
        System.out.println(name + " is wagging tail!");
    }
}

public class SingleInheritance {

    public static void main(String[] args) {

        System.out.println("=== Animal (Parent) ===");
        Animal animal = new Animal("Generic Animal");
        animal.makeSound();
        animal.eat();
        animal.sleep();

        System.out.println("\n=== Dog (Child) ===");
        Dog dog = new Dog("Buddy", "Golden Retriever");
        dog.makeSound();      // Dog's version runs (overridden)
        dog.eat();            // Inherited from Animal
        dog.sleep();          // Inherited from Animal
        dog.wagTail();        // Dog's own method

        // Child IS-A Parent (polymorphism)
        Animal a = new Dog("Max", "Lab");  // Dog IS an Animal
        a.makeSound();        // Dog's makeSound runs! (runtime polymorphism)
        // a.wagTail();       // ERROR! Animal reference doesn't know about wagTail()
    }
}
```

### Code Example 2: Multilevel & Hierarchical Inheritance

```java
// === MULTILEVEL INHERITANCE ===
// Grandparent -> Parent -> Child

class Vehicle {
    String brand;

    Vehicle(String brand) {
        this.brand = brand;
    }

    void start() {
        System.out.println(brand + " vehicle is starting...");
    }

    void stop() {
        System.out.println(brand + " vehicle is stopping...");
    }
}

// Car extends Vehicle (inherits: brand, start(), stop())
class Car extends Vehicle {
    int doors;

    Car(String brand, int doors) {
        super(brand);        // call Vehicle's constructor
        this.doors = doors;
    }

    void honk() {
        System.out.println(brand + " car honks: Beep beep!");
    }
}

// ElectricCar extends Car (inherits: brand, doors, start(), stop(), honk())
class ElectricCar extends Car {
    int batteryRange;

    ElectricCar(String brand, int doors, int batteryRange) {
        super(brand, doors);  // call Car's constructor
        this.batteryRange = batteryRange;
    }

    @Override
    void start() {
        System.out.println(brand + " electric car starts silently...");
    }

    void charge() {
        System.out.println(brand + " is charging. Range: " + batteryRange + " miles");
    }
}

// === HIERARCHICAL INHERITANCE ===
// One parent, multiple children

class Bike extends Vehicle {
    boolean hasCarrier;

    Bike(String brand, boolean hasCarrier) {
        super(brand);
        this.hasCarrier = hasCarrier;
    }

    void wheelie() {
        System.out.println(brand + " bike doing a wheelie!");
    }
}

class Truck extends Vehicle {
    double loadCapacity;

    Truck(String brand, double loadCapacity) {
        super(brand);
        this.loadCapacity = loadCapacity;
    }

    void loadCargo() {
        System.out.println(brand + " truck loading " + loadCapacity + " tons");
    }
}

public class InheritanceTypes {

    public static void main(String[] args) {

        System.out.println("=== Multilevel Inheritance ===");
        Vehicle v = new Vehicle("Generic");
        v.start();

        Car c = new Car("Toyota", 4);
        c.start();       // Vehicle's start()
        c.honk();        // Car's method

        ElectricCar ec = new ElectricCar("Tesla", 4, 350);
        ec.start();      // ElectricCar's overridden start()
        ec.honk();       // Inherited from Car
        ec.charge();     // ElectricCar's own method
        ec.stop();       // Inherited from Vehicle

        System.out.println("\nBattery range: " + ec.batteryRange + " miles");

        System.out.println("\n=== Hierarchical Inheritance ===");
        Bike bike = new Bike("Hero", true);
        bike.start();
        bike.wheelie();

        Truck truck = new Truck("Volvo", 20.5);
        truck.start();
        truck.loadCargo();
    }
}
```

---

## 7.3 Polymorphism

### Concept Explanation

**Polymorphism** = "many forms." Same name, different behavior.

- **Compile-time (Method Overloading):** Same method name, different parameters. Java decides which version to call at compile time (we already learned this!).
- **Runtime (Method Overriding):** Child class provides its own version of a parent method. Java decides which version to call AT RUNTIME based on the actual object type.

### Code Example 1: Runtime Polymorphism (Method Overriding)

```java
// Method Overriding: Child class provides specific implementation
// of a method that already exists in the parent class

class Shape {
    void draw() {
        System.out.println("Drawing a shape...");
    }

    double area() {
        return 0;
    }
}

class Circle extends Shape {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override  // optional but good practice - tells Java we're overriding
    void draw() {
        System.out.println("Drawing a circle with radius " + radius);
    }

    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}

class Rectangle extends Shape {
    double length, width;

    Rectangle(double l, double w) {
        length = l;
        width = w;
    }

    @Override
    void draw() {
        System.out.println("Drawing a rectangle " + length + "x" + width);
    }

    @Override
    double area() {
        return length * width;
    }
}

class Triangle extends Shape {
    double base, height;

    Triangle(double base, double height) {
        this.base = base;
        this.height = height;
    }

    @Override
    void draw() {
        System.out.println("Drawing a triangle (base=" + base + ", height=" + height + ")");
    }

    @Override
    double area() {
        return 0.5 * base * height;
    }
}

public class RuntimePolymorphism {

    public static void main(String[] args) {

        System.out.println("=== Runtime Polymorphism ===");
        System.out.println("Same method call 'draw()' - different behavior!\n");

        // Parent reference, child objects
        Shape s;  // just a reference variable

        s = new Circle(5.0);
        s.draw();          // Circle's draw() runs!
        System.out.println("Area: " + s.area());

        s = new Rectangle(4.0, 6.0);
        s.draw();          // Rectangle's draw() runs!
        System.out.println("Area: " + s.area());

        s = new Triangle(3.0, 8.0);
        s.draw();          // Triangle's draw() runs!
        System.out.println("Area: " + s.area());

        // Array of shapes - polymorphism in action!
        System.out.println("\n=== Polymorphic Array ===");
        Shape[] shapes = {
            new Circle(3),
            new Rectangle(2, 5),
            new Triangle(4, 6),
            new Circle(7)
        };

        for (Shape shape : shapes) {
            shape.draw();  // correct version called for each!
            System.out.println("  Area: " + shape.area());
        }
    }
}
```

---

## 7.4 Abstraction

### Concept Explanation

**Abstraction** means HIDING the complex details and showing ONLY the essential features. Like driving a car — you press the gas pedal, but you don't need to know how the engine works internally.

Two ways to achieve abstraction:
1. **Abstract classes** (can have both abstract and regular methods)
2. **Interfaces** (ALL methods are abstract by default; just a contract)

### Code Example 1: Abstract Classes

```java
// Abstract class: CANNOT be instantiated (can't create objects directly)
// It's like a "partial" blueprint - some methods defined, some just declared

abstract class Animal {
    String name;

    Animal(String name) {
        this.name = name;
    }

    // CONCRETE METHOD (has implementation)
    void eat() {
        System.out.println(name + " is eating...");
    }

    void sleep() {
        System.out.println(name + " is sleeping...");
    }

    // ABSTRACT METHOD (no body, just declaration)
    // Subclasses MUST implement this!
    abstract void makeSound();
}

// Concrete class MUST implement all abstract methods
class Dog extends Animal {
    Dog(String name) {
        super(name);
    }

    @Override
    void makeSound() {
        System.out.println(name + " barks: Woof!");
    }
}

class Cat extends Animal {
    Cat(String name) {
        super(name);
    }

    @Override
    void makeSound() {
        System.out.println(name + " meows: Meow!");
    }
}

public class AbstractClassDemo {

    public static void main(String[] args) {

        // Animal a = new Animal("Test");  // ERROR! Can't instantiate abstract class

        Animal d = new Dog("Buddy");
        Animal c = new Cat("Whiskers");

        d.eat();
        d.makeSound();   // Dog's implementation
        d.sleep();

        System.out.println();

        c.eat();
        c.makeSound();   // Cat's implementation
        c.sleep();
    }
}
```

### Code Example 2: Interfaces

```java
// Interface: a COMPLETE contract. ALL methods are abstract (no body).
// A class can implement MULTIPLE interfaces (unlike classes - can only extend one)

// Interface 1
interface Flyable {
    // All methods in interface are implicitly public and abstract
    void fly();
    void land();
}

// Interface 2
interface Swimmable {
    void swim();
    void dive();
}

// Interface 3
interface Runnable {
    void run();
    int getSpeed();
}

// A class can implement MULTIPLE interfaces
class Bird implements Flyable, Runnable {
    String name;

    Bird(String name) {
        this.name = name;
    }

    @Override
    public void fly() {
        System.out.println(name + " is flying!");
    }

    @Override
    public void land() {
        System.out.println(name + " is landing.");
    }

    @Override
    public void run() {
        System.out.println(name + " is running.");
    }

    @Override
    public int getSpeed() {
        return 15;  // km/h
    }
}

class Fish implements Swimmable {
    String name;

    Fish(String name) {
        this.name = name;
    }

    @Override
    public void swim() {
        System.out.println(name + " is swimming!");
    }

    @Override
    public void dive() {
        System.out.println(name + " dives deep!");
    }
}

class Duck implements Flyable, Swimmable, Runnable {
    String name;

    Duck(String name) {
        this.name = name;
    }

    @Override
    public void fly() {
        System.out.println(name + " flies!");
    }

    @Override
    public void land() {
        System.out.println(name + " lands on water.");
    }

    @Override
    public void swim() {
        System.out.println(name + " swims!");
    }

    @Override
    public void dive() {
        System.out.println(name + " dives!");
    }

    @Override
    public void run() {
        System.out.println(name + " waddles.");
    }

    @Override
    public int getSpeed() {
        return 5;
    }
}

public class InterfaceDemo {

    public static void main(String[] args) {

        System.out.println("=== Interfaces ===");

        Bird bird = new Bird("Sparrow");
        bird.fly();
        bird.land();
        bird.run();

        System.out.println();

        Fish fish = new Fish("Nemo");
        fish.swim();
        fish.dive();

        System.out.println();

        Duck duck = new Duck("Donald");
        duck.fly();
        duck.swim();
        duck.run();

        // Interface references
        System.out.println("\n=== Interface References ===");
        Flyable f = new Duck("Daffy");
        f.fly();      // only Flyable methods available
        // f.swim();  // ERROR! Flyable reference doesn't have swim()
    }
}
```

---

## 7.5 Encapsulation

### Concept Explanation

**Encapsulation** means keeping data SAFE by making it private and only allowing access through controlled methods (getters/setters). Like a bank vault — you can't just reach in and grab money; you must use the proper procedures.

- Private fields: cannot be accessed directly from outside the class
- Public getters: allow READING the value
- Public setters: allow WRITING the value (with validation!)

### Code Example 1: Getter & Setter Methods

```java
class BankAccount {
    // PRIVATE fields - can't be accessed directly from outside!
    private String accountNumber;
    private String accountHolder;
    private double balance;
    private String password;

    // Constructor
    BankAccount(String accountNumber, String accountHolder, double balance) {
        this.accountNumber = accountNumber;
        this.accountHolder = accountHolder;
        this.balance = balance;
        this.password = "default123";
    }

    // === GETTERS (read access) ===

    public String getAccountNumber() {
        return accountNumber;
    }

    public String getAccountHolder() {
        return accountHolder;
    }

    public double getBalance() {
        return balance;
    }

    // === SETTERS (write access with validation) ===

    public void setAccountHolder(String newName) {
        if (newName != null && newName.length() >= 2) {
            this.accountHolder = newName;
        } else {
            System.out.println("Error: Invalid name!");
        }
    }

    // Controlled way to modify balance (not a simple setter)
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited $" + amount + ". New balance: $" + balance);
        } else {
            System.out.println("Error: Can't deposit negative amount!");
        }
    }

    public boolean withdraw(double amount) {
        if (amount <= 0) {
            System.out.println("Error: Invalid amount!");
            return false;
        }
        if (amount > balance) {
            System.out.println("Error: Insufficient funds!");
            return false;
        }
        balance -= amount;
        System.out.println("Withdrew $" + amount + ". New balance: $" + balance);
        return true;
    }

    // Display (hides private details like password)
    public void displayAccountInfo() {
        System.out.println("Account #: " + accountNumber);
        System.out.println("Holder: " + accountHolder);
        System.out.println("Balance: $" + balance);
        // Note: we DON'T print password!
    }
}

public class EncapsulationDemo {

    public static void main(String[] args) {

        BankAccount account = new BankAccount("ACC123", "Alice", 1000.0);

        System.out.println("=== Account Info ===");
        account.displayAccountInfo();

        // Can't access private fields directly:
        // account.balance = 999999;        // ERROR! balance is private
        // System.out.println(account.balance);  // ERROR!

        // Must use public methods:
        System.out.println("\nBalance via getter: $" + account.getBalance());

        account.deposit(500);
        account.withdraw(200);
        account.withdraw(2000);  // Should fail (insufficient)

        // Update name via setter
        account.setAccountHolder("Alice Johnson");
        System.out.println("\nUpdated name: " + account.getAccountHolder());
    }
}
```

---

## 7.6 Static & Final Keywords

### Concept Explanation

**`static`** = belongs to the CLASS, not to any individual object. Like a school's name — all students share the same school name. You don't need an object to access it.

**`final`** = once assigned, CAN'T BE CHANGED. Like your date of birth.
- `final` variable = constant (can't reassign)
- `final` method = can't be overridden
- `final` class = can't be extended (no child classes)

### Code Example 1: static Keyword

```java
class Counter {
    // Instance variable (each object has its own copy)
    int instanceCount = 0;

    // Static variable (ONE copy shared by ALL objects)
    static int totalCount = 0;

    Counter() {
        instanceCount++;   // increments for this specific object
        totalCount++;      // increments for ALL objects
    }

    void display() {
        System.out.println("  Instance count: " + instanceCount +
                         ", Total count: " + totalCount);
    }

    // Static method: can only access static members!
    static void showTotal() {
        System.out.println("  Total objects created: " + totalCount);
        // System.out.println(instanceCount);  // ERROR! Can't access non-static
    }
}

class MathUtils {
    // Static constant
    static final double PI = 3.14159;

    // Static utility methods (no object needed)
    static int add(int a, int b) { return a + b; }
    static int max(int a, int b) { return a > b ? a : b; }
    static int factorial(int n) {
        int result = 1;
        for (int i = 2; i <= n; i++) result *= i;
        return result;
    }
}

public class StaticKeyword {

    // Static variable - loaded when class is loaded
    static String className = "StaticDemo";

    public static void main(String[] args) {

        // Access static members WITHOUT creating an object
        System.out.println("MathUtils.PI = " + MathUtils.PI);
        System.out.println("MathUtils.add(5,3) = " + MathUtils.add(5, 3));
        System.out.println("MathUtils.max(10,7) = " + MathUtils.max(10, 7));
        System.out.println("MathUtils.factorial(5) = " + MathUtils.factorial(5));

        System.out.println("\n=== Static vs Instance ===");
        Counter c1 = new Counter();
        c1.display();  // instance: 1, total: 1

        Counter c2 = new Counter();
        c2.display();  // instance: 1, total: 2

        Counter c3 = new Counter();
        c3.display();  // instance: 1, total: 3

        // Static method called on class directly
        System.out.println();
        Counter.showTotal();  // Total: 3

        // Static can also be called on object (but this is bad practice)
        c1.showTotal();  // works but confusing - it's really a class method!
    }
}
```

### Code Example 2: final Keyword

```java
// 'final' means "can't be changed"

// 1. final CLASS: can't be extended (no child classes)
final class FinalClass {
    void doSomething() {
        System.out.println("This class can't be extended!");
    }
}
// class Child extends FinalClass { }  // ERROR! Can't extend final class

// 2. final METHOD: can't be overridden
class Parent {
    final void cannotOverride() {
        System.out.println("I'm final, you can't override me!");
    }

    void canOverride() {
        System.out.println("I'm NOT final, you CAN override me!");
    }
}

class Child extends Parent {
    // @Override
    // void cannotOverride() { }  // ERROR! Can't override final method

    @Override
    void canOverride() {
        System.out.println("Overridden! I'm the child's version!");
    }
}

// 3. final VARIABLE: can't be reassigned (constant)
public class FinalKeyword {

    public static void main(String[] args) {

        // final local variable
        final int MAX_SIZE = 100;
        System.out.println("MAX_SIZE = " + MAX_SIZE);
        // MAX_SIZE = 200;  // ERROR! Can't change a final variable

        // final reference variable - can't point to a different object
        final StringBuilder sb = new StringBuilder("Hello");
        sb.append(" World");              // OK! Modifying the OBJECT is fine
        System.out.println("sb: " + sb);
        // sb = new StringBuilder("New");  // ERROR! Can't reassign final reference

        // final with objects
        Child child = new Child();
        child.cannotOverride();  // Parent's version
        child.canOverride();     // Child's overridden version
    }
}
```

---

## 7.7 Packages & Access Modifiers

### Concept Explanation

**Packages** are like **folders** for your code. They help organize classes and avoid name conflicts.

**Access Modifiers** control WHO can see/use your class members:
- `public` → anyone can access (like a public park)
- `protected` → same package + child classes (like a family heirloom)
- `default` (no modifier) → only same package (like a shared apartment building)
- `private` → only the same class (like your personal diary)

### Code Example 1: Access Modifiers

```java
// This demonstrates ALL access modifiers in one file for learning
// (Package-private classes are the most common for beginners)

class AccessModifiersDemo {

    // === ALL FOUR ACCESS MODIFIERS ===

    public int publicVar = 1;       // Everyone can see this
    protected int protectedVar = 2; // Package + children can see
    int defaultVar = 3;             // Only same package can see
    private int privateVar = 4;     // Only THIS class can see

    public void publicMethod() {
        System.out.println("public method");
    }

    protected void protectedMethod() {
        System.out.println("protected method");
    }

    void defaultMethod() {
        System.out.println("default method");
    }

    private void privateMethod() {
        System.out.println("private method");
    }

    // Within the same class, everything is accessible
    void demonstrateSameClass() {
        System.out.println("\n=== Same Class ===");
        System.out.println("  publicVar: " + publicVar);
        System.out.println("  protectedVar: " + protectedVar);
        System.out.println("  defaultVar: " + defaultVar);
        System.out.println("  privateVar: " + privateVar);  // can access private!

        publicMethod();
        protectedMethod();
        defaultMethod();
        privateMethod();  // can access private!
    }
}

// Class in the SAME PACKAGE
class SamePackage {

    void demonstrateSamePackage() {
        AccessModifiersDemo demo = new AccessModifiersDemo();

        System.out.println("\n=== Same Package ===");
        System.out.println("  publicVar: " + demo.publicVar);      // OK
        System.out.println("  protectedVar: " + demo.protectedVar); // OK
        System.out.println("  defaultVar: " + demo.defaultVar);     // OK
        // System.out.println("  privateVar: " + demo.privateVar);  // ERROR!

        demo.publicMethod();      // OK
        demo.protectedMethod();   // OK
        demo.defaultMethod();     // OK
        // demo.privateMethod();  // ERROR!
    }
}

public class AccessModifiers {

    public static void main(String[] args) {

        AccessModifiersDemo demo = new AccessModifiersDemo();

        // Access from main (same class)
        demo.demonstrateSameClass();

        // Access from same package
        SamePackage sp = new SamePackage();
        sp.demonstrateSamePackage();

        // Quick reference:
        System.out.println("\n=== Access Modifier Summary ===");
        System.out.println("public:    Any class anywhere");
        System.out.println("protected: Same package + subclasses");
        System.out.println("default:   Same package only");
        System.out.println("private:   Same class only");
    }
}
```

---

# 🎉 YOU'VE COMPLETED SECTION 1! 🎉

## What to Do Next

1. **Type every example yourself** — typing makes you learn!
2. **Compile and run** each program: `javac FileName.java && java FileName`
3. **Experiment** — change values, add features, break things and fix them
4. **Move to Section 2** — more advanced DSA topics like recursion, linked lists, stacks, queues, trees, graphs, and dynamic programming!

### Note on Compilation:
- Each Java file must have the SAME name as the class containing `main()`
- So `public class Hello` must be in a file called `Hello.java`
- Compile with: `javac Hello.java`
- Run with: `java Hello`

### Common Errors (and what they mean):
- `cannot find symbol` → you misspelled a variable/method name
- `missing return statement` → your function promised to return a value but didn't
- `incompatible types` → you're trying to put a big type into a small type without casting
- `class X is public, should be declared in a file named X.java` → filename must match class name
- `ArrayIndexOutOfBoundsException` → you accessed an index that doesn't exist
- `NullPointerException` → you tried to use an object that is null (points to nothing)

### Happy Coding! 🚀
# Java DSA — Complete Beginner's Guide

> **Note for absolute beginners**: If you see a word in *italics*, it's being defined for the first time. If you see `code`, it's Java syntax. Take it slow — one example at a time. Compile and run every program yourself.

---

# 1. RECURSION

## 1.0 What Is Recursion?

**Simple definition**: Recursion is when a function calls **itself**.

Think of it like Russian nesting dolls (matryoshka). To open the biggest doll, you open it to find a smaller doll, open that to find an even smaller one... until you reach the tiniest doll that cannot be opened. Then you STOP.

In programming:
- You write a method that calls itself.
- Each call works on a **smaller** version of the problem.
- You MUST have a **stopping condition** (base case) or you'll get infinite recursion and a `StackOverflowError`.

### The Call Stack (Simple Visualization)

Every time you call a method, Java puts that call on **the call stack** — like stacking plates. The last plate placed is the first one removed (LIFO — Last In, First Out).

```
main() calls factorial(5)
    ↓
factorial(5) calls factorial(4)
    ↓
factorial(4) calls factorial(3)
    ↓
factorial(3) calls factorial(2)
    ↓
factorial(2) calls factorial(1)
    ↓
factorial(1) returns 1   ← base case reached!
    ↑
factorial(2) returns 2 * 1 = 2
    ↑
factorial(3) returns 3 * 2 = 6
    ↑
factorial(4) returns 4 * 6 = 24
    ↑
factorial(5) returns 5 * 24 = 120
    ↑
main() gets 120
```

**Key insight**: The calls go **down** (forward), the returns come **back up** (backward).

---

## 1.1 Base Case and Recursion Case

Every recursive function must have two parts:

| Part | What it does | What happens if you forget it |
|------|-------------|-------------------------------|
| **Base case** | Stops the recursion | Infinite recursion → crash |
| **Recursion case** | Calls itself with different input | Nothing useful happens |

```java
public class RecursionBasics {

    // Example: countdown from n to 1
    // Base case: n == 0 (stop)
    // Recursion case: call countdown(n - 1)
    public static void countdown(int n) {
        // BASE CASE: if n is 0, stop (don't call again)
        if (n == 0) {
            return; // exit the method
        }

        // Print current number
        System.out.println(n);

        // RECURSION CASE: call ourselves with a SMALLER value
        countdown(n - 1);
    }

    public static void main(String[] args) {
        System.out.println("=== Countdown ===");
        countdown(5);
        // Expected output: 5 4 3 2 1
    }
}
```

---

## 1.2 Print Numbers from n to 1 and 1 to n

This example demonstrates the **power of print placement**. Where you put the `println` changes the output completely.

```java
public class PrintNumbers {

    // Prints n to 1 (decreasing order)
    // We print FIRST, then recurse
    public static void printNto1(int n) {
        // Base case: if n is 0, stop
        if (n == 0) {
            return;
        }

        // PRINT FIRST, then recurse
        // This means we print BEFORE going deeper into the stack
        System.out.print(n + " ");

        // Recurse with smaller value
        printNto1(n - 1);
    }

    // Prints 1 to n (increasing order)
    // We recurse FIRST, then print
    public static void print1toN(int n) {
        // Base case: if n is 0, stop
        if (n == 0) {
            return;
        }

        // RECURSE FIRST, then print
        // This means we go all the way down the stack FIRST,
        // then print on the way back UP
        print1toN(n - 1);

        // Print AFTER recursion
        // By the time we reach this line, the deeper call has already returned
        System.out.print(n + " ");
    }

    public static void main(String[] args) {
        int n = 5;

        System.out.print("n to 1: ");
        printNto1(n);  // Output: 5 4 3 2 1
        System.out.println();

        System.out.print("1 to n: ");
        print1toN(n);  // Output: 1 2 3 4 5
        System.out.println();
    }
}
```

**Why does print placement matter?**
- `printNto1`: Prints THEN recurses. The first call (n=5) prints immediately, then calls n=4, which prints, then n=3... Result: `5 4 3 2 1`.
- `print1toN`: Recurse THEN print. The first call (n=5) calls n=4, which calls n=3... all the way to n=0 (base case). Then n=1 prints, returns, then n=2 prints, returns... Result: `1 2 3 4 5`.

---

## 1.3 Factorial Using Recursion

**What is factorial?** `n!` (n factorial) = `n * (n-1) * (n-2) * ... * 1`
Example: `5! = 5 * 4 * 3 * 2 * 1 = 120`

**Recursive definition**: `factorial(n) = n * factorial(n-1)`, with base case `factorial(0) = 1`

```java
public class Factorial {

    // Returns n! (n factorial)
    // Formula: n! = n * (n-1)!
    // Base case: 0! = 1
    public static int factorial(int n) {
        // Base case: 0! = 1 (by definition)
        if (n == 0) {
            return 1;
        }

        // Recursion case: n! = n * (n-1)!
        // We trust that factorial(n-1) will give us the right answer
        int smallerFactorial = factorial(n - 1);
        int result = n * smallerFactorial;

        return result;

        // Or in one line: return n * factorial(n - 1);
    }

    public static void main(String[] args) {
        System.out.println("=== Factorial ===");

        // Test with various values
        for (int i = 0; i <= 10; i++) {
            System.out.println(i + "! = " + factorial(i));
        }

        // Expected output:
        // 0! = 1
        // 1! = 1
        // 2! = 2
        // 3! = 6
        // 4! = 24
        // 5! = 120
        // 6! = 720
        // 7! = 5040
        // 8! = 40320
        // 9! = 362880
        // 10! = 3628800
    }
}
```

**Execution trace for factorial(4):**
```
factorial(4) → 4 * factorial(3)
                   → 3 * factorial(2)
                       → 2 * factorial(1)
                           → 1 * factorial(0)
                               → 1 (base case)
                           → returns 1 * 1 = 1
                       → returns 2 * 1 = 2
                   → returns 3 * 2 = 6
               → returns 4 * 6 = 24
```

---

## 1.4 Fibonacci Series

**What is Fibonacci?** A sequence where each number is the sum of the two preceding ones.
`0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...`

**Recursive definition**: `fib(n) = fib(n-1) + fib(n-2)`
**Base cases**: `fib(0) = 0`, `fib(1) = 1`

```java
public class Fibonacci {

    // Returns the nth Fibonacci number
    // WARNING: This simple version is VERY SLOW for n > 40
    // because it recalculates the same values many times
    public static int fib(int n) {
        // Base case 1: fib(0) = 0
        if (n == 0) {
            return 0;
        }

        // Base case 2: fib(1) = 1
        if (n == 1) {
            return 1;
        }

        // Recursion case: fib(n) = fib(n-1) + fib(n-2)
        int prev1 = fib(n - 1); // Previous Fibonacci number
        int prev2 = fib(n - 2); // Two steps back
        int result = prev1 + prev2;

        return result;
    }

    // OPTIMIZED Fibonacci using memoization (top-down DP)
    // We store previously computed values in an array to avoid recalculation
    public static int fibOptimized(int n, int[] memo) {
        // Base case
        if (n == 0 || n == 1) {
            return n;
        }

        // If already computed, return stored value
        if (memo[n] != 0) {
            return memo[n];
        }

        // Compute, store, and return
        memo[n] = fibOptimized(n - 1, memo) + fibOptimized(n - 2, memo);
        return memo[n];
    }

    public static void main(String[] args) {
        System.out.println("=== Fibonacci (Simple) ===");

        // Print first 10 Fibonacci numbers
        for (int i = 0; i < 10; i++) {
            System.out.println("fib(" + i + ") = " + fib(i));
        }
        // Output: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34

        System.out.println();

        // Optimized version - can handle much larger n
        System.out.println("=== Fibonacci (Optimized with Memoization) ===");
        int n = 45;
        int[] memo = new int[n + 1]; // Array to store computed values
        System.out.println("fib(" + n + ") = " + fibOptimized(n, memo));
        // This would be extremely slow with the simple version
        // but fast with memoization
    }
}
```

**Why is the simple version slow?** Each call makes TWO recursive calls. This creates a **binary tree** of calls. `fib(5)` calls `fib(4)` and `fib(3)`, which each call two more... The number of calls grows exponentially (~2^n). With memoization, each value is computed only once, giving O(n) time.

---

## 1.5 Check if Array is Sorted

Use recursion to check if an array is sorted in **strictly increasing** order.

**Logic**: An array is sorted if:
1. The first element is less than the second element, AND
2. The rest of the array (from index 1 onward) is also sorted.

```java
public class CheckSorted {

    // Returns true if array arr is sorted in increasing order
    // We check from index i onwards
    public static boolean isSorted(int[] arr, int i) {
        // Base case: if we've reached the last element
        // (or passed it), the array is sorted by definition
        if (i == arr.length - 1) {
            return true;
        }

        // Check if current element is greater than next element
        // If so, array is NOT sorted
        if (arr[i] > arr[i + 1]) {
            return false;
        }

        // Recursively check the rest of the array
        // Start from the next element
        return isSorted(arr, i + 1);
    }

    public static void main(String[] args) {
        System.out.println("=== Check if Array is Sorted ===");

        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = {1, 3, 2, 4, 5};
        int[] arr3 = {5, 4, 3, 2, 1};

        System.out.print("arr1 {1,2,3,4,5}: ");
        System.out.println(isSorted(arr1, 0)); // true

        System.out.print("arr2 {1,3,2,4,5}: ");
        System.out.println(isSorted(arr2, 0)); // false

        System.out.print("arr3 {5,4,3,2,1}: ");
        System.out.println(isSorted(arr3, 0)); // false
    }
}
```

```java
public class CheckSortedFixed {

    // Returns true if array is sorted in STRICTLY increasing order
    public static boolean isSortedStrictly(int[] arr, int i) {
        if (i == arr.length - 1) {
            return true;
        }

        // Use >= to catch equal elements (not strictly increasing)
        if (arr[i] >= arr[i + 1]) {
            return false;
        }

        return isSortedStrictly(arr, i + 1);
    }

    // Returns true if array is sorted in NON-DECREASING order
    // (allows equal elements: 1, 2, 2, 3 is OK)
    public static boolean isSortedNonDecreasing(int[] arr, int i) {
        if (i == arr.length - 1) {
            return true;
        }

        // Only check if current is GREATER than next
        if (arr[i] > arr[i + 1]) {
            return false;
        }

        return isSortedNonDecreasing(arr, i + 1);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 2, 4, 5};

        System.out.println("Strictly increasing: " + isSortedStrictly(arr, 0));
        // false (because 2 == 2)

        System.out.println("Non-decreasing: " + isSortedNonDecreasing(arr, 0));
        // true (2 <= 2 is OK)
    }
}
```

---

## 1.6 First and Last Occurrence of Element

Find the **first** and **last** index where a given element appears in an array.

**Example**: In `{1, 2, 3, 2, 2, 5}`, the first occurrence of `2` is at index 1, the last at index 4.

```java
public class FirstLastOccurrence {

    // Find FIRST occurrence of key in array starting from index i
    // Returns -1 if not found
    public static int firstOccurrence(int[] arr, int key, int i) {
        // Base case: if we've checked all elements, key not found
        if (i == arr.length) {
            return -1;
        }

        // If current element matches key, return its index
        if (arr[i] == key) {
            return i;
        }

        // Otherwise, continue searching forward
        return firstOccurrence(arr, key, i + 1);
    }

    // Find LAST occurrence of key in array starting from index i
    // We search from the END of the array
    public static int lastOccurrence(int[] arr, int key, int i) {
        // Base case: reached the end without finding
        if (i == arr.length) {
            return -1;
        }

        // First, check the rest of the array
        // We recurse FIRST, THEN check current element
        // This way, we go to the end and work backward
        int foundInRest = lastOccurrence(arr, key, i + 1);

        // If key was found somewhere later in the array,
        // return that index (it's further right, so it's "later")
        if (foundInRest != -1) {
            return foundInRest;
        }

        // If key wasn't found later, check current position
        if (arr[i] == key) {
            return i;
        }

        // Not found anywhere
        return -1;
    }

    // Alternative: search from the END (more intuitive)
    public static int lastOccurrenceFromEnd(int[] arr, int key, int i) {
        // Base case: went past the beginning
        if (i < 0) {
            return -1;
        }

        // Check current element first (starting from end)
        if (arr[i] == key) {
            return i;
        }

        // Move backward
        return lastOccurrenceFromEnd(arr, key, i - 1);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 2, 2, 5, 2, 6};

        System.out.println("Array: {1, 2, 3, 2, 2, 5, 2, 6}");
        System.out.println("First occurrence of 2: " + firstOccurrence(arr, 2, 0));
        // Output: 1

        System.out.println("Last occurrence of 2: " + lastOccurrence(arr, 2, 0));
        // Output: 6

        System.out.println("Last occurrence of 2 (from end): " +
                          lastOccurrenceFromEnd(arr, 2, arr.length - 1));
        // Output: 6

        System.out.println("First occurrence of 9: " + firstOccurrence(arr, 9, 0));
        // Output: -1 (not found)
    }
}
```

**Key insight about `lastOccurrence`**: By recursing FIRST and then checking, we go all the way to the end of the array, then check each element on the way back. The FIRST match we find on the way back is actually the LAST match in the array (because we're working backward).

---

## 1.7 Print x^n (with Optimized Power — O(log n))

Compute `x` raised to the power `n` (x^n).

**Simple approach**: Multiply x by itself n times: O(n) time.

**Optimized approach (O(log n))**: Use the property:
- If n is even: `x^n = (x^(n/2)) * (x^(n/2))`
- If n is odd: `x^n = x * (x^(n/2)) * (x^(n/2))`

This halves the problem size at each step, giving O(log n) time.

```java
public class Power {

    // Simple approach: O(n) time
    // Multiply x by itself n times
    public static int powerSimple(int x, int n) {
        // Base case: anything raised to 0 is 1
        if (n == 0) {
            return 1;
        }

        // x^n = x * x^(n-1)
        return x * powerSimple(x, n - 1);
    }

    // Optimized approach: O(log n) time
    // Uses divide and conquer
    public static int powerOptimized(int x, int n) {
        // Base case: x^0 = 1
        if (n == 0) {
            return 1;
        }

        // Compute x^(n/2) once (not twice!)
        int halfPower = powerOptimized(x, n / 2);

        // If n is even: x^n = (x^(n/2)) * (x^(n/2))
        if (n % 2 == 0) {
            return halfPower * halfPower;
        }
        // If n is odd: x^n = x * (x^(n/2)) * (x^(n/2))
        else {
            return x * halfPower * halfPower;
        }
    }

    public static void main(String[] args) {
        System.out.println("=== Power ===");

        int x = 2;
        System.out.println("2^5 (simple) = " + powerSimple(x, 5));
        // Output: 32
        System.out.println("2^5 (optimized) = " + powerOptimized(x, 5));
        // Output: 32

        System.out.println("2^10 (optimized) = " + powerOptimized(2, 10));
        // Output: 1024

        System.out.println("3^4 (optimized) = " + powerOptimized(3, 4));
        // Output: 81

        // Demonstrate the efficiency difference
        // powerOptimized(2, 1000) works fine
        // powerSimple(2, 1000) would cause stack overflow
        System.out.println("2^20 (optimized) = " + powerOptimized(2, 20));
        // Output: 1048576
    }
}
```

**Execution trace for powerOptimized(2, 5):**
```
powerOptimized(2, 5)
  → halfPower = powerOptimized(2, 2)
      → halfPower = powerOptimized(2, 1)
          → halfPower = powerOptimized(2, 0)
              → returns 1
          → halfPower = 1, n is odd: returns 2 * 1 * 1 = 2
      → halfPower = 2, n is even: returns 2 * 2 = 4
  → halfPower = 4, n is odd: returns 2 * 4 * 4 = 32
```

---

## 1.8 Tiling Problem

**Problem**: Given a floor of size `2 × n` (2 rows, n columns), and tiles of size `2 × 1`, count the number of ways to tile the floor. Tiles can be placed **vertically** (covering 1 column) or **horizontally** (covering 2 columns but requiring another tile below it).

**Think of it this way**: You have a `2 × n` board. You can place:
1. A **vertical** tile (2×1) — that fills 1 column. You're left with a `2 × (n-1)` board.
2. Two **horizontal** tiles stacked (1×2 each) — that fills 2 columns. You're left with a `2 × (n-2)` board.

So: `tiling(n) = tiling(n-1) + tiling(n-2)` — it's Fibonacci!

```java
public class TilingProblem {

    // Count ways to tile a 2×n floor with 2×1 tiles
    public static int tilingWays(int n) {
        // Base case 1: if n is 0 or 1, only 1 way
        // n=0: empty floor (1 way to tile it — do nothing)
        // n=1: 2×1 floor, only 1 way (one vertical tile)
        if (n == 0 || n == 1) {
            return 1;
        }

        // Choice 1: place vertical tile → remaining: 2×(n-1)
        int verticalChoice = tilingWays(n - 1);

        // Choice 2: place 2 horizontal tiles → remaining: 2×(n-2)
        int horizontalChoice = tilingWays(n - 2);

        // Total ways = sum of both choices
        return verticalChoice + horizontalChoice;
    }

    public static void main(String[] args) {
        System.out.println("=== Tiling Problem (2×n floor) ===");

        for (int n = 0; n <= 8; n++) {
            System.out.println("2×" + n + " floor: " + tilingWays(n) + " ways");
        }

        // Expected output:
        // 2×0 floor: 1 way
        // 2×1 floor: 1 way
        // 2×2 floor: 2 ways  (2 vertical OR 2 horizontal)
        // 2×3 floor: 3 ways
        // 2×4 floor: 5 ways
        // 2×5 floor: 8 ways
        // ... it's the Fibonacci sequence!

        System.out.println();
        System.out.println("Visualization for 2×3 floor (3 ways):");
        System.out.println("Way 1: | | |    (three vertical tiles)");
        System.out.println("Way 2: | — —    (one vertical + two horizontal)");
        System.out.println("Way 3: — — |    (two horizontal + one vertical)");
    }
}
```

---

## 1.9 Remove Duplicates from String

**Problem**: Given a string, remove all duplicate characters (keep only the first occurrence). The string contains only lowercase letters 'a' to 'z'.

**Approach**: Use a boolean array of size 26 to track which characters we've already seen. Recurse through the string.

```java
public class RemoveDuplicates {

    // Remove duplicates from a string (only a-z)
    // We use an index to track current position in the string
    // and a boolean array to track seen characters
    public static String removeDups(String str, int idx, boolean[] seen) {
        // Base case: if we've processed all characters, return empty string
        if (idx == str.length()) {
            return "";
        }

        // Get current character
        char curr = str.charAt(idx);

        // Convert character to index (0 for 'a', 1 for 'b', etc.)
        int charIndex = curr - 'a';

        // Get the result from the rest of the string (recursively)
        String restResult = removeDups(str, idx + 1, seen);

        // If we've already seen this character, skip it
        if (seen[charIndex]) {
            return restResult; // Don't include this character
        } else {
            // Mark this character as seen
            seen[charIndex] = true;
            // Include this character + the result from rest
            return curr + restResult;
        }
    }

    // Alternative: build the result forward (more intuitive for beginners)
    public static String removeDupsForward(String str, int idx,
                                            boolean[] seen, StringBuilder result) {
        // Base case: processed all characters
        if (idx == str.length()) {
            return result.toString();
        }

        char curr = str.charAt(idx);
        int charIndex = curr - 'a';

        // If not seen yet, add to result and mark as seen
        if (!seen[charIndex]) {
            seen[charIndex] = true;
            result.append(curr);
        }

        // Move to next character
        return removeDupsForward(str, idx + 1, seen, result);
    }

    public static void main(String[] args) {
        System.out.println("=== Remove Duplicates ===");

        String str = "hellohello";
        boolean[] seen = new boolean[26]; // All false by default

        String result = removeDups(str, 0, seen);
        System.out.println("Original: " + str);
        System.out.println("Without duplicates: " + result);
        // Output: helo

        System.out.println();

        // Test with more strings
        String str2 = "aabbccddeeff";
        boolean[] seen2 = new boolean[26];
        System.out.println("Original: " + str2);
        System.out.println("Without duplicates: " + removeDups(str2, 0, seen2));
        // Output: abcdef

        // Test with forward approach
        String str3 = "programming";
        boolean[] seen3 = new boolean[26];
        System.out.println("Original: " + str3);
        System.out.println("Without duplicates: " +
                          removeDupsForward(str3, 0, seen3, new StringBuilder()));
        // Output: progamin
    }
}
```

---

## 1.10 Friends Pairing Problem

**Problem**: Given n friends, each can either stay single or pair up with one other friend. Count the total number of ways they can do this.

**Think of it this way**: For the first friend:
1. They stay **single** — then the remaining n-1 friends arrange themselves: `f(n-1)` ways.
2. They **pair up** with any of the remaining n-1 friends — that friend is now taken, so the remaining n-2 friends arrange themselves. They have (n-1) choices: `(n-1) × f(n-2)` ways.

So: `f(n) = f(n-1) + (n-1) × f(n-2)`

Base cases:
- `f(0) = 1` (empty group, 1 way)
- `f(1) = 1` (just one person, must stay single)

```java
public class FriendsPairing {

    // Count ways for n friends to stay single or pair up
    public static int friendsPairingWays(int n) {
        // Base case: 0 or 1 friend → only 1 way
        if (n == 0 || n == 1) {
            return 1;
        }

        // Choice 1: first friend stays single
        // Remaining n-1 friends solve the same problem
        int singleWay = friendsPairingWays(n - 1);

        // Choice 2: first friend pairs with someone
        // They have (n-1) choices for who to pair with
        // The remaining n-2 friends solve the same problem
        int pairWay = (n - 1) * friendsPairingWays(n - 2);

        // Total ways
        return singleWay + pairWay;
    }

    public static void main(String[] args) {
        System.out.println("=== Friends Pairing Problem ===");

        for (int n = 0; n <= 6; n++) {
            System.out.println(n + " friend(s): " +
                              friendsPairingWays(n) + " way(s)");
        }

        // Expected output:
        // 0 friend(s): 1 way (empty group)
        // 1 friend(s): 1 way (single)
        // 2 friend(s): 2 ways (both single OR pair up)
        // 3 friend(s): 4 ways
        // 4 friend(s): 10 ways
        // 5 friend(s): 26 ways
        // 6 friend(s): 76 ways

        System.out.println();
        System.out.println("Explanation for 3 friends (A, B, C):");
        System.out.println("1. All single: A B C");
        System.out.println("2. A pairs with B, C single: (AB) C");
        System.out.println("3. A pairs with C, B single: (AC) B");
        System.out.println("4. B pairs with C, A single: (BC) A");
    }
}
```

---

## 1.11 Binary Strings Problem (No Consecutive 1s)

**Problem**: Given a length n, print all binary strings of length n that do NOT have consecutive 1s.

**Example** for n = 3: Valid strings are `000, 001, 010, 100, 101`. Invalid: `011, 110, 111`.

**Approach**: Build the string character by character. At each position:
- You can ALWAYS place a `0`.
- You can place a `1` ONLY if the previous character was NOT a `1`.

```java
public class BinaryStrings {

    // Print all binary strings of length n with no consecutive 1s
    // str: the string built so far
    // n: total length we need
    // lastChar: the last character placed ('0' or '1')
    public static void printBinaryStrings(int n, int lastChar, String str) {
        // Base case: string is complete (length = n)
        if (str.length() == n) {
            System.out.println(str);
            return;
        }

        // Choice 1: always place '0'
        // 0 is always safe regardless of last character
        printBinaryStrings(n, 0, str + "0");

        // Choice 2: place '1' ONLY if last character was NOT 1
        if (lastChar != 1) {
            printBinaryStrings(n, 1, str + "1");
        }
    }

    // Alternative version: count the number of valid strings
    // (without printing them all)
    public static int countBinaryStrings(int n, int lastChar) {
        // Base case: no more positions to fill
        if (n == 0) {
            return 1; // One valid way (the empty string)
        }

        // Always can place 0
        int count = countBinaryStrings(n - 1, 0);

        // Can place 1 only if last was not 1
        if (lastChar != 1) {
            count += countBinaryStrings(n - 1, 1);
        }

        return count;
    }

    public static void main(String[] args) {
        System.out.println("=== Binary Strings (no consecutive 1s) ===");

        int n = 3;
        System.out.println("All valid strings of length " + n + ":");
        printBinaryStrings(n, 0, "");
        // Expected output:
        // 000
        // 001
        // 010
        // 100
        // 101

        System.out.println();
        System.out.println("Counting valid strings:");
        for (int len = 1; len <= 6; len++) {
            System.out.println("Length " + len + ": " +
                              countBinaryStrings(len, 0) + " strings");
        }
        // Output: 2, 3, 5, 8, 13, 21 — it's Fibonacci!
        // Because f(n) = f(n-1) + f(n-2) — same recurrence!
    }
}
```

---

## 1.12 Tower of Hanoi

**Problem**: You have 3 rods (A, B, C) and n disks of different sizes placed on rod A in decreasing order (largest at bottom). You need to move ALL disks to rod C, following these rules:
1. Only ONE disk can be moved at a time.
2. Only the TOP disk can be moved.
3. A larger disk can NEVER be placed on top of a smaller disk.

**Recursive insight**: To move n disks from A to C:
1. Move the top (n-1) disks from A → B (using C as helper).
2. Move the largest disk from A → C (direct move).
3. Move the (n-1) disks from B → C (using A as helper).

```java
public class TowerOfHanoi {

    // Move n disks from source to destination using helper
    // n: number of disks
    // source: the rod where disks currently are
    // dest: the rod we want to move disks to
    // helper: the extra rod (auxiliary)
    public static void towerOfHanoi(int n, char source,
                                     char dest, char helper) {
        // Base case: no disks to move
        if (n == 0) {
            return;
        }

        // Step 1: Move top (n-1) disks from source to helper
        // (using dest as helper rod)
        towerOfHanoi(n - 1, source, helper, dest);

        // Step 2: Move the largest disk from source to dest
        System.out.println("Move disk " + n + " from " + source +
                          " to " + dest);

        // Step 3: Move (n-1) disks from helper to dest
        // (using source as helper rod)
        towerOfHanoi(n - 1, helper, dest, source);
    }

    // Count the minimum number of moves needed
    public static int countMoves(int n) {
        if (n == 0) {
            return 0;
        }
        // Each disk requires 2 moves of the smaller disks + 1 move of itself
        return 2 * countMoves(n - 1) + 1;
        // Formula: 2^n - 1
    }

    public static void main(String[] args) {
        System.out.println("=== Tower of Hanoi ===");
        System.out.println("Move 3 disks from A to C:");
        towerOfHanoi(3, 'A', 'C', 'B');

        System.out.println();
        System.out.println("Minimum moves needed:");
        for (int n = 1; n <= 8; n++) {
            System.out.println(n + " disk(s): " + countMoves(n) +
                              " moves (2^" + n + " - 1 = " +
                              ((int)Math.pow(2, n) - 1) + ")");
        }
        // Output: 1, 3, 7, 15, 31, 63, 127, 255

        System.out.println();
        System.out.println("Note: For 64 disks (legend), it would take");
        System.out.println("about 585 billion years at 1 move/second!");
    }
}
```

**Execution trace for towerOfHanoi(2, 'A', 'C', 'B'):**
```
towerOfHanoi(2, A, C, B)
  → towerOfHanoi(1, A, B, C)
      → towerOfHanoi(0, A, C, B) → return (base case)
      → Move disk 1 from A to B
      → towerOfHanoi(0, C, B, A) → return (base case)
  → Move disk 2 from A to C
  → towerOfHanoi(1, B, C, A)
      → towerOfHanoi(0, B, A, C) → return (base case)
      → Move disk 1 from B to C
      → towerOfHanoi(0, A, C, B) → return (base case)
```

---

## 1.13 Recursion with Strings and Arrays — More Examples

```java
public class StringArrayRecursion {

    // ===== STRING RECURSION =====

    // 1. Reverse a string recursively
    public static String reverse(String str) {
        // Base case: empty or single character string
        if (str.isEmpty() || str.length() == 1) {
            return str;
        }
        // Take first character, put it at the end of the reversed rest
        return reverse(str.substring(1)) + str.charAt(0);
    }

    // 2. Check if string is palindrome
    public static boolean isPalindrome(String str, int left, int right) {
        // Base case: pointers crossed or met → it's a palindrome
        if (left >= right) {
            return true;
        }
        // If characters at both ends don't match → not palindrome
        if (str.charAt(left) != str.charAt(right)) {
            return false;
        }
        // Check inner substring
        return isPalindrome(str, left + 1, right - 1);
    }

    // 3. Count occurrences of a character in a string
    public static int countChar(String str, char target, int idx) {
        if (idx == str.length()) {
            return 0;
        }
        int count = (str.charAt(idx) == target) ? 1 : 0;
        return count + countChar(str, target, idx + 1);
    }

    // 4. Replace all occurrences of a character
    public static String replaceChar(String str, char oldChar,
                                      char newChar, int idx) {
        if (idx == str.length()) {
            return "";
        }
        char curr = str.charAt(idx);
        if (curr == oldChar) {
            curr = newChar;
        }
        return curr + replaceChar(str, oldChar, newChar, idx + 1);
    }

    // ===== ARRAY RECURSION =====

    // 5. Find maximum element in array
    public static int findMax(int[] arr, int idx) {
        if (idx == arr.length - 1) {
            return arr[idx];
        }
        int maxInRest = findMax(arr, idx + 1);
        return Math.max(arr[idx], maxInRest);
    }

    // 6. Sum of all elements in array
    public static int arraySum(int[] arr, int idx) {
        if (idx == arr.length) {
            return 0;
        }
        return arr[idx] + arraySum(arr, idx + 1);
    }

    // 7. Linear search (find element, return index or -1)
    public static int linearSearch(int[] arr, int target, int idx) {
        if (idx == arr.length) {
            return -1;
        }
        if (arr[idx] == target) {
            return idx;
        }
        return linearSearch(arr, target, idx + 1);
    }

    // 8. Binary search (array must be sorted)
    public static int binarySearch(int[] arr, int target,
                                    int left, int right) {
        if (left > right) {
            return -1; // Not found
        }
        int mid = left + (right - left) / 2; // Avoid overflow
        if (arr[mid] == target) {
            return mid;
        }
        if (arr[mid] > target) {
            return binarySearch(arr, target, left, mid - 1);
        }
        return binarySearch(arr, target, mid + 1, right);
    }

    public static void main(String[] args) {
        System.out.println("=== More Recursion Examples ===");

        // String examples
        System.out.println("Reverse of 'hello': " + reverse("hello"));
        // Output: olleh

        System.out.println("'racecar' is palindrome: " +
                          isPalindrome("racecar", 0, 6));
        // Output: true

        System.out.println("'hello' is palindrome: " +
                          isPalindrome("hello", 0, 4));
        // Output: false

        System.out.println("Count of 'l' in 'hello': " +
                          countChar("hello", 'l', 0));
        // Output: 2

        System.out.println("Replace 'l' with 'w' in 'hello': " +
                          replaceChar("hello", 'l', 'w', 0));
        // Output: hewwo

        // Array examples
        int[] arr = {3, 7, 2, 9, 5};
        System.out.println("Array sum: " + arraySum(arr, 0));
        // Output: 26

        System.out.println("Max element: " + findMax(arr, 0));
        // Output: 9

        System.out.println("Index of 7: " + linearSearch(arr, 7, 0));
        // Output: 1
        System.out.println("Index of 10: " + linearSearch(arr, 10, 0));
        // Output: -1

        // Binary search (sorted array)
        int[] sortedArr = {1, 3, 5, 7, 9, 11, 13};
        System.out.println("Binary search for 7: " +
                          binarySearch(sortedArr, 7, 0, sortedArr.length - 1));
        // Output: 3
        System.out.println("Binary search for 6: " +
                          binarySearch(sortedArr, 6, 0, sortedArr.length - 1));
        // Output: -1
    }
}
```

# 2. DIVIDE & CONQUER

## 2.0 What is Divide & Conquer?

**Simple definition**: Divide & Conquer is a strategy where you:
1. **Divide** the problem into smaller subproblems (usually halves).
2. **Conquer** each subproblem recursively.
3. **Combine** the solutions to get the answer.

Think of it like cleaning a messy room: Divide the room into sections, clean each section separately, then combine the clean sections.

The two most famous D&C algorithms are **Merge Sort** and **Quick Sort**.

---

## 2.1 Merge Sort

**How it works**:
1. **Divide**: Split the array into two halves.
2. **Conquer**: Recursively sort each half.
3. **Combine**: Merge the two sorted halves into one sorted array.

**The merge step** is the key: You have two already-sorted piles. To merge them, you repeatedly compare the top of each pile and take the smaller one.

```java
public class MergeSort {

    // Main merge sort function
    // arr: the array to sort
    // left: starting index (inclusive)
    // right: ending index (inclusive)
    public static void mergeSort(int[] arr, int left, int right) {
        // Base case: if the subarray has 0 or 1 element, it's already sorted
        if (left >= right) {
            return;
        }

        // DIVIDE: Find the middle point
        // Calculate mid to avoid integer overflow:
        // mid = (left + right) / 2 but safer
        int mid = left + (right - left) / 2;

        // CONQUER: Recursively sort both halves
        mergeSort(arr, left, mid);     // Sort left half
        mergeSort(arr, mid + 1, right); // Sort right half

        // COMBINE: Merge the two sorted halves
        merge(arr, left, mid, right);
    }

    // Merge two sorted subarrays into one sorted array
    // arr[left..mid] is sorted
    // arr[mid+1..right] is sorted
    public static void merge(int[] arr, int left, int mid, int right) {
        // Create a temporary array to store merged result
        int[] temp = new int[right - left + 1];

        // i = index for left subarray (starts at 'left')
        int i = left;
        // j = index for right subarray (starts at 'mid + 1')
        int j = mid + 1;
        // k = index for temp array
        int k = 0;

        // Compare elements from both subarrays and pick the smaller one
        while (i <= mid && j <= right) {
            if (arr[i] < arr[j]) {
                // Left subarray has the smaller element
                temp[k] = arr[i];
                i++; // Move to next element in left subarray
            } else {
                // Right subarray has the smaller element (or equal)
                temp[k] = arr[j];
                j++; // Move to next element in right subarray
            }
            k++; // Move to next position in temp
        }

        // Copy remaining elements from left subarray (if any)
        // This happens when right subarray is exhausted first
        while (i <= mid) {
            temp[k] = arr[i];
            i++;
            k++;
        }

        // Copy remaining elements from right subarray (if any)
        // This happens when left subarray is exhausted first
        while (j <= right) {
            temp[k] = arr[j];
            j++;
            k++;
        }

        // Copy merged temp array back to original array
        for (k = 0; k < temp.length; k++) {
            arr[left + k] = temp[k];
        }
    }

    // Utility method to print array
    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        System.out.println("=== Merge Sort ===");

        int[] arr = {6, 3, 9, 5, 2, 8};

        System.out.print("Original array: ");
        printArray(arr);

        mergeSort(arr, 0, arr.length - 1);

        System.out.print("Sorted array: ");
        printArray(arr);

        System.out.println();
        System.out.println("=== Time Complexity ===");
        System.out.println("Best/Average/Worst: O(n log n)");
        System.out.println("Space Complexity: O(n) — needs temp array");
    }
}
```

**Merge sort visualization for {6, 3, 9, 5, 2, 8}:**
```
                     [6, 3, 9, 5, 2, 8]
                   /                    \
          [6, 3, 9]                    [5, 2, 8]
          /        \                   /        \
       [6]       [3, 9]            [5]        [2, 8]
                 /    \                      /    \
               [3]    [9]                  [2]    [8]
                \      /                     \     /
               merge: [3, 9]               merge: [2, 8]
          \        /                        \        /
        [6] + [3, 9]                       [5] + [2, 8]
           merge: [3, 6, 9]                  merge: [2, 5, 8]
                    \                            /
                     merge: [2, 3, 5, 6, 8, 9]
```

---

## 2.2 Quick Sort

**How it works**:
1. **Select a pivot** (usually the last element).
2. **Partition** the array so that elements smaller than the pivot come first, then the pivot, then elements larger.
3. **Recursively sort** the left and right subarrays (excluding the pivot — it's already in its final position).

**Key difference from Merge Sort**: Quick Sort does the work DURING the division (partitioning), not during combination. Merge Sort does the work during combination (merging).

```java
public class QuickSort {

    // Main quick sort function
    public static void quickSort(int[] arr, int low, int high) {
        // Base case: if subarray has 0 or 1 element, it's sorted
        if (low >= high) {
            return;
        }

        // Partition the array and get the pivot's final index
        // After partition:
        //   - All elements left of pivotIndex are <= pivot
        //   - All elements right of pivotIndex are >= pivot
        //   - The pivot is in its correct sorted position
        int pivotIndex = partition(arr, low, high);

        // Recursively sort elements before pivot
        quickSort(arr, low, pivotIndex - 1);

        // Recursively sort elements after pivot
        quickSort(arr, pivotIndex + 1, high);
    }

    // Partition function: places pivot in correct position
    // and rearranges elements around it
    public static int partition(int[] arr, int low, int high) {
        // Choose the rightmost element as pivot
        int pivot = arr[high];

        // i tracks the boundary between "smaller" and "larger" elements
        // All elements before i are <= pivot
        // i starts at low - 1 (meaning no "smaller" elements found yet)
        int i = low - 1;

        // j scans through the array (except the pivot)
        for (int j = low; j < high; j++) {
            // If current element is smaller than (or equal to) pivot
            if (arr[j] <= pivot) {
                i++; // Expand the "smaller" region

                // Swap arr[i] and arr[j]
                // This moves the small element to the "smaller" region
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
            // If arr[j] > pivot, we do nothing — j just moves forward
            // The element stays in the "larger" region
        }

        // Place the pivot in its correct position
        // Swap arr[i+1] (first "larger" element) with pivot
        i++;
        int temp = arr[i];
        arr[i] = arr[high]; // arr[high] is the pivot
        arr[high] = temp;

        // Return the index where pivot ended up
        return i;
    }

    public static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        System.out.println("=== Quick Sort ===");

        int[] arr = {6, 3, 9, 5, 2, 8};

        System.out.print("Original array: ");
        printArray(arr);

        quickSort(arr, 0, arr.length - 1);

        System.out.print("Sorted array: ");
        printArray(arr);

        System.out.println();
        System.out.println("=== Time Complexity ===");
        System.out.println("Best/Average: O(n log n)");
        System.out.println("Worst: O(n²) — happens when array is already sorted");
        System.out.println("  (because pivot is always the smallest or largest)");
        System.out.println("Space Complexity: O(log n) — recursion stack");
    }
}
```

**Partition visualization for {6, 3, 9, 5, 2, 8}:**
```
pivot = 8, i = -1
j=0: arr[0]=6 ≤ 8 → i=0, swap(6,6) → {6, 3, 9, 5, 2, 8}
j=1: arr[1]=3 ≤ 8 → i=1, swap(3,3) → {6, 3, 9, 5, 2, 8}
j=2: arr[2]=9 > 8 → do nothing
j=3: arr[3]=5 ≤ 8 → i=2, swap(9,5) → {6, 3, 5, 9, 2, 8}
j=4: arr[4]=2 ≤ 8 → i=3, swap(9,2) → {6, 3, 5, 2, 9, 8}
j=5: j=high → stop loop
Place pivot: swap(i+1=4, high=5) → {6, 3, 5, 2, 8, 9}
pivotIndex = 4

Now left={6,3,5,2} and right={9}
```

---

## 2.3 Search in Rotated Sorted Array

**Problem**: You have a sorted array that has been rotated (shifted) at some pivot point. e.g., `{4, 5, 6, 7, 0, 1, 2}`. Find a target value. Do it in O(log n) time.

**How it works**: Modified binary search. At each step, one half of the array is still sorted normally. Check which half is sorted and whether the target lies in it.

```java
public class RotatedArraySearch {

    // Search for target in a rotated sorted array
    // Returns index of target, or -1 if not found
    public static int search(int[] arr, int target, int left, int right) {
        // Base case: empty subarray
        if (left > right) {
            return -1;
        }

        int mid = left + (right - left) / 2;

        // Found target
        if (arr[mid] == target) {
            return mid;
        }

        // Check if LEFT half is sorted (arr[left] to arr[mid])
        if (arr[left] <= arr[mid]) {
            // Left half is sorted
            // Check if target lies in left half
            if (target >= arr[left] && target < arr[mid]) {
                // Target is in left half — search left
                return search(arr, target, left, mid - 1);
            } else {
                // Target is in right half — search right
                return search(arr, target, mid + 1, right);
            }
        }
        // RIGHT half is sorted (arr[mid] to arr[right])
        else {
            // Check if target lies in right half
            if (target > arr[mid] && target <= arr[right]) {
                // Target is in right half — search right
                return search(arr, target, mid + 1, right);
            } else {
                // Target is in left half — search left
                return search(arr, target, left, mid - 1);
            }
        }
    }

    public static void main(String[] args) {
        System.out.println("=== Search in Rotated Sorted Array ===");

        int[] arr = {4, 5, 6, 7, 0, 1, 2};

        System.out.print("Array: ");
        for (int num : arr) System.out.print(num + " ");
        System.out.println();

        int[] targets = {0, 3, 4, 2, 7, 8};
        for (int target : targets) {
            int result = search(arr, target, 0, arr.length - 1);
            System.out.println("Target " + target + " found at index: " + result);
        }

        // Expected output:
        // Target 0 → index 4
        // Target 3 → index -1
        // Target 4 → index 0
        // Target 2 → index 6
        // Target 7 → index 3
        // Target 8 → index -1
    }
}
```

---

## 2.4 Time Complexity Analysis

| Algorithm | Best Case | Average Case | Worst Case | Space |
|-----------|-----------|-------------|------------|-------|
| **Merge Sort** | O(n log n) | O(n log n) | O(n log n) | O(n) |
| **Quick Sort** | O(n log n) | O(n log n) | O(n²) | O(log n) |
| **Binary Search** | O(1) | O(log n) | O(log n) | O(1) |

**Why Merge Sort is always O(n log n)**:
- We divide the array in half at each step: log n levels.
- At each level, we merge n elements total: O(n) per level.
- Total: O(n log n).

**Why Quick Sort can be O(n²)**:
- If the pivot is always the smallest or largest element (e.g., already sorted array with last-element pivot), one partition has n-1 elements and the other has 0.
- This gives n levels instead of log n levels: O(n²).
- Fix: Use a random pivot or median-of-three.

---

# 3. BACKTRACKING

## 3.0 What is Backtracking?

**Simple definition**: Backtracking is a way to solve problems by trying all possibilities, but you "backtrack" (undo) when you realize a choice leads to a dead end.

Think of it like navigating a maze:
1. At each intersection, pick a path.
2. If you hit a dead end, go BACK to the last intersection and try a different path.
3. If all paths from an intersection lead to dead ends, go further back.

**Key idea**: **Decide → Recurse → Undo** (the undo step is what makes it backtracking, not just recursion).

```java
// Template for backtracking:
public void backtrack(parameters) {
    if (base case reached) {
        // Save/print solution
        return;
    }

    for (each possible choice) {
        // DECIDE: make the choice
        doChoice();

        // RECURSE: move to next step
        backtrack(updated parameters);

        // UNDO: unmake the choice (BACKTRACK)
        undoChoice();
    }
}
```

The **undo** step is crucial. Without it, previous choices would affect future explorations.

---

## 3.1 Print All Subsets of a Set (n strings)

**Problem**: Given a set of n distinct elements, print all possible subsets (the power set).

**Example**: For `{"a", "b", "c"}`, the subsets are: `{}, {a}, {b}, {c}, {a,b}, {a,c}, {b,c}, {a,b,c}`.

**Approach**: For each element, we have two choices: include it or exclude it. We make a decision, recurse, then backtrack.

```java
public class FindSubsets {

    // Print all subsets of the given string array
    // arr: the input array
    // idx: current index in arr
    // current: string builder storing current subset
    public static void findSubsets(String[] arr, int idx, StringBuilder current) {
        // Base case: processed all elements
        if (idx == arr.length) {
            // Print current subset (or "{}" if empty)
            if (current.length() == 0) {
                System.out.println("{}");
            } else {
                System.out.println("{" + current.toString() + "}");
            }
            return;
        }

        // DECIDE: include current element
        // Save length to restore later (for backtracking)
        int lenBeforeInclude = current.length();

        // Append current element to the subset
        if (current.length() > 0) {
            current.append(", ");
        }
        current.append(arr[idx]);

        // RECURSE: move to next element
        findSubsets(arr, idx + 1, current);

        // UNDO (BACKTRACK): remove the element we just added
        // Restore StringBuilder to its state before we added this element
        current.setLength(lenBeforeInclude);

        // DECIDE: exclude current element
        // RECURSE: move to next element (without adding anything)
        findSubsets(arr, idx + 1, current);
    }

    // Alternative: using String concatenation (simpler but less efficient)
    public static void findSubsetsSimple(String[] arr, int idx, String current) {
        if (idx == arr.length) {
            if (current.isEmpty()) {
                System.out.println("{}");
            } else {
                System.out.println("{" + current + "}");
            }
            return;
        }

        // Include: add element to current string
        String separator = current.isEmpty() ? "" : ", ";
        findSubsetsSimple(arr, idx + 1, current + separator + arr[idx]);

        // Exclude: don't add element
        // NO "undo" needed because String is immutable — each call gets its own copy!
        findSubsetsSimple(arr, idx + 1, current);
    }

    public static void main(String[] args) {
        System.out.println("=== Find All Subsets ===");

        String[] arr = {"a", "b", "c"};
        System.out.println("Subsets of {a, b, c}:");
        findSubsets(arr, 0, new StringBuilder());

        System.out.println();

        String[] arr2 = {"x", "y"};
        System.out.println("Subsets of {x, y}:");
        findSubsetsSimple(arr2, 0, "");
    }
}
```

**Execution tree for {a, b, c}:**
```
                        start("")
                  /              \
          include a            exclude a
           /      \            /       \
     include b exclude b   include b exclude b
       /   \     /   \      /   \     /   \
     inc c exc inc exc   inc exc  inc  exc
         c    c     c      c    c    c    c
    abc    ab   ac   a    bc    b    c   {}
```

---

## 3.2 Find All Permutations of a String

**Problem**: Given a string, print all possible arrangements (permutations) of its characters.

**Example**: For `"abc"`, the permutations are: `abc, acb, bac, bca, cab, cba`.

**Approach**: Swap each character with the position we're currently filling, recurse, then swap back (backtrack).

```java
public class FindPermutations {

    // Print all permutations of the string
    // str: the character array (so we can swap in place)
    // idx: the position we're currently filling
    public static void findPermutations(char[] str, int idx) {
        // Base case: if we've filled all positions, print the result
        if (idx == str.length) {
            System.out.println(new String(str));
            return;
        }

        // Try placing each remaining character at position 'idx'
        for (int i = idx; i < str.length; i++) {
            // DECIDE: swap character at i with character at idx
            // This places str[i] at the current position
            swap(str, idx, i);

            // RECURSE: fill the next position
            findPermutations(str, idx + 1);

            // UNDO (BACKTRACK): swap back to restore original order
            // This is CRUCIAL — without it, the next iteration would
            // have a modified array
            swap(str, idx, i);
        }
    }

    // Swap characters at positions i and j
    public static void swap(char[] arr, int i, int j) {
        char temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public static void main(String[] args) {
        System.out.println("=== Find Permutations ===");

        String input = "abc";
        System.out.println("Permutations of " + input + ":");
        findPermutations(input.toCharArray(), 0);

        System.out.println();

        String input2 = "AB";
        System.out.println("Permutations of " + input2 + ":");
        findPermutations(input2.toCharArray(), 0);
        // Output: AB, BA
    }
}
```

**Execution trace for "abc":**
```
findPermutations("abc", 0)
  i=0: swap(0,0) → "abc"
    findPermutations("abc", 1)
      i=1: swap(1,1) → "abc"
        findPermutations("abc", 2) ... → prints "abc"
      i=2: swap(1,2) → "acb"
        findPermutations("acb", 2) ... → prints "acb"
      swap(1,2) → "abc" (backtrack)
  i=1: swap(0,1) → "bac"
    ... → prints "bac", "bca"
  swap(0,1) → "abc" (backtrack)
  i=2: swap(0,2) → "cba"
    ... → prints "cba", "cab"
  swap(0,2) → "abc" (backtrack)
```

---

## 3.3 N-Queens Problem

**Problem**: Place N queens on an N×N chessboard such that no two queens attack each other. Queens can attack horizontally, vertically, and diagonally.

**Approach**: Place queens one row at a time. For each row, try each column. If a position is safe, place the queen and recurse to the next row. If no column works, backtrack.

```java
public class NQueens {

    // Count solutions (to verify correctness)
    static int solutionCount = 0;

    // Solve N-Queens and print all solutions
    // board: the chessboard (true = queen placed, false = empty)
    // row: current row we're trying to place a queen in
    public static void nQueens(boolean[][] board, int row) {
        // Base case: placed queens in all rows → found a solution
        if (row == board.length) {
            printBoard(board);
            solutionCount++;
            return;
        }

        // Try placing queen in each column of current row
        for (int col = 0; col < board.length; col++) {
            // Check if position (row, col) is safe
            if (isSafe(board, row, col)) {
                // DECIDE: place queen
                board[row][col] = true;

                // RECURSE: move to next row
                nQueens(board, row + 1);

                // UNDO (BACKTRACK): remove queen
                board[row][col] = false;
            }
        }
        // If no column works, we just return — the previous row will try
        // its next column (backtracking)
    }

    // Check if placing a queen at (row, col) is safe
    public static boolean isSafe(boolean[][] board, int row, int col) {
        // Check vertical (same column, rows above)
        // No need to check rows below — we haven't placed queens there yet
        for (int r = 0; r < row; r++) {
            if (board[r][col]) {
                return false; // Another queen in same column
            }
        }

        // Check upper-left diagonal
        for (int r = row - 1, c = col - 1; r >= 0 && c >= 0; r--, c--) {
            if (board[r][c]) {
                return false; // Another queen on this diagonal
            }
        }

        // Check upper-right diagonal
        for (int r = row - 1, c = col + 1; r >= 0 && c < board.length; r--, c++) {
            if (board[r][c]) {
                return false; // Another queen on this diagonal
            }
        }

        // Position is safe
        return true;
    }

    // Print the board
    public static void printBoard(boolean[][] board) {
        System.out.println("Solution " + solutionCount + ":");
        for (int r = 0; r < board.length; r++) {
            for (int c = 0; c < board.length; c++) {
                if (board[r][c]) {
                    System.out.print("Q ");
                } else {
                    System.out.print(". ");
                }
            }
            System.out.println();
        }
        System.out.println();
    }

    public static void main(String[] args) {
        System.out.println("=== N-Queens Problem ===");

        int n = 4; // Change this to test other sizes
        System.out.println("All solutions for " + n + "-Queens:\n");

        boolean[][] board = new boolean[n][n];
        nQueens(board, 0);

        System.out.println("Total solutions for " + n + "-Queens: " + solutionCount);
        // n=4: 2 solutions, n=8: 92 solutions

        System.out.println();
        System.out.println("Known solution counts:");
        System.out.println("n=1: 1, n=2: 0, n=3: 0, n=4: 2, n=5: 10");
        System.out.println("n=6: 4, n=7: 40, n=8: 92, n=9: 352");
    }
}
```

---

## 3.4 Grid Ways (Count Ways from (0,0) to (n-1,m-1))

**Problem**: Count the number of ways to reach from the top-left corner `(0,0)` to the bottom-right corner `(n-1,m-1)` of an n×m grid. You can only move **right** or **down**.

**Approach**: At each cell `(i,j)`, you can:
1. Move **right** to `(i, j+1)` — if you're not at the last column.
2. Move **down** to `(i+1, j)` — if you're not at the last row.

Base case: If you're at `(n-1, m-1)`, you've reached the destination — count this as 1 way.

```java
public class GridWays {

    // Count ways to reach (n-1, m-1) from (0, 0)
    // i: current row, j: current column
    // n: total rows, m: total columns
    public static int countWays(int i, int j, int n, int m) {
        // Base case: reached destination
        if (i == n - 1 && j == m - 1) {
            return 1; // One valid path found
        }

        // If we're outside the grid (shouldn't happen with correct logic)
        if (i >= n || j >= m) {
            return 0;
        }

        // Move RIGHT: stay in same row, move to next column
        int rightWays = countWays(i, j + 1, n, m);

        // Move DOWN: move to next row, stay in same column
        int downWays = countWays(i + 1, j, n, m);

        // Total ways = ways going right + ways going down
        return rightWays + downWays;
    }

    // OPTIMIZED: Using combinatorial formula
    // Total steps needed: (n-1) down + (m-1) right = (n+m-2) steps
    // Choose (n-1) of those steps to be "down" (rest are "right")
    public static int countWaysOptimized(int n, int m) {
        int steps = n + m - 2; // Total steps needed
        int choose = Math.min(n - 1, m - 1); // Choose the smaller one
        return binomialCoefficient(steps, choose);
    }

    // Calculate C(n, k) = n! / (k! * (n-k)!)
    public static int binomialCoefficient(int n, int k) {
        if (k > n) return 0;
        if (k == 0 || k == n) return 1;

        // Use multiplicative formula for efficiency
        long result = 1;
        for (int i = 1; i <= k; i++) {
            result = result * (n - k + i) / i;
        }
        return (int) result;
    }

    public static void main(String[] args) {
        System.out.println("=== Grid Ways ===");

        // Test various grid sizes
        int[][] grids = {{3, 3}, {4, 4}, {3, 4}, {5, 5}};

        for (int[] grid : grids) {
            int n = grid[0], m = grid[1];
            int ways = countWays(0, 0, n, m);
            int waysOpt = countWaysOptimized(n, m);
            System.out.println(n + "×" + m + " grid: " + ways +
                              " ways (optimized: " + waysOpt + ")");
        }

        // Expected output:
        // 3×3 grid: 6 ways
        // 4×4 grid: 20 ways
        // 3×4 grid: 10 ways
        // 5×5 grid: 70 ways

        System.out.println();
        System.out.println("Visualization of 3×3 grid ways (6 paths):");
        System.out.println("1: → → ↓ ↓");
        System.out.println("2: → ↓ → ↓");
        System.out.println("3: → ↓ ↓ →");
        System.out.println("4: ↓ → → ↓");
        System.out.println("5: ↓ → ↓ →");
        System.out.println("6: ↓ ↓ → →");
    }
}
```

---

## 3.5 Knight's Tour

**Problem**: A knight moves in an L-shape (2 steps in one direction, 1 step perpendicular). Place a knight on a chessboard and make it visit EVERY square exactly once.

```java
public class KnightsTour {

    static final int N = 8; // Board size (8×8)
    static int[][] board = new int[N][N]; // 0 = unvisited, >0 = move number
    static int moveCount = 0;

    // Possible knight moves (8 directions)
    static int[] rowMoves = {-2, -1, 1, 2, 2, 1, -1, -2};
    static int[] colMoves = {1, 2, 2, 1, -1, -2, -2, -1};

    // Solve knight's tour starting from (startRow, startCol)
    public static boolean solveKnightTour(int row, int col, int moveNum) {
        // Mark current cell with the move number
        board[row][col] = moveNum;

        // Base case: visited all N×N cells
        if (moveNum == N * N) {
            moveCount++;
            return true;
        }

        // Try all 8 possible knight moves
        for (int i = 0; i < 8; i++) {
            int nextRow = row + rowMoves[i];
            int nextCol = col + colMoves[i];

            // Check if the move is valid
            if (isValid(nextRow, nextCol)) {
                // RECURSE: try to complete the tour from the new position
                if (solveKnightTour(nextRow, nextCol, moveNum + 1)) {
                    return true; // Found a solution
                }
            }
        }

        // UNDO (BACKTRACK): unmark current cell
        board[row][col] = 0;
        return false; // No valid move leads to a solution
    }

    // Check if cell is on the board and not yet visited
    public static boolean isValid(int row, int col) {
        return row >= 0 && row < N && col >= 0 && col < N && board[row][col] == 0;
    }

    // Print the board (showing move numbers)
    public static void printBoard() {
        for (int r = 0; r < N; r++) {
            for (int c = 0; c < N; c++) {
                System.out.printf("%2d ", board[r][c]);
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        System.out.println("=== Knight's Tour ===");

        // Start from top-left corner (0, 0)
        if (solveKnightTour(0, 0, 1)) {
            System.out.println("Solution found! Move sequence:");
            printBoard();
        } else {
            System.out.println("No solution exists.");
        }

        System.out.println();
        System.out.println("Note: For an 8×8 board starting from (0,0),");
        System.out.println("there are approximately 26.5 quadrillion tours.");
        System.out.println("This code finds one tour using backtracking.");
    }
}
```

---

## 3.6 Sudoku Solver

**Problem**: Solve a 9×9 Sudoku puzzle. Fill empty cells (represented by 0) with digits 1-9 such that:
1. Each row has digits 1-9 without repetition.
2. Each column has digits 1-9 without repetition.
3. Each 3×3 subgrid has digits 1-9 without repetition.

**Approach**: Find an empty cell, try digits 1-9, check if valid, recurse, backtrack if necessary.

```java
public class SudokuSolver {

    static final int SIZE = 9;
    static final int SUBGRID = 3;

    // Solve the Sudoku puzzle in-place
    public static boolean solveSudoku(int[][] board) {
        // Find an empty cell (value = 0)
        int[] emptyCell = findEmpty(board);

        // If no empty cell exists, puzzle is solved
        if (emptyCell == null) {
            return true;
        }

        int row = emptyCell[0];
        int col = emptyCell[1];

        // Try digits 1-9 in the empty cell
        for (int digit = 1; digit <= 9; digit++) {
            // Check if placing this digit is valid
            if (isValid(board, row, col, digit)) {
                // DECIDE: place the digit
                board[row][col] = digit;

                // RECURSE: solve the rest of the puzzle
                if (solveSudoku(board)) {
                    return true; // Found solution
                }

                // UNDO (BACKTRACK): remove the digit
                board[row][col] = 0;
            }
        }

        // No digit works — backtrack
        return false;
    }

    // Find an empty cell (value = 0)
    public static int[] findEmpty(int[][] board) {
        for (int r = 0; r < SIZE; r++) {
            for (int c = 0; c < SIZE; c++) {
                if (board[r][c] == 0) {
                    return new int[]{r, c};
                }
            }
        }
        return null; // No empty cells — puzzle solved
    }

    // Check if placing 'digit' at (row, col) is valid
    public static boolean isValid(int[][] board, int row, int col, int digit) {
        // Check row
        for (int c = 0; c < SIZE; c++) {
            if (board[row][c] == digit) {
                return false;
            }
        }

        // Check column
        for (int r = 0; r < SIZE; r++) {
            if (board[r][col] == digit) {
                return false;
            }
        }

        // Check 3×3 subgrid
        int subgridRowStart = (row / SUBGRID) * SUBGRID;
        int subgridColStart = (col / SUBGRID) * SUBGRID;

        for (int r = subgridRowStart; r < subgridRowStart + SUBGRID; r++) {
            for (int c = subgridColStart; c < subgridColStart + SUBGRID; c++) {
                if (board[r][c] == digit) {
                    return false;
                }
            }
        }

        return true;
    }

    // Print the board
    public static void printBoard(int[][] board) {
        for (int r = 0; r < SIZE; r++) {
            if (r % SUBGRID == 0 && r != 0) {
                System.out.println("------+-------+------");
            }
            for (int c = 0; c < SIZE; c++) {
                if (c % SUBGRID == 0 && c != 0) {
                    System.out.print("| ");
                }
                if (board[r][c] == 0) {
                    System.out.print(". ");
                } else {
                    System.out.print(board[r][c] + " ");
                }
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        System.out.println("=== Sudoku Solver ===");

        int[][] puzzle = {
            {5, 3, 0, 0, 7, 0, 0, 0, 0},
            {6, 0, 0, 1, 9, 5, 0, 0, 0},
            {0, 9, 8, 0, 0, 0, 0, 6, 0},
            {8, 0, 0, 0, 6, 0, 0, 0, 3},
            {4, 0, 0, 8, 0, 3, 0, 0, 1},
            {7, 0, 0, 0, 2, 0, 0, 0, 6},
            {0, 6, 0, 0, 0, 0, 2, 8, 0},
            {0, 0, 0, 4, 1, 9, 0, 0, 5},
            {0, 0, 0, 0, 8, 0, 0, 7, 9}
        };

        System.out.println("Puzzle:");
        printBoard(puzzle);

        if (solveSudoku(puzzle)) {
            System.out.println("\nSolved:");
            printBoard(puzzle);
        } else {
            System.out.println("No solution exists.");
        }
    }
}
```

# 4. ARRAYLIST

## 4.0 ArrayList vs Array

| Feature | Array | ArrayList |
|---------|-------|-----------|
| Size | Fixed (cannot change) | Dynamic (grows/shrinks) |
| Type | Can be primitive (`int[]`) or objects | Only objects (`Integer`, not `int`) |
| Package | Built-in | `java.util.*` |
| Syntax | `int[] arr = new int[5];` | `ArrayList<Integer> list = new ArrayList<>();` |
| Access | `arr[i]` | `list.get(i)` |
| Memory | Contiguous | Contiguous (backed by array) |

**Key insight**: ArrayList is like a resizable array. When it gets full, it creates a new array (typically 1.5× larger) and copies everything over.

---

## 4.1 All Operations: add, get, remove, set, contains, size, sort

```java
import java.util.ArrayList;
import java.util.Collections;

public class ArrayListOperations {

    public static void main(String[] args) {
        System.out.println("=== ArrayList Operations ===\n");

        // Create an ArrayList of Integers
        // NOTE: We use Integer (not int) because ArrayList only works with objects
        ArrayList<Integer> list = new ArrayList<>();

        // ----- add(element) — appends to the end -----
        list.add(10); // list: [10]
        list.add(20); // list: [10, 20]
        list.add(30); // list: [10, 20, 30]
        list.add(40); // list: [10, 20, 30, 40]
        System.out.println("After add(): " + list);
        // Output: [10, 20, 30, 40]

        // ----- add(index, element) — inserts at specific position -----
        list.add(2, 25); // Insert 25 at index 2 (between 20 and 30)
        System.out.println("After add(2, 25): " + list);
        // Output: [10, 20, 25, 30, 40]

        // ----- get(index) — retrieve element at index -----
        int element = list.get(3); // Element at index 3
        System.out.println("get(3): " + element);
        // Output: 30

        // ----- remove(index) — remove element at index -----
        int removed = list.remove(2); // Remove element at index 2 (which is 25)
        System.out.println("Removed element at index 2: " + removed);
        System.out.println("After remove: " + list);
        // Output: Removed 25, list: [10, 20, 30, 40]

        // ----- set(index, element) — replace element at index -----
        int oldValue = list.set(1, 99); // Replace index 1 (20) with 99
        System.out.println("Replaced " + oldValue + " with 99");
        System.out.println("After set(): " + list);
        // Output: [10, 99, 30, 40]

        // ----- contains(element) — check if element exists -----
        boolean has30 = list.contains(30);
        boolean has50 = list.contains(50);
        System.out.println("Contains 30? " + has30); // true
        System.out.println("Contains 50? " + has50); // false

        // ----- size() — get number of elements -----
        System.out.println("Size: " + list.size());
        // Output: 4

        // ----- indexOf(element) — find index of element -----
        System.out.println("Index of 30: " + list.indexOf(30));
        // Output: 2
        System.out.println("Index of 999: " + list.indexOf(999));
        // Output: -1 (not found)

        // ----- isEmpty() — check if list is empty -----
        System.out.println("Is empty? " + list.isEmpty());
        // Output: false

        // ----- clear() — remove all elements -----
        ArrayList<Integer> temp = new ArrayList<>();
        temp.add(1);
        temp.add(2);
        System.out.println("Before clear: " + temp);
        temp.clear();
        System.out.println("After clear: " + temp);
        // Output: []

        // ----- sort() — sort the list -----
        ArrayList<Integer> unsorted = new ArrayList<>();
        unsorted.add(50);
        unsorted.add(10);
        unsorted.add(40);
        unsorted.add(20);
        unsorted.add(30);

        System.out.println("\nUnsorted: " + unsorted);
        Collections.sort(unsorted); // Sort in ascending order
        System.out.println("Sorted ascending: " + unsorted);

        // Sort in descending order
        Collections.sort(unsorted, Collections.reverseOrder());
        System.out.println("Sorted descending: " + unsorted);

        // ----- Iterating over ArrayList (for loop) -----
        System.out.println("\nIterating with for loop:");
        for (int i = 0; i < list.size(); i++) {
            System.out.println("Index " + i + ": " + list.get(i));
        }

        // ----- Iterating with for-each loop -----
        System.out.println("\nIterating with for-each:");
        for (int num : list) {
            System.out.println(num);
        }

        // ----- Working with Strings -----
        System.out.println("\n=== ArrayList of Strings ===");
        ArrayList<String> names = new ArrayList<>();
        names.add("Alice");
        names.add("Bob");
        names.add("Charlie");
        System.out.println("Names: " + names);
        Collections.sort(names);
        System.out.println("Sorted names: " + names);
    }
}
```

---

## 4.2 Multi-dimensional ArrayList

Just like you can have a 2D array (`int[][]`), you can have an ArrayList of ArrayLists.

```java
import java.util.ArrayList;

public class MultiDimensionalArrayList {

    public static void main(String[] args) {
        System.out.println("=== Multi-dimensional ArrayList ===\n");

        // Create a 2D ArrayList (ArrayList of ArrayLists)
        // Think of it as a "jagged" 2D array where each row can have different length
        ArrayList<ArrayList<Integer>> matrix = new ArrayList<>();

        // Create rows
        ArrayList<Integer> row1 = new ArrayList<>();
        row1.add(1);
        row1.add(2);
        row1.add(3);

        ArrayList<Integer> row2 = new ArrayList<>();
        row2.add(4);
        row2.add(5);

        ArrayList<Integer> row3 = new ArrayList<>();
        row3.add(6);
        row3.add(7);
        row3.add(8);
        row3.add(9);

        // Add rows to the matrix
        matrix.add(row1);
        matrix.add(row2);
        matrix.add(row3);

        System.out.println("2D ArrayList (jagged):");
        for (int r = 0; r < matrix.size(); r++) {
            System.out.print("Row " + r + ": ");
            for (int c = 0; c < matrix.get(r).size(); c++) {
                System.out.print(matrix.get(r).get(c) + " ");
            }
            System.out.println();
        }

        System.out.println();

        // --- Creating a rectangular 2D ArrayList (like a 3×4 matrix) ---
        int rows = 3, cols = 4;
        ArrayList<ArrayList<Integer>> rectMatrix = new ArrayList<>();

        // Initialize all cells to 0
        for (int r = 0; r < rows; r++) {
            rectMatrix.add(new ArrayList<>());
            for (int c = 0; c < cols; c++) {
                rectMatrix.get(r).add(0);
            }
        }

        // Fill with values (row * col format)
        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                rectMatrix.get(r).set(c, r * cols + c);
            }
        }

        System.out.println("Rectangular 3×4 matrix:");
        for (ArrayList<Integer> row : rectMatrix) {
            for (int val : row) {
                System.out.print(val + "\t");
            }
            System.out.println();
        }

        // Output:
        // 0  1  2  3
        // 4  5  6  7
        // 8  9  10 11
    }
}
```

---

## 4.3 Container with Most Water

**Problem**: Given an array of heights, where the i-th element represents the height of a vertical line at position i. Find two lines that, together with the x-axis, form a container that holds the most water.

**Brute Force**: Check every pair of lines (i, j), calculate the area, keep the maximum. O(n²).

**Two Pointer**: Start with the widest container (i=0, j=n-1). Move the pointer with the SMALLER height inward.

```java
public class ContainerWithMostWater {

    // BRUTE FORCE: Check all pairs — O(n²)
    public static int maxAreaBrute(int[] height) {
        int n = height.length;
        int maxArea = 0;

        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                // Width = distance between lines
                int width = j - i;
                // Height = smaller of the two lines (water spills over the shorter one)
                int h = Math.min(height[i], height[j]);
                // Area = width × height
                int area = width * h;
                // Update max area if current is larger
                if (area > maxArea) {
                    maxArea = area;
                }
            }
        }

        return maxArea;
    }

    // TWO POINTER: Optimal — O(n)
    public static int maxAreaTwoPointer(int[] height) {
        int n = height.length;
        int maxArea = 0;

        // Start with pointers at both ends (widest possible container)
        int left = 0;
        int right = n - 1;

        // Move pointers toward each other
        while (left < right) {
            // Calculate width
            int width = right - left;
            // Height is limited by the shorter line
            int h = Math.min(height[left], height[right]);
            // Current area
            int area = width * h;

            // Update max area
            maxArea = Math.max(maxArea, area);

            // Move the pointer pointing to the SHORTER line
            if (height[left] < height[right]) {
                left++; // Move left pointer rightward
            } else {
                right--; // Move right pointer leftward
            }
        }

        return maxArea;
    }

    public static void main(String[] args) {
        System.out.println("=== Container With Most Water ===\n");

        int[] height = {1, 8, 6, 2, 5, 4, 8, 3, 7};

        System.out.println("Heights: [1, 8, 6, 2, 5, 4, 8, 3, 7]");

        long start = System.nanoTime();
        int bruteResult = maxAreaBrute(height);
        long bruteTime = System.nanoTime() - start;

        start = System.nanoTime();
        int twoPointerResult = maxAreaTwoPointer(height);
        long twoPointerTime = System.nanoTime() - start;

        System.out.println("Brute Force: " + bruteResult + " (took " + bruteTime + " ns)");
        System.out.println("Two Pointer: " + twoPointerResult + " (took " + twoPointerTime + " ns)");
        // Both should return 49 (between indices 1 and 6: height 8, width 5)

        System.out.println("Max area = 49");
    }
}
```

---

## 4.4 Pair Sum

**Problem**: Given a sorted array (or ArrayList), find if there exists a pair with a given target sum.

**Brute Force**: Check every pair. O(n²).

**Two Pointer**: Since the array is sorted, place one pointer at the start and one at the end. If the sum is too small, move the left pointer right. If too large, move the right pointer left.

```java
import java.util.ArrayList;
import java.util.HashMap;

public class PairSum {

    // BRUTE FORCE: Check all pairs — O(n²)
    public static boolean pairSumBrute(ArrayList<Integer> list, int target) {
        for (int i = 0; i < list.size(); i++) {
            for (int j = i + 1; j < list.size(); j++) {
                if (list.get(i) + list.get(j) == target) {
                    System.out.println("Found: " + list.get(i) + " + " +
                                      list.get(j) + " = " + target);
                    return true;
                }
            }
        }
        return false;
    }

    // TWO POINTER: Works on sorted arrays only — O(n)
    public static boolean pairSumTwoPointer(ArrayList<Integer> list, int target) {
        int left = 0;
        int right = list.size() - 1;

        while (left < right) {
            int sum = list.get(left) + list.get(right);

            if (sum == target) {
                System.out.println("Found: " + list.get(left) + " + " +
                                  list.get(right) + " = " + target);
                return true;
            } else if (sum < target) {
                left++; // Sum too small — increase it
            } else {
                right--; // Sum too large — decrease it
            }
        }

        return false;
    }

    // RETURN PAIR INDICES
    public static int[] pairSumIndices(ArrayList<Integer> list, int target) {
        int left = 0;
        int right = list.size() - 1;

        while (left < right) {
            int sum = list.get(left) + list.get(right);
            if (sum == target) {
                return new int[]{left, right};
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }

        return new int[]{-1, -1}; // Not found
    }

    // TWO SUM — what if the array is NOT sorted?
    // Use a HashMap for O(n) time
    public static int[] pairSumUnsorted(ArrayList<Integer> list, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < list.size(); i++) {
            int curr = list.get(i);
            int complement = target - curr;

            // Check if we've seen the complement before
            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }

            // Store current element with its index
            map.put(curr, i);
        }

        return new int[]{-1, -1};
    }

    public static void main(String[] args) {
        System.out.println("=== Pair Sum ===");

        // Sorted ArrayList
        ArrayList<Integer> sorted = new ArrayList<>();
        sorted.add(1);
        sorted.add(2);
        sorted.add(3);
        sorted.add(4);
        sorted.add(5);
        sorted.add(6);
        System.out.println("Sorted list: " + sorted);

        int target = 9;
        System.out.println("Target sum: " + target);

        System.out.print("Brute force: ");
        pairSumBrute(sorted, target);

        System.out.print("Two pointer: ");
        boolean found = pairSumTwoPointer(sorted, target);

        int[] indices = pairSumIndices(sorted, target);
        System.out.println("Indices: [" + indices[0] + ", " + indices[1] + "]");

        // Unsorted array
        System.out.println("\n=== Pair Sum (Unsorted) ===");
        ArrayList<Integer> unsorted = new ArrayList<>();
        unsorted.add(3);
        unsorted.add(5);
        unsorted.add(2);
        unsorted.add(8);
        unsorted.add(1);
        System.out.println("Unsorted list: " + unsorted);

        int[] result = pairSumUnsorted(unsorted, 10);
        System.out.println("Target 10 found at indices: [" +
                          result[0] + ", " + result[1] + "]");
    }
}
```

---

# 5. LINKED LIST

## 5.0 What is a Linked List?

**Simple definition**: A linked list is a sequence of **nodes**, where each node contains:
1. **Data** (the value)
2. A **pointer** (reference) to the next node

Unlike arrays, nodes are NOT stored in contiguous memory. Each node "points" to the next.

```
Array:  [10] [20] [30] [40]    ← contiguous in memory, index-based access

Linked List:
  [10 | •] → [20 | •] → [30 | •] → [40 | null]
   ↑                                    ↑
  head                                tail (last node)
```

**Why Linked List?**
- **Dynamic size** (like ArrayList)
- **Fast insertions/deletions at the beginning** (O(1) vs O(n) for arrays)
- **No random access** — to get the 5th element, you must traverse from the head

---

## 5.1 Node Class, LinkedList Class

```java
// Node class: represents a single element in the linked list
class Node {
    int data;      // The value stored in this node
    Node next;     // Reference to the next node (null if this is the last)

    // Constructor
    Node(int data) {
        this.data = data;
        this.next = null; // By default, a new node points to nothing
    }
}

// LinkedList class: manages the entire list
class LinkedList {
    Node head;  // First node in the list
    Node tail;  // Last node in the list (useful for O(1) addLast)
    int size;   // Number of nodes in the list

    // Constructor: creates an empty list
    LinkedList() {
        this.head = null;
        this.tail = null;
        this.size = 0;
    }

    // ----- ADD OPERATIONS -----

    // addFirst: add a node at the BEGINNING — O(1)
    public void addFirst(int data) {
        // Step 1: Create a new node
        Node newNode = new Node(data);

        // Step 2: Point the new node to the current head
        newNode.next = head;

        // Step 3: Update head to be the new node
        head = newNode;

        // Step 4: If this is the first node, it's also the tail
        if (tail == null) {
            tail = newNode;
        }

        // Step 5: Increase size
        size++;
    }

    // addLast: add a node at the END — O(1) because we have tail
    public void addLast(int data) {
        // Create new node
        Node newNode = new Node(data);

        // If list is empty, new node is both head and tail
        if (head == null) {
            head = newNode;
            tail = newNode;
        } else {
            // Point current tail's next to new node
            tail.next = newNode;
            // Update tail to be the new node
            tail = newNode;
        }

        size++;
    }

    // add at SPECIFIC INDEX — O(n)
    public void add(int index, int data) {
        // Check if index is valid
        if (index < 0 || index > size) {
            System.out.println("Invalid index: " + index);
            return;
        }

        // If adding at beginning, use addFirst
        if (index == 0) {
            addFirst(data);
            return;
        }

        // If adding at end, use addLast
        if (index == size) {
            addLast(data);
            return;
        }

        // Create new node
        Node newNode = new Node(data);

        // Traverse to the node just before the insertion point (index-1)
        Node current = head;
        for (int i = 0; i < index - 1; i++) {
            current = current.next;
        }

        // Insert the new node
        newNode.next = current.next;
        current.next = newNode;

        size++;
    }

    // ----- REMOVE OPERATIONS -----

    // removeFirst: remove the FIRST node — O(1)
    public int removeFirst() {
        if (head == null) {
            System.out.println("List is empty");
            return Integer.MIN_VALUE;
        }

        int data = head.data;
        head = head.next;     // Move head to the next node
        size--;

        // If list is now empty, tail should also be null
        if (head == null) {
            tail = null;
        }

        return data;
    }

    // removeLast: remove the LAST node — O(n) for singly linked list
    public int removeLast() {
        if (head == null) {
            System.out.println("List is empty");
            return Integer.MIN_VALUE;
        }

        // If only one node, removeFirst handles it
        if (size == 1) {
            return removeFirst();
        }

        // Traverse to second-to-last node (at index size-2)
        Node current = head;
        for (int i = 0; i < size - 2; i++) {
            current = current.next;
        }

        // current is now the second-to-last node
        int data = current.next.data; // Tail's data
        current.next = null;          // Remove reference to tail
        tail = current;               // Update tail
        size--;

        return data;
    }

    // remove at INDEX — O(n)
    public int remove(int index) {
        if (index < 0 || index >= size) {
            System.out.println("Invalid index");
            return Integer.MIN_VALUE;
        }

        if (index == 0) {
            return removeFirst();
        }

        if (index == size - 1) {
            return removeLast();
        }

        // Traverse to node just before the one to remove
        Node current = head;
        for (int i = 0; i < index - 1; i++) {
            current = current.next;
        }

        int data = current.next.data;
        current.next = current.next.next;
        size--;

        return data;
    }

    // ----- SEARCH -----

    // Iterative search — O(n)
    public int searchIterative(int key) {
        Node current = head;
        int index = 0;

        while (current != null) {
            if (current.data == key) {
                return index; // Found, return index
            }
            current = current.next;
            index++;
        }

        return -1; // Not found
    }

    // Recursive search — O(n)
    public int searchRecursive(int key) {
        return searchRecursiveHelper(head, key, 0);
    }

    private int searchRecursiveHelper(Node node, int key, int index) {
        // Base case: reached end of list
        if (node == null) {
            return -1;
        }

        // If current node has the key, return its index
        if (node.data == key) {
            return index;
        }

        // Recurse to next node
        return searchRecursiveHelper(node.next, key, index + 1);
    }

    // ----- UTILITY -----

    // Print the list
    public void print() {
        Node current = head;
        System.out.print("LinkedList: ");
        while (current != null) {
            System.out.print(current.data + " → ");
            current = current.next;
        }
        System.out.println("null");
        System.out.println("Size: " + size);
    }

    // Get size
    public int getSize() {
        return size;
    }
}

// Main class to test everything
public class LinkedListBasics {

    public static void main(String[] args) {
        System.out.println("=== Linked List Basics ===\n");

        // Create an empty linked list
        LinkedList list = new LinkedList();
        list.print(); // LinkedList: null, Size: 0

        // Add elements at the beginning
        System.out.println("\n--- addFirst ---");
        list.addFirst(30);
        list.addFirst(20);
        list.addFirst(10);
        list.print(); // 10 → 20 → 30 → null

        // Add elements at the end
        System.out.println("\n--- addLast ---");
        list.addLast(40);
        list.addLast(50);
        list.print(); // 10 → 20 → 30 → 40 → 50 → null

        // Add at specific index
        System.out.println("\n--- add at index ---");
        list.add(2, 25); // Insert 25 at index 2
        list.print(); // 10 → 20 → 25 → 30 → 40 → 50 → null

        // Remove first
        System.out.println("\n--- removeFirst ---");
        int removed = list.removeFirst();
        System.out.println("Removed: " + removed);
        list.print(); // 20 → 25 → 30 → 40 → 50 → null

        // Remove last
        System.out.println("\n--- removeLast ---");
        removed = list.removeLast();
        System.out.println("Removed: " + removed);
        list.print(); // 20 → 25 → 30 → 40 → null

        // Remove at index
        System.out.println("\n--- remove at index ---");
        removed = list.remove(1); // Remove index 1 (25)
        System.out.println("Removed: " + removed);
        list.print(); // 20 → 30 → 40 → null

        // Search
        System.out.println("\n--- Search ---");
        System.out.println("Index of 30 (iterative): " + list.searchIterative(30));
        System.out.println("Index of 30 (recursive): " + list.searchRecursive(30));
        System.out.println("Index of 100 (iterative): " + list.searchIterative(100));
        System.out.println("Index of 100 (recursive): " + list.searchRecursive(100));
    }
}
```

---

## 5.2 Reverse a Linked List (Iterative + Recursive)

**Iterative approach**: Walk through the list and change each node's `next` pointer to point to the previous node.

```
Initial:  10 → 20 → 30 → null
           ↑
         head

After reverse: null ← 10 ← 20 ← 30
                                   ↑
                                 head
```

```java
// Extending our LinkedList class with reverse methods
class LinkedListExtended extends LinkedList {

    // ITERATIVE REVERSE — O(n) time, O(1) space
    public void reverseIterative() {
        if (head == null || head.next == null) {
            return; // 0 or 1 node — already reversed
        }

        Node prev = null;   // The node before current (starts as null)
        Node current = head; // The node we're currently processing
        Node next;          // The node after current (to avoid losing reference)

        while (current != null) {
            // Save the next node (before we break the link)
            next = current.next;

            // REVERSE: point current.next to the PREVIOUS node
            current.next = prev;

            // Move all pointers forward
            prev = current;    // prev moves to current
            current = next;    // current moves to next
        }

        // After the loop:
        // prev points to the OLD tail (which is the NEW head)
        tail = head;  // Old head is now the tail
        head = prev;  // Old tail is now the head
    }

    // RECURSIVE REVERSE — O(n) time, O(n) space (recursion stack)
    public void reverseRecursive() {
        tail = head; // Old head will become the new tail
        head = reverseRecursiveHelper(head);
    }

    private Node reverseRecursiveHelper(Node node) {
        // Base case: last node (or empty list)
        if (node == null || node.next == null) {
            return node; // This becomes the new head
        }

        // Recursively reverse the rest of the list
        Node newHead = reverseRecursiveHelper(node.next);

        // After recursion returns, node.next is the node AFTER current
        // Make THAT node point back to current node
        node.next.next = node;

        // Break the original forward link
        node.next = null;

        return newHead;
    }
}

public class ReverseLinkedList {

    public static void main(String[] args) {
        System.out.println("=== Reverse Linked List ===\n");

        // Test Iterative Reverse
        LinkedListExtended list1 = new LinkedListExtended();
        list1.addLast(10);
        list1.addLast(20);
        list1.addLast(30);
        list1.addLast(40);

        System.out.println("Original:");
        list1.print();

        list1.reverseIterative();
        System.out.println("After iterative reverse:");
        list1.print();

        System.out.println();

        // Test Recursive Reverse
        LinkedListExtended list2 = new LinkedListExtended();
        list2.addLast(10);
        list2.addLast(20);
        list2.addLast(30);
        list2.addLast(40);

        System.out.println("Original:");
        list2.print();

        list2.reverseRecursive();
        System.out.println("After recursive reverse:");
        list2.print();

        // Edge case: single node
        LinkedListExtended list3 = new LinkedListExtended();
        list3.addLast(5);
        System.out.println("\nSingle node:");
        list3.print();
        list3.reverseIterative();
        list3.print();
    }
}
```

---

## 5.3 Find and Remove nth Node from End

**Problem**: Given a linked list, remove the nth node from the end. Do it in one pass.

**Two-pointer approach**: Use two pointers spaced n+1 nodes apart. When the front pointer reaches the end, the back pointer is at the node just before the one to remove.

```java
class LinkedListRemoveNth extends LinkedListExtended {

    // Remove nth node from the END (1-indexed)
    public int removeNthFromEnd(int n) {
        if (head == null || n <= 0 || n > size) {
            System.out.println("Invalid operation");
            return Integer.MIN_VALUE;
        }

        // Create a dummy node that points to head
        Node dummy = new Node(0);
        dummy.next = head;

        Node fast = dummy; // Fast pointer
        Node slow = dummy; // Slow pointer

        // Move fast pointer n+1 steps ahead of slow
        for (int i = 0; i <= n; i++) {
            fast = fast.next;
        }

        // Move both pointers until fast reaches the end
        while (fast != null) {
            slow = slow.next;
            fast = fast.next;
        }

        // slow is now at the node BEFORE the one to remove
        int removedData = slow.next.data;
        slow.next = slow.next.next; // Skip the target node

        // Update head if we removed the first node
        head = dummy.next;

        // Update tail if we removed the last node
        if (slow.next == null) {
            tail = slow;
        }

        size--;
        return removedData;
    }
}

public class RemoveNthFromEnd {

    public static void main(String[] args) {
        System.out.println("=== Remove Nth Node from End ===\n");

        LinkedListRemoveNth list = new LinkedListRemoveNth();
        list.addLast(10);
        list.addLast(20);
        list.addLast(30);
        list.addLast(40);
        list.addLast(50);

        System.out.println("Original:");
        list.print(); // 10 → 20 → 30 → 40 → 50 → null

        int n = 2;
        int removed = list.removeNthFromEnd(n);
        System.out.println("Removed " + n + "nd from end: " + removed);
        list.print(); // 10 → 20 → 30 → 50 → null

        // Remove head (4th from end in the new list)
        removed = list.removeNthFromEnd(4);
        System.out.println("Removed 4th from end: " + removed);
        list.print(); // 20 → 30 → 50 → null

        // Remove tail (1st from end)
        removed = list.removeNthFromEnd(1);
        System.out.println("Removed last: " + removed);
        list.print(); // 20 → 30 → null
    }
}
```

---

## 5.4 Check if Palindrome

**Problem**: Check if a linked list's values form a palindrome (reads the same forward and backward).

**Approach**: 
1. Find the **middle** of the list (slow/fast pointer).
2. **Reverse** the second half.
3. **Compare** the first half with the reversed second half.

```java
class LinkedListPalindrome extends LinkedListExtended {

    // Check if the linked list is a palindrome
    public boolean isPalindrome() {
        if (head == null || head.next == null) {
            return true;
        }

        // Step 1: Find the middle node
        Node slow = head;
        Node fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;       // Move 1 step
            fast = fast.next.next;  // Move 2 steps
        }

        // Step 2: Reverse the second half
        Node secondHalfStart = reverse(slow);

        // Step 3: Compare first half and reversed second half
        Node firstHalf = head;
        Node secondHalf = secondHalfStart;
        boolean isPalindrome = true;

        while (secondHalf != null) {
            if (firstHalf.data != secondHalf.data) {
                isPalindrome = false;
                break;
            }
            firstHalf = firstHalf.next;
            secondHalf = secondHalf.next;
        }

        // Step 4: Restore the list (re-reverse the second half)
        reverse(secondHalfStart);

        return isPalindrome;
    }

    // Helper to reverse a linked list starting from a given node
    private Node reverse(Node startNode) {
        Node prev = null;
        Node current = startNode;

        while (current != null) {
            Node next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }

        return prev;
    }
}

public class PalindromeLinkedList {

    public static void main(String[] args) {
        System.out.println("=== Palindrome Linked List ===\n");

        // Test palindrome: 1 → 2 → 3 → 2 → 1
        LinkedListPalindrome list1 = new LinkedListPalindrome();
        list1.addLast(1);
        list1.addLast(2);
        list1.addLast(3);
        list1.addLast(2);
        list1.addLast(1);
        System.out.print("List 1: ");
        list1.print();
        System.out.println("Is palindrome? " + list1.isPalindrome()); // true

        // Test non-palindrome: 1 → 2 → 3 → 4
        LinkedListPalindrome list2 = new LinkedListPalindrome();
        list2.addLast(1);
        list2.addLast(2);
        list2.addLast(3);
        list2.addLast(4);
        System.out.print("List 2: ");
        list2.print();
        System.out.println("Is palindrome? " + list2.isPalindrome()); // false

        // Test even-length palindrome: 1 → 2 → 2 → 1
        LinkedListPalindrome list3 = new LinkedListPalindrome();
        list3.addLast(1);
        list3.addLast(2);
        list3.addLast(2);
        list3.addLast(1);
        System.out.print("List 3: ");
        list3.print();
        System.out.println("Is palindrome? " + list3.isPalindrome()); // true
    }
}
```

---

## 5.5 Detect Cycle (Floyd's Cycle Detection)

**Problem**: A linked list has a cycle if some node's `next` pointer points back to an earlier node. Detect if a cycle exists.

**Floyd's Cycle Detection (Tortoise and Hare)**: `slow` moves 1 step, `fast` moves 2 steps. If there's a cycle, they'll meet.

```java
class LinkedListCycle extends LinkedList {

    // Detect if a cycle exists
    public boolean hasCycle() {
        if (head == null || head.next == null) {
            return false;
        }

        Node slow = head;  // Tortoise: moves 1 step
        Node fast = head;  // Hare: moves 2 steps

        while (fast != null && fast.next != null) {
            slow = slow.next;       // Move 1 step
            fast = fast.next.next;  // Move 2 steps

            if (slow == fast) {
                return true; // They met — there's a cycle!
            }
        }

        return false; // fast reached null — no cycle
    }

    // REMOVE CYCLE: find the start of the cycle and break it
    public void removeCycle() {
        if (head == null || head.next == null) {
            return;
        }

        // Step 1: Detect cycle
        Node slow = head;
        Node fast = head;
        boolean cycleExists = false;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {
                cycleExists = true;
                break;
            }
        }

        if (!cycleExists) {
            return; // No cycle to remove
        }

        // Step 2: Find the START node of the cycle
        // Reset one pointer to head, move both at same speed
        slow = head;

        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }

        // Now slow (and fast) point to the START of the cycle
        // Step 3: Find the last node of the cycle
        Node cycleNode = fast;
        while (fast.next != cycleNode) {
            fast = fast.next;
        }

        // Step 4: Break the cycle
        fast.next = null;
        System.out.println("Cycle removed!");
    }
}

public class CycleDetection {

    public static void main(String[] args) {
        System.out.println("=== Cycle Detection (Floyd's Algorithm) ===\n");

        // Create a list with a cycle
        LinkedListCycle list = new LinkedListCycle();
        list.addLast(10);
        list.addLast(20);
        list.addLast(30);
        list.addLast(40);
        list.addLast(50);

        // Create a cycle: make the last node (50) point back to (20)
        Node lastNode = list.head;
        while (lastNode.next != null) {
            lastNode = lastNode.next;
        }
        Node secondNode = list.head.next;
        lastNode.next = secondNode;

        System.out.println("Created a cycle: 50 → 20");
        System.out.println("Has cycle? " + list.hasCycle()); // true

        // Remove the cycle
        list.removeCycle();
        System.out.println("Has cycle after removal? " + list.hasCycle()); // false

        System.out.println();

        // Normal list (no cycle)
        LinkedListCycle list2 = new LinkedListCycle();
        list2.addLast(10);
        list2.addLast(20);
        list2.addLast(30);
        System.out.println("Normal list has cycle? " + list2.hasCycle()); // false

        // Empty list
        LinkedListCycle list3 = new LinkedListCycle();
        System.out.println("Empty list has cycle? " + list3.hasCycle()); // false
    }
}
```

---

## 5.6 Merge Sort on Linked List

**Why use merge sort on linked lists?** Unlike arrays, linked lists don't have O(1) random access, so Quick Sort's partitioning doesn't work well. Merge Sort is perfect because:
1. Finding the middle is easy (slow/fast pointer).
2. Merging two sorted linked lists is O(1) space (just adjust pointers).

```java
class LinkedListMergeSort extends LinkedList {

    // Sort the linked list using merge sort
    public void mergeSort() {
        if (head == null || head.next == null) {
            return; // 0 or 1 node — already sorted
        }

        head = mergeSortHelper(head);

        // Update tail — traverse to the end
        Node current = head;
        while (current != null && current.next != null) {
            current = current.next;
        }
        tail = current;
    }

    // Recursive merge sort helper
    private Node mergeSortHelper(Node node) {
        if (node == null || node.next == null) {
            return node;
        }

        // Step 1: Find the middle
        Node mid = findMiddle(node);

        // Step 2: Split into two halves
        Node left = node;
        Node right = mid.next;
        mid.next = null; // Break the link

        // Step 3: Recursively sort both halves
        Node sortedLeft = mergeSortHelper(left);
        Node sortedRight = mergeSortHelper(right);

        // Step 4: Merge the two sorted halves
        return merge(sortedLeft, sortedRight);
    }

    // Find the middle node using slow/fast pointer
    private Node findMiddle(Node node) {
        Node slow = node;
        Node fast = node.next;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }

    // Merge two sorted linked lists
    private Node merge(Node left, Node right) {
        Node dummy = new Node(0);
        Node current = dummy;

        while (left != null && right != null) {
            if (left.data <= right.data) {
                current.next = left;
                left = left.next;
            } else {
                current.next = right;
                right = right.next;
            }
            current = current.next;
        }

        if (left != null) {
            current.next = left;
        }
        if (right != null) {
            current.next = right;
        }

        return dummy.next;
    }
}

public class MergeSortLinkedList {

    public static void main(String[] args) {
        System.out.println("=== Merge Sort on Linked List ===\n");

        LinkedListMergeSort list = new LinkedListMergeSort();
        list.addLast(50);
        list.addLast(10);
        list.addLast(40);
        list.addLast(20);
        list.addLast(30);

        System.out.println("Original:");
        list.print(); // 50 → 10 → 40 → 20 → 30 → null

        list.mergeSort();

        System.out.println("After merge sort:");
        list.print(); // 10 → 20 → 30 → 40 → 50 → null
    }
}
```

---

## 5.7 Zig-Zag Linked List

**Problem**: Rearrange a linked list in zig-zag order: first node, last node, second node, second-last node, etc.

**Example**: `1 → 2 → 3 → 4 → 5` becomes `1 → 5 → 2 → 4 → 3`.

```java
class LinkedListZigZag extends LinkedListExtended {

    // Rearrange the list in zig-zag order
    public void zigZag() {
        if (head == null || head.next == null) {
            return;
        }

        // Step 1: Find the middle
        Node slow = head;
        Node fast = head.next;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }

        Node mid = slow;

        // Step 2: Reverse the second half
        Node secondHalfStart = reverse(mid.next);
        mid.next = null;

        // Step 3: Merge by interleaving
        Node first = head;
        Node second = secondHalfStart;

        while (first != null && second != null) {
            Node firstNext = first.next;
            Node secondNext = second.next;

            first.next = second;
            second.next = firstNext;

            first = firstNext;
            second = secondNext;
        }

        // Update tail
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        tail = current;
    }
}

public class ZigZagLinkedList {

    public static void main(String[] args) {
        System.out.println("=== Zig-Zag Linked List ===\n");

        LinkedListZigZag list = new LinkedListZigZag();
        list.addLast(1);
        list.addLast(2);
        list.addLast(3);
        list.addLast(4);
        list.addLast(5);

        System.out.println("Original:");
        list.print(); // 1 → 2 → 3 → 4 → 5 → null

        list.zigZag();

        System.out.println("After zig-zag:");
        list.print(); // 1 → 5 → 2 → 4 → 3 → null

        System.out.println();

        // Test with even number of nodes
        LinkedListZigZag list2 = new LinkedListZigZag();
        list2.addLast(1);
        list2.addLast(2);
        list2.addLast(3);
        list2.addLast(4);

        System.out.println("Original (even):");
        list2.print(); // 1 → 2 → 3 → 4 → null

        list2.zigZag();

        System.out.println("After zig-zag:");
        list2.print(); // 1 → 4 → 2 → 3 → null
    }
}
```

---

## 5.8 Doubly Linked List

**What is a Doubly Linked List?** Each node has TWO pointers: one to the next node, one to the PREVIOUS node. This allows traversal in both directions.

```
null ← [10 | • | •] ↔ [20 | • | •] ↔ [30 | • | •] → null
       ↑                                          ↑
     head                                       tail
```

**Advantages**: Can traverse both directions. `removeLast` is O(1).

```java
// Node for doubly linked list
class DoublyNode {
    int data;
    DoublyNode next; // Pointer to next node
    DoublyNode prev; // Pointer to previous node

    DoublyNode(int data) {
        this.data = data;
        this.next = null;
        this.prev = null;
    }
}

class DoublyLinkedList {
    DoublyNode head;
    DoublyNode tail;
    int size;

    DoublyLinkedList() {
        this.head = null;
        this.tail = null;
        this.size = 0;
    }

    // addFirst — O(1)
    public void addFirst(int data) {
        DoublyNode newNode = new DoublyNode(data);

        if (head == null) {
            head = newNode;
            tail = newNode;
        } else {
            newNode.next = head;
            head.prev = newNode;
            head = newNode;
        }
        size++;
    }

    // addLast — O(1)
    public void addLast(int data) {
        DoublyNode newNode = new DoublyNode(data);

        if (head == null) {
            head = newNode;
            tail = newNode;
        } else {
            tail.next = newNode;
            newNode.prev = tail;
            tail = newNode;
        }
        size++;
    }

    // removeFirst — O(1)
    public int removeFirst() {
        if (head == null) {
            System.out.println("List is empty");
            return Integer.MIN_VALUE;
        }

        int data = head.data;

        if (head == tail) {
            head = null;
            tail = null;
        } else {
            head = head.next;
            head.prev = null;
        }
        size--;
        return data;
    }

    // removeLast — O(1) because we have prev pointer
    public int removeLast() {
        if (head == null) {
            System.out.println("List is empty");
            return Integer.MIN_VALUE;
        }

        int data = tail.data;

        if (head == tail) {
            head = null;
            tail = null;
        } else {
            tail = tail.prev;
            tail.next = null;
        }
        size--;
        return data;
    }

    // add at index — O(n)
    public void add(int index, int data) {
        if (index < 0 || index > size) {
            System.out.println("Invalid index");
            return;
        }

        if (index == 0) {
            addFirst(data);
            return;
        }
        if (index == size) {
            addLast(data);
            return;
        }

        DoublyNode newNode = new DoublyNode(data);
        DoublyNode current = head;
        for (int i = 0; i < index; i++) {
            current = current.next;
        }

        // Insert before 'current'
        newNode.prev = current.prev;
        newNode.next = current;
        current.prev.next = newNode;
        current.prev = newNode;
        size++;
    }

    // remove at index — O(n)
    public int remove(int index) {
        if (index < 0 || index >= size) {
            System.out.println("Invalid index");
            return Integer.MIN_VALUE;
        }

        if (index == 0) return removeFirst();
        if (index == size - 1) return removeLast();

        DoublyNode current = head;
        for (int i = 0; i < index; i++) {
            current = current.next;
        }

        current.prev.next = current.next;
        current.next.prev = current.prev;
        size--;
        return current.data;
    }

    // Print forward
    public void printForward() {
        System.out.print("Forward: null ↔ ");
        DoublyNode current = head;
        while (current != null) {
            System.out.print(current.data + " ↔ ");
            current = current.next;
        }
        System.out.println("null");
    }

    // Print backward (using prev pointers)
    public void printBackward() {
        System.out.print("Backward: null ↔ ");
        DoublyNode current = tail;
        while (current != null) {
            System.out.print(current.data + " ↔ ");
            current = current.prev;
        }
        System.out.println("null");
    }

    public int getSize() {
        return size;
    }
}

public class DoublyLinkedListDemo {

    public static void main(String[] args) {
        System.out.println("=== Doubly Linked List ===\n");

        DoublyLinkedList list = new DoublyLinkedList();

        // Add elements
        list.addLast(10);
        list.addLast(20);
        list.addLast(30);
        list.addLast(40);
        System.out.println("After addLast:");
        list.printForward();  // 10 ↔ 20 ↔ 30 ↔ 40 ↔ null
        list.printBackward(); // 40 ↔ 30 ↔ 20 ↔ 10 ↔ null

        // addFirst
        list.addFirst(5);
        System.out.println("\nAfter addFirst(5):");
        list.printForward(); // 5 ↔ 10 ↔ 20 ↔ 30 ↔ 40 ↔ null

        // add at index
        list.add(2, 15);
        System.out.println("\nAfter add(2, 15):");
        list.printForward(); // 5 ↔ 10 ↔ 15 ↔ 20 ↔ 30 ↔ 40 ↔ null

        // removeFirst
        list.removeFirst();
        System.out.println("\nAfter removeFirst:");
        list.printForward(); // 10 ↔ 15 ↔ 20 ↔ 30 ↔ 40 ↔ null

        // removeLast
        list.removeLast();
        System.out.println("\nAfter removeLast:");
        list.printForward(); // 10 ↔ 15 ↔ 20 ↔ 30 ↔ null

        // remove at index
        list.remove(1);
        System.out.println("\nAfter remove(1):");
        list.printForward(); // 10 ↔ 20 ↔ 30 ↔ null
    }
}
```

---

## 5.9 Circular Linked List

**What is a Circular Linked List?** The last node's `next` pointer points back to the **head** (instead of null). There is NO null in a circular linked list.

```
Singly Circular:
  [10 | •] → [20 | •] → [30 | •]
    ↑                          │
    └──────────────────────────┘

The last node (30) points back to head (10).
```

```java
// Node class (same as singly linked list)
class CircularNode {
    int data;
    CircularNode next;

    CircularNode(int data) {
        this.data = data;
        this.next = null;
    }
}

class CircularLinkedList {
    CircularNode head;
    CircularNode tail;
    int size;

    CircularLinkedList() {
        this.head = null;
        this.tail = null;
        this.size = 0;
    }

    // addFirst — O(1)
    public void addFirst(int data) {
        CircularNode newNode = new CircularNode(data);

        if (head == null) {
            head = newNode;
            tail = newNode;
            tail.next = head; // Point back to head (circular!)
        } else {
            newNode.next = head;
            head = newNode;
            tail.next = head; // Maintain circular link
        }
        size++;
    }

    // addLast — O(1) (because we have tail)
    public void addLast(int data) {
        CircularNode newNode = new CircularNode(data);

        if (head == null) {
            head = newNode;
            tail = newNode;
            tail.next = head; // Point back to head
        } else {
            tail.next = newNode;
            tail = newNode;
            tail.next = head; // Maintain circular link
        }
        size++;
    }

    // removeFirst — O(1)
    public int removeFirst() {
        if (head == null) {
            System.out.println("List is empty");
            return Integer.MIN_VALUE;
        }

        int data = head.data;

        if (head == tail) {
            // Only one node
            head = null;
            tail = null;
        } else {
            head = head.next;
            tail.next = head; // Maintain circular link
        }
        size--;
        return data;
    }

    // removeLast — O(n) for singly circular (need to find second-last)
    public int removeLast() {
        if (head == null) {
            System.out.println("List is empty");
            return Integer.MIN_VALUE;
        }

        int data = tail.data;

        if (head == tail) {
            head = null;
            tail = null;
        } else {
            // Traverse to second-to-last node
            CircularNode current = head;
            while (current.next != tail) {
                current = current.next;
            }
            // current is now second-to-last
            current.next = head; // New last points to head
            tail = current;
        }
        size--;
        return data;
    }

    // Print the circular list
    public void print() {
        if (head == null) {
            System.out.println("CircularLinkedList: (empty)");
            return;
        }

        System.out.print("CircularLinkedList: ");
        CircularNode current = head;
        do {
            System.out.print(current.data + " → ");
            current = current.next;
        } while (current != head); // Stop when we've come full circle

        System.out.println("(back to head)");
        System.out.println("Size: " + size);
    }

    // Traverse n steps around the circle (demonstrates circularity)
    public void traverseSteps(int steps) {
        if (head == null) return;

        System.out.print("Traversing " + steps + " steps: ");
        CircularNode current = head;
        for (int i = 0; i < steps; i++) {
            System.out.print(current.data + " → ");
            current = current.next;
        }
        System.out.println("(stopped at " + current.data + ")");
    }

    public int getSize() {
        return size;
    }
}

public class CircularLinkedListDemo {

    public static void main(String[] args) {
        System.out.println("=== Circular Linked List ===\n");

        CircularLinkedList list = new CircularLinkedList();

        // Add elements
        list.addLast(10);
        list.addLast(20);
        list.addLast(30);
        list.addLast(40);
        list.print();
        // 10 → 20 → 30 → 40 → (back to head)

        // addFirst
        list.addFirst(5);
        System.out.println("\nAfter addFirst(5):");
        list.print();
        // 5 → 10 → 20 → 30 → 40 → (back to head)

        // Demonstrate circularity — traverse 10 steps
        System.out.println();
        list.traverseSteps(10);

        // removeFirst
        list.removeFirst();
        System.out.println("\nAfter removeFirst:");
        list.print();

        // removeLast
        list.removeLast();
        System.out.println("\nAfter removeLast:");
        list.print();

        // Keep removing to show empty state
        list.removeFirst();
        list.removeFirst();
        list.removeFirst();
        System.out.println("\nAfter removing all:");
        list.print();

        // Show circularity by adding two and traversing many steps
        list.addLast(100);
        list.addLast(200);
        System.out.println("\nTwo elements added:");
        list.print();
        list.traverseSteps(6); // Will go 100 → 200 → 100 → 200 → 100 → 200
    }
}
```

---

## Summary

This document covered:

1. **Recursion**: Call stack, factorial, Fibonacci, sorted array check, first/last occurrence, power (O(log n)), tiling, remove duplicates, friends pairing, binary strings, Tower of Hanoi, string/array recursion.

2. **Divide & Conquer**: Merge Sort, Quick Sort (with visualization), search in rotated sorted array, time complexity analysis.

3. **Backtracking**: Subsets, permutations, N-Queens, grid ways, Knight's Tour, Sudoku solver.

4. **ArrayList**: All operations, multi-dimensional, Container With Most Water (brute + 2-pointer), Pair Sum (brute + 2-pointer + HashMap).

5. **Linked List**: Node/List class, all add/remove operations, search (iterative + recursive), reverse (iterative + recursive), remove nth from end, palindrome check, cycle detection/removal, merge sort, zig-zag, doubly linked list, circular linked list.

**Remember**: The key to mastering DSA is practice. Compile and run every program. Modify them. Break them. Fix them. Happy coding!
# Java DSA — Complete Beginner's Guide with Full Code

> Every section: **concept explanation first**, then **full Java code with `main()`**, then **line-by-line comments**.

---

## 1. STACKS

### What is a Stack?

A **stack** is a linear data structure that follows **LIFO** (Last In, First Out). Think of a stack of plates — you add a plate on top, and you take the top plate off first.

**Operations:**
- `push(x)` — put `x` on top
- `pop()` — remove and return top element
- `peek()`  — see top element without removing
- `isEmpty()` — check if stack is empty

---

### Stack using ArrayList

```java
import java.util.ArrayList;

public class StackUsingArrayList {

    // We'll use an ArrayList internally. The end of the list = top of stack.
    static class Stack {
        ArrayList<Integer> list = new ArrayList<>();

        // isEmpty: returns true if list is empty
        public boolean isEmpty() {
            return list.size() == 0;
        }

        // push: add element to the end (top of stack)
        public void push(int data) {
            list.add(data);                   // ArrayList auto-grows
        }

        // pop: remove and return the last element
        public int pop() {
            if (isEmpty()) {
                return -1;                    // stack underflow
            }
            int top = list.get(list.size() - 1); // get last element
            list.remove(list.size() - 1);         // remove it
            return top;
        }

        // peek: return last element without removing
        public int peek() {
            if (isEmpty()) {
                return -1;
            }
            return list.get(list.size() - 1);
        }
    }

    public static void main(String[] args) {
        Stack s = new Stack();        // create our custom stack
        s.push(10);                   // stack: [10]
        s.push(20);                   // stack: [10, 20]
        s.push(30);                   // stack: [10, 20, 30]

        // Pop and print until empty
        while (!s.isEmpty()) {
            System.out.println(s.peek()); // look at top
            s.pop();                       // remove top
        }
        // Output: 30 20 10
    }
}
```

---

### Stack using LinkedList

```java
public class StackUsingLinkedList {

    // Each node holds data + pointer to next node
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    static class Stack {
        static Node head = null;        // head always points to top of stack

        public boolean isEmpty() {
            return head == null;
        }

        // push: add new node at the beginning (top)
        public void push(int data) {
            Node newNode = new Node(data);
            if (isEmpty()) {
                head = newNode;          // first element
                return;
            }
            newNode.next = head;         // new node points to old head
            head = newNode;              // head becomes new node
        }

        // pop: remove head node
        public int pop() {
            if (isEmpty()) {
                return -1;
            }
            int top = head.data;         // save the data
            head = head.next;            // move head to next node (old head gets GC'd)
            return top;
        }

        // peek: return head's data
        public int peek() {
            if (isEmpty()) {
                return -1;
            }
            return head.data;
        }
    }

    public static void main(String[] args) {
        Stack s = new Stack();
        s.push(1);
        s.push(2);
        s.push(3);

        while (!s.isEmpty()) {
            System.out.println(s.peek());
            s.pop();
        }
        // Output: 3 2 1
    }
}
```

---

### Stack using Java Collection Framework

Java provides a built-in `Stack` class. You rarely need to write your own.

```java
import java.util.Stack;

public class StackJCF {
    public static void main(String[] args) {
        Stack<Integer> s = new Stack<>(); // generic type = Integer

        s.push(5);                        //  [5]
        s.push(10);                       //  [5, 10]
        s.push(15);                       //  [5, 10, 15]

        while (!s.isEmpty()) {
            System.out.println(s.peek()); // see top
            s.pop();                      // remove top
        }
        // Output: 15 10 5
    }
}
```

---

### Push at Bottom of Stack

Push a new element to the **bottom** of a stack (so it comes out last). This requires recursion.

```java
import java.util.Stack;

public class PushAtBottom {

    // Recursively remove all elements, push new data, then push them back
    public static void pushAtBottom(Stack<Integer> s, int data) {
        // Base case: stack empty → push data at bottom
        if (s.isEmpty()) {
            s.push(data);
            return;
        }

        // Recursive step:
        int top = s.pop();            // remove top element
        pushAtBottom(s, data);        // recursive call with remaining stack
        s.push(top);                  // put the removed element back on top
    }

    public static void main(String[] args) {
        Stack<Integer> s = new Stack<>();
        s.push(1);
        s.push(2);
        s.push(3);                    // stack = [1,2,3] (top=3)

        pushAtBottom(s, 0);           // stack = [0,1,2,3] (0 at bottom)

        while (!s.isEmpty()) {
            System.out.println(s.pop()); // prints: 3,2,1,0
        }
    }
}
```

---

### Reverse a String using Stack

A stack naturally reverses things. Push all characters, then pop them out — they come out backwards.

```java
import java.util.Stack;

public class ReverseString {

    public static String reverse(String str) {
        Stack<Character> s = new Stack<>();

        // Push every character onto stack
        for (int i = 0; i < str.length(); i++) {
            s.push(str.charAt(i));
        }

        // Pop them off — characters come out in reverse order
        StringBuilder result = new StringBuilder();
        while (!s.isEmpty()) {
            result.append(s.pop());
        }

        return result.toString();
    }

    public static void main(String[] args) {
        String input = "abcde";
        String reversed = reverse(input);
        System.out.println("Original: " + input);   // abcde
        System.out.println("Reversed: " + reversed); // edcba
    }
}
```

---

### Reverse a Stack

Reverse a stack using recursion (no extra stack). Similar to push-at-bottom logic.

```java
import java.util.Stack;

public class ReverseStack {

    // Helper: push element at bottom of stack
    public static void pushAtBottom(Stack<Integer> s, int data) {
        if (s.isEmpty()) {
            s.push(data);
            return;
        }
        int top = s.pop();
        pushAtBottom(s, data);
        s.push(top);
    }

    // Recursively reverse: pop top, reverse remaining, push top at bottom
    public static void reverse(Stack<Integer> s) {
        if (s.isEmpty()) {
            return;
        }
        int top = s.pop();         // remove top
        reverse(s);                // reverse the smaller stack
        pushAtBottom(s, top);      // put top at bottom
    }

    public static void main(String[] args) {
        Stack<Integer> s = new Stack<>();
        s.push(1);
        s.push(2);
        s.push(3);                 // stack = [1,2,3], top=3

        reverse(s);                // stack = [3,2,1], top=1 now

        while (!s.isEmpty()) {
            System.out.println(s.pop()); // 1,2,3
        }
    }
}
```

---

### Stock Span Problem

**Problem:** Given an array of stock prices for each day, find the **span** (consecutive days before today where price ≤ today's price, including today).

**Example:** prices = [100, 80, 60, 70, 60, 75, 85]
spans   = [  1,  1,  1,  2,  1,  4,  6]

**Logic:** Use a stack to store indices of previous days. For each day, pop while stack top has a smaller price, then span = currentIndex - stackTopIndex.

```java
import java.util.Stack;

public class StockSpan {

    public static void stockSpan(int[] prices, int[] span) {
        Stack<Integer> s = new Stack<>();
        s.push(0);                    // first day's index
        span[0] = 1;                  // span of first day is always 1

        for (int i = 1; i < prices.length; i++) {
            // Pop all indices whose price is less than or equal to current
            while (!s.isEmpty() && prices[s.peek()] <= prices[i]) {
                s.pop();
            }

            // If stack empty → current price is highest so far → span = i+1
            // Else → span = i - last greater element's index
            if (s.isEmpty()) {
                span[i] = i + 1;
            } else {
                span[i] = i - s.peek();
            }

            s.push(i);                // push current day's index
        }
    }

    public static void main(String[] args) {
        int[] prices = {100, 80, 60, 70, 60, 75, 85};
        int[] span = new int[prices.length];

        stockSpan(prices, span);

        // Print results
        for (int i = 0; i < span.length; i++) {
            System.out.print(span[i] + " ");
        }
        // Output: 1 1 1 2 1 4 6
    }
}
```

---

### Next Greater Element

**Problem:** For each element in an array, find the **next greater element** to its right. If none, output -1.

**Example:** arr = [6, 8, 0, 1, 3]
nextGreater = [8, -1, 1, 3, -1]

**Logic:** Traverse from right to left. Stack stores elements (not indices). For each element, pop while stack top ≤ current. The new top is the next greater.

```java
import java.util.Stack;

public class NextGreaterElement {

    public static void main(String[] args) {
        int[] arr = {6, 8, 0, 1, 3};
        int[] nextGreater = new int[arr.length];
        Stack<Integer> s = new Stack<>();

        // Traverse from right to left
        for (int i = arr.length - 1; i >= 0; i--) {
            // Pop while stack top is not greater than current
            while (!s.isEmpty() && arr[s.peek()] <= arr[i]) {
                s.pop();
            }

            // If stack empty → no greater element to right
            if (s.isEmpty()) {
                nextGreater[i] = -1;
            } else {
                nextGreater[i] = arr[s.peek()];
            }

            s.push(i);  // push current index onto stack
        }

        // Print result
        for (int i = 0; i < nextGreater.length; i++) {
            System.out.print(nextGreater[i] + " ");
        }
        // Output: 8 -1 1 3 -1
    }
}
```

**Variations** (same pattern, just change the condition):
- Next Greater Element — right side, greater
- Next Smaller Element — right side, smaller (`>=` becomes `<=`)
- Previous Greater Element — traverse left-to-right
- Previous Smaller Element — traverse left-to-right with `<=`

---

### Valid Parentheses

**Problem:** Given a string like `"({[]})"`, check if brackets are properly matched and nested.

**Logic:** Push opening brackets onto stack. When you see a closing bracket, check if it matches the top of the stack.

```java
import java.util.Stack;

public class ValidParentheses {

    public static boolean isValid(String str) {
        Stack<Character> s = new Stack<>();

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);

            // Opening bracket → push onto stack
            if (ch == '(' || ch == '{' || ch == '[') {
                s.push(ch);
            } else {
                // Closing bracket but stack empty → no matching opener
                if (s.isEmpty()) {
                    return false;
                }

                // Check if top of stack matches this closing bracket
                char top = s.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;           // mismatch
                }
                // If matched → continue (top already popped)
            }
        }

        // Stack must be empty at end (every opener had a closer)
        return s.isEmpty();
    }

    public static void main(String[] args) {
        String test1 = "({[]})";      // valid
        String test2 = "({[})";       // invalid — mismatched
        String test3 = "({[})]";      // invalid — extra closing

        System.out.println(isValid(test1)); // true
        System.out.println(isValid(test2)); // false
        System.out.println(isValid(test3)); // false
    }
}
```

---

### Duplicate Parentheses

**Problem:** Given a valid expression with parentheses, check if there are **duplicate** parentheses — i.e., a sub-expression surrounded by unnecessary parentheses like `((a+b))`.

**Logic:** Push everything onto stack. When you see `)`, pop until you find `(`. If you pop immediately (next char is `(`), it's a duplicate.

```java
import java.util.Stack;

public class DuplicateParentheses {

    public static boolean hasDuplicate(String str) {
        Stack<Character> s = new Stack<>();

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);

            // Closing bracket found
            if (ch == ')') {
                int count = 0;

                // Pop until we find matching '('
                while (s.peek() != '(') {
                    s.pop();
                    count++;
                }

                // If no characters between '(' and ')' → duplicate
                if (count < 1) {
                    return true;
                }

                s.pop(); // remove the '(' itself
            } else {
                s.push(ch); // push everything else (including '(')
            }
        }

        return false; // no duplicate found
    }

    public static void main(String[] args) {
        String expr1 = "((a+b))";       // duplicate inner parentheses
        String expr2 = "(a+b)";         // no duplicate
        String expr3 = "(a+(b-c))";     // no duplicate (inner has content)

        System.out.println(hasDuplicate(expr1)); // true
        System.out.println(hasDuplicate(expr2)); // false
        System.out.println(hasDuplicate(expr3)); // false
    }
}
```

---

## 2. QUEUES

### What is a Queue?

A **queue** follows **FIFO** (First In, First Out). Think of a line at a ticket counter — the first person in line gets served first.

**Operations:**
- `add(x)` — add to the **rear** (enqueue)
- `remove()` — remove from the **front** (dequeue)
- `peek()` — see front element
- `isEmpty()`

---

### Queue using Array (Circular Queue)

A simple array queue wastes space (front moves forward, those slots are never reused). A **circular** queue reuses empty slots by wrapping around using modulo.

```java
public class QueueUsingArray {

    static class Queue {
        static int[] arr;
        static int size;
        static int rear = -1;
        static int front = -1;   // needed for circular

        Queue(int n) {
            arr = new int[n];
            size = n;
        }

        public boolean isEmpty() {
            return rear == -1 && front == -1;
        }

        // Circular queue full condition
        public boolean isFull() {
            return (rear + 1) % size == front;
        }

        // add — enqueue
        public void add(int data) {
            if (isFull()) {
                System.out.println("Queue full");
                return;
            }

            // First element: set front to 0
            if (front == -1) {
                front = 0;
            }

            rear = (rear + 1) % size;  // move rear circularly
            arr[rear] = data;
        }

        // remove — dequeue
        public int remove() {
            if (isEmpty()) {
                System.out.println("Empty queue");
                return -1;
            }

            int result = arr[front];

            // If single element → reset queue
            if (rear == front) {
                rear = front = -1;
            } else {
                front = (front + 1) % size;  // move front forward (circularly)
            }

            return result;
        }

        // peek
        public int peek() {
            if (isEmpty()) {
                System.out.println("Empty queue");
                return -1;
            }
            return arr[front];
        }
    }

    public static void main(String[] args) {
        Queue q = new Queue(5);
        q.add(10);
        q.add(20);
        q.add(30);

        // Remove 10, then add 40, 50 — demonstrates circular wrap
        System.out.println(q.remove()); // 10
        q.add(40);
        q.add(50);

        while (!q.isEmpty()) {
            System.out.print(q.peek() + " ");  // 20 30 40 50
            q.remove();
        }
    }
}
```

---

### Queue using LinkedList

A linked list is ideal for a queue — `add` at tail, `remove` from head, both O(1).

```java
public class QueueUsingLinkedList {

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    static class Queue {
        static Node head = null;  // front
        static Node tail = null;  // rear

        public boolean isEmpty() {
            return head == null && tail == null;
        }

        // add to rear
        public void add(int data) {
            Node newNode = new Node(data);
            if (isEmpty()) {
                head = tail = newNode;
                return;
            }
            tail.next = newNode;   // link new node after tail
            tail = newNode;        // tail becomes new node
        }

        // remove from front
        public int remove() {
            if (isEmpty()) {
                System.out.println("Empty queue");
                return -1;
            }

            int front = head.data;

            // If only one element
            if (head == tail) {
                head = tail = null;
            } else {
                head = head.next;  // move head to next node
            }

            return front;
        }

        // peek front
        public int peek() {
            if (isEmpty()) {
                System.out.println("Empty queue");
                return -1;
            }
            return head.data;
        }
    }

    public static void main(String[] args) {
        Queue q = new Queue();
        q.add(1);
        q.add(2);
        q.add(3);

        while (!q.isEmpty()) {
            System.out.print(q.peek() + " "); // 1 2 3
            q.remove();
        }
    }
}
```

---

### Queue using Java Collection Framework

Java provides `Queue` as an interface implemented by `LinkedList` and `ArrayDeque`.

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueJCF {
    public static void main(String[] args) {
        // Queue is an interface; LinkedList implements it
        Queue<Integer> q = new LinkedList<>();

        q.add(1);
        q.add(2);
        q.add(3);

        while (!q.isEmpty()) {
            System.out.print(q.peek() + " "); // 1 2 3
            q.remove();
        }
    }
}
```

---

### Queue using Two Stacks

Use two stacks to simulate a queue. One stack is for pushing (`s1`), the other for popping/peeking (`s2`). When popping, move all elements from `s1` to `s2` if `s2` is empty — this reverses order, achieving FIFO.

```java
import java.util.Stack;

public class QueueUsingTwoStacks {

    static class Queue {
        static Stack<Integer> s1 = new Stack<>();
        static Stack<Integer> s2 = new Stack<>();

        public boolean isEmpty() {
            return s1.isEmpty();
        }

        // add — O(1) always push to s1
        public void add(int data) {
            s1.push(data);
        }

        // remove — O(n) worst case
        public int remove() {
            if (isEmpty()) {
                System.out.println("Empty queue");
                return -1;
            }

            // Move all from s1 to s2 (reverses order)
            while (!s1.isEmpty()) {
                s2.push(s1.pop());
            }

            int result = s2.pop(); // pop front of queue

            // Move back from s2 to s1
            while (!s2.isEmpty()) {
                s1.push(s2.pop());
            }

            return result;
        }

        // peek — O(n)
        public int peek() {
            if (isEmpty()) {
                System.out.println("Empty queue");
                return -1;
            }

            while (!s1.isEmpty()) {
                s2.push(s1.pop());
            }

            int result = s2.peek();

            while (!s2.isEmpty()) {
                s1.push(s2.pop());
            }

            return result;
        }
    }

    public static void main(String[] args) {
        Queue q = new Queue();
        q.add(10);
        q.add(20);
        q.add(30);

        System.out.println(q.remove()); // 10
        System.out.println(q.remove()); // 20
        q.add(40);
        System.out.println(q.remove()); // 30
        System.out.println(q.remove()); // 40
    }
}
```

---

### Stack using Two Queues

Use two queues to simulate a stack. Push to `q1`. For pop, move all except last element from `q1` to `q2`, pop the last, then swap `q1` and `q2`.

```java
import java.util.LinkedList;
import java.util.Queue;

public class StackUsingTwoQueues {

    static class Stack {
        static Queue<Integer> q1 = new LinkedList<>();
        static Queue<Integer> q2 = new LinkedList<>();

        public boolean isEmpty() {
            return q1.isEmpty() && q2.isEmpty();
        }

        // push — O(1)
        public void push(int data) {
            q1.add(data);
        }

        // pop — O(n)
        public int pop() {
            if (isEmpty()) {
                System.out.println("Empty stack");
                return -1;
            }

            // Move all except last from q1 to q2
            while (q1.size() > 1) {
                q2.add(q1.remove());
            }

            int result = q1.remove(); // last element = top of stack

            // Swap: q1 and q2 references
            Queue<Integer> temp = q1;
            q1 = q2;
            q2 = temp;

            return result;
        }

        // peek — O(n)
        public int peek() {
            if (isEmpty()) {
                System.out.println("Empty stack");
                return -1;
            }

            while (q1.size() > 1) {
                q2.add(q1.remove());
            }

            int result = q1.peek(); // look at top

            q2.add(q1.remove());    // move it to q2 too

            Queue<Integer> temp = q1;
            q1 = q2;
            q2 = temp;

            return result;
        }
    }

    public static void main(String[] args) {
        Stack s = new Stack();
        s.push(1);
        s.push(2);
        s.push(3);

        System.out.println(s.pop()); // 3
        System.out.println(s.pop()); // 2
        s.push(4);
        System.out.println(s.pop()); // 4
        System.out.println(s.pop()); // 1
    }
}
```

---

### First Non-Repeating Character in a Stream

**Problem:** Given a stream of characters, find the **first non-repeating** character after each character insertion.

**Logic:** Use a queue to maintain order of characters seen. Use a frequency array of size 26 (for a-z). For each new char:
1. Increment its frequency.
2. Add it to queue.
3. While queue front has frequency > 1, remove it.
4. If queue empty → output -1, else output queue front.

```java
import java.util.LinkedList;
import java.util.Queue;

public class FirstNonRepeating {

    public static void printFirstNonRepeating(String str) {
        int[] freq = new int[26];           // frequency of each letter
        Queue<Character> q = new LinkedList<>();

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            q.add(ch);                      // add to queue
            freq[ch - 'a']++;               // increment frequency

            // Remove from front if frequency > 1 (repeating)
            while (!q.isEmpty() && freq[q.peek() - 'a'] > 1) {
                q.remove();
            }

            // Print result for this step
            if (q.isEmpty()) {
                System.out.print("-1 ");
            } else {
                System.out.print(q.peek() + " ");
            }
        }
    }

    public static void main(String[] args) {
        String stream = "aabccxb";
        printFirstNonRepeating(stream);
        // Output: a -1 b b b b x
        // Step-by-step:
        // a → a      (first non-repeating = a)
        // a → -1     (a repeats)
        // b → b      (b is first non-repeating)
        // c → b      (b still first non-repeating)
        // c → b      (b still)
        // x → b      (b still, x not repeated yet but b came first)
        // b → x      (b repeated, next non-repeating = x)
    }
}
```

---

### Interleave Two Halves of a Queue

**Problem:** Given a queue of even length, interleave the first half with the second half.

Example: `[1,2,3,4,5,6]` → `[1,4,2,5,3,6]`

**Logic:** Move first half to a separate queue, then alternately take from firstHalf and original.

```java
import java.util.LinkedList;
import java.util.Queue;

public class InterleaveTwoHalves {

    public static void interleave(Queue<Integer> q) {
        int size = q.size();
        Queue<Integer> firstHalf = new LinkedList<>();

        // Move first half of q to firstHalf queue
        for (int i = 0; i < size / 2; i++) {
            firstHalf.add(q.remove());
        }

        // Now alternately take from firstHalf and original q
        while (!firstHalf.isEmpty()) {
            q.add(firstHalf.remove());  // take from first half
            q.add(q.remove());          // take from second half (original q)
        }
    }

    public static void main(String[] args) {
        Queue<Integer> q = new LinkedList<>();
        q.add(1);
        q.add(2);
        q.add(3);
        q.add(4);
        q.add(5);
        q.add(6);

        interleave(q);

        // Print result
        while (!q.isEmpty()) {
            System.out.print(q.remove() + " "); // 1 4 2 5 3 6
        }
    }
}
```

---

### Queue Reversal

Reverse a queue using a stack. Dequeue all elements into a stack, then pop them back into the queue.

```java
import java.util.LinkedList;
import java.util.Queue;
import java.util.Stack;

public class QueueReversal {

    public static void reverse(Queue<Integer> q) {
        Stack<Integer> s = new Stack<>();

        // Move all elements to stack (reverses order)
        while (!q.isEmpty()) {
            s.push(q.remove());
        }

        // Pop back into queue
        while (!s.isEmpty()) {
            q.add(s.pop());
        }
    }

    public static void main(String[] args) {
        Queue<Integer> q = new LinkedList<>();
        q.add(1);
        q.add(2);
        q.add(3);
        q.add(4);
        q.add(5);

        reverse(q);

        while (!q.isEmpty()) {
            System.out.print(q.remove() + " "); // 5 4 3 2 1
        }
    }
}
```

---

## 3. GREEDY ALGORITHMS

### What is a Greedy Algorithm?

A **greedy** algorithm makes the **best choice at each step**, hoping this leads to the globally optimal solution.

**Key idea:** Don't think about the future — just pick what looks best *right now*.

**When it works:** When a locally optimal choice is also globally optimal (e.g., Activity Selection, Huffman coding).

**When it fails:** When a local choice can lead to a dead end (e.g., 0/1 Knapsack — for that you need DP).

---

### Activity Selection (Max Activities)

**Problem:** Given start and end times of activities, select the **maximum number** of non-overlapping activities.

**Greedy choice:** Pick the activity with the **earliest finishing time** first. This leaves the most room for remaining activities.

```java
import java.util.ArrayList;
import java.util.Collections;

public class ActivitySelection {

    public static void main(String[] args) {
        int[] start = {1, 3, 0, 5, 8, 5};
        int[] end   = {2, 4, 6, 7, 9, 9};

        // We'll create a list of activities
        ArrayList<Activity> activities = new ArrayList<>();
        for (int i = 0; i < start.length; i++) {
            activities.add(new Activity(start[i], end[i], i));
        }

        // Sort by end time (earliest first) — the greedy part
        Collections.sort(activities, (a, b) -> a.end - b.end);

        ArrayList<Integer> selected = new ArrayList<>();
        selected.add(activities.get(0).index); // always pick first
        int lastEnd = activities.get(0).end;

        for (int i = 1; i < activities.size(); i++) {
            // If this activity starts after (or at) last end → pick it
            if (activities.get(i).start >= lastEnd) {
                selected.add(activities.get(i).index);
                lastEnd = activities.get(i).end;
            }
        }

        // Print result
        System.out.println("Max activities: " + selected.size());
        System.out.print("Selected indices: ");
        for (int idx : selected) {
            System.out.print("A" + idx + " ");
        }
        // Output: Max activities: 4
        //         Selected indices: A0 A1 A3 A4
    }

    static class Activity {
        int start, end, index;
        Activity(int s, int e, int i) {
            start = s;
            end = e;
            index = i;
        }
    }
}
```

---

### Fractional Knapsack

**Problem:** You have items with weight and value, and a knapsack with capacity `W`. You can take **fractions** of items. Maximize total value.

**Greedy choice:** Take items with the **highest value-to-weight ratio** first.

```java
import java.util.Arrays;
import java.util.Comparator;

public class FractionalKnapsack {

    public static void main(String[] args) {
        int[] value = {60, 100, 120};
        int[] weight = {10, 20, 30};
        int capacity = 50;

        // Create items array
        Item[] items = new Item[value.length];
        for (int i = 0; i < value.length; i++) {
            items[i] = new Item(value[i], weight[i]);
        }

        // Sort by value/weight ratio descending
        Arrays.sort(items, (a, b) -> Double.compare(b.ratio, a.ratio));

        double totalValue = 0;
        int remaining = capacity;

        for (Item item : items) {
            if (remaining >= item.weight) {
                // Take the whole item
                totalValue += item.value;
                remaining -= item.weight;
            } else {
                // Take a fraction
                totalValue += item.ratio * remaining;
                break; // knapsack full
            }
        }

        System.out.println("Maximum value: " + totalValue);
        // Output: Maximum value: 240.0
        // Calculation: take whole item2 (120 value, 30 weight),
        //              take whole item0 (60 value, 10 weight),
        //              take 10/20 of item1 (50 value remaining capacity)
        //              Total = 120 + 60 + 50 = 240
    }

    static class Item {
        int value, weight;
        double ratio;

        Item(int v, int w) {
            value = v;
            weight = w;
            ratio = (double) v / w; // value per unit weight
        }
    }
}
```

---

### Minimum Absolute Difference Pairs

**Problem:** Given two arrays A and B, pair each element of A with one element of B such that the **sum of absolute differences** is minimized.

**Greedy:** Sort both arrays. Then the smallest in A pairs with smallest in B, etc.

```java
import java.util.Arrays;

public class MinAbsoluteDifference {

    public static void main(String[] args) {
        int[] A = {4, 1, 8, 7};
        int[] B = {2, 3, 6, 5};

        Arrays.sort(A);   // A = [1, 4, 7, 8]
        Arrays.sort(B);   // B = [2, 3, 5, 6]

        int sum = 0;
        for (int i = 0; i < A.length; i++) {
            sum += Math.abs(A[i] - B[i]); // pair at same index after sorting
        }

        System.out.println("Min absolute difference sum: " + sum);
        // |1-2| + |4-3| + |7-5| + |8-6| = 1 + 1 + 2 + 2 = 6
    }
}
```

---

### Max Length Chain of Pairs

**Problem:** Given pairs (a, b) where a < b, find the longest chain where second number < first number of next pair.

**Greedy:** Sort by second number (ending). Then similar to Activity Selection — pick the pair with smallest ending first.

```java
import java.util.Arrays;
import java.util.Comparator;

public class MaxLengthChain {

    public static void main(String[] args) {
        int[][] pairs = {{5, 24}, {39, 60}, {5, 28}, {27, 40}, {50, 90}};

        // Sort by second element (end)
        Arrays.sort(pairs, (a, b) -> a[1] - b[1]);

        int chainLen = 1;          // at least one pair
        int lastEnd = pairs[0][1]; // end of first pair

        for (int i = 1; i < pairs.length; i++) {
            if (pairs[i][0] > lastEnd) { // can chain if start > last end
                chainLen++;
                lastEnd = pairs[i][1];   // update end
            }
        }

        System.out.println("Max chain length: " + chainLen);
        // Output: Max chain length: 3
        // Chain: (5,24) → (27,40) → (50,90)
    }
}
```

---

### Indian Coins (Minimum Coins for Change)

**Problem:** Given denominations `{1, 2, 5, 10, 20, 50, 100, 500, 2000}`, find the **minimum number of coins** to make a given amount.

**Greedy:** Start with the largest denomination less than or equal to remaining amount.

```java
import java.util.ArrayList;
import java.util.Arrays;

public class IndianCoins {

    public static void main(String[] args) {
        Integer[] coins = {1, 2, 5, 10, 20, 50, 100, 500, 2000};
        int amount = 590;

        // Sort descending
        Arrays.sort(coins, (a, b) -> b - a);

        ArrayList<Integer> used = new ArrayList<>();
        int count = 0;

        for (int coin : coins) {
            while (amount >= coin) {
                amount -= coin;
                used.add(coin);
                count++;
            }
        }

        System.out.println("Min coins needed: " + count);
        System.out.print("Coins used: ");
        for (int c : used) {
            System.out.print(c + " ");
        }
        // Output: Min coins needed: 4
        //         Coins used: 500 50 20 20
        // 590 = 500 + 50 + 20 + 20
    }
}
```

---

### Job Sequencing Problem

**Problem:** Each job has a deadline and profit. Each job takes 1 unit time. Schedule jobs to **maximize profit**. Only one job can run at a time.

**Greedy:** Sort jobs by profit descending. For each job, try to schedule it at the latest available slot before its deadline.

```java
import java.util.ArrayList;
import java.util.Collections;

public class JobSequencing {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static void main(String[] args) {
        int[][] jobsInfo = {{4, 20}, {1, 10}, {1, 40}, {1, 30}};
        // Each inner array = {deadline, profit}
        // Job 0: deadline=4, profit=20
        // Job 1: deadline=1, profit=10
        // Job 2: deadline=1, profit=40
        // Job 3: deadline=1, profit=30

        ArrayList<Job> jobs = new ArrayList<>();
        for (int i = 0; i < jobsInfo.length; i++) {
            jobs.add(new Job(i, jobsInfo[i][0], jobsInfo[i][1]));
        }

        // Sort by profit descending
        Collections.sort(jobs, (a, b) -> b.profit - a.profit);

        // Find max deadline
        int maxDeadline = 0;
        for (Job j : jobs) {
            maxDeadline = Math.max(maxDeadline, j.deadline);
        }

        // Time slots: -1 = empty
        int[] slots = new int[maxDeadline + 1];
        for (int i = 0; i < slots.length; i++) {
            slots[i] = -1;
        }

        int totalProfit = 0;
        ArrayList<Integer> scheduled = new ArrayList<>();

        for (Job job : jobs) {
            // Try to find an empty slot from job.deadline down to 1
            for (int t = job.deadline; t >= 1; t--) {
                if (slots[t] == -1) {         // slot available
                    slots[t] = job.id;        // assign job
                    scheduled.add(job.id);
                    totalProfit += job.profit;
                    break;
                }
            }
        }

        System.out.println("Total profit: " + totalProfit);
        System.out.print("Job sequence: ");
        for (int id : scheduled) {
            System.out.print("Job" + id + " ");
        }
        // Output: Total profit: 90
        //         Job sequence: Job2 Job0
        // Job2 (deadline 1, profit 40) → slot 1
        // Job0 (deadline 4, profit 20) → slot 4
        // Job3 (deadline 1, profit 30) → slot 1 taken
        // Job1 (deadline 1, profit 10) → slot 1 taken
    }
}
```

---

### Chocolate Distribution Problem

**Problem:** Given an array of chocolate packet sizes and `m` students, distribute **one packet per student** such that the **difference between max and min** in the group is minimized.

**Greedy:** Sort the array. A group of `m` consecutive packets (in sorted order) will have the minimum difference. Slide a window of size `m`.

```java
import java.util.Arrays;

public class ChocolateDistribution {

    public static int findMinDiff(int[] packets, int m) {
        if (m > packets.length) return -1;

        Arrays.sort(packets);  // sort ascending

        int minDiff = Integer.MAX_VALUE;

        // Slide window of size m
        for (int i = 0; i + m - 1 < packets.length; i++) {
            int diff = packets[i + m - 1] - packets[i]; // max - min in window
            minDiff = Math.min(minDiff, diff);
        }

        return minDiff;
    }

    public static void main(String[] args) {
        int[] packets = {7, 3, 2, 4, 9, 12, 56};
        int m = 3;  // students

        int result = findMinDiff(packets, m);
        System.out.println("Minimum difference: " + result);
        // Sorted: [2, 3, 4, 7, 9, 12, 56]
        // Windows of size 3:
        //   (2,3,4) → diff = 2
        //   (3,4,7) → diff = 4
        //   (4,7,9) → diff = 5
        //   (7,9,12) → diff = 5
        //   (9,12,56) → diff = 47
        // Min = 2
    }
}
```

---

### Minimum Cost to Cut Boards

**Problem:** You have a board to cut into pieces. Cutting a board costs the length of the board. Given costs to cut at each vertical and horizontal line, find the **minimum total cost**.

**Greedy:** Always cut the most expensive line first (because cutting a line affects all future cuts on that segment). Sort costs descending.

```java
import java.util.Arrays;
import java.util.Collections;

public class MinimumCostToCut {

    public static void main(String[] args) {
        int n = 4, m = 3; // board dimensions (n-1 vertical cuts, m-1 horizontal)
        Integer[] vertical = {2, 1, 3, 1, 4};   // cost of each vertical cut
        Integer[] horizontal = {4, 1, 2};       // cost of each horizontal cut

        // Sort descending
        Arrays.sort(vertical, Collections.reverseOrder());
        Arrays.sort(horizontal, Collections.reverseOrder());

        int vp = 0, hp = 0;               // pointers
        int vSegments = 1, hSegments = 1; // current number of segments
        int totalCost = 0;

        while (vp < vertical.length && hp < horizontal.length) {
            // Pick the more expensive cut
            if (vertical[vp] >= horizontal[hp]) {
                // Making a vertical cut: affects all horizontal segments
                totalCost += vertical[vp] * hSegments;
                vp++;
                vSegments++;
            } else {
                // Making a horizontal cut: affects all vertical segments
                totalCost += horizontal[hp] * vSegments;
                hp++;
                hSegments++;
            }
        }

        // Remaining vertical cuts
        while (vp < vertical.length) {
            totalCost += vertical[vp] * hSegments;
            vp++;
            vSegments++;
        }

        // Remaining horizontal cuts
        while (hp < horizontal.length) {
            totalCost += horizontal[hp] * vSegments;
            hp++;
            hSegments++;
        }

        System.out.println("Minimum cost: " + totalCost);
        // The logic: cut most expensive line first
        // (you'd need the actual board to verify, but greedy works here)
    }
}
```

---

## 4. BINARY TREES

### What is a Binary Tree?

A **binary tree** is a hierarchical data structure where each **node** has at most **two children**: left and right.

```
       1          ← root
     /   \
    2     3       ← internal nodes
   / \   / \
  4   5 6   7     ← leaves
```

**Terms:**
- **Root**: topmost node (no parent)
- **Leaf**: node with no children
- **Height**: longest path from root to leaf (edges)
- **Depth**: edges from root to that node

---

### Node Class and Build Tree (Preorder)

We'll build a tree from a preorder sequence where `-1` represents null.

```java
import java.util.LinkedList;
import java.util.Queue;

public class BinaryTreeBuild {

    static class Node {
        int data;
        Node left;
        Node right;

        Node(int data) {
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }

    static class BinaryTree {
        static int idx = -1;  // global index for preorder array

        // Build tree from preorder array; -1 means null
        public static Node buildTree(int[] nodes) {
            idx++;                     // move to next element
            if (nodes[idx] == -1) {    // null node
                return null;
            }

            Node newNode = new Node(nodes[idx]); // create node
            newNode.left = buildTree(nodes);      // build left subtree
            newNode.right = buildTree(nodes);     // build right subtree

            return newNode;
        }
    }

    public static void main(String[] args) {
        int[] nodes = {1, 2, 4, -1, -1, 5, -1, -1, 3, -1, 6, -1, -1};
        // This represents:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6

        BinaryTree tree = new BinaryTree();
        Node root = BinaryTree.buildTree(nodes);
        System.out.println("Root data: " + root.data); // 1
    }
}
```

---

### Preorder, Inorder, Postorder Traversal (Recursive)

**Preorder:** Root → Left → Right
**Inorder:** Left → Root → Right
**Postorder:** Left → Right → Root

```java
public class TreeTraversals {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Preorder: Root → Left → Right
    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " "); // print root first
        preorder(root.left);               // then left
        preorder(root.right);              // then right
    }

    // Inorder: Left → Root → Right
    public static void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);                // left first
        System.out.print(root.data + " "); // then root
        inorder(root.right);               // then right
    }

    // Postorder: Left → Right → Root
    public static void postorder(Node root) {
        if (root == null) return;
        postorder(root.left);              // left first
        postorder(root.right);             // then right
        System.out.print(root.data + " "); // then root
    }

    public static void main(String[] args) {
        // Build a simple tree:
        //        1
        //       / \
        //      2   3
        //     / \
        //    4   5
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);

        System.out.print("Preorder:  ");
        preorder(root);   // 1 2 4 5 3
        System.out.println();

        System.out.print("Inorder:   ");
        inorder(root);    // 4 2 5 1 3
        System.out.println();

        System.out.print("Postorder: ");
        postorder(root);  // 4 5 2 3 1
        System.out.println();
    }
}
```

---

### Level Order Traversal

Visit nodes level by level (breadth-first). Use a queue.

```java
import java.util.LinkedList;
import java.util.Queue;

public class LevelOrder {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static void levelOrder(Node root) {
        if (root == null) return;

        Queue<Node> q = new LinkedList<>();
        q.add(root);
        q.add(null);    // null marks end of a level

        while (!q.isEmpty()) {
            Node curr = q.remove();

            if (curr == null) {
                System.out.println();         // new line for next level
                if (q.isEmpty()) break;       // no more nodes
                q.add(null);                  // end of next level marker
            } else {
                System.out.print(curr.data + " ");
                if (curr.left != null)  q.add(curr.left);
                if (curr.right != null) q.add(curr.right);
            }
        }
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);

        levelOrder(root);
        // Output:
        // 1
        // 2 3
        // 4 5 6
    }
}
```

---

### Count Nodes, Sum of Nodes, Height of Tree

All three use recursion: solve for left, solve for right, combine.

```java
public class TreeProperties {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Count total nodes
    public static int countNodes(Node root) {
        if (root == null) return 0;
        int leftCount = countNodes(root.left);
        int rightCount = countNodes(root.right);
        return leftCount + rightCount + 1; // +1 for current node
    }

    // Sum of all node values
    public static int sumNodes(Node root) {
        if (root == null) return 0;
        int leftSum = sumNodes(root.left);
        int rightSum = sumNodes(root.right);
        return leftSum + rightSum + root.data;
    }

    // Height (number of edges in longest root-to-leaf path)
    public static int height(Node root) {
        if (root == null) return 0;
        int leftHeight = height(root.left);
        int rightHeight = height(root.right);
        return Math.max(leftHeight, rightHeight) + 1;
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);

        System.out.println("Count: " + countNodes(root)); // 6
        System.out.println("Sum:   " + sumNodes(root));   // 21
        System.out.println("Height:" + height(root));     // 3 (edges: 1→2→4 or 1→3→6)
    }
}
```

---

### Diameter of Tree

**Diameter** = longest path between any two nodes (may or may not pass through root).

**Approach 1 (O(n²)):** Compute height of left & right for every node, find max of (leftHeight + rightHeight + 1).

**Approach 2 (O(n)):** Return both height and diameter from each recursive call.

```java
public class TreeDiameter {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // ---------- APPROACH 1: O(n²) ----------
    public static int height(Node root) {
        if (root == null) return 0;
        return Math.max(height(root.left), height(root.right)) + 1;
    }

    public static int diameter1(Node root) {
        if (root == null) return 0;

        int leftDiam = diameter1(root.left);
        int rightDiam = diameter1(root.right);
        int throughRoot = height(root.left) + height(root.right) + 1;

        return Math.max(throughRoot, Math.max(leftDiam, rightDiam));
    }

    // ---------- APPROACH 2: O(n) ----------
    static class Info {
        int diam;
        int ht;
        Info(int d, int h) {
            diam = d;
            ht = h;
        }
    }

    public static Info diameter2(Node root) {
        if (root == null) {
            return new Info(0, 0);
        }

        Info left = diameter2(root.left);
        Info right = diameter2(root.right);

        int myHeight = Math.max(left.ht, right.ht) + 1;
        int throughRoot = left.ht + right.ht + 1;
        int myDiam = Math.max(throughRoot, Math.max(left.diam, right.diam));

        return new Info(myDiam, myHeight);
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6
        //   /
        //  7
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);
        root.left.left.left = new Node(7);

        System.out.println("Diameter (O(n²)): " + diameter1(root));
        // Path: 7→4→2→5 (or 7→4→2→1→3→6) = 5 edges

        System.out.println("Diameter (O(n)):  " + diameter2(root).diam);
        // Same result, but O(n)
    }
}
```

---

### Subtree Check

**Problem:** Given two trees `root` and `subRoot`, check if `subRoot` is a subtree of `root`.

**Logic:** If root matches subRoot's value, check if they are identical trees. Otherwise recurse on left and right subtrees.

```java
public class SubtreeCheck {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Check if two trees are identical
    public static boolean isIdentical(Node root, Node subRoot) {
        if (root == null && subRoot == null) return true;  // both null = match
        if (root == null || subRoot == null) return false; // one null = mismatch
        if (root.data != subRoot.data) return false;       // data mismatch

        // Check left and right subtrees
        return isIdentical(root.left, subRoot.left) &&
               isIdentical(root.right, subRoot.right);
    }

    // Check if subRoot is a subtree of root
    public static boolean isSubtree(Node root, Node subRoot) {
        if (root == null) return false; // nothing left to check

        // If current node matches subRoot, check if identical
        if (root.data == subRoot.data && isIdentical(root, subRoot)) {
            return true;
        }

        // Otherwise search in left and right subtrees
        return isSubtree(root.left, subRoot) || isSubtree(root.right, subRoot);
    }

    public static void main(String[] args) {
        // Main tree:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);

        // Subtree to check:
        //      2
        //     / \
        //    4   5
        Node subRoot = new Node(2);
        subRoot.left = new Node(4);
        subRoot.right = new Node(5);

        System.out.println("Is subtree? " + isSubtree(root, subRoot)); // true
    }
}
```

---

### Top View of Binary Tree

**Problem:** Print the nodes visible from the top of the tree. For each horizontal distance (HD) from root, only the first node at that HD is visible.

**Logic:** Use level order traversal + a HashMap for HD → node. Track min/max HD.

```
       1 (HD=0)
     /   \
    2(-1) 3(+1)
     \      \
     5(-1)  6(+2)
```

Top view: 2, 1, 3, 6 (first node at each HD)

```java
import java.util.HashMap;
import java.util.LinkedList;
import java.util.Queue;

public class TopView {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    static class QueueInfo {
        Node node;
        int hd; // horizontal distance
        QueueInfo(Node n, int h) {
            node = n;
            hd = h;
        }
    }

    public static void topView(Node root) {
        if (root == null) return;

        Queue<QueueInfo> q = new LinkedList<>();
        HashMap<Integer, Node> map = new HashMap<>();

        int min = 0, max = 0; // track range of HDs

        q.add(new QueueInfo(root, 0));
        q.add(null); // level marker

        while (!q.isEmpty()) {
            QueueInfo curr = q.remove();

            if (curr == null) {
                if (q.isEmpty()) break;
                q.add(null);
                continue;
            }

            // If this HD is not in map → first node at this HD → add to top view
            if (!map.containsKey(curr.hd)) {
                map.put(curr.hd, curr.node);
            }

            if (curr.node.left != null) {
                q.add(new QueueInfo(curr.node.left, curr.hd - 1));
                min = Math.min(min, curr.hd - 1);
            }
            if (curr.node.right != null) {
                q.add(new QueueInfo(curr.node.right, curr.hd + 1));
                max = Math.max(max, curr.hd + 1);
            }
        }

        // Print from min HD to max HD
        for (int i = min; i <= max; i++) {
            System.out.print(map.get(i).data + " ");
        }
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //       \
        //        5
        //         \
        //          6
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.right = new Node(5);
        root.left.right.right = new Node(6);

        System.out.print("Top view: ");
        topView(root); // 2 1 3 6
    }
}
```

---

### Bottom View of Binary Tree

**Problem:** Print nodes visible from the bottom. For each HD, the **last** node encountered at that HD (in level order) is visible.

**Logic:** Same as top view, but overwrite map at every node (don't check `containsKey`). The last node at each HD wins.

```java
import java.util.HashMap;
import java.util.LinkedList;
import java.util.Queue;

public class BottomView {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    static class QueueInfo {
        Node node;
        int hd;
        QueueInfo(Node n, int h) {
            node = n;
            hd = h;
        }
    }

    public static void bottomView(Node root) {
        if (root == null) return;

        Queue<QueueInfo> q = new LinkedList<>();
        HashMap<Integer, Node> map = new HashMap<>();

        int min = 0, max = 0;
        q.add(new QueueInfo(root, 0));

        while (!q.isEmpty()) {
            QueueInfo curr = q.remove();

            // Overwrite every time — bottom view gets the last node at this HD
            map.put(curr.hd, curr.node);

            if (curr.node.left != null) {
                q.add(new QueueInfo(curr.node.left, curr.hd - 1));
                min = Math.min(min, curr.hd - 1);
            }
            if (curr.node.right != null) {
                q.add(new QueueInfo(curr.node.right, curr.hd + 1));
                max = Math.max(max, curr.hd + 1);
            }
        }

        for (int i = min; i <= max; i++) {
            System.out.print(map.get(i).data + " ");
        }
    }

    public static void main(String[] args) {
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.right = new Node(5);
        root.left.right.right = new Node(6);

        System.out.print("Bottom view: ");
        bottomView(root); // 2 5 3 6  (last node at each HD)
    }
}
```

---

### Kth Level Nodes

Print all nodes at a given level `k` (root is level 1, its children level 2, etc.).

**Approach 1:** Recursive (pass level counter).
**Approach 2:** Iterative (level order, stop at k).

```java
import java.util.LinkedList;
import java.util.Queue;

public class KthLevel {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Recursive approach
    public static void printKthLevel(Node root, int level, int k) {
        if (root == null) return;

        if (level == k) {
            System.out.print(root.data + " ");
            return; // no need to go deeper
        }

        printKthLevel(root.left, level + 1, k);
        printKthLevel(root.right, level + 1, k);
    }

    public static void main(String[] args) {
        // Tree:
        //        1   (level 1)
        //       / \
        //      2   3 (level 2)
        //     / \   \
        //    4   5   6 (level 3)
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);

        int k = 3;
        System.out.print("Nodes at level " + k + ": ");
        printKthLevel(root, 1, k); // 4 5 6
    }
}
```

---

### Lowest Common Ancestor (LCA)

**LCA** of two nodes is the deepest node that is an ancestor of both.

**Approach 1:** Find paths from root to both nodes, then find last common node in both paths. O(n) space.

**Approach 2:** Recursive — if root matches either node, return root. If left returns non-null and right returns non-null, root is LCA. Otherwise return non-null side.

```java
import java.util.ArrayList;

public class LCA {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // ---------- APPROACH 1: Path-based (O(n) space) ----------
    public static boolean getPath(Node root, int n, ArrayList<Node> path) {
        if (root == null) return false;

        path.add(root);

        if (root.data == n) return true;

        if (getPath(root.left, n, path) || getPath(root.right, n, path)) {
            return true;
        }

        path.remove(path.size() - 1); // backtrack
        return false;
    }

    public static Node lca1(Node root, int n1, int n2) {
        ArrayList<Node> path1 = new ArrayList<>();
        ArrayList<Node> path2 = new ArrayList<>();

        getPath(root, n1, path1);
        getPath(root, n2, path2);

        // Find last common node
        int i = 0;
        for (; i < path1.size() && i < path2.size(); i++) {
            if (path1.get(i) != path2.get(i)) break;
        }

        return path1.get(i - 1); // last common ancestor
    }

    // ---------- APPROACH 2: Recursive (O(1) extra space) ----------
    public static Node lca2(Node root, int n1, int n2) {
        if (root == null || root.data == n1 || root.data == n2) {
            return root;
        }

        Node leftLCA = lca2(root.left, n1, n2);
        Node rightLCA = lca2(root.right, n1, n2);

        // If both sides return non-null → root is LCA
        if (leftLCA != null && rightLCA != null) {
            return root;
        }

        // Otherwise return the non-null side
        return (leftLCA != null) ? leftLCA : rightLCA;
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6
        //   /
        //  7
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);
        root.left.left.left = new Node(7);

        int n1 = 7, n2 = 5;
        System.out.println("LCA of " + n1 + " and " + n2 + " = " +
                           lca1(root, n1, n2).data); // 2
        System.out.println("LCA of " + n1 + " and " + n2 + " = " +
                           lca2(root, n1, n2).data); // 2
    }
}
```

---

### Min Distance Between Nodes

**Problem:** Find the minimum distance between two nodes in a binary tree (number of edges).

**Formula:** `dist(n1, n2) = dist(root, n1) + dist(root, n2) - 2 * dist(root, LCA)`

But simpler: Find distance from LCA to n1 + distance from LCA to n2.

```java
public class MinDistance {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Find LCA first (approach 2)
    public static Node lca(Node root, int n1, int n2) {
        if (root == null || root.data == n1 || root.data == n2) {
            return root;
        }
        Node leftLCA = lca(root.left, n1, n2);
        Node rightLCA = lca(root.right, n1, n2);
        if (leftLCA != null && rightLCA != null) return root;
        return (leftLCA != null) ? leftLCA : rightLCA;
    }

    // Find distance from root to a given node
    public static int distanceFromRoot(Node root, int n) {
        if (root == null) return -1;   // not found

        if (root.data == n) return 0;  // found at current node

        int leftDist = distanceFromRoot(root.left, n);
        if (leftDist != -1) return leftDist + 1;

        int rightDist = distanceFromRoot(root.right, n);
        if (rightDist != -1) return rightDist + 1;

        return -1;
    }

    public static int minDistance(Node root, int n1, int n2) {
        Node lcaNode = lca(root, n1, n2);

        int dist1 = distanceFromRoot(lcaNode, n1);
        int dist2 = distanceFromRoot(lcaNode, n2);

        return dist1 + dist2;
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //     / \   \
        //    4   5   6
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        root.right.right = new Node(6);

        System.out.println("Distance between 4 and 6: " +
                           minDistance(root, 4, 6)); // 4
        // path: 4→2→1→3→6 = 4 edges
    }
}
```

---

### Kth Ancestor

**Problem:** Find the kth ancestor of a given node.

**Logic:** Recursively search. When found, decrement k as you backtrack. When k=0, that node is the kth ancestor.

```java
public class KthAncestor {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static int kthAncestor(Node root, int n, int k) {
        if (root == null) return -1;

        if (root.data == n) return 0; // found node, distance = 0

        int leftDist = kthAncestor(root.left, n, k);
        int rightDist = kthAncestor(root.right, n, k);

        if (leftDist == -1 && rightDist == -1) return -1; // not found in subtree

        // One side found it; distance increases by 1 as we go up
        int dist = (leftDist != -1) ? leftDist + 1 : rightDist + 1;

        // When distance == k, this node is the kth ancestor
        if (dist == k) {
            System.out.println("Kth ancestor: " + root.data);
        }

        return dist;
    }

    public static void main(String[] args) {
        // Tree:
        //        1
        //       / \
        //      2   3
        //     / \
        //    4   5
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);

        int n = 5, k = 2;
        System.out.print("Looking for " + k + "th ancestor of " + n + ": ");
        kthAncestor(root, n, k);
        // 2nd ancestor of 5: 5→2→1 → so it's 1
        // Output: Kth ancestor: 1
    }
}
```

---

### Transform to Sum Tree

**Problem:** Replace each node's value with the sum of its left and right subtree values. Leaves become 0.

**Logic:** Postorder traversal. Save old value, set node's data = leftSum + rightSum, return total = oldValue + newData.

```java
public class SumTree {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static int transform(Node root) {
        if (root == null) return 0;

        int leftSum = transform(root.left);   // transform left subtree
        int rightSum = transform(root.right); // transform right subtree

        int oldValue = root.data;

        // New value = sum of left and right subtree values
        root.data = leftSum + rightSum;

        // Return old value + new data (for parent's calculation)
        return oldValue + root.data;
    }

    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void main(String[] args) {
        // Before:
        //        1
        //       / \
        //      2   3
        //     / \
        //    4   5

        // After:
        //        9
        //       / \
        //      9   3
        //     / \
        //    0   0
        // left: (4+5)+2=9, right: 0+3=3, root: 9+3=12... wait let's trace:

        // transform(4): leftSum=0, rightSum=0, data=0, return 4
        // transform(5): data=0, return 5
        // transform(2): leftSum=4, rightSum=5, data=9, return 2+9=11
        // transform(3): data=0, return 3
        // transform(1): leftSum=11, rightSum=3, data=14, return 1+14=15

        // Tree:
        //        14
        //       / \
        //      9   3
        //     / \
        //    0   0

        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);

        transform(root);

        System.out.print("Preorder after transform: ");
        preorder(root); // 14 9 0 0 3
    }
}
```

---

### Build Tree from Preorder & Inorder

**Problem:** Given preorder and inorder traversals, reconstruct the binary tree.

**Logic:** First element of preorder is root. Find it in inorder — elements left of it form left subtree, elements right of it form right subtree. Recurse.

```java
import java.util.HashMap;

public class BuildTreePreIn {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    static HashMap<Integer, Integer> inorderMap; // value → index map for O(1) lookup
    static int preIdx = 0; // index in preorder array

    public static Node buildTree(int[] preorder, int[] inorder, int inStart, int inEnd) {
        if (inStart > inEnd) return null;

        // Current root value from preorder
        int rootData = preorder[preIdx++];
        Node root = new Node(rootData);

        // Find root's index in inorder
        int inIdx = inorderMap.get(rootData);

        // Build left subtree (elements left of root in inorder)
        root.left = buildTree(preorder, inorder, inStart, inIdx - 1);
        // Build right subtree (elements right of root in inorder)
        root.right = buildTree(preorder, inorder, inIdx + 1, inEnd);

        return root;
    }

    public static void postorder(Node root) {
        if (root == null) return;
        postorder(root.left);
        postorder(root.right);
        System.out.print(root.data + " ");
    }

    public static void main(String[] args) {
        int[] preorder = {1, 2, 4, 5, 3, 6};
        int[] inorder = {4, 2, 5, 1, 3, 6};

        inorderMap = new HashMap<>();
        for (int i = 0; i < inorder.length; i++) {
            inorderMap.put(inorder[i], i);
        }

        Node root = buildTree(preorder, inorder, 0, inorder.length - 1);

        System.out.print("Postorder: ");
        postorder(root); // 4 5 2 6 3 1
        // which matches: left→right→root from the reconstructed tree
    }
}
```

---

### Build Tree from Postorder & Inorder

Same logic, but now the root is the **last** element of postorder, and we process right subtree first.

```java
import java.util.HashMap;

public class BuildTreePostIn {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    static HashMap<Integer, Integer> inorderMap;
    static int postIdx;

    public static Node buildTree(int[] postorder, int[] inorder, int inStart, int inEnd) {
        if (inStart > inEnd) return null;

        // Root is last element in postorder traversal
        int rootData = postorder[postIdx--];
        Node root = new Node(rootData);

        int inIdx = inorderMap.get(rootData);

        // Build RIGHT subtree first (postorder is LRN, so when going backwards we hit R first)
        root.right = buildTree(postorder, inorder, inIdx + 1, inEnd);
        root.left = buildTree(postorder, inorder, inStart, inIdx - 1);

        return root;
    }

    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void main(String[] args) {
        int[] postorder = {4, 5, 2, 6, 3, 1};
        int[] inorder = {4, 2, 5, 1, 3, 6};

        inorderMap = new HashMap<>();
        for (int i = 0; i < inorder.length; i++) {
            inorderMap.put(inorder[i], i);
        }

        postIdx = postorder.length - 1; // start from last element

        Node root = buildTree(postorder, inorder, 0, inorder.length - 1);

        System.out.print("Preorder: ");
        preorder(root); // 1 2 4 5 3 6 — matches original
    }
}
```

---

## 5. BINARY SEARCH TREES (BST)

### BST Definition and Properties

A **Binary Search Tree (BST)** is a binary tree with an extra property:

> For **every** node:
> - All nodes in its **left** subtree have values **less than** the node.
> - All nodes in its **right** subtree have values **greater than** the node.
> - No duplicate values (usually).

```
        5
       / \
      3   7
     / \   \
    2   4   8
   /
  1
```

**Why BST?** Searching is O(log n) on average (O(n) worst-case if unbalanced).

**Inorder traversal of BST gives sorted order.**

---

### Build BST from Array

Insert elements one by one. For each element, compare with root: go left if smaller, right if larger.

```java
public class BuildBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static Node insert(Node root, int val) {
        if (root == null) {
            root = new Node(val); // first node becomes root
            return root;
        }

        if (val < root.data) {
            root.left = insert(root.left, val);  // go left
        } else {
            root.right = insert(root.right, val); // go right
        }

        return root;
    }

    public static void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.data + " ");
        inorder(root.right);
    }

    public static void main(String[] args) {
        int[] values = {5, 1, 3, 4, 2, 7};
        Node root = null;

        for (int val : values) {
            root = insert(root, val); // build BST
        }

        // Tree built:
        //        5
        //       / \
        //      1   7
        //       \
        //        3
        //       / \
        //      2   4

        System.out.print("Inorder: ");
        inorder(root); // 1 2 3 4 5 7 — sorted!
    }
}
```

---

### Search in BST

Search for a key. At each node: if equal → found. If key < node → go left. If key > node → go right.

```java
public class SearchBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static boolean search(Node root, int key) {
        if (root == null) return false; // not found

        if (root.data == key) return true; // found

        if (key < root.data) {
            return search(root.left, key);  // search left
        } else {
            return search(root.right, key); // search right
        }
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void main(String[] args) {
        int[] values = {5, 1, 3, 4, 2, 7};
        Node root = null;
        for (int v : values) root = insert(root, v);

        System.out.println("Search for 4: " + search(root, 4)); // true
        System.out.println("Search for 9: " + search(root, 9)); // false
    }
}
```

---

### Delete a Node (All 3 Cases)

**3 cases when deleting a node:**
1. **Leaf node** (no children) → just remove it.
2. **One child** → replace node with its child.
3. **Two children** → find **inorder successor** (smallest in right subtree), copy its value, delete the successor.

```java
public class DeleteBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    // Find inorder successor: smallest node in right subtree
    public static Node findInorderSuccessor(Node root) {
        while (root.left != null) {
            root = root.left; // go as left as possible
        }
        return root;
    }

    public static Node delete(Node root, int val) {
        if (root == null) return null;

        // First, find the node to delete
        if (val < root.data) {
            root.left = delete(root.left, val); // search left
        } else if (val > root.data) {
            root.right = delete(root.right, val); // search right
        } else {
            // Found the node to delete

            // Case 1: Leaf node
            if (root.left == null && root.right == null) {
                return null;
            }

            // Case 2: One child
            if (root.left == null) {
                return root.right; // replace with right child
            }
            if (root.right == null) {
                return root.left; // replace with left child
            }

            // Case 3: Two children
            Node successor = findInorderSuccessor(root.right);
            root.data = successor.data;                         // copy successor value
            root.right = delete(root.right, successor.data);    // delete successor
        }

        return root;
    }

    public static void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.data + " ");
        inorder(root.right);
    }

    public static void main(String[] args) {
        int[] values = {8, 5, 10, 3, 6, 11, 1, 4, 14};
        Node root = null;
        for (int v : values) root = insert(root, v);

        System.out.print("Original: ");
        inorder(root); // 1 3 4 5 6 8 10 11 14
        System.out.println();

        // Delete leaf (1)
        root = delete(root, 1);
        System.out.print("After deleting 1: ");
        inorder(root); // 3 4 5 6 8 10 11 14
        System.out.println();

        // Delete node with one child (10 has right child 11)
        root = delete(root, 10);
        System.out.print("After deleting 10: ");
        inorder(root); // 3 4 5 6 8 11 14
        System.out.println();

        // Delete node with two children (5 has two children)
        root = delete(root, 5);
        System.out.print("After deleting 5: ");
        inorder(root); // 3 4 6 8 11 14 (or 3 4 6 8 11 14 depending on successor)
        System.out.println();
    }
}
```

---

### Print in Range

Print all nodes whose values lie between `k1` and `k2` (inclusive).

```java
public class PrintInRange {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void printInRange(Node root, int k1, int k2) {
        if (root == null) return;

        // If current node lies in range
        if (root.data >= k1 && root.data <= k2) {
            printInRange(root.left, k1, k2);       // left may have values in range
            System.out.print(root.data + " ");      // print current
            printInRange(root.right, k1, k2);      // right may have values in range
        } else if (root.data < k1) {
            // Current too small → only right side can have values ≥ k1
            printInRange(root.right, k1, k2);
        } else {
            // Current too large → only left side can have values ≤ k2
            printInRange(root.left, k1, k2);
        }
    }

    public static void main(String[] args) {
        int[] values = {8, 5, 10, 3, 6, 11, 1, 4, 14};
        Node root = null;
        for (int v : values) root = insert(root, v);

        System.out.print("Values in range [5, 11]: ");
        printInRange(root, 5, 11); // 5 6 8 10 11
    }
}
```

---

### Root to Leaf Paths

Print all paths from the root to every leaf.

```java
import java.util.ArrayList;

public class RootToLeaf {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void printPath(ArrayList<Integer> path) {
        for (int i = 0; i < path.size(); i++) {
            System.out.print(path.get(i));
            if (i < path.size() - 1) System.out.print(" → ");
        }
        System.out.println();
    }

    public static void printRootToLeaf(Node root, ArrayList<Integer> path) {
        if (root == null) return;

        path.add(root.data); // add current node to path

        // If leaf → print path
        if (root.left == null && root.right == null) {
            printPath(path);
        } else {
            printRootToLeaf(root.left, path);
            printRootToLeaf(root.right, path);
        }

        path.remove(path.size() - 1); // backtrack
    }

    public static void main(String[] args) {
        int[] values = {8, 5, 10, 3, 6, 11, 14};
        Node root = null;
        for (int v : values) root = insert(root, v);

        System.out.println("Root to leaf paths:");
        printRootToLeaf(root, new ArrayList<>());
        // Paths:
        // 8 → 5 → 3
        // 8 → 5 → 6
        // 8 → 10 → 11 → 14
    }
}
```

---

### Validate BST

Check if a binary tree is a valid BST.

**Approach 1 (Inorder):** Inorder of BST is sorted. Do inorder traversal and check if values are strictly increasing.

**Approach 2 (Min-Max):** Each node must be within a valid range (min, max). Root: (-∞, +∞). Left child: (-∞, root.data). Right child: (root.data, +∞).

```java
import java.util.ArrayList;

public class ValidateBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // ---------- Approach 1: Inorder (check if sorted) ----------
    public static void inorder(Node root, ArrayList<Integer> list) {
        if (root == null) return;
        inorder(root.left, list);
        list.add(root.data);
        inorder(root.right, list);
    }

    public static boolean isValidBST1(Node root) {
        ArrayList<Integer> list = new ArrayList<>();
        inorder(root, list);

        for (int i = 1; i < list.size(); i++) {
            if (list.get(i) <= list.get(i - 1)) return false; // not strictly increasing
        }
        return true;
    }

    // ---------- Approach 2: Min-Max range ----------
    public static boolean isValidBST2(Node root, Node min, Node max) {
        if (root == null) return true;

        // If there's a max constraint and current > max → invalid
        if (max != null && root.data >= max.data) return false;
        // If there's a min constraint and current < min → invalid
        if (min != null && root.data <= min.data) return false;

        // Left subtree: max = current, min = same min
        // Right subtree: min = current, max = same max
        return isValidBST2(root.left, min, root) &&
               isValidBST2(root.right, root, max);
    }

    public static Node insert(Node root, int val) {
        // Using Integer.MIN_VALUE wouldn't work (the tree has real nodes)
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void main(String[] args) {
        // Build a valid BST
        int[] values = {8, 5, 10, 3, 6, 11};
        Node root = null;
        for (int v : values) root = insert(root, v);

        System.out.println("Valid BST (inorder): " + isValidBST1(root));  // true
        System.out.println("Valid BST (min-max): " + isValidBST2(root, null, null)); // true

        // Create an invalid tree
        //        8
        //       / \
        //      5   10
        //     / \
        //    3   12  ← 12 is in left of 8, should be < 8
        Node badRoot = new Node(8);
        badRoot.left = new Node(5);
        badRoot.right = new Node(10);
        badRoot.left.left = new Node(3);
        badRoot.left.right = new Node(12);

        System.out.println("Valid BST (inorder): " + isValidBST1(badRoot)); // false
        System.out.println("Valid BST (min-max): " + isValidBST2(badRoot, null, null)); // false
    }
}
```

---

### Mirror a BST

Mirror (invert) a BST: swap left and right children for every node.

```java
public class MirrorBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static Node mirror(Node root) {
        if (root == null) return null;

        Node leftMirror = mirror(root.left);
        Node rightMirror = mirror(root.right);

        // Swap left and right
        root.left = rightMirror;
        root.right = leftMirror;

        return root;
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void main(String[] args) {
        int[] values = {8, 5, 10, 3, 6, 11};
        Node root = null;
        for (int v : values) root = insert(root, v);

        System.out.print("Original preorder: ");
        preorder(root); // 8 5 3 6 10 11

        root = mirror(root);

        System.out.print("\nMirrored preorder: ");
        preorder(root); // 8 10 11 5 6 3
    }
}
```

---

### Convert Sorted Array to Balanced BST

**Balanced BST** means height difference between left and right subtrees of every node is at most 1.

**Logic:** Pick middle element as root. Recursively build left half as left subtree, right half as right subtree.

```java
public class SortedArrayToBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    public static Node sortedArrayToBST(int[] arr, int start, int end) {
        if (start > end) return null;

        int mid = (start + end) / 2;      // middle element as root
        Node root = new Node(arr[mid]);

        root.left = sortedArrayToBST(arr, start, mid - 1);  // left half
        root.right = sortedArrayToBST(arr, mid + 1, end);   // right half

        return root;
    }

    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void main(String[] args) {
        int[] arr = {3, 5, 6, 8, 10, 11, 12}; // sorted array

        Node root = sortedArrayToBST(arr, 0, arr.length - 1);

        System.out.print("Preorder of balanced BST: ");
        preorder(root);
        // Resulting tree (approximately):
        //        8
        //       / \
        //      5   11
        //     / \  / \
        //    3  6 10 12
    }
}
```

---

### Convert BST to Balanced BST

If you have an unbalanced BST, convert it to balanced by:
1. Get sorted values from inorder traversal.
2. Build balanced BST from sorted array (as above).

```java
import java.util.ArrayList;

public class BSTToBalancedBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Step 1: Get inorder (sorted) values
    public static void inorder(Node root, ArrayList<Integer> list) {
        if (root == null) return;
        inorder(root.left, list);
        list.add(root.data);
        inorder(root.right, list);
    }

    // Step 2: Build balanced BST from sorted array
    public static Node sortedArrayToBST(ArrayList<Integer> arr, int start, int end) {
        if (start > end) return null;

        int mid = (start + end) / 2;
        Node root = new Node(arr.get(mid));

        root.left = sortedArrayToBST(arr, start, mid - 1);
        root.right = sortedArrayToBST(arr, mid + 1, end);

        return root;
    }

    public static Node balanceBST(Node root) {
        // Step 1: Get inorder
        ArrayList<Integer> inorderList = new ArrayList<>();
        inorder(root, inorderList);

        // Step 2: Build balanced BST from sorted list
        return sortedArrayToBST(inorderList, 0, inorderList.size() - 1);
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void main(String[] args) {
        // Build an unbalanced BST
        //        8
        //       / \
        //      5   10
        //     /
        //    3
        //   /
        //  1
        Node root = null;
        root = insert(root, 8);
        root = insert(root, 5);
        root = insert(root, 10);
        root = insert(root, 3);
        root = insert(root, 1);

        System.out.print("Before balancing (preorder): ");
        preorder(root); // 8 5 3 1 10

        root = balanceBST(root);

        System.out.print("\nAfter balancing (preorder): ");
        preorder(root); // 5 3 1 8 10 (balanced tree)
    }
}
```

---

### Size of Largest BST in Binary Tree

**Problem:** Given a binary tree (not necessarily BST), find the size of the **largest subtree** that is a valid BST.

**Logic:** Postorder traversal. For each node, return:
- `isBST` — whether subtree rooted at this node is BST
- `size` — number of nodes in this subtree
- `min` — minimum value in this subtree
- `max` — maximum value in this subtree

```java
public class LargestBST {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    static class Info {
        boolean isBST;
        int size;
        int min;
        int max;

        Info(boolean isBST, int s, int min, int max) {
            this.isBST = isBST;
            this.size = s;
            this.min = min;
            this.max = max;
        }
    }

    static int maxBSTSize = 0;

    public static Info largestBST(Node root) {
        if (root == null) {
            return new Info(true, 0, Integer.MAX_VALUE, Integer.MIN_VALUE);
        }

        Info left = largestBST(root.left);
        Info right = largestBST(root.right);

        int size = left.size + right.size + 1;
        int min = Math.min(root.data, Math.min(left.min, right.min));
        int max = Math.max(root.data, Math.max(left.max, right.max));

        // Check if current subtree is BST
        if (left.isBST && right.isBST &&
            root.data > left.max && root.data < right.min) {

            maxBSTSize = Math.max(maxBSTSize, size);
            return new Info(true, size, min, max);
        }

        return new Info(false, size, min, max);
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void main(String[] args) {
        // Build a normal BST first
        //        8
        //       / \
        //      5   10
        //     / \    \
        //    3   6    11
        Node root = insert(null, 8);
        root = insert(root, 5);
        root = insert(root, 10);
        root = insert(root, 3);
        root = insert(root, 6);
        root = insert(root, 11);

        largestBST(root);
        System.out.println("Size of largest BST: " + maxBSTSize); // 6 (the whole tree)

        // Now build a non-BST tree
        //        8
        //       / \
        //      5   10
        //     / \
        //    3   12  ← 12 > 8, violates BST property
        Node badRoot = new Node(8);
        badRoot.left = new Node(5);
        badRoot.right = new Node(10);
        badRoot.left.left = new Node(3);
        badRoot.left.right = new Node(12);

        maxBSTSize = 0;
        largestBST(badRoot);
        System.out.println("Size of largest BST in non-BST tree: " + maxBSTSize);
        // Could be 3 (subtree rooted at 10, or 5-3, etc.)
    }
}
```

---

### Merge Two BSTs

**Problem:** Merge two BSTs into a single sorted list or a single BST.

**Approach 1:** Inorder of both → merge sorted arrays → build balanced BST.

```java
import java.util.ArrayList;

public class MergeTwoBSTs {

    static class Node {
        int data;
        Node left, right;
        Node(int data) { this.data = data; }
    }

    // Step 1: Get inorder traversal (sorted)
    public static void inorder(Node root, ArrayList<Integer> list) {
        if (root == null) return;
        inorder(root.left, list);
        list.add(root.data);
        inorder(root.right, list);
    }

    // Step 2: Merge two sorted arrays
    public static ArrayList<Integer> mergeLists(ArrayList<Integer> l1, ArrayList<Integer> l2) {
        ArrayList<Integer> merged = new ArrayList<>();
        int i = 0, j = 0;

        while (i < l1.size() && j < l2.size()) {
            if (l1.get(i) <= l2.get(j)) {
                merged.add(l1.get(i++));
            } else {
                merged.add(l2.get(j++));
            }
        }

        // Add remaining elements
        while (i < l1.size()) merged.add(l1.get(i++));
        while (j < l2.size()) merged.add(l2.get(j++));

        return merged;
    }

    // Step 3: Build balanced BST from sorted array
    public static Node sortedArrayToBST(ArrayList<Integer> arr, int start, int end) {
        if (start > end) return null;

        int mid = (start + end) / 2;
        Node root = new Node(arr.get(mid));

        root.left = sortedArrayToBST(arr, start, mid - 1);
        root.right = sortedArrayToBST(arr, mid + 1, end);

        return root;
    }

    public static Node mergeBSTs(Node root1, Node root2) {
        // Get sorted lists
        ArrayList<Integer> list1 = new ArrayList<>();
        ArrayList<Integer> list2 = new ArrayList<>();
        inorder(root1, list1);
        inorder(root2, list2);

        // Merge sorted lists
        ArrayList<Integer> merged = mergeLists(list1, list2);

        // Build balanced BST from merged list
        return sortedArrayToBST(merged, 0, merged.size() - 1);
    }

    public static Node insert(Node root, int val) {
        if (root == null) return new Node(val);
        if (val < root.data) root.left = insert(root.left, val);
        else root.right = insert(root.right, val);
        return root;
    }

    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    public static void main(String[] args) {
        // BST 1: {2, 1, 4}
        //         2
        //        / \
        //       1   4
        Node root1 = null;
        root1 = insert(root1, 2);
        root1 = insert(root1, 1);
        root1 = insert(root1, 4);

        // BST 2: {9, 3, 12}
        //         9
        //        / \
        //       3   12
        Node root2 = null;
        root2 = insert(root2, 9);
        root2 = insert(root2, 3);
        root2 = insert(root2, 12);

        Node mergedRoot = mergeBSTs(root1, root2);

        System.out.print("Merged BST (preorder): ");
        preorder(mergedRoot);
        // Sorted values: [1, 2, 3, 4, 9, 12]
        // Balanced BST preorder (approximately): 4 2 1 3 9 12
    }
}
```

---

> **End of Section 3 — Stacks, Queues, Greedy, Binary Trees, Binary Search Trees**
# Section 4: Data Structures & Algorithms in Java — Complete Beginner's Guide

> **How to use this guide**: Each topic starts with a plain-English explanation. Then comes **full Java code** you can copy, compile, and run. Every line has a comment. Read the explanation, then trace through the code.

---

# 1. HEAPS

## 1.1 What is a Heap?

A **heap** is a special tree-based data structure that satisfies the **heap property**:

- **Min-Heap**: parent is always SMALLER than (or equal to) its children → smallest element at root.
- **Max-Heap**: parent is always LARGER than (or equal to) its children → largest element at root.

Think of a heap as a **priority queue** — the element with the highest (or lowest) priority is always at the top.

**Key facts**:
- It's a **complete binary tree** (all levels filled except possibly last, which fills left-to-right).
- We typically implement it with an **array or ArrayList** (not linked nodes) because the complete-tree structure lets us use simple index math:
  - Parent of node at index `i` = `(i-1)/2`
  - Left child = `2*i + 1`
  - Right child = `2*i + 2`
- Insertion and deletion both take **O(log n)** time.

---

## 1.2 Heap Using ArrayList — Implement from Scratch

```java
import java.util.ArrayList;

// Min-Heap implementation using ArrayList
public class HeapFromScratch {

    static class MinHeap {
        ArrayList<Integer> arr = new ArrayList<>();

        // ---- INSERT ----
        // Add at end, then "bubble up" (percolate up) until heap property restored
        public void insert(int data) {
            arr.add(data);                       // Step 1: add to end (rightmost leaf)

            int childIdx = arr.size() - 1;       // index of newly added element
            int parentIdx = (childIdx - 1) / 2;  // parent index formula

            // Step 2: bubble up — keep swapping child with parent if child < parent
            while (childIdx > 0 && arr.get(childIdx) < arr.get(parentIdx)) {
                // swap child and parent
                int temp = arr.get(childIdx);
                arr.set(childIdx, arr.get(parentIdx));
                arr.set(parentIdx, temp);

                // move up the tree
                childIdx = parentIdx;
                parentIdx = (childIdx - 1) / 2;
            }
        }

        // ---- PEEK (get min without removing) ----
        public int peek() {
            if (arr.isEmpty()) {
                throw new RuntimeException("Heap is empty");
            }
            return arr.get(0);  // root is always the smallest
        }

        // ---- DELETE (remove min) ----
        // Replace root with last element, remove last, then "bubble down" (heapify)
        public int delete() {
            if (arr.isEmpty()) {
                throw new RuntimeException("Heap is empty");
            }

            int minValue = arr.get(0);   // save the min to return later

            // Step 1: swap root with last element
            int lastIdx = arr.size() - 1;
            arr.set(0, arr.get(lastIdx));
            arr.remove(lastIdx);         // remove the last element (old root is gone)

            // Step 2: bubble down (heapify) from root
            heapify(0);

            return minValue;
        }

        // ---- HEAPIFY ----
        // Fix the heap property at index i by swapping with smallest child
        private void heapify(int i) {
            int smallest = i;              // assume current node is smallest
            int leftChild = 2 * i + 1;
            int rightChild = 2 * i + 2;

            // if left child exists and is smaller than current smallest
            if (leftChild < arr.size() && arr.get(leftChild) < arr.get(smallest)) {
                smallest = leftChild;
            }
            // if right child exists and is smaller than current smallest
            if (rightChild < arr.size() && arr.get(rightChild) < arr.get(smallest)) {
                smallest = rightChild;
            }

            // if smallest is not the original i, swap and recurse
            if (smallest != i) {
                int temp = arr.get(i);
                arr.set(i, arr.get(smallest));
                arr.set(smallest, temp);

                heapify(smallest);  // recursively fix the affected subtree
            }
        }

        public boolean isEmpty() {
            return arr.isEmpty();
        }

        public void print() {
            System.out.println(arr);
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        MinHeap heap = new MinHeap();

        System.out.println("=== Min-Heap Demo ===");

        heap.insert(5);
        heap.insert(3);
        heap.insert(8);
        heap.insert(1);
        heap.insert(2);

        System.out.print("Heap array: ");
        heap.print();            // [1, 2, 8, 5, 3]  (min at root = 1)

        System.out.println("Peek (min): " + heap.peek());  // 1

        System.out.println("Delete: " + heap.delete());    // removes 1
        System.out.print("After delete: ");
        heap.print();            // [2, 3, 8, 5]

        System.out.println("Delete: " + heap.delete());    // removes 2
        System.out.print("After delete: ");
        heap.print();            // [3, 5, 8]

        System.out.println("Delete: " + heap.delete());    // removes 3
        System.out.print("After delete: ");
        heap.print();            // [5, 8]

        System.out.println("Delete: " + heap.delete());    // removes 5
        System.out.print("After delete: ");
        heap.print();            // [8]

        System.out.println("Delete: " + heap.delete());    // removes 8
        System.out.println("Heap empty? " + heap.isEmpty()); // true
    }
}
```

### Heap Sort Using Our Min-Heap

```java
import java.util.ArrayList;

// Heap Sort: insert all elements, then repeatedly delete min
public class HeapSortDemo {

    // Reuse the MinHeap class from above (copied here for standalone use)
    static class MinHeap {
        ArrayList<Integer> arr = new ArrayList<>();

        public void insert(int data) {
            arr.add(data);
            int childIdx = arr.size() - 1;
            int parentIdx = (childIdx - 1) / 2;
            while (childIdx > 0 && arr.get(childIdx) < arr.get(parentIdx)) {
                int temp = arr.get(childIdx);
                arr.set(childIdx, arr.get(parentIdx));
                arr.set(parentIdx, temp);
                childIdx = parentIdx;
                parentIdx = (childIdx - 1) / 2;
            }
        }

        public int delete() {
            if (arr.isEmpty()) throw new RuntimeException("Empty");
            int minValue = arr.get(0);
            int lastIdx = arr.size() - 1;
            arr.set(0, arr.get(lastIdx));
            arr.remove(lastIdx);
            heapify(0);
            return minValue;
        }

        private void heapify(int i) {
            int smallest = i;
            int left = 2 * i + 1, right = 2 * i + 2;
            if (left < arr.size() && arr.get(left) < arr.get(smallest)) smallest = left;
            if (right < arr.size() && arr.get(right) < arr.get(smallest)) smallest = right;
            if (smallest != i) {
                int t = arr.get(i); arr.set(i, arr.get(smallest)); arr.set(smallest, t);
                heapify(smallest);
            }
        }

        public boolean isEmpty() { return arr.isEmpty(); }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] nums = {5, 3, 8, 1, 2, 9, 4};
        MinHeap heap = new MinHeap();

        // Step 1: insert all elements into heap
        System.out.println("Original array:");
        for (int n : nums) {
            System.out.print(n + " ");
            heap.insert(n);
        }
        System.out.println();

        // Step 2: repeatedly extract min → array is now sorted ascending
        System.out.println("Sorted (ascending):");
        while (!heap.isEmpty()) {
            System.out.print(heap.delete() + " ");  // 1 2 3 4 5 8 9
        }
        System.out.println();
    }
}
```

---

## 1.3 PriorityQueue in JCF (Java Collections Framework)

Java provides `PriorityQueue` which is a **min-heap by default**. To make it a **max-heap**, pass `Comparator.reverseOrder()`.

```java
import java.util.PriorityQueue;
import java.util.Comparator;

public class JCFPriorityQueueDemo {

    // ========== MAIN ==========
    public static void main(String[] args) {

        // --- Min-Heap (default) ---
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        minHeap.add(5);
        minHeap.add(1);
        minHeap.add(3);
        minHeap.add(8);

        System.out.println("Min-Heap (default PriorityQueue):");
        while (!minHeap.isEmpty()) {
            System.out.print(minHeap.poll() + " ");  // 1 3 5 8 (sorted order)
        }
        System.out.println();

        // --- Max-Heap (using Comparator.reverseOrder()) ---
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Comparator.reverseOrder());
        maxHeap.add(5);
        maxHeap.add(1);
        maxHeap.add(3);
        maxHeap.add(8);

        System.out.println("Max-Heap (Comparator.reverseOrder()):");
        while (!maxHeap.isEmpty()) {
            System.out.print(maxHeap.poll() + " ");  // 8 5 3 1
        }
        System.out.println();

        // --- Custom Object in PriorityQueue ---
        // Example: students sorted by marks (ascending)
        PriorityQueue<Student> pq = new PriorityQueue<>();
        pq.add(new Student("Alice", 85));
        pq.add(new Student("Bob", 72));
        pq.add(new Student("Charlie", 95));

        System.out.println("Students sorted by marks (ascending):");
        while (!pq.isEmpty()) {
            Student s = pq.poll();
            System.out.println(s.name + " → " + s.marks);
        }
    }

    // Student class implementing Comparable to define priority order
    static class Student implements Comparable<Student> {
        String name;
        int marks;

        Student(String name, int marks) {
            this.name = name;
            this.marks = marks;
        }

        // compareTo returns negative if this.marks < other.marks → higher priority (lower marks first)
        @Override
        public int compareTo(Student other) {
            return this.marks - other.marks;  // ascending order of marks
        }
    }
}
```

### Methods Summary for PriorityQueue

| Method | Description |
|--------|-------------|
| `add(e)` / `offer(e)` | Insert element |
| `peek()` | Get min/max without removing (null if empty) |
| `poll()` | Remove and return min/max (null if empty) |
| `remove(e)` | Remove specific element |
| `size()` | Number of elements |
| `isEmpty()` | Check if empty |

---

## 1.4 Nearby Cars Problem

**Problem**: Given an array of points (cars) and an integer K, find the K closest cars to the origin (0,0). Distance = `x² + y²`.

**Approach**: Use a Min-Heap (by distance). Insert all points. Poll K times.

```java
import java.util.PriorityQueue;

public class NearbyCars {

    // Helper class to store a point and its squared distance from origin
    static class Point implements Comparable<Point> {
        int x, y;
        int distSq;  // squared distance from origin (avoid sqrt for performance)

        Point(int x, int y) {
            this.x = x;
            this.y = y;
            this.distSq = x * x + y * y;
        }

        // Min-heap: smaller distance = higher priority
        @Override
        public int compareTo(Point other) {
            return this.distSq - other.distSq;
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[][] points = {{3, 3}, {5, -1}, {-2, 4}};
        int K = 2;

        // Insert all points into min-heap
        PriorityQueue<Point> pq = new PriorityQueue<>();
        for (int[] p : points) {
            pq.add(new Point(p[0], p[1]));
        }

        // Extract K closest points
        System.out.println("The " + K + " closest cars to (0,0):");
        for (int i = 0; i < K; i++) {
            Point p = pq.poll();                 // gets the smallest distance each time
            System.out.println("(" + p.x + ", " + p.y + ")  distance² = " + p.distSq);
        }
    }
}
```

---

## 1.5 Connect N Ropes (Minimum Cost)

**Problem**: Given N ropes of different lengths, connect them into one rope. Cost of connecting two ropes = sum of their lengths. Find minimum total cost.

**Approach**: Always connect the two **shortest** ropes first (greedy). Use a min-heap.

```java
import java.util.PriorityQueue;

public class ConnectNRopes {

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] ropes = {4, 3, 2, 6};

        // Step 1: add all rope lengths to min-heap
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        for (int len : ropes) {
            pq.add(len);
        }

        int totalCost = 0;

        // Step 2: keep combining two smallest ropes until one rope remains
        while (pq.size() > 1) {
            int smallest = pq.poll();   // remove shortest rope
            int secondSmallest = pq.poll(); // remove second shortest

            int cost = smallest + secondSmallest;  // cost to connect these two
            totalCost += cost;

            pq.add(cost);  // add the new combined rope back into the heap
        }

        System.out.println("Minimum cost to connect all ropes: " + totalCost);
        // For ropes {4,3,2,6}: (2+3)=5, (4+5)=9, (6+9)=15 → total = 5+9+15 = 29
    }
}
```

---

## 1.6 Weakest Soldier Problem

**Problem**: Given an `m x n` binary matrix where `1` = soldier, `0` = civilian. A row's strength = number of soldiers. Find the K **weakest** rows (fewest soldiers). If tie, the row with smaller index is weaker.

**Approach**: Use a min-heap that compares by soldier count first, then row index.

```java
import java.util.PriorityQueue;

public class WeakestSoldier {

    // Helper class representing a row
    static class Row implements Comparable<Row> {
        int soldierCount;  // number of soldiers (1s) in this row
        int idx;           // row index

        Row(int soldierCount, int idx) {
            this.soldierCount = soldierCount;
            this.idx = idx;
        }

        // Sort by soldier count first, then by index
        @Override
        public int compareTo(Row other) {
            if (this.soldierCount != other.soldierCount) {
                return this.soldierCount - other.soldierCount;  // fewer soldiers = weaker
            }
            return this.idx - other.idx;  // if tie, smaller index = weaker
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 0, 0, 0},        // 1 soldier
            {1, 1, 1, 1},        // 4 soldiers
            {1, 0, 0, 0},        // 1 soldier
            {1, 1, 0, 0}         // 2 soldiers
        };
        int K = 2;

        // Count soldiers per row and add to min-heap
        PriorityQueue<Row> pq = new PriorityQueue<>();
        for (int i = 0; i < matrix.length; i++) {
            int count = 0;
            for (int j = 0; j < matrix[i].length; j++) {
                if (matrix[i][j] == 1) count++;  // count soldiers in this row
            }
            pq.add(new Row(count, i));
        }

        // Extract K weakest rows
        System.out.println("The " + K + " weakest rows are:");
        for (int i = 0; i < K; i++) {
            System.out.println("Row " + pq.poll().idx);
        }
    }
}
```

---

## 1.7 Sliding Window Maximum

**Problem**: Given an array and a window size K, find the maximum element in every contiguous subarray of size K.

**Approach**: Use a **max-heap** (PriorityQueue with reverse order). Store `[value, index]`. For each window:
1. Add current element to heap
2. Remove elements that are out of window bounds (index < window start)
3. The heap's root is the max of the current window

```java
import java.util.PriorityQueue;
import java.util.ArrayList;
import java.util.Comparator;

public class SlidingWindowMax {

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] arr = {1, 3, -1, -3, 5, 3, 6, 7};
        int K = 3;

        // Max-heap: each element is an int[] where [0]=value, [1]=index
        // We use a custom Comparator to sort by value descending
        PriorityQueue<int[]> pq = new PriorityQueue<>(
            (a, b) -> b[0] - a[0]   // compare values: bigger value = higher priority
        );

        ArrayList<Integer> result = new ArrayList<>();

        // Process each element
        for (int i = 0; i < arr.length; i++) {
            // Add current element with its index
            pq.add(new int[]{arr[i], i});

            // Remove elements that are outside the current window
            // Window is [i-K+1, i]; any index less than (i-K+1) is out
            while (!pq.isEmpty() && pq.peek()[1] <= i - K) {
                pq.poll();  // remove outdated max
            }

            // Once we've processed at least K elements, the root is the window's max
            if (i >= K - 1) {
                result.add(pq.peek()[0]);  // peek() gives max of current window
            }
        }

        System.out.print("Sliding window maximums: ");
        for (int max : result) {
            System.out.print(max + " ");  // 3 3 5 5 6 7
        }
        System.out.println();
    }
}
```

---

# 2. HASHING

## 2.1 What is Hashing?

**Hashing** is a technique to map data of arbitrary size to fixed-size values (called **hash codes** or **hashes**). We use a **hash function** that takes a key and returns an integer index into an array (the **bucket**).

**HashMap**: Stores key-value pairs. Keys are unique. Average **O(1)** for put, get, remove.

**HashSet**: Stores unique elements only. Built on top of HashMap (keys are the elements, values are dummy).

**Collision**: When two different keys hash to the same index. Handled by:
- **Chaining**: Each bucket is a linked list (or tree) of entries.
- **Open addressing**: Find next empty slot (probe sequence).

---

## 2.2 HashMap Operations

```java
import java.util.HashMap;
import java.util.Map;  // for Map.Entry

public class HashMapDemo {

    // ========== MAIN ==========
    public static void main(String[] args) {

        // Create a HashMap: key = String, value = Integer
        HashMap<String, Integer> map = new HashMap<>();

        // ---- put(key, value) : insert or update ----
        map.put("India", 140);      // adds entry: India → 140
        map.put("China", 142);
        map.put("USA", 33);
        map.put("India", 141);      // updates India's value from 140 to 141

        System.out.println("HashMap: " + map);

        // ---- get(key) : retrieve value (null if absent) ----
        System.out.println("Population of India: " + map.get("India"));   // 141
        System.out.println("Population of France: " + map.get("France")); // null

        // ---- containsKey(key) : check if key exists ----
        System.out.println("Contains India? " + map.containsKey("India"));   // true
        System.out.println("Contains France? " + map.containsKey("France")); // false

        // ---- remove(key) : delete entry ----
        map.remove("USA");
        System.out.println("After removing USA: " + map);

        // ---- size() : number of entries ----
        System.out.println("Size: " + map.size());  // 2

        // ---- keySet() : get all keys ----
        System.out.print("Keys: ");
        for (String key : map.keySet()) {
            System.out.print(key + " ");  // India China (order not guaranteed)
        }
        System.out.println();

        // ---- Iterate over both keys and values ----
        System.out.println("All entries:");
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            String country = entry.getKey();
            int population = entry.getValue();
            System.out.println("  " + country + " → " + population);
        }

        // ---- clear() : remove all entries ----
        map.clear();
        System.out.println("After clear, size: " + map.size());  // 0
    }
}
```

### HashMap Time Complexities

| Operation | Average Case | Worst Case |
|-----------|-------------|------------|
| put       | O(1)        | O(n)       |
| get       | O(1)        | O(n)       |
| remove    | O(1)        | O(n)       |
| containsKey | O(1)      | O(n)       |

---

## 2.3 HashMap Implementation Using ArrayList<LinkedList> (From Scratch)

```java
import java.util.ArrayList;
import java.util.LinkedList;

// A simple HashMap from scratch with chaining
public class HashMapScratch {

    // Node class to store key-value pairs in the linked list
    static class Node<K, V> {
        K key;
        V value;

        Node(K key, V value) {
            this.key = key;
            this.value = value;
        }
    }

    // Our custom HashMap class
    static class MyHashMap<K, V> {

        private ArrayList<LinkedList<Node<K, V>>> buckets;  // array of linked lists
        private int size = 0;           // number of key-value pairs
        private int numBuckets;         // number of buckets = capacity of array
        private static final double LOAD_FACTOR = 0.75;  // resize when 75% full

        public MyHashMap() {
            this.numBuckets = 4;        // start with 4 buckets
            buckets = new ArrayList<>(numBuckets);
            for (int i = 0; i < numBuckets; i++) {
                buckets.add(new LinkedList<>());  // initialize each bucket as empty list
            }
        }

        // Hash function: converts key to bucket index
        private int hashFunction(K key) {
            int hashCode = key.hashCode();          // get Java's hash code
            return Math.abs(hashCode) % numBuckets; // compress to bucket range
        }

        // ---- PUT ----
        public void put(K key, V value) {
            int bucketIdx = hashFunction(key);
            LinkedList<Node<K, V>> ll = buckets.get(bucketIdx);

            // Check if key already exists → update value
            for (Node<K, V> node : ll) {
                if (node.key.equals(key)) {
                    node.value = value;     // key already present, update value
                    return;
                }
            }

            // Key doesn't exist → add new node
            ll.add(new Node<>(key, value));
            size++;

            // Check if we need to resize (rehash)
            double currentLoadFactor = (double) size / numBuckets;
            if (currentLoadFactor > LOAD_FACTOR) {
                rehash();
            }
        }

        // ---- GET ----
        public V get(K key) {
            int bucketIdx = hashFunction(key);
            LinkedList<Node<K, V>> ll = buckets.get(bucketIdx);

            for (Node<K, V> node : ll) {
                if (node.key.equals(key)) {
                    return node.value;   // found! return value
                }
            }
            return null;  // key not found
        }

        // ---- containsKey ----
        public boolean containsKey(K key) {
            int bucketIdx = hashFunction(key);
            LinkedList<Node<K, V>> ll = buckets.get(bucketIdx);

            for (Node<K, V> node : ll) {
                if (node.key.equals(key)) {
                    return true;         // found!
                }
            }
            return false;
        }

        // ---- REMOVE ----
        public V remove(K key) {
            int bucketIdx = hashFunction(key);
            LinkedList<Node<K, V>> ll = buckets.get(bucketIdx);

            for (Node<K, V> node : ll) {
                if (node.key.equals(key)) {
                    V val = node.value;
                    ll.remove(node);     // remove from linked list
                    size--;
                    return val;
                }
            }
            return null;  // key not found
        }

        // ---- size ----
        public int size() {
            return size;
        }

        // ---- isEmpty ----
        public boolean isEmpty() {
            return size == 0;
        }

        // ---- keySet ----
        public ArrayList<K> keySet() {
            ArrayList<K> keys = new ArrayList<>();
            for (LinkedList<Node<K, V>> ll : buckets) {
                for (Node<K, V> node : ll) {
                    keys.add(node.key);
                }
            }
            return keys;
        }

        // ---- REHASH (resize when load factor exceeded) ----
        private void rehash() {
            // Save reference to old buckets
            ArrayList<LinkedList<Node<K, V>>> oldBuckets = buckets;

            // Double the number of buckets
            numBuckets = numBuckets * 2;
            buckets = new ArrayList<>(numBuckets);
            for (int i = 0; i < numBuckets; i++) {
                buckets.add(new LinkedList<>());
            }

            size = 0;  // reset size; put() will increment

            // Re-insert all existing entries into the new (larger) bucket array
            for (LinkedList<Node<K, V>> ll : oldBuckets) {
                for (Node<K, V> node : ll) {
                    put(node.key, node.value);  // re-insert (this will compute new hash)
                }
            }
        }

        public void print() {
            for (int i = 0; i < numBuckets; i++) {
                LinkedList<Node<K, V>> ll = buckets.get(i);
                if (!ll.isEmpty()) {
                    System.out.print("Bucket " + i + ": ");
                    for (Node<K, V> node : ll) {
                        System.out.print("[" + node.key + ":" + node.value + "] ");
                    }
                    System.out.println();
                }
            }
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        MyHashMap<String, Integer> map = new MyHashMap<>();

        System.out.println("=== Custom HashMap Demo ===");

        map.put("India", 140);
        map.put("China", 142);
        map.put("USA", 33);
        map.put("Indonesia", 27);
        map.put("Brazil", 21);

        System.out.println("Size: " + map.size());  // 5

        System.out.println("Get India: " + map.get("India"));     // 140
        System.out.println("Get France: " + map.get("France"));   // null

        System.out.println("Contains USA? " + map.containsKey("USA")); // true

        map.remove("USA");
        System.out.println("After removing USA, size: " + map.size()); // 4
        System.out.println("Contains USA? " + map.containsKey("USA")); // false

        System.out.println("\nBucket layout:");
        map.print();

        System.out.println("\nAll keys: " + map.keySet());
    }
}
```

---

## 2.4 HashSet Operations

```java
import java.util.HashSet;
import java.util.Iterator;

public class HashSetDemo {

    // ========== MAIN ==========
    public static void main(String[] args) {

        HashSet<Integer> set = new HashSet<>();

        // ---- add(value) : insert element ----
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(10);  // duplicate! set still has only one 10

        System.out.println("HashSet: " + set);  // [10, 20, 30] (order not guaranteed)

        // ---- contains(value) : check existence ----
        System.out.println("Contains 20? " + set.contains(20));  // true
        System.out.println("Contains 99? " + set.contains(99));  // false

        // ---- remove(value) : delete element ----
        set.remove(20);
        System.out.println("After removing 20: " + set);  // [10, 30]

        // ---- size() : number of elements ----
        System.out.println("Size: " + set.size());  // 2

        // ---- isEmpty() ----
        System.out.println("Is empty? " + set.isEmpty());  // false

        // ---- Iteration using for-each ----
        System.out.print("Elements: ");
        for (int val : set) {
            System.out.print(val + " ");   // 10 30
        }
        System.out.println();

        // ---- Iteration using Iterator ----
        Iterator<Integer> it = set.iterator();
        System.out.print("Using Iterator: ");
        while (it.hasNext()) {
            System.out.print(it.next() + " ");
        }
        System.out.println();

        // ---- clear() : remove all ----
        set.clear();
        System.out.println("After clear, size: " + set.size());  // 0
    }
}
```

---

## 2.5 Majority Element

**Problem**: Given an array of size N, find all elements that appear more than `N/3` times.

**Approach**: Count frequencies using HashMap.

```java
import java.util.HashMap;
import java.util.ArrayList;

public class MajorityElement {

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] arr = {1, 3, 2, 5, 1, 3, 1, 5, 1};
        // Expected: elements with frequency > N/3 = 9/3 = 3 → 1 appears 4 times

        int threshold = arr.length / 3;

        // Step 1: count frequencies
        HashMap<Integer, Integer> freqMap = new HashMap<>();
        for (int num : arr) {
            // freqMap.getOrDefault(num, 0) returns current count (or 0 if absent), then +1
            freqMap.put(num, freqMap.getOrDefault(num, 0) + 1);
        }

        // Step 2: find elements exceeding threshold
        ArrayList<Integer> result = new ArrayList<>();
        for (int key : freqMap.keySet()) {
            if (freqMap.get(key) > threshold) {
                result.add(key);
                System.out.println(key + " appears " + freqMap.get(key) + " times (> " + threshold + ")");
            }
        }

        System.out.println("Majority elements: " + result);  // [1]
    }
}
```

---

## 2.6 Union and Intersection of Arrays

**Problem**: Given two arrays, find their union (all distinct elements) and intersection (common elements).

**Approach**: Use HashSet for O(1) lookups.

```java
import java.util.HashSet;

public class UnionIntersection {

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] arr1 = {7, 3, 9};
        int[] arr2 = {6, 3, 9, 2, 9, 4};

        // ---- UNION: all distinct elements from both arrays ----
        HashSet<Integer> unionSet = new HashSet<>();

        // add all elements from arr1
        for (int num : arr1) {
            unionSet.add(num);
        }
        // add all elements from arr2 (duplicates are ignored)
        for (int num : arr2) {
            unionSet.add(num);
        }

        System.out.println("Union: " + unionSet + "  (size = " + unionSet.size() + ")");
        // {2, 3, 4, 6, 7, 9}  size = 6

        // ---- INTERSECTION: elements common to both arrays ----
        HashSet<Integer> set1 = new HashSet<>();
        HashSet<Integer> intersectionSet = new HashSet<>();

        // put all arr1 elements into set1
        for (int num : arr1) {
            set1.add(num);
        }

        // check each element of arr2 against set1
        for (int num : arr2) {
            if (set1.contains(num)) {
                intersectionSet.add(num);   // add to intersection
                set1.remove(num);           // remove to avoid duplicates in result
            }
        }

        System.out.println("Intersection: " + intersectionSet + "  (size = " + intersectionSet.size() + ")");
        // {3, 9}  size = 2
    }
}
```

---

## 2.7 Find Itinerary from Tickets

**Problem**: Given a list of tickets (source → destination), find the complete journey. Assume the itinerary is a linear path (no cycles).

**Approach**: Build a HashMap of `source → destination`. Find the starting point (a source that is never a destination). Then traverse.

```java
import java.util.HashMap;

public class FindItinerary {

    // ========== MAIN ==========
    public static void main(String[] args) {

        // Tickets: source → destination
        HashMap<String, String> tickets = new HashMap<>();
        tickets.put("Chennai", "Bengaluru");
        tickets.put("Mumbai", "Delhi");
        tickets.put("Goa", "Chennai");
        tickets.put("Delhi", "Goa");

        // Step 1: Find the starting city
        // The start is a city that appears as a source but NOT as any destination
        String start = findStart(tickets);
        System.out.println("Start city: " + start);

        // Step 2: Traverse the itinerary
        System.out.print("Itinerary: " + start);
        String current = start;
        while (tickets.containsKey(current)) {
            String next = tickets.get(current);  // get destination for current city
            System.out.print(" → " + next);
            current = next;                       // move to next city
        }
        System.out.println();

        // Expected: Mumbai → Delhi → Goa → Chennai → Bengaluru
    }

    // Helper method to find the starting point
    public static String findStart(HashMap<String, String> tickets) {
        // Build a reverse map: destination → true (mark every city that is a destination)
        HashMap<String, Boolean> destMap = new HashMap<>();
        for (String src : tickets.keySet()) {
            String dest = tickets.get(src);
            destMap.put(dest, true);  // mark this city as a destination
        }

        // The starting city is a source that is NOT in destination map
        for (String src : tickets.keySet()) {
            if (!destMap.containsKey(src)) {
                return src;  // this source is never a destination → it's the start
            }
        }
        return null;
    }
}
```

---

## 2.8 Subarray Sum Equal to K

**Problem**: Given an array of integers, count the number of subarrays whose sum equals K.

**Approach**: Use prefix sum + HashMap. As we iterate, maintain `sumSoFar`. If `sumSoFar - K` has appeared before, those subarrays sum to K.

```java
import java.util.HashMap;

public class SubarraySumEqualsK {

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] arr = {10, 2, -2, -20, 10};
        int K = -10;

        // Key: prefix sum value
        // Value: how many times this prefix sum has occurred
        HashMap<Integer, Integer> prefixSumMap = new HashMap<>();

        // sum 0 has occurred once (empty prefix before index 0)
        prefixSumMap.put(0, 1);

        int sumSoFar = 0;   // running prefix sum
        int count = 0;      // number of subarrays found

        for (int i = 0; i < arr.length; i++) {
            sumSoFar += arr[i];  // update prefix sum

            // If (sumSoFar - K) exists, subarrays ending at i sum to K
            // Reason: prefix[j] - prefix[i-1] = sum of subarray from i to j
            // Rearranged: prefix[j] - K = prefix[i-1]
            int needed = sumSoFar - K;
            if (prefixSumMap.containsKey(needed)) {
                count += prefixSumMap.get(needed);  // add all matching prefixes
            }

            // Record the current prefix sum for future lookups
            prefixSumMap.put(sumSoFar, prefixSumMap.getOrDefault(sumSoFar, 0) + 1);
        }

        System.out.println("Number of subarrays summing to " + K + ": " + count);
        // Subarrays: [10,2,-2,-20] = -10, [-20,10] = -10  → count = 2
    }
}
```

---

## 2.9 Largest Subarray with 0 Sum

**Problem**: Find the length of the longest subarray whose sum is 0.

**Approach**: Use prefix sum + HashMap storing the **first occurrence** of each prefix sum. If same prefix sum appears again, the elements between them sum to 0.

```java
import java.util.HashMap;

public class LargestSubarrayZeroSum {

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[] arr = {15, -2, 2, -8, 1, 7, 10, 23};

        // Key: prefix sum value
        // Value: first index where this sum occurred
        HashMap<Integer, Integer> map = new HashMap<>();

        int sum = 0;        // running prefix sum
        int maxLen = 0;     // length of longest zero-sum subarray

        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];  // update running sum

            if (sum == 0) {
                // Entire array from index 0 to i sums to 0
                maxLen = i + 1;
            }

            // If this sum has been seen before, subarray from (firstIdx+1) to i sums to 0
            if (map.containsKey(sum)) {
                int firstIdx = map.get(sum);                // first time we saw this sum
                int subarrayLen = i - firstIdx;             // length of zero-sum subarray
                maxLen = Math.max(maxLen, subarrayLen);
            } else {
                // Store first occurrence of this sum
                map.put(sum, i);
            }
        }

        System.out.println("Length of longest subarray with sum 0: " + maxLen);
        // Subarray {-2, 2, -8, 1, 7} = 0 at indices 1..5 → length = 5
    }
}
```

---

# 3. TRIES

## 3.1 What is a Trie?

A **Trie** (pronounced "try") is a tree structure used to store **strings** (or sequences). Each node represents a single character. The root represents an empty string.

### Why use a Trie?
- **Fast prefix matching**: O(L) where L = length of the word (much faster than comparing against N strings)
- **Autocomplete**, **spell checker**, **IP routing**

### Node Structure
Each node has:
- An array (or HashMap) of children (one per possible character, e.g., 26 for lowercase letters)
- A boolean `isEndOfWord` flag indicating whether a word ends at this node

```java
// Basic Trie Node structure
class TrieNode {
    TrieNode[] children = new TrieNode[26];  // 'a' to 'z'
    boolean isEndOfWord = false;             // true if a word ends here
}
```

---

## 3.2 Trie: Insert, Search, StartsWith

```java
public class TrieDemo {

    // ---- TrieNode class ----
    static class TrieNode {
        TrieNode[] children = new TrieNode[26];  // each slot = one letter
        boolean isEndOfWord = false;             // marks end of a complete word
    }

    // ---- Trie class ----
    static class Trie {
        private TrieNode root;

        public Trie() {
            root = new TrieNode();  // root node represents empty string
        }

        // ---- INSERT a word into the trie ----
        public void insert(String word) {
            TrieNode current = root;

            for (int i = 0; i < word.length(); i++) {
                char ch = word.charAt(i);
                int idx = ch - 'a';  // convert 'a' → 0, 'b' → 1, ..., 'z' → 25

                // if child doesn't exist, create it
                if (current.children[idx] == null) {
                    current.children[idx] = new TrieNode();
                }

                current = current.children[idx];  // move to child node
            }

            current.isEndOfWord = true;  // mark end of word
        }

        // ---- SEARCH for a complete word ----
        public boolean search(String word) {
            TrieNode current = root;

            for (int i = 0; i < word.length(); i++) {
                char ch = word.charAt(i);
                int idx = ch - 'a';

                if (current.children[idx] == null) {
                    return false;   // character missing → word not present
                }

                current = current.children[idx];
            }

            // Word exists only if we ended at a node marked isEndOfWord
            return current.isEndOfWord;
        }

        // ---- STARTSWITH: check if any word has given prefix ----
        public boolean startsWith(String prefix) {
            TrieNode current = root;

            for (int i = 0; i < prefix.length(); i++) {
                char ch = prefix.charAt(i);
                int idx = ch - 'a';

                if (current.children[idx] == null) {
                    return false;   // prefix path doesn't exist
                }

                current = current.children[idx];
            }

            return true;  // we successfully traversed the entire prefix
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        Trie trie = new Trie();

        // Insert words
        trie.insert("apple");
        trie.insert("app");
        trie.insert("apricot");
        trie.insert("bat");
        trie.insert("ball");

        System.out.println("=== Trie Demo ===");

        // Search complete words
        System.out.println("Search 'apple': " + trie.search("apple"));     // true
        System.out.println("Search 'app': " + trie.search("app"));         // true
        System.out.println("Search 'appl': " + trie.search("appl"));       // false (partial word)
        System.out.println("Search 'bat': " + trie.search("bat"));         // true
        System.out.println("Search 'cat': " + trie.search("cat"));         // false

        // Check prefixes
        System.out.println("StartsWith 'ap': " + trie.startsWith("ap"));   // true
        System.out.println("StartsWith 'app': " + trie.startsWith("app")); // true
        System.out.println("StartsWith 'ba': " + trie.startsWith("ba"));   // true
        System.out.println("StartsWith 'ca': " + trie.startsWith("ca"));   // false
    }
}
```

---

## 3.3 Word Break Problem

**Problem**: Given a string and a dictionary of words, determine if the string can be segmented into dictionary words.

**Approach**: Use a Trie to store dictionary. Use DP (or recursive search) to check if string can be split.

```java
import java.util.HashSet;

public class WordBreak {

    // ---- TrieNode (same as before) ----
    static class TrieNode {
        TrieNode[] children = new TrieNode[26];
        boolean isEndOfWord = false;
    }

    // ---- Insert a word into Trie ----
    static void insert(TrieNode root, String word) {
        TrieNode curr = root;
        for (int i = 0; i < word.length(); i++) {
            int idx = word.charAt(i) - 'a';
            if (curr.children[idx] == null) curr.children[idx] = new TrieNode();
            curr = curr.children[idx];
        }
        curr.isEndOfWord = true;
    }

    // ---- Check if word exists in Trie ----
    static boolean search(TrieNode root, String word) {
        TrieNode curr = root;
        for (int i = 0; i < word.length(); i++) {
            int idx = word.charAt(i) - 'a';
            if (curr.children[idx] == null) return false;
            curr = curr.children[idx];
        }
        return curr.isEndOfWord;
    }

    // ---- Word Break using recursion + memoization ----
    static boolean canBreak(String str, TrieNode root, int start, Boolean[] memo) {
        // Base: if we've reached past the end of string, success
        if (start == str.length()) {
            return true;
        }

        // Check memo
        if (memo[start] != null) return memo[start];

        // Try all possible end positions from start
        for (int end = start + 1; end <= str.length(); end++) {
            String prefix = str.substring(start, end);

            // If prefix is in dictionary AND the rest is breakable, success
            if (search(root, prefix) && canBreak(str, root, end, memo)) {
                memo[start] = true;
                return true;
            }
        }

        memo[start] = false;
        return false;
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        String[] dictionary = {"i", "like", "sam", "samsung", "mobile", "ice"};
        String target = "ilikesamsung";

        // Build Trie from dictionary
        TrieNode root = new TrieNode();
        for (String word : dictionary) {
            insert(root, word);
        }

        Boolean[] memo = new Boolean[target.length()];  // null = uncomputed
        boolean result = canBreak(target, root, 0, memo);

        System.out.println("Can \"" + target + "\" be broken? " + result);
        // "i like samsung" → true
    }
}
```

---

## 3.4 Prefix and Suffix Matching

**Problem**: Find all words in a trie that have a given prefix (autocomplete).

```java
import java.util.ArrayList;
import java.util.List;

public class PrefixMatching {

    static class TrieNode {
        TrieNode[] children = new TrieNode[26];
        boolean isEndOfWord = false;
    }

    static class Trie {
        TrieNode root = new TrieNode();

        public void insert(String word) {
            TrieNode curr = root;
            for (int i = 0; i < word.length(); i++) {
                int idx = word.charAt(i) - 'a';
                if (curr.children[idx] == null) curr.children[idx] = new TrieNode();
                curr = curr.children[idx];
            }
            curr.isEndOfWord = true;
        }

        // Find the node corresponding to the end of the prefix
        private TrieNode findNode(String prefix) {
            TrieNode curr = root;
            for (int i = 0; i < prefix.length(); i++) {
                int idx = prefix.charAt(i) - 'a';
                if (curr.children[idx] == null) return null;  // prefix not found
                curr = curr.children[idx];
            }
            return curr;  // node at end of prefix
        }

        // Get all words with given prefix
        public List<String> autocomplete(String prefix) {
            List<String> result = new ArrayList<>();
            TrieNode node = findNode(prefix);
            if (node == null) return result;  // no words with this prefix

            // DFS from this node to collect all complete words
            collectWords(node, prefix, result);
            return result;
        }

        // Recursively collect words (DFS)
        private void collectWords(TrieNode node, String currentPrefix, List<String> result) {
            if (node.isEndOfWord) {
                result.add(currentPrefix);  // we've built a complete word
            }
            // Explore all 26 children
            for (int i = 0; i < 26; i++) {
                if (node.children[i] != null) {
                    char ch = (char) ('a' + i);
                    collectWords(node.children[i], currentPrefix + ch, result);
                }
            }
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        Trie trie = new Trie();
        trie.insert("apple");
        trie.insert("app");
        trie.insert("apricot");
        trie.insert("bat");
        trie.insert("ball");
        trie.insert("balloon");
        trie.insert("banana");

        System.out.println("Autocomplete for 'ap': " + trie.autocomplete("ap"));
        // [app, apple, apricot]

        System.out.println("Autocomplete for 'bal': " + trie.autocomplete("bal"));
        // [ball, balloon]

        System.out.println("Autocomplete for 'cat': " + trie.autocomplete("cat"));
        // [] (empty)
    }
}
```

---

## 3.5 Unique Substrings Count

**Problem**: Count the total number of distinct substrings of a given string.

**Approach**: Insert every suffix of the string into a Trie. The total number of nodes created (minus the root) = number of unique substrings.

```java
public class UniqueSubstrings {

    static class TrieNode {
        TrieNode[] children = new TrieNode[26];
        // isEndOfWord is NOT needed here — we count nodes, not words
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        String str = "ababa";

        TrieNode root = new TrieNode();
        int uniqueCount = 0;

        // Insert every suffix of the string into the trie
        // For "ababa", suffixes: "ababa", "baba", "aba", "ba", "a"
        for (int i = 0; i < str.length(); i++) {
            String suffix = str.substring(i);   // get suffix starting at i
            TrieNode current = root;

            for (int j = 0; j < suffix.length(); j++) {
                char ch = suffix.charAt(j);
                int idx = ch - 'a';

                if (current.children[idx] == null) {
                    current.children[idx] = new TrieNode();
                    uniqueCount++;  // each new node = one new unique substring
                }

                current = current.children[idx];
            }
        }

        System.out.println("String: " + str);
        System.out.println("Number of unique substrings: " + uniqueCount);
        // "ababa" has 10 unique substrings (the formula: n*(n+1)/2 - dupes)
    }
}
```

---

## 3.6 Longest Word with All Prefixes

**Problem**: Find the longest word in a dictionary such that **every prefix** of that word is also in the dictionary.

**Approach**: Insert all words into a Trie. Mark each node when it represents an end of a word. Then DFS to find the deepest path where every node along the path is a valid word.

```java
public class LongestWordAllPrefixes {

    static class TrieNode {
        TrieNode[] children = new TrieNode[26];
        boolean isEndOfWord = false;
    }

    static class Trie {
        TrieNode root = new TrieNode();

        public void insert(String word) {
            TrieNode curr = root;
            for (int i = 0; i < word.length(); i++) {
                int idx = word.charAt(i) - 'a';
                if (curr.children[idx] == null) curr.children[idx] = new TrieNode();
                curr = curr.children[idx];
            }
            curr.isEndOfWord = true;
        }

        public String longestWordWithAllPrefixes() {
            // Start DFS from root; currentPrefix = empty string
            return dfs(root, "");
        }

        private String dfs(TrieNode node, String currentPrefix) {
            String best = currentPrefix;  // start with current word

            for (int i = 0; i < 26; i++) {
                if (node.children[i] != null && node.children[i].isEndOfWord) {
                    // Only explore if this child represents a valid word
                    char ch = (char) ('a' + i);
                    String candidate = dfs(node.children[i], currentPrefix + ch);

                    // Choose the better candidate:
                    // 1. longer length wins
                    // 2. if same length, lexicographically smaller wins
                    if (candidate.length() > best.length() ||
                        (candidate.length() == best.length() && candidate.compareTo(best) < 0)) {
                        best = candidate;
                    }
                }
            }

            return best;
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        String[] words = {"a", "banana", "app", "appl", "ap", "apply", "apple"};

        Trie trie = new Trie();
        for (String word : words) {
            trie.insert(word);
        }

        String result = trie.longestWordWithAllPrefixes();

        System.out.println("Longest word where every prefix is in dictionary: " + result);
        // "apple" — because "a", "ap", "app", "appl", "apple" are all in dictionary
        // "appl" is not valid here... wait: check words: "a", "ap", "app", "appl", "apple"
        // All are present? "appl" is in words → yes. So "apply" candidate?
        // "apply" prefixes: a, ap, app, appl → all present. But "apply" itself is in words too.
        // So result could be "apply" or "apple". Both have length 5. "apple" < "apply" lexicographically.
    }
}
```

---

# 4. GRAPHS

## 4.1 What is a Graph?

A **graph** is a set of **vertices** (nodes) connected by **edges**. 

- **Directed vs Undirected**: Edges have direction or not.
- **Weighted vs Unweighted**: Edges have weights (costs) or not.
- **Cyclic vs Acyclic**: Contains cycles or not (a **tree** is an acyclic graph).
- **Connected vs Disconnected**: Every vertex reachable from every other or not.

### Graph Representations

#### Adjacency Matrix
- A 2D array `adj[][]` where `adj[i][j] = 1` (or weight) if there's an edge from `i` to `j`.
- **Pro**: O(1) edge lookup. **Con**: O(V²) memory.

#### Adjacency List
- An array of lists. `adj[i]` contains all neighbors of vertex `i`.
- **Pro**: O(V + E) memory. **Con**: O(degree) edge lookup.

We'll use **Adjacency List** for most problems since it's efficient and common.

---

## 4.2 Node Class, Edge Class, Creating Graph with Adjacency List

```java
import java.util.ArrayList;

public class GraphRepresentation {

    // ---- Edge class: represents a single edge ----
    static class Edge {
        int src;     // source vertex
        int dest;    // destination vertex
        int weight;  // weight (1 for unweighted graphs)

        Edge(int src, int dest, int weight) {
            this.src = src;
            this.dest = dest;
            this.weight = weight;
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {

        int V = 5;  // number of vertices

        // Create graph as adjacency list: an array of ArrayList<Edge>
        // graph[0] = list of edges from vertex 0
        // graph[1] = list of edges from vertex 1, etc.
        ArrayList<Edge>[] graph = new ArrayList[V];

        // Initialize each ArrayList (otherwise they're null)
        for (int i = 0; i < V; i++) {
            graph[i] = new ArrayList<>();
        }

        // --- Add edges for an undirected weighted graph ---
        // Graph:
        //     0 --- 1
        //     |     |
        //     2 --- 3
        //           |
        //           4

        // Vertex 0 connections
        graph[0].add(new Edge(0, 1, 5));   // edge 0→1 weight 5
        graph[0].add(new Edge(0, 2, 3));   // edge 0→2 weight 3

        // Vertex 1 connections
        graph[1].add(new Edge(1, 0, 5));   // edge 1→0 weight 5 (undirected)
        graph[1].add(new Edge(1, 3, 2));   // edge 1→3 weight 2

        // Vertex 2 connections
        graph[2].add(new Edge(2, 0, 3));   // edge 2→0 weight 3
        graph[2].add(new Edge(2, 3, 1));   // edge 2→3 weight 1

        // Vertex 3 connections
        graph[3].add(new Edge(3, 1, 2));   // edge 3→1 weight 2
        graph[3].add(new Edge(3, 2, 1));   // edge 3→2 weight 1
        graph[3].add(new Edge(3, 4, 7));   // edge 3→4 weight 7

        // Vertex 4 connections
        graph[4].add(new Edge(4, 3, 7));   // edge 4→3 weight 7

        // ---- Print all neighbors of vertex 3 ----
        System.out.println("Neighbors of vertex 3:");
        for (Edge e : graph[3]) {
            System.out.println("  → " + e.dest + " (weight: " + e.weight + ")");
        }
        // Output: → 1 (weight: 2), → 2 (weight: 1), → 4 (weight: 7)
    }
}
```

---

## 4.3 BFS Traversal (Breadth-First Search)

**BFS**: Visit neighbors level by level (use a queue). Like a wave spreading outward.

**Use cases**: Shortest path (unweighted), level-order traversal.

```java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Queue;

public class BFSDemo {

    static class Edge {
        int src, dest, weight;
        Edge(int s, int d, int w) { src = s; dest = d; weight = w; }
    }

    // ---- BFS from a source vertex ----
    public static void bfs(ArrayList<Edge>[] graph, int startVertex) {
        boolean[] visited = new boolean[graph.length];  // track visited vertices
        Queue<Integer> queue = new LinkedList<>();      // queue for BFS

        queue.add(startVertex);     // start from this vertex
        visited[startVertex] = true;

        System.out.print("BFS traversal: ");

        while (!queue.isEmpty()) {
            int current = queue.poll();   // remove front of queue
            System.out.print(current + " ");

            // Visit all unvisited neighbors
            for (Edge e : graph[current]) {
                if (!visited[e.dest]) {
                    queue.add(e.dest);           // add neighbor to queue
                    visited[e.dest] = true;      // mark as visited
                }
            }
        }
        System.out.println();
    }

    // ---- BFS for disconnected graphs (visit all components) ----
    public static void bfsDisconnected(ArrayList<Edge>[] graph) {
        boolean[] visited = new boolean[graph.length];

        System.out.print("BFS (full graph): ");
        for (int start = 0; start < graph.length; start++) {
            if (!visited[start]) {
                Queue<Integer> queue = new LinkedList<>();
                queue.add(start);
                visited[start] = true;

                while (!queue.isEmpty()) {
                    int curr = queue.poll();
                    System.out.print(curr + " ");

                    for (Edge e : graph[curr]) {
                        if (!visited[e.dest]) {
                            queue.add(e.dest);
                            visited[e.dest] = true;
                        }
                    }
                }
            }
        }
        System.out.println();
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 7;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // Build graph (undirected)
        // 0---1---2---3
        //     |   |
        //     4---5---6
        graph[0].add(new Edge(0, 1, 1));
        graph[1].add(new Edge(1, 0, 1)); graph[1].add(new Edge(1, 2, 1)); graph[1].add(new Edge(1, 4, 1));
        graph[2].add(new Edge(2, 1, 1)); graph[2].add(new Edge(2, 3, 1)); graph[2].add(new Edge(2, 5, 1));
        graph[3].add(new Edge(3, 2, 1));
        graph[4].add(new Edge(4, 1, 1)); graph[4].add(new Edge(4, 5, 1));
        graph[5].add(new Edge(5, 2, 1)); graph[5].add(new Edge(5, 4, 1)); graph[5].add(new Edge(5, 6, 1));
        graph[6].add(new Edge(6, 5, 1));

        bfs(graph, 0);  // BFS starting from vertex 0
    }
}
```

---

## 4.4 DFS Traversal (Depth-First Search)

**DFS**: Explore as far as possible along each branch before backtracking (use recursion/stack).

**Use cases**: Path finding, topological sort, cycle detection.

```java
import java.util.ArrayList;

public class DFSDemo {

    static class Edge {
        int src, dest, weight;
        Edge(int s, int d, int w) { src = s; dest = d; weight = w; }
    }

    // ---- DFS using recursion ----
    public static void dfs(ArrayList<Edge>[] graph, int current, boolean[] visited) {
        System.out.print(current + " ");    // visit current vertex
        visited[current] = true;             // mark visited

        // Recursively visit all unvisited neighbors
        for (Edge e : graph[current]) {
            if (!visited[e.dest]) {
                dfs(graph, e.dest, visited);
            }
        }
    }

    // ---- DFS for disconnected graphs ----
    public static void dfsFull(ArrayList<Edge>[] graph) {
        boolean[] visited = new boolean[graph.length];

        System.out.print("DFS (full graph): ");
        for (int i = 0; i < graph.length; i++) {
            if (!visited[i]) {
                dfs(graph, i, visited);
            }
        }
        System.out.println();
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 7;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        graph[0].add(new Edge(0, 1, 1));
        graph[1].add(new Edge(1, 0, 1)); graph[1].add(new Edge(1, 2, 1)); graph[1].add(new Edge(1, 4, 1));
        graph[2].add(new Edge(2, 1, 1)); graph[2].add(new Edge(2, 3, 1)); graph[2].add(new Edge(2, 5, 1));
        graph[3].add(new Edge(3, 2, 1));
        graph[4].add(new Edge(4, 1, 1)); graph[4].add(new Edge(4, 5, 1));
        graph[5].add(new Edge(5, 2, 1)); graph[5].add(new Edge(5, 4, 1)); graph[5].add(new Edge(5, 6, 1));
        graph[6].add(new Edge(6, 5, 1));

        System.out.print("DFS starting from 0: ");
        boolean[] visited = new boolean[V];
        dfs(graph, 0, visited);
        System.out.println();
    }
}
```

---

## 4.5 Detect Cycle in Undirected Graph

**Approach**: DFS with parent tracking. If we visit a neighbor that's already visited AND it's NOT the parent, we found a cycle.

```java
import java.util.ArrayList;

public class CycleUndirected {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    // ---- Cycle detection in undirected graph ----
    public static boolean hasCycle(ArrayList<Edge>[] graph) {
        boolean[] visited = new boolean[graph.length];

        // Check every component (disconnected graph might have cycle in one component)
        for (int start = 0; start < graph.length; start++) {
            if (!visited[start]) {
                if (dfsCycleDetect(graph, start, -1, visited)) {
                    return true;  // cycle found
                }
            }
        }
        return false;
    }

    // DFS with parent tracking
    private static boolean dfsCycleDetect(ArrayList<Edge>[] graph, int curr, int parent, boolean[] visited) {
        visited[curr] = true;

        for (Edge e : graph[curr]) {
            int neighbor = e.dest;

            if (!visited[neighbor]) {
                // Recursively check neighbor; if it detects a cycle, propagate true
                if (dfsCycleDetect(graph, neighbor, curr, visited)) {
                    return true;
                }
            } else if (neighbor != parent) {
                // Visited neighbor that is NOT parent → cycle exists
                return true;
            }
        }

        return false;  // no cycle in this component
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        // Graph WITH a cycle: 0-1-2-3-0 (square)
        int V = 4;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();
        graph[0].add(new Edge(0, 1)); graph[0].add(new Edge(0, 3));
        graph[1].add(new Edge(1, 0)); graph[1].add(new Edge(1, 2));
        graph[2].add(new Edge(2, 1)); graph[2].add(new Edge(2, 3));
        graph[3].add(new Edge(3, 0)); graph[3].add(new Edge(3, 2));

        System.out.println("Graph has cycle? " + hasCycle(graph));  // true

        // Graph WITHOUT a cycle: tree 0-1-2-3
        int V2 = 4;
        ArrayList<Edge>[] graph2 = new ArrayList[V2];
        for (int i = 0; i < V2; i++) graph2[i] = new ArrayList<>();
        graph2[0].add(new Edge(0, 1));
        graph2[1].add(new Edge(1, 0)); graph2[1].add(new Edge(1, 2));
        graph2[2].add(new Edge(2, 1)); graph2[2].add(new Edge(2, 3));
        graph2[3].add(new Edge(3, 2));

        System.out.println("Tree has cycle? " + hasCycle(graph2));  // false
    }
}
```

---

## 4.6 Detect Cycle in Directed Graph

**Approach**: DFS with two arrays:
- `visited[]` — visited in this traversal
- `stackTrace[]` — visited on the current recursion stack (ancestors in DFS tree)

If we visit a node already in the recursion stack → back edge → cycle.

```java
import java.util.ArrayList;

public class CycleDirected {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    public static boolean hasCycle(ArrayList<Edge>[] graph) {
        boolean[] visited = new boolean[graph.length];
        boolean[] stackTrace = new boolean[graph.length];  // recursion stack

        for (int start = 0; start < graph.length; start++) {
            if (!visited[start]) {
                if (dfsCycleDetect(graph, start, visited, stackTrace)) {
                    return true;
                }
            }
        }
        return false;
    }

    private static boolean dfsCycleDetect(ArrayList<Edge>[] graph, int curr,
                                           boolean[] visited, boolean[] stackTrace) {
        visited[curr] = true;
        stackTrace[curr] = true;  // mark as in current recursion stack

        for (Edge e : graph[curr]) {
            int neighbor = e.dest;

            if (!visited[neighbor]) {
                if (dfsCycleDetect(graph, neighbor, visited, stackTrace)) {
                    return true;
                }
            } else if (stackTrace[neighbor]) {
                // Found a back edge: neighbor is an ancestor in DFS tree → cycle
                return true;
            }
        }

        stackTrace[curr] = false;  // remove from recursion stack as we backtrack
        return false;
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        // Directed graph WITH cycle: 0 → 1 → 2 → 0
        int V = 3;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();
        graph[0].add(new Edge(0, 1));
        graph[1].add(new Edge(1, 2));
        graph[2].add(new Edge(2, 0));  // back to 0

        System.out.println("Cyclic graph has cycle? " + hasCycle(graph));  // true

        // Directed graph WITHOUT cycle: 0 → 1 → 2
        int V2 = 3;
        ArrayList<Edge>[] graph2 = new ArrayList[V2];
        for (int i = 0; i < V2; i++) graph2[i] = new ArrayList<>();
        graph2[0].add(new Edge(0, 1));
        graph2[1].add(new Edge(1, 2));

        System.out.println("DAG has cycle? " + hasCycle(graph2));  // false
    }
}
```

---

## 4.7 Topological Sorting

**Topological order**: In a **Directed Acyclic Graph (DAG)**, an ordering of vertices such that for every directed edge `u → v`, `u` comes before `v`.

### Approach 1: DFS-based
Do DFS; after visiting all descendants, push current node to a stack. Pop stack for topological order.

### Approach 2: Kahn's Algorithm (BFS-based)
Count in-degree of each node. Repeatedly remove nodes with in-degree 0.

```java
import java.util.ArrayList;
import java.util.Stack;
import java.util.LinkedList;
import java.util.Queue;

public class TopologicalSort {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    // ---- DFS-based Topological Sort ----
    public static void topoSortDFS(ArrayList<Edge>[] graph) {
        boolean[] visited = new boolean[graph.length];
        Stack<Integer> stack = new Stack<>();

        for (int i = 0; i < graph.length; i++) {
            if (!visited[i]) {
                topoDFS(graph, i, visited, stack);
            }
        }

        System.out.print("Topological Order (DFS): ");
        while (!stack.isEmpty()) {
            System.out.print(stack.pop() + " ");
        }
        System.out.println();
    }

    private static void topoDFS(ArrayList<Edge>[] graph, int curr, boolean[] visited, Stack<Integer> stack) {
        visited[curr] = true;

        for (Edge e : graph[curr]) {
            if (!visited[e.dest]) {
                topoDFS(graph, e.dest, visited, stack);
            }
        }

        // After all descendants are processed, push current to stack
        stack.push(curr);
    }

    // ---- Kahn's Algorithm (BFS-based) ----
    public static void topoSortKahn(ArrayList<Edge>[] graph) {
        int V = graph.length;

        // Step 1: compute in-degree of each vertex
        int[] inDegree = new int[V];
        for (int i = 0; i < V; i++) {
            for (Edge e : graph[i]) {
                inDegree[e.dest]++;  // e.dest has one more incoming edge
            }
        }

        // Step 2: queue all vertices with in-degree 0
        Queue<Integer> queue = new LinkedList<>();
        for (int i = 0; i < V; i++) {
            if (inDegree[i] == 0) {
                queue.add(i);
            }
        }

        System.out.print("Topological Order (Kahn's): ");
        while (!queue.isEmpty()) {
            int curr = queue.poll();
            System.out.print(curr + " ");

            // Reduce in-degree of all neighbors by 1
            for (Edge e : graph[curr]) {
                inDegree[e.dest]--;
                // If neighbor now has in-degree 0, add to queue
                if (inDegree[e.dest] == 0) {
                    queue.add(e.dest);
                }
            }
        }

        // If not all vertices were printed, the graph has a cycle
        System.out.println();
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 6;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // DAG: 5→0, 5→2, 4→0, 4→1, 2→3, 3→1
        graph[5].add(new Edge(5, 0));
        graph[5].add(new Edge(5, 2));
        graph[4].add(new Edge(4, 0));
        graph[4].add(new Edge(4, 1));
        graph[2].add(new Edge(2, 3));
        graph[3].add(new Edge(3, 1));

        topoSortDFS(graph);
        topoSortKahn(graph);
        // Valid orders: 4 5 0 2 3 1  or  5 4 2 3 0 1  (among others)
    }
}
```

---

## 4.8 Dijkstra's Algorithm (Shortest Path from Source)

**Problem**: Find the shortest path from a source vertex to all other vertices in a **weighted graph** (non-negative weights only).

**Approach**: Use a **PriorityQueue** (min-heap) storing `[distance, vertex]`. Always process the closest unvisited vertex.

```java
import java.util.ArrayList;
import java.util.PriorityQueue;
import java.util.Arrays;

public class DijkstraDemo {

    static class Edge {
        int src, dest, weight;
        Edge(int s, int d, int w) { src = s; dest = d; weight = w; }
    }

    // Helper class for PriorityQueue: pairs of (vertex, distance from source)
    static class Pair implements Comparable<Pair> {
        int vertex;
        int distance;  // shortest distance from source to this vertex (known so far)

        Pair(int v, int d) { vertex = v; distance = d; }

        @Override
        public int compareTo(Pair other) {
            return this.distance - other.distance;  // smaller distance = higher priority
        }
    }

    public static void dijkstra(ArrayList<Edge>[] graph, int source) {
        int V = graph.length;
        int[] dist = new int[V];       // dist[i] = shortest distance from source to i
        Arrays.fill(dist, Integer.MAX_VALUE);  // initialize all distances to "infinity"
        dist[source] = 0;                     // distance from source to itself is 0

        boolean[] visited = new boolean[V];

        PriorityQueue<Pair> pq = new PriorityQueue<>();
        pq.add(new Pair(source, 0));  // start from source

        while (!pq.isEmpty()) {
            Pair current = pq.poll();
            int currVertex = current.vertex;

            if (visited[currVertex]) continue;  // already processed
            visited[currVertex] = true;

            // Relax all edges from current vertex
            for (Edge e : graph[currVertex]) {
                int neighbor = e.dest;
                int edgeWeight = e.weight;

                // If we found a shorter path to neighbor through currVertex
                if (!visited[neighbor] && dist[currVertex] + edgeWeight < dist[neighbor]) {
                    dist[neighbor] = dist[currVertex] + edgeWeight;  // update distance
                    pq.add(new Pair(neighbor, dist[neighbor]));      // add to queue with new distance
                }
            }
        }

        // Print results
        System.out.println("Shortest distances from source " + source + ":");
        for (int i = 0; i < V; i++) {
            System.out.println("  To vertex " + i + " → " + dist[i] + (dist[i] == Integer.MAX_VALUE ? " (unreachable)" : ""));
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 6;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // Graph (directed, non-negative weights):
        // 0 → 1 (2), 0 → 2 (4)
        // 1 → 2 (1), 1 → 3 (7)
        // 2 → 4 (3)
        // 3 → 5 (1)
        // 4 → 3 (2), 4 → 5 (5)
        graph[0].add(new Edge(0, 1, 2));  graph[0].add(new Edge(0, 2, 4));
        graph[1].add(new Edge(1, 2, 1));  graph[1].add(new Edge(1, 3, 7));
        graph[2].add(new Edge(2, 4, 3));
        graph[3].add(new Edge(3, 5, 1));
        graph[4].add(new Edge(4, 3, 2));  graph[4].add(new Edge(4, 5, 5));

        dijkstra(graph, 0);
        // Expected: 0→0=0, 0→1=2, 0→2=3, 0→3=8, 0→4=6, 0→5=9
    }
}
```

---

## 4.9 Bellman Ford Algorithm

**Problem**: Find shortest paths from source. Unlike Dijkstra, it handles **negative weights** and detects **negative cycles**.

**Approach**: Relax all edges V-1 times. In each relaxation, if `dist[u] + weight(u→v) < dist[v]`, update `dist[v]`. After V-1 passes, one more pass to detect negative cycles.

**Why V-1?** The longest possible shortest path can have at most V-1 edges (no cycles in shortest path).

```java
import java.util.ArrayList;
import java.util.Arrays;

public class BellmanFordDemo {

    static class Edge {
        int src, dest, weight;
        Edge(int s, int d, int w) { src = s; dest = d; weight = w; }
    }

    public static void bellmanFord(ArrayList<Edge>[] graph, int source) {
        int V = graph.length;

        int[] dist = new int[V];
        Arrays.fill(dist, Integer.MAX_VALUE);
        dist[source] = 0;

        // ---- Relax all edges V-1 times ----
        for (int i = 0; i < V - 1; i++) {
            // Traverse all edges
            for (int u = 0; u < V; u++) {
                for (Edge e : graph[u]) {
                    // If dist[u] is known and dist[u] + weight < dist[v], update
                    if (dist[u] != Integer.MAX_VALUE && dist[u] + e.weight < dist[e.dest]) {
                        dist[e.dest] = dist[u] + e.weight;
                    }
                }
            }
        }

        // ---- Check for negative weight cycles ----
        boolean hasNegativeCycle = false;
        for (int u = 0; u < V; u++) {
            for (Edge e : graph[u]) {
                if (dist[u] != Integer.MAX_VALUE && dist[u] + e.weight < dist[e.dest]) {
                    hasNegativeCycle = true;
                    break;
                }
            }
            if (hasNegativeCycle) break;
        }

        if (hasNegativeCycle) {
            System.out.println("Graph contains a negative weight cycle!");
        } else {
            System.out.println("Shortest distances from source " + source + ":");
            for (int i = 0; i < V; i++) {
                System.out.println("  To " + i + " → " + (dist[i] == Integer.MAX_VALUE ? "INF" : dist[i]));
            }
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 5;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // Graph with negative weights (no negative cycle):
        // 0 → 1 (6), 0 → 2 (7)
        // 1 → 2 (8), 1 → 3 (5), 1 → 4 (-4)
        // 2 → 3 (-3), 2 → 4 (9)
        // 3 → 1 (-2)
        // 4 → 0 (2), 4 → 3 (7)
        graph[0].add(new Edge(0, 1, 6));    graph[0].add(new Edge(0, 2, 7));
        graph[1].add(new Edge(1, 2, 8));    graph[1].add(new Edge(1, 3, 5));  graph[1].add(new Edge(1, 4, -4));
        graph[2].add(new Edge(2, 3, -3));   graph[2].add(new Edge(2, 4, 9));
        graph[3].add(new Edge(3, 1, -2));
        graph[4].add(new Edge(4, 0, 2));    graph[4].add(new Edge(4, 3, 7));

        bellmanFord(graph, 0);
    }
}
```

---

## 4.10 Prim's Algorithm (Minimum Spanning Tree)

**Problem**: Find a **Minimum Spanning Tree (MST)** — a subset of edges that connects all vertices with minimum total weight (no cycles).

**Approach**: Greedy. Start from any vertex. Always pick the cheapest edge connecting the visited set to an unvisited vertex.

```java
import java.util.ArrayList;
import java.util.PriorityQueue;
import java.util.Arrays;

public class PrimsAlgorithm {

    static class Edge {
        int src, dest, weight;
        Edge(int s, int d, int w) { src = s; dest = d; weight = w; }
    }

    static class Pair implements Comparable<Pair> {
        int vertex;
        int cost;  // minimum cost to connect this vertex to the MST

        Pair(int v, int c) { vertex = v; cost = c; }

        @Override
        public int compareTo(Pair other) {
            return this.cost - other.cost;  // min-heap by cost
        }
    }

    public static void primsMST(ArrayList<Edge>[] graph) {
        int V = graph.length;
        boolean[] visited = new boolean[V];
        int[] parent = new int[V];     // to reconstruct the MST
        int[] cost = new int[V];       // minimum cost to connect each vertex
        Arrays.fill(cost, Integer.MAX_VALUE);

        PriorityQueue<Pair> pq = new PriorityQueue<>();
        cost[0] = 0;                    // start from vertex 0
        parent[0] = -1;                 // root has no parent
        pq.add(new Pair(0, 0));

        int totalMSTCost = 0;

        while (!pq.isEmpty()) {
            Pair current = pq.poll();
            int u = current.vertex;

            if (visited[u]) continue;   // already included in MST
            visited[u] = true;
            totalMSTCost += current.cost;

            // Explore neighbors: if neighbor not visited and edge weight is cheaper
            for (Edge e : graph[u]) {
                int v = e.dest;
                if (!visited[v] && e.weight < cost[v]) {
                    cost[v] = e.weight;        // update minimum cost to connect v
                    parent[v] = u;             // track parent in MST
                    pq.add(new Pair(v, e.weight));
                }
            }
        }

        // Print MST
        System.out.println("Minimum Spanning Tree (total cost: " + totalMSTCost + "):");
        for (int i = 1; i < V; i++) {  // skip root (0)
            System.out.println("  Edge: " + parent[i] + " — " + i + "  (cost: " + cost[i] + ")");
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 5;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // Undirected weighted graph
        // 0---1 (2)  0---3 (6)
        // 1---2 (3)  1---3 (8)  1---4 (5)
        // 2---4 (7)
        // 3---4 (9)
        graph[0].add(new Edge(0, 1, 2));  graph[0].add(new Edge(0, 3, 6));
        graph[1].add(new Edge(1, 0, 2));  graph[1].add(new Edge(1, 2, 3));  graph[1].add(new Edge(1, 3, 8));  graph[1].add(new Edge(1, 4, 5));
        graph[2].add(new Edge(2, 1, 3));  graph[2].add(new Edge(2, 4, 7));
        graph[3].add(new Edge(3, 0, 6));  graph[3].add(new Edge(3, 1, 8));  graph[3].add(new Edge(3, 4, 9));
        graph[4].add(new Edge(4, 1, 5));  graph[4].add(new Edge(4, 2, 7));  graph[4].add(new Edge(4, 3, 9));

        primsMST(graph);
        // Expected MST cost: 2 + 3 + 5 + 6 = 16
    }
}
```

---

## 4.11 Kruskal's Algorithm (MST with Disjoint Set Union / Union-Find)

**Approach**: Sort all edges by weight. Pick the smallest edge that doesn't form a cycle. Use **Union-Find** to detect cycles efficiently.

```java
import java.util.ArrayList;
import java.util.Collections;

public class KruskalsAlgorithm {

    static class Edge implements Comparable<Edge> {
        int src, dest, weight;
        Edge(int s, int d, int w) { src = s; dest = d; weight = w; }

        @Override
        public int compareTo(Edge other) {
            return this.weight - other.weight;  // sort by weight ascending
        }
    }

    // ---- Disjoint Set Union (Union-Find) ----
    static class DisjointSet {
        int[] parent;
        int[] rank;

        DisjointSet(int n) {
            parent = new int[n];
            rank = new int[n];
            for (int i = 0; i < n; i++) parent[i] = i;  // each node is its own parent
        }

        // Find with path compression
        int find(int x) {
            if (parent[x] != x) {
                parent[x] = find(parent[x]);  // compress: point directly to root
            }
            return parent[x];
        }

        // Union by rank
        void union(int x, int y) {
            int rootX = find(x);
            int rootY = find(y);
            if (rootX == rootY) return;

            if (rank[rootX] < rank[rootY]) {
                parent[rootX] = rootY;
            } else if (rank[rootX] > rank[rootY]) {
                parent[rootY] = rootX;
            } else {
                parent[rootY] = rootX;
                rank[rootX]++;
            }
        }
    }

    public static void kruskalMST(ArrayList<Edge> edges, int V) {
        // Sort all edges by weight
        Collections.sort(edges);

        DisjointSet ds = new DisjointSet(V);
        ArrayList<Edge> mst = new ArrayList<>();
        int totalCost = 0;

        for (Edge e : edges) {
            int rootSrc = ds.find(e.src);
            int rootDest = ds.find(e.dest);

            // If adding this edge doesn't create a cycle (different roots)
            if (rootSrc != rootDest) {
                mst.add(e);
                totalCost += e.weight;
                ds.union(e.src, e.dest);  // merge the two sets
            }
        }

        // Print MST
        System.out.println("MST (Kruskal's) — total cost: " + totalCost);
        for (Edge e : mst) {
            System.out.println("  Edge: " + e.src + " — " + e.dest + "  (weight: " + e.weight + ")");
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 5;
        ArrayList<Edge> edges = new ArrayList<>();

        // Same graph as Prim's example
        edges.add(new Edge(0, 1, 2));
        edges.add(new Edge(0, 3, 6));
        edges.add(new Edge(1, 2, 3));
        edges.add(new Edge(1, 3, 8));
        edges.add(new Edge(1, 4, 5));
        edges.add(new Edge(2, 4, 7));
        edges.add(new Edge(3, 4, 9));

        kruskalMST(edges, V);
        // Expected: edges (0-1:2), (1-2:3), (1-4:5), (0-3:6) → total = 16
    }
}
```

---

## 4.12 Kosaraju's Algorithm (Strongly Connected Components)

**Problem**: Find all **Strongly Connected Components (SCCs)** in a directed graph. An SCC is a maximal subgraph where every vertex is reachable from every other vertex.

**Approach** (3 steps of Kosaraju):
1. DFS to populate a stack (by finish time — like topological sort).
2. Reverse all edges (transpose graph).
3. Pop vertices from stack, DFS on reversed graph to find one SCC each.

```java
import java.util.ArrayList;
import java.util.Stack;

public class KosarajuAlgorithm {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    // Step 1: DFS to fill stack (vertices ordered by finish time)
    private static void dfsFillOrder(ArrayList<Edge>[] graph, int curr, boolean[] visited, Stack<Integer> stack) {
        visited[curr] = true;

        for (Edge e : graph[curr]) {
            if (!visited[e.dest]) {
                dfsFillOrder(graph, e.dest, visited, stack);
            }
        }

        stack.push(curr);  // all descendants processed, push to stack
    }

    // Step 2: Reverse all edges (create transpose graph)
    private static ArrayList<Edge>[] transpose(ArrayList<Edge>[] graph) {
        int V = graph.length;
        ArrayList<Edge>[] transposed = new ArrayList[V];
        for (int i = 0; i < V; i++) transposed[i] = new ArrayList<>();

        for (int i = 0; i < V; i++) {
            for (Edge e : graph[i]) {
                transposed[e.dest].add(new Edge(e.dest, e.src));  // reverse direction
            }
        }
        return transposed;
    }

    // Step 3: DFS on reversed graph to collect SCC
    private static void dfsOnReverse(ArrayList<Edge>[] graph, int curr, boolean[] visited, ArrayList<Integer> component) {
        visited[curr] = true;
        component.add(curr);

        for (Edge e : graph[curr]) {
            if (!visited[e.dest]) {
                dfsOnReverse(graph, e.dest, visited, component);
            }
        }
    }

    public static void kosarajuSCC(ArrayList<Edge>[] graph) {
        int V = graph.length;
        Stack<Integer> stack = new Stack<>();
        boolean[] visited = new boolean[V];

        // Step 1: DFS to fill stack
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                dfsFillOrder(graph, i, visited, stack);
            }
        }

        // Step 2: Create transpose graph
        ArrayList<Edge>[] reversedGraph = transpose(graph);

        // Step 3: Process vertices in stack order, each DFS gives one SCC
        visited = new boolean[V];  // reset visited
        System.out.println("Strongly Connected Components:");
        int componentNumber = 0;

        while (!stack.isEmpty()) {
            int vertex = stack.pop();

            if (!visited[vertex]) {
                ArrayList<Integer> component = new ArrayList<>();
                dfsOnReverse(reversedGraph, vertex, visited, component);

                System.out.print("  SCC " + (++componentNumber) + ": ");
                for (int v : component) {
                    System.out.print(v + " ");
                }
                System.out.println();
            }
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 5;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // Graph: 0→1→2→0  and  3→4  (2 SCCs)
        graph[0].add(new Edge(0, 1));
        graph[1].add(new Edge(1, 2));
        graph[2].add(new Edge(2, 0));
        graph[3].add(new Edge(3, 4));

        kosarajuSCC(graph);
        // SCC 1: {0, 1, 2}
        // SCC 2: {3, 4}
    }
}
```

---

## 4.13 Tarjan's Algorithm (Bridges in Graph — Articulation Points & Bridges)

**Problem**: Find **bridges** (critical edges whose removal disconnects the graph) and **articulation points** (vertices whose removal disconnects the graph).

**Approach**: DFS with:
- `disc[v]` = discovery time of vertex v
- `low[v]` = lowest discovery time reachable from v (including via back edges)
- If `low[neighbor] > disc[current]`, edge (current, neighbor) is a **bridge**.
- If `low[neighbor] >= disc[current]` and current is not root, current is an **articulation point**.

```java
import java.util.ArrayList;
import java.util.Arrays;

public class TarjanBridges {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    public static void findBridges(ArrayList<Edge>[] graph) {
        int V = graph.length;
        int[] disc = new int[V];     // discovery time
        int[] low = new int[V];      // lowest discovery time reachable
        boolean[] visited = new boolean[V];
        int[] time = new int[1];     // global timer (wrapped in array for mutability)

        System.out.println("Bridges in the graph:");

        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                dfsBridge(graph, i, -1, visited, disc, low, time);
            }
        }
    }

    private static void dfsBridge(ArrayList<Edge>[] graph, int curr, int parent,
                                   boolean[] visited, int[] disc, int[] low, int[] time) {
        visited[curr] = true;
        disc[curr] = low[curr] = ++time[0];  // set discovery time and initial low value

        for (Edge e : graph[curr]) {
            int neighbor = e.dest;

            if (neighbor == parent) continue;  // skip edge back to parent

            if (!visited[neighbor]) {
                // Recurse into neighbor
                dfsBridge(graph, neighbor, curr, visited, disc, low, time);

                // After returning, update low of current
                low[curr] = Math.min(low[curr], low[neighbor]);

                // Bridge condition: low[neighbor] > disc[curr]
                // No back edge from neighbor's subtree reaches curr or its ancestors
                if (low[neighbor] > disc[curr]) {
                    System.out.println("  Bridge: " + curr + " — " + neighbor);
                }
            } else {
                // Back edge: neighbor already visited (and not parent)
                low[curr] = Math.min(low[curr], disc[neighbor]);
            }
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 7;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // Graph with bridges:
        // 0-1   2-3-4-5
        // | |   |   |
        // 1-3   6   5
        graph[0].add(new Edge(0, 1)); graph[0].add(new Edge(0, 2));
        graph[1].add(new Edge(1, 0)); graph[1].add(new Edge(1, 3));
        graph[2].add(new Edge(2, 0)); graph[2].add(new Edge(2, 3)); graph[2].add(new Edge(2, 6));
        graph[3].add(new Edge(3, 1)); graph[3].add(new Edge(3, 2)); graph[3].add(new Edge(3, 4));
        graph[4].add(new Edge(4, 3)); graph[4].add(new Edge(4, 5));
        graph[5].add(new Edge(5, 4));
        graph[6].add(new Edge(6, 2));

        findBridges(graph);
        // Bridges: 0-2, 2-6, 3-4, 4-5
    }
}
```

---

## 4.14 Bipartite Graph Check

**Problem**: A graph is **bipartite** if vertices can be divided into two groups such that every edge connects vertices from different groups (i.e., no odd-length cycle).

**Approach**: BFS with coloring. Color start node 0. Neighbors get opposite color (1). If a neighbor already has the same color, graph is NOT bipartite.

```java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Queue;
import java.util.Arrays;

public class BipartiteGraph {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    public static boolean isBipartite(ArrayList<Edge>[] graph) {
        int V = graph.length;
        int[] color = new int[V];
        Arrays.fill(color, -1);  // -1 = uncolored

        // Check all components (disconnected graph)
        for (int start = 0; start < V; start++) {
            if (color[start] == -1) {
                // BFS from start
                Queue<Integer> queue = new LinkedList<>();
                queue.add(start);
                color[start] = 0;  // color with 0

                while (!queue.isEmpty()) {
                    int curr = queue.poll();

                    for (Edge e : graph[curr]) {
                        int neighbor = e.dest;

                        if (color[neighbor] == -1) {
                            // Assign opposite color
                            color[neighbor] = (color[curr] == 0) ? 1 : 0;
                            queue.add(neighbor);
                        } else if (color[neighbor] == color[curr]) {
                            // Same color as current → not bipartite
                            return false;
                        }
                    }
                }
            }
        }

        return true;  // all components are bipartite
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        // Bipartite graph (even cycle): 0-1-2-3-0 (square)
        int V = 4;
        ArrayList<Edge>[] bipartiteGraph = new ArrayList[V];
        for (int i = 0; i < V; i++) bipartiteGraph[i] = new ArrayList<>();
        bipartiteGraph[0].add(new Edge(0, 1)); bipartiteGraph[0].add(new Edge(0, 3));
        bipartiteGraph[1].add(new Edge(1, 0)); bipartiteGraph[1].add(new Edge(1, 2));
        bipartiteGraph[2].add(new Edge(2, 1)); bipartiteGraph[2].add(new Edge(2, 3));
        bipartiteGraph[3].add(new Edge(3, 0)); bipartiteGraph[3].add(new Edge(3, 2));

        System.out.println("Square graph is bipartite? " + isBipartite(bipartiteGraph));  // true

        // Non-bipartite graph (odd cycle triangle): 0-1-2-0
        int V2 = 3;
        ArrayList<Edge>[] nonBipartite = new ArrayList[V2];
        for (int i = 0; i < V2; i++) nonBipartite[i] = new ArrayList<>();
        nonBipartite[0].add(new Edge(0, 1)); nonBipartite[0].add(new Edge(0, 2));
        nonBipartite[1].add(new Edge(1, 0)); nonBipartite[1].add(new Edge(1, 2));
        nonBipartite[2].add(new Edge(2, 0)); nonBipartite[2].add(new Edge(2, 1));

        System.out.println("Triangle graph is bipartite? " + isBipartite(nonBipartite));  // false
    }
}
```

---

## 4.15 Paths from Source to Target

**Problem**: Given a directed graph, find all paths from source to target vertex.

**Approach**: DFS with backtracking. Maintain a `path` list; when we reach target, add a copy of path to results.

```java
import java.util.ArrayList;

public class PathsFromSourceToTarget {

    static class Edge {
        int src, dest;
        Edge(int s, int d) { src = s; dest = d; }
    }

    public static void findAllPaths(ArrayList<Edge>[] graph, int source, int target) {
        ArrayList<ArrayList<Integer>> allPaths = new ArrayList<>();
        ArrayList<Integer> currentPath = new ArrayList<>();

        // Use backtracking: keep a visited array to avoid cycles
        boolean[] visited = new boolean[graph.length];

        dfsPaths(graph, source, target, visited, currentPath, allPaths);

        System.out.println("All paths from " + source + " to " + target + ":");
        if (allPaths.isEmpty()) {
            System.out.println("  No paths found.");
        } else {
            for (ArrayList<Integer> path : allPaths) {
                System.out.println("  " + path);
            }
        }
    }

    private static void dfsPaths(ArrayList<Edge>[] graph, int curr, int target,
                                  boolean[] visited, ArrayList<Integer> path,
                                  ArrayList<ArrayList<Integer>> allPaths) {
        visited[curr] = true;
        path.add(curr);

        if (curr == target) {
            // Reached target — add a copy of current path to results
            allPaths.add(new ArrayList<>(path));
        } else {
            // Continue exploring neighbors
            for (Edge e : graph[curr]) {
                if (!visited[e.dest]) {
                    dfsPaths(graph, e.dest, target, visited, path, allPaths);
                }
            }
        }

        // Backtrack: remove current node from path and unmark visited
        path.remove(path.size() - 1);
        visited[curr] = false;
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int V = 5;
        ArrayList<Edge>[] graph = new ArrayList[V];
        for (int i = 0; i < V; i++) graph[i] = new ArrayList<>();

        // DAG: 0→1, 0→2, 1→3, 2→3, 1→4, 3→4
        graph[0].add(new Edge(0, 1)); graph[0].add(new Edge(0, 2));
        graph[1].add(new Edge(1, 3)); graph[1].add(new Edge(1, 4));
        graph[2].add(new Edge(2, 3));
        graph[3].add(new Edge(3, 4));

        findAllPaths(graph, 0, 4);
        // Paths: [0,1,4], [0,1,3,4], [0,2,3,4]
    }
}
```

---

## 4.16 Flood Fill Algorithm

**Problem**: Given a 2D grid and a starting cell, change the color of the starting cell and all connected cells of the same color to a new color. Like the "paint bucket" tool.

**Approach**: DFS or BFS. If the current cell matches the original color, change it and recurse in 4 directions.

```java
import java.util.Arrays;

public class FloodFill {

    // ---- DFS-based flood fill ----
    public static void floodFill(int[][] image, int startRow, int startCol, int newColor) {
        int originalColor = image[startRow][startCol];
        if (originalColor == newColor) return;  // nothing to do

        dfs(image, startRow, startCol, originalColor, newColor);
    }

    private static void dfs(int[][] image, int row, int col, int originalColor, int newColor) {
        // Bounds check: if outside grid, return
        if (row < 0 || row >= image.length || col < 0 || col >= image[0].length) {
            return;
        }

        // If this cell doesn't have the original color, return
        if (image[row][col] != originalColor) {
            return;
        }

        // Change color of this cell
        image[row][col] = newColor;

        // Recursively visit all 4 adjacent cells (up, down, left, right)
        dfs(image, row - 1, col, originalColor, newColor);  // up
        dfs(image, row + 1, col, originalColor, newColor);  // down
        dfs(image, row, col - 1, originalColor, newColor);  // left
        dfs(image, row, col + 1, originalColor, newColor);  // right
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[][] image = {
            {1, 1, 1, 2},
            {1, 1, 0, 2},
            {1, 0, 1, 2},
            {2, 2, 2, 2}
        };

        System.out.println("Original image:");
        for (int[] row : image) System.out.println(Arrays.toString(row));

        // Flood fill from (0, 0) with new color 5
        // All cells with value 1 that are connected to (0,0) become 5
        floodFill(image, 0, 0, 5);

        System.out.println("\nAfter flood fill (0,0) with color 5:");
        for (int[] row : image) System.out.println(Arrays.toString(row));
        // [5,5,5,2]
        // [5,5,0,2]
        // [5,0,1,2]
        // [2,2,2,2]
    }
}
```

---

## 4.17 Cheapest Flights Within K Stops

**Problem**: Given flight routes (u → v with price) and a limit of K stops, find the cheapest price from source to destination.

**Approach**: Modified Dijkstra with state = `(city, stops, cost)`. Use a queue (or priority queue by cost) to explore. Stop exploring a path if stops exceed K.

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.LinkedList;
import java.util.Queue;

public class CheapestFlights {

    static class Edge {
        int src, dest, price;
        Edge(int s, int d, int p) { src = s; dest = d; price = p; }
    }

    // Helper class to track state during BFS
    static class FlightState {
        int city;
        int stops;
        int cost;

        FlightState(int c, int s, int cost) { city = c; stops = s; cost = cost; }
    }

    public static int findCheapestPrice(int n, int[][] flights, int src, int dst, int K) {
        // Build graph
        ArrayList<Edge>[] graph = new ArrayList[n];
        for (int i = 0; i < n; i++) graph[i] = new ArrayList<>();
        for (int[] f : flights) {
            graph[f[0]].add(new Edge(f[0], f[1], f[2]));
        }

        // Track minimum cost to reach each city (for pruning)
        int[] minCost = new int[n];
        Arrays.fill(minCost, Integer.MAX_VALUE);

        // BFS (not Dijkstra — we care about stops, not minimizing cost greedily)
        Queue<FlightState> queue = new LinkedList<>();
        queue.add(new FlightState(src, 0, 0));
        minCost[src] = 0;

        int cheapest = Integer.MAX_VALUE;

        while (!queue.isEmpty()) {
            FlightState current = queue.poll();

            // If we've exceeded stops limit, skip
            if (current.stops > K) continue;

            // Explore neighbors
            for (Edge e : graph[current.city]) {
                int newCost = current.cost + e.price;

                // If we reached destination
                if (e.dest == dst) {
                    cheapest = Math.min(cheapest, newCost);
                }

                // Prune: only continue if newCost < best known cost to that city
                // This still lets us explore alternate paths with fewer stops
                if (newCost < minCost[e.dest]) {
                    minCost[e.dest] = newCost;
                    queue.add(new FlightState(e.dest, current.stops + 1, newCost));
                }
            }
        }

        return cheapest == Integer.MAX_VALUE ? -1 : cheapest;
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int n = 4;
        int[][] flights = {
            {0, 1, 100},
            {1, 2, 100},
            {2, 3, 100},
            {0, 2, 500},
            {1, 3, 600}
        };
        int src = 0, dst = 3, K = 1;

        int price = findCheapestPrice(n, flights, src, dst, K);
        System.out.println("Cheapest price from " + src + " to " + dst + " with at most " + K + " stops: $" + price);
        // Route: 0→1→3 = 100 + 600 = 700 (within 1 stop)
        // Route: 0→2→3 = 500 + 100 = 600 but requires 2 stops
        // With K=1, cheapest = 700
    }
}
```

---

## 4.18 Connecting Cities (Minimum Cost)

**Problem**: Given N cities and the cost to connect each pair, find the minimum cost to connect all cities (i.e., find MST).

**Approach**: Prim's algorithm (works directly on a 2D cost matrix).

```java
import java.util.PriorityQueue;

public class ConnectingCities {

    static class CityConnection implements Comparable<CityConnection> {
        int city;
        int cost;  // cost to connect this city to the MST

        CityConnection(int city, int cost) { this.city = city; this.cost = cost; }

        @Override
        public int compareTo(CityConnection other) {
            return this.cost - other.cost;
        }
    }

    public static int minCostToConnectCities(int[][] costMatrix) {
        int N = costMatrix.length;  // number of cities

        boolean[] visited = new boolean[N];
        PriorityQueue<CityConnection> pq = new PriorityQueue<>();

        // Start from city 0 with cost 0
        pq.add(new CityConnection(0, 0));
        int totalCost = 0;

        while (!pq.isEmpty()) {
            CityConnection current = pq.poll();
            int city = current.city;

            if (visited[city]) continue;  // already in MST

            visited[city] = true;
            totalCost += current.cost;    // add cost to connect this city

            // Check all other cities for possible connections
            for (int neighbor = 0; neighbor < N; neighbor++) {
                if (!visited[neighbor] && costMatrix[city][neighbor] > 0) {
                    // There's a cost to connect city → neighbor
                    pq.add(new CityConnection(neighbor, costMatrix[city][neighbor]));
                }
            }
        }

        return totalCost;
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int[][] cities = {
            {0, 10, 15, 20},
            {10, 0, 35, 25},
            {15, 35, 0, 30},
            {20, 25, 30, 0}
        };

        int minCost = minCostToConnectCities(cities);
        System.out.println("Minimum cost to connect all cities: " + minCost);
        // Expected: edges (0-1:10), (0-3:20), (0-2:15) → total = 45
        // Or (0-1:10), (3-1:25), (0-2:15) → 50 (not minimal)
        // Actually Prim's finds: 0-1(10), 0-2(15), 0-3(20) = 45
    }
}
```

---

## 4.19 Disjoint Set Union (DSU) with Path Compression and Rank

**DSU (Union-Find)** is a data structure that tracks a set of elements partitioned into disjoint (non-overlapping) subsets. It supports:
- `find(x)`: find which set x belongs to
- `union(x, y)`: merge the sets containing x and y

**Optimizations**:
- **Path compression**: During find, make every node point directly to the root.
- **Union by rank**: Attach the smaller tree under the larger tree.

This is the foundation of Kruskal's algorithm (see section 4.11).

```java
import java.util.Arrays;

public class DisjointSetDemo {

    // Complete DSU implementation
    static class DisjointSet {
        int[] parent;
        int[] rank;

        // Initialize: each element is its own parent (singleton sets)
        DisjointSet(int n) {
            parent = new int[n];
            rank = new int[n];
            for (int i = 0; i < n; i++) {
                parent[i] = i;  // each node is its own root
                rank[i] = 0;    // initial rank is 0
            }
        }

        // Find with PATH COMPRESSION
        // Makes every node on the path point directly to the root
        public int find(int x) {
            if (parent[x] != x) {
                parent[x] = find(parent[x]);  // recursive path compression
            }
            return parent[x];
        }

        // Union by RANK
        // Attach the tree with smaller rank under the tree with larger rank
        public void union(int x, int y) {
            int rootX = find(x);
            int rootY = find(y);

            if (rootX == rootY) return;  // already in same set

            // Attach smaller rank tree under larger rank tree
            if (rank[rootX] < rank[rootY]) {
                parent[rootX] = rootY;
            } else if (rank[rootX] > rank[rootY]) {
                parent[rootY] = rootX;
            } else {
                // Same rank: pick one as root and increase its rank
                parent[rootY] = rootX;
                rank[rootX]++;
            }
        }

        // Check if two elements are in the same set
        public boolean isConnected(int x, int y) {
            return find(x) == find(y);
        }

        // Count number of disjoint sets
        public int countSets() {
            int count = 0;
            for (int i = 0; i < parent.length; i++) {
                if (parent[i] == i) count++;  // each root defines a set
            }
            return count;
        }

        public void printSets() {
            // Group elements by their root
            System.out.println("Current DSU state:");
            int n = parent.length;
            for (int i = 0; i < n; i++) {
                System.out.println("  Element " + i + " → root: " + find(i));
            }
            System.out.println("  Number of sets: " + countSets());
            System.out.println();
        }
    }

    // ========== MAIN ==========
    public static void main(String[] args) {
        int n = 8;
        DisjointSet dsu = new DisjointSet(n);

        System.out.println("=== DSU (Union-Find) Demo ===\n");
        System.out.println("Initial state (each element is its own set):");
        dsu.printSets();

        // Union operations
        dsu.union(0, 1);   // merge {0} and {1} → {0,1}
        dsu.union(2, 3);   // merge {2} and {3} → {2,3}
        dsu.union(1, 2);   // merge {0,1} and {2,3} → {0,1,2,3}

        System.out.println("After union(0,1), union(2,3), union(1,2):");
        dsu.printSets();

        dsu.union(4, 5);   // {4,5}
        dsu.union(6, 7);   // {6,7}
        dsu.union(5, 6);   // merge {4,5} and {6,7} → {4,5,6,7}

        System.out.println("After unions on set {4,5,6,7}:");
        dsu.printSets();

        // Demonstrate path compression: find(0) compresses path
        System.out.println("Find operations:");
        System.out.println("find(0) = " + dsu.find(0));
        System.out.println("find(3) = " + dsu.find(3));
        System.out.println("find(7) = " + dsu.find(7));

        // Check connectivity
        System.out.println("\nConnectivity checks:");
        System.out.println("Is 0 connected to 3? " + dsu.isConnected(0, 3));   // true
        System.out.println("Is 0 connected to 7? " + dsu.isConnected(0, 7));   // false
        System.out.println("Is 4 connected to 6? " + dsu.isConnected(4, 6));   // true

        // Union across the two large sets
        dsu.union(3, 5);   // merges {0,1,2,3} with {4,5,6,7}
        System.out.println("\nAfter union(3, 5):");
        dsu.printSets();
        System.out.println("All elements now in one set? " + (dsu.countSets() == 1));  // true
    }
}
```

---

# End of Section 4

This document covered:
- **Heaps**: From-scratch implementation, PriorityQueue JCF, heap sort, 5 classic problems
- **Hashing**: HashMap/HashSet operations, from-scratch HashMap implementation with chaining + rehashing, 5 problems
- **Tries**: Insert/Search/StartsWith, autocomplete, word break, unique substrings, longest word with all prefixes
- **Graphs**: Representations, BFS, DFS, cycle detection (undirected + directed), topological sort (DFS + Kahn's), Dijkstra, Bellman Ford, Prim's, Kruskal's with DSU, Kosaraju's SCC, Tarjan's bridges, bipartite check, paths from source to target, flood fill, cheapest flights within K stops, connecting cities, complete DSU with path compression and rank

Every concept is explained simply with **complete Java code**, **`main()` methods**, and **line-by-line comments**.
# JAVA DSA: DYNAMIC PROGRAMMING, SEGMENT TREES & FENWICK TREES

## FOR THE ABSOLUTE BEGINNER

This guide assumes you know basic Java (loops, arrays, methods, recursion). Everything else is explained from scratch. Every concept is first explained like you're 5, then we dive into code.

---

# PART 1: WHAT IS DYNAMIC PROGRAMMING?

## Imagine This...

You need to calculate the 50th number in the Fibonacci sequence. You write a recursive function. It works... but it's SLOW. Really slow. Like, won't-finish-in-your-lifetime slow.

What went wrong? The same calculation gets repeated MILLIONS of times. `fib(3)` gets calculated over and over and over.

**DP (Dynamic Programming)** is just a fancy name for: *"Hey, let's remember stuff we already calculated so we don't do it again."*

That's literally it.

## Two Magic Properties of DP Problems

### 1. Overlapping Subproblems
The big problem can be broken into smaller problems, AND those smaller problems are the SAME ones that keep appearing.

Like Fibonacci: `fib(5) = fib(4) + fib(3)`, and `fib(4) = fib(3) + fib(2)` — see how `fib(3)` appears in BOTH? That's overlapping.

### 2. Optimal Substructure
The optimal answer to the big problem can be built from optimal answers to the smaller problems.

Like: "What's the shortest path from A to C through B?" If you know the shortest path from A to B and B to C, you combine them. Simple.

## The Three Approaches

### Approach 1: Recursion (Naive) — "The Slow Way"
Just write the recursive formula as-is. No caching. SLOOOOOW.

### Approach 2: Memoization (Top-Down) — "The Smart Recursive Way"
Same recursion, but you STORE results in an array/table before returning. When the same call comes again, you just look up the stored value. FAST.

### Approach 3: Tabulation (Bottom-Up) — "The Loop Way"
Instead of recursion, you fill a table iteratively from smallest subproblem to biggest. NO recursion at all. OFTEN the fastest.

---

# FIBONACCI — THE HELLO WORLD OF DP

## Problem: Find the nth Fibonacci number
Fibonacci: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...
- fib(0) = 0
- fib(1) = 1
- fib(n) = fib(n-1) + fib(n-2)

---

### APPROACH 1: RECURSION (NAIVE)

```java
public class FibonacciRecursion {

    // This is the RAW recursive formula. Looks elegant. Runs like garbage.
    public static int fib(int n) {
        // Base cases: fib(0) = 0, fib(1) = 1
        if (n <= 1) {
            return n;
        }

        // Recursive case: fib(n) = fib(n-1) + fib(n-2)
        // Problem: for n=50, this calls itself BILLIONS of times
        int result = fib(n - 1) + fib(n - 2);
        return result;
    }

    public static void main(String[] args) {
        int n = 6;
        // Try changing n to 50 and watch your computer cry
        System.out.println("fib(" + n + ") = " + fib(n));
    }
}
```

**Time Complexity: O(2^n)** — exponentially BAD
**Space Complexity: O(n)** — call stack depth

**Why is it so slow?** Draw the call tree. `fib(5)` calls `fib(4)` and `fib(3)`. `fib(4)` calls `fib(3)` and `fib(2)`. Notice `fib(3)` is called TWICE. `fib(2)` is called THREE times. This duplication explodes exponentially.

---

### APPROACH 2: MEMOIZATION (TOP-DOWN DP)

```java
public class FibonacciMemoization {

    // We use a "memo" (memory) array to store already-computed values
    // Size: n+1 because we need indices 0 through n
    // Initialize with -1 (or any sentinel) to mean "not computed yet"
    public static int fib(int n, int[] memo) {
        // Base case
        if (n <= 1) {
            return n;
        }

        // MAGIC LINE: If we've already computed fib(n), just return it!
        // This is the entire point of DP — avoid recomputation
        if (memo[n] != -1) {
            return memo[n];
        }

        // Compute and STORE before returning
        memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
        return memo[n];
    }

    public static void main(String[] args) {
        int n = 50; // Try n=50 now — runs INSTANTLY

        // Create memo array, fill with -1 (means "not computed yet")
        int[] memo = new int[n + 1];
        for (int i = 0; i <= n; i++) {
            memo[i] = -1;
        }

        System.out.println("fib(" + n + ") = " + fib(n, memo));
    }
}
```

**Time Complexity: O(n)** — each number computed once!
**Space Complexity: O(n)** — memo array + call stack

**What changed?** Every `fib(k)` is computed exactly once. The second time we need it, we just read `memo[k]`. That's it. That's the whole secret of DP.

### APPROACH 3: TABULATION (BOTTOM-UP DP)

```java
public class FibonacciTabulation {

    // No recursion! We fill the table from bottom (small numbers) to top (n)
    public static int fib(int n) {
        if (n <= 1) {
            return n;
        }

        // Create table (tab) to store values
        int[] tab = new int[n + 1];

        // Base cases (the "bottom" of our bottom-up)
        tab[0] = 0;
        tab[1] = 1;

        // Fill upwards: tab[2], tab[3], ..., tab[n]
        // Each tab[i] depends ONLY on tab[i-1] and tab[i-2]
        // Those are ALREADY computed (we filled them in previous iterations)
        for (int i = 2; i <= n; i++) {
            tab[i] = tab[i - 1] + tab[i - 2];
        }

        return tab[n];
    }

    public static void main(String[] args) {
        int n = 50;
        System.out.println("fib(" + n + ") = " + fib(n));
    }
}
```

**Time Complexity: O(n)**
**Space Complexity: O(n)** but can be optimized to O(1)

**Space-optimized version (no array, just two variables):**

```java
public class FibonacciTabulationOptimized {

    public static int fib(int n) {
        if (n <= 1) {
            return n;
        }

        // We only need the LAST TWO values at any point
        int prev2 = 0; // fib(0)
        int prev1 = 1; // fib(1)

        for (int i = 2; i <= n; i++) {
            int curr = prev1 + prev2;
            prev2 = prev1; // Shift: old prev1 becomes new prev2
            prev1 = curr;  // Shift: new value becomes new prev1
        }

        return prev1;
    }

    public static void main(String[] args) {
        int n = 50;
        System.out.println("fib(" + n + ") = " + fib(n));
    }
}
```

**Space Complexity: O(1)** — just two variables!

---

# CLIMBING STAIRS

## Problem
You're climbing a staircase with `n` steps. Each time you can climb 1 or 2 steps. In how many DISTINCT ways can you reach the top?

## Think About It
- To reach step 0 (ground): 1 way (just stand there)
- To reach step 1: 1 way (1 step)
- To reach step 2: 2 ways (1+1 or 2)
- To reach step 3: You got here from step 2 (then took 1 step) OR from step 1 (then took 2 steps). So ways(3) = ways(2) + ways(1) = 2 + 1 = 3

**Pattern:** ways(n) = ways(n-1) + ways(n-2) — it's Fibonacci!

```java
public class ClimbingStairs {

    // ---- RECURSION (NAIVE) ----
    public static int climbRecur(int n) {
        // Base cases
        if (n == 0 || n == 1) {
            return 1; // Only 1 way to be at step 0 or 1
        }

        // To reach step n, you came from step n-1 (took 1 step)
        // OR from step n-2 (took 2 steps)
        return climbRecur(n - 1) + climbRecur(n - 2);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int climbMemo(int n, int[] memo) {
        if (n == 0 || n == 1) {
            return 1;
        }

        // If already computed, return stored value
        if (memo[n] != -1) {
            return memo[n];
        }

        // Compute, store, then return
        memo[n] = climbMemo(n - 1, memo) + climbMemo(n - 2, memo);
        return memo[n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int climbTab(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }

        int[] dp = new int[n + 1];
        dp[0] = 1; // 1 way to be at step 0
        dp[1] = 1; // 1 way to be at step 1

        // Fill bottom-up: step 2, 3, ..., n
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }

        return dp[n];
    }

    // ---- TABULATION (SPACE OPTIMIZED) ----
    public static int climbTabOpt(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }

        int prev2 = 1; // ways to reach step 0
        int prev1 = 1; // ways to reach step 1

        for (int i = 2; i <= n; i++) {
            int curr = prev1 + prev2;
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }

    public static void main(String[] args) {
        int n = 10;

        System.out.println("Recursion: climb(" + n + ") = " + climbRecur(n));

        int[] memo = new int[n + 1];
        java.util.Arrays.fill(memo, -1);
        System.out.println("Memoization: climb(" + n + ") = " + climbMemo(n, memo));

        System.out.println("Tabulation: climb(" + n + ") = " + climbTab(n));
        System.out.println("Tabulation Opt: climb(" + n + ") = " + climbTabOpt(n));
    }
}
```

---

# MIN COST CLIMBING STAIRS

## Problem
You're given an array `cost[]` where `cost[i]` is the cost to step onto step i. Once you pay, you can climb 1 or 2 steps. You start at step 0 or step 1 (your choice). Find the MINIMUM cost to reach the top (past the last step).

## Think About It
To reach step i, you came from step i-1 (cost = cost[i-1]) or step i-2 (cost = cost[i-2]). You want the MINIMUM cost so far plus the cost of the step you're STANDING on.

**Recurrence:** `minCost(i) = cost[i] + min(minCost(i-1), minCost(i-2))`

The TOP is past the last step, so answer is `min(minCost(n-1), minCost(n-2))`.

```java
public class MinCostClimbingStairs {

    // ---- RECURSION (NAIVE) ----
    // minCost(i) = minimum cost to reach step i (and pay its cost)
    public static int minCostRecur(int i, int[] cost) {
        // Base: step 0 or 1 — just pay the cost to stand here
        if (i == 0 || i == 1) {
            return cost[i];
        }

        // To reach step i: pay cost[i] PLUS the minimum of reaching i-1 or i-2
        int totalCost = cost[i] + Math.min(minCostRecur(i - 1, cost), minCostRecur(i - 2, cost));
        return totalCost;
    }

    // Wrapper for recursion approach
    public static int minCostClimbingStairsRecur(int[] cost) {
        int n = cost.length;
        // Top is past the last step, so we take min of reaching n-1 or n-2
        return Math.min(minCostRecur(n - 1, cost), minCostRecur(n - 2, cost));
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minCostMemo(int i, int[] cost, int[] memo) {
        if (i == 0 || i == 1) {
            return cost[i];
        }

        if (memo[i] != -1) {
            return memo[i];
        }

        memo[i] = cost[i] + Math.min(minCostMemo(i - 1, cost, memo), minCostMemo(i - 2, cost, memo));
        return memo[i];
    }

    public static int minCostClimbingStairsMemo(int[] cost) {
        int n = cost.length;
        int[] memo = new int[n];
        java.util.Arrays.fill(memo, -1);
        return Math.min(minCostMemo(n - 1, cost, memo), minCostMemo(n - 2, cost, memo));
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minCostClimbingStairsTab(int[] cost) {
        int n = cost.length;

        // dp[i] = min cost to reach step i (and pay its cost)
        int[] dp = new int[n];

        // Base cases
        dp[0] = cost[0];
        dp[1] = cost[1];

        // Fill bottom-up
        for (int i = 2; i < n; i++) {
            dp[i] = cost[i] + Math.min(dp[i - 1], dp[i - 2]);
        }

        // Answer: min of reaching step n-1 or skipping from n-2 to top
        return Math.min(dp[n - 1], dp[n - 2]);
    }

    // ---- TABULATION (SPACE OPTIMIZED) ----
    public static int minCostClimbingStairsOpt(int[] cost) {
        int n = cost.length;

        int prev2 = cost[0]; // dp[i-2]
        int prev1 = cost[1]; // dp[i-1]

        for (int i = 2; i < n; i++) {
            int curr = cost[i] + Math.min(prev1, prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return Math.min(prev1, prev2);
    }

    public static void main(String[] args) {
        int[] cost = {10, 15, 20, 25, 30};

        System.out.println("Recursion: " + minCostClimbingStairsRecur(cost));
        System.out.println("Memoization: " + minCostClimbingStairsMemo(cost));
        System.out.println("Tabulation: " + minCostClimbingStairsTab(cost));
        System.out.println("Tabulation Opt: " + minCostClimbingStairsOpt(cost));
    }
}
```

---

# HOUSE ROBBER

## Problem
You're a robber planning to rob houses on a street. Each house has a certain amount of money stashed. ADJACENT houses cannot be robbed on the same night (silent alarm system). Find the MAXIMUM amount you can rob.

## Think About It
At each house `i`, you have TWO choices:
1. **Rob it**: You get `nums[i]` + whatever you got up to house `i-2` (can't rob i-1)
2. **Skip it**: You get whatever you got up to house `i-1`

Take the MAX of these two options.

**Recurrence:** `rob(i) = max(rob(i-1), nums[i] + rob(i-2))`

```java
public class HouseRobber {

    // ---- RECURSION (NAIVE) ----
    // robRecur(i) = max money from houses [0...i]
    public static int robRecur(int i, int[] nums) {
        // Base: no houses left
        if (i < 0) {
            return 0;
        }

        // Option 1: Skip house i, take best from houses [0...i-1]
        int skip = robRecur(i - 1, nums);

        // Option 2: Rob house i, add its money, then take best from [0...i-2]
        int rob = nums[i] + robRecur(i - 2, nums);

        // Return whichever gives MORE money
        return Math.max(skip, rob);
    }

    public static int robRecurWrapper(int[] nums) {
        return robRecur(nums.length - 1, nums);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int robMemo(int i, int[] nums, int[] memo) {
        if (i < 0) {
            return 0;
        }

        if (memo[i] != -1) {
            return memo[i];
        }

        int skip = robMemo(i - 1, nums, memo);
        int rob = nums[i] + robMemo(i - 2, nums, memo);

        memo[i] = Math.max(skip, rob);
        return memo[i];
    }

    public static int robMemoWrapper(int[] nums) {
        int n = nums.length;
        int[] memo = new int[n];
        java.util.Arrays.fill(memo, -1);
        return robMemo(n - 1, nums, memo);
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int robTab(int[] nums) {
        int n = nums.length;

        if (n == 0) return 0;
        if (n == 1) return nums[0];

        // dp[i] = max money from houses [0...i]
        int[] dp = new int[n];

        // Base cases
        dp[0] = nums[0];                       // Only one house? Rob it
        dp[1] = Math.max(nums[0], nums[1]);    // Two houses? Take the richer one

        // For each subsequent house, decide: rob or skip?
        for (int i = 2; i < n; i++) {
            // Skip house i -> dp[i-1]
            // Rob house i  -> nums[i] + dp[i-2]
            dp[i] = Math.max(dp[i - 1], nums[i] + dp[i - 2]);
        }

        return dp[n - 1];
    }

    // ---- TABULATION (SPACE OPTIMIZED) ----
    public static int robOpt(int[] nums) {
        int n = nums.length;

        if (n == 0) return 0;
        if (n == 1) return nums[0];

        int prev2 = nums[0];          // dp[i-2]
        int prev1 = Math.max(nums[0], nums[1]); // dp[i-1]

        for (int i = 2; i < n; i++) {
            int curr = Math.max(prev1, nums[i] + prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }

    public static void main(String[] args) {
        int[] nums = {2, 7, 9, 3, 1};

        System.out.println("Houses: [2, 7, 9, 3, 1]");
        System.out.println("Recursion: " + robRecurWrapper(nums));
        System.out.println("Memoization: " + robMemoWrapper(nums));
        System.out.println("Tabulation: " + robTab(nums));
        System.out.println("Tabulation Opt: " + robOpt(nums));
        // Expected: 12 (rob house 0=2, house 2=9, house 4=1 => 2+9+1=12)
        // Or: rob house 1=7, house 3=3 => 10. Max is 12.
    }
}
```

# HOUSE ROBBER II (CIRCULAR)

## Problem
Same as House Robber BUT the houses are arranged in a CIRCLE. The first and last houses are adjacent.

## Think About It
Since house 0 and house n-1 are adjacent, we can't rob both. Solution: solve TWO linear House Robber problems:
1. Rob houses [0...n-2] (exclude last house)
2. Rob houses [1...n-1] (exclude first house)
3. Answer = max(option1, option2)

```java
public class HouseRobberII {

    // Helper: linear House Robber on a subarray
    private static int robLinear(int[] nums, int start, int end) {
        int prev2 = 0; // dp[i-2], starts as 0 for "no house"
        int prev1 = 0; // dp[i-1]

        for (int i = start; i <= end; i++) {
            int curr = Math.max(prev1, nums[i] + prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }

    // ---- RECURSION (NAIVE) ----
    public static int robRecur(int[] nums) {
        int n = nums.length;
        if (n == 0) return 0;
        if (n == 1) return nums[0];
        if (n == 2) return Math.max(nums[0], nums[1]);

        // We use our linear rob helper with the two ranges
        // (Recursion on linear part is same as House Robber)
        return Math.max(
            HouseRobber.robRecurWrapper(java.util.Arrays.copyOfRange(nums, 0, n - 1)),
            HouseRobber.robRecurWrapper(java.util.Arrays.copyOfRange(nums, 1, n))
        );
    }

    // ---- TABULATION (using linear helper) ----
    public static int robTab(int[] nums) {
        int n = nums.length;
        if (n == 0) return 0;
        if (n == 1) return nums[0];
        if (n == 2) return Math.max(nums[0], nums[1]);

        // Case 1: Exclude last house
        int case1 = robLinear(nums, 0, n - 2);
        // Case 2: Exclude first house
        int case2 = robLinear(nums, 1, n - 1);

        return Math.max(case1, case2);
    }

    public static void main(String[] args) {
        int[] nums = {2, 3, 2};

        System.out.println("Houses (circular): [2, 3, 2]");
        System.out.println("Recursion: " + robRecur(nums));
        System.out.println("Tabulation: " + robTab(nums));
        // Expected: 3 (can't rob 0 and 2 since they're adjacent in circle)
        // Option 1: houses [0,1] = max(2,3) = 3
        // Option 2: houses [1,2] = max(3,2) = 3
        // Answer: 3
    }
}
```

---

# 0/1 KNAPSACK — THE CLASSIC DP PROBLEM

## Problem
You have a bag (knapsack) that can hold at most `W` weight. You have `n` items, each with a `weight` and a `value`. You can either take an item or leave it (0/1 choice — can't take fractions). Maximize the total value in your bag.

## Understanding the 2D Table

Let's say:
- Items: (val=60, wt=10), (val=100, wt=20), (val=120, wt=30)
- Capacity = 50

We build a table where:
- ROWS = items (0 to n)
- COLUMNS = capacity (0 to W)
- `dp[i][w]` = max value using first `i` items with capacity `w`

### How to read the table:
- `dp[0][w]` = 0 (no items, no value)
- `dp[i][0]` = 0 (no capacity, no value)
- For each cell: either skip item `i` (take value from above) or take item `i` (item value + value from row above at capacity minus item weight)

### Example table walkthrough:

```
Capacity ->    0   10   20   30   40   50
Item 0         0    0    0    0    0    0
Item 1(w10)    0   60   60   60   60   60
Item 2(w20)    0   60  100  160  160  160
Item 3(w30)    0   60  100  160  180  220
```

**How cell [3][50] = 220 is computed:**
- Skip item 3: above cell [2][50] = 160
- Take item 3: val[3] + dp[2][50-wt[3]] = 120 + dp[2][20] = 120 + 100 = 220
- Max(160, 220) = 220

```java
public class Knapsack01 {

    // ---- RECURSION (NAIVE) ----
    // knapRecur(n, W) = max value with first n items and capacity W
    public static int knapRecur(int n, int W, int[] val, int[] wt) {
        // Base: no items left or no capacity left
        if (n == 0 || W == 0) {
            return 0;
        }

        // If current item's weight exceeds remaining capacity, skip it
        if (wt[n - 1] > W) {
            return knapRecur(n - 1, W, val, wt);
        }

        // Option 1: Skip item n-1
        int skip = knapRecur(n - 1, W, val, wt);

        // Option 2: Take item n-1
        int take = val[n - 1] + knapRecur(n - 1, W - wt[n - 1], val, wt);

        return Math.max(skip, take);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int knapMemo(int n, int W, int[] val, int[] wt, int[][] memo) {
        if (n == 0 || W == 0) {
            return 0;
        }

        if (memo[n][W] != -1) {
            return memo[n][W];
        }

        if (wt[n - 1] > W) {
            memo[n][W] = knapMemo(n - 1, W, val, wt, memo);
        } else {
            int skip = knapMemo(n - 1, W, val, wt, memo);
            int take = val[n - 1] + knapMemo(n - 1, W - wt[n - 1], val, wt, memo);
            memo[n][W] = Math.max(skip, take);
        }

        return memo[n][W];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int knapTab(int W, int[] val, int[] wt) {
        int n = val.length;

        // dp[i][w] = max value using first i items with capacity w
        int[][] dp = new int[n + 1][W + 1];

        // i=0 or w=0 are already initialized to 0 (default in Java)

        // Fill the table bottom-up
        for (int i = 1; i <= n; i++) {
            for (int w = 1; w <= W; w++) {
                // If current item fits...
                if (wt[i - 1] <= w) {
                    // Max of: skip item vs take item
                    dp[i][w] = Math.max(
                        dp[i - 1][w],                                    // skip
                        val[i - 1] + dp[i - 1][w - wt[i - 1]]            // take
                    );
                } else {
                    // Item too heavy, must skip
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        // Print the DP table for learning
        System.out.println("DP Table (items vs capacity):");
        System.out.print("    ");
        for (int w = 0; w <= W; w++) {
            System.out.printf("%4d", w);
        }
        System.out.println();
        for (int i = 0; i <= n; i++) {
            System.out.printf("%4d ", i);
            for (int w = 0; w <= W; w++) {
                System.out.printf("%4d", dp[i][w]);
            }
            System.out.println();
        }

        return dp[n][W];
    }

    public static void main(String[] args) {
        int[] val = {60, 100, 120};
        int[] wt = {10, 20, 30};
        int W = 50;
        int n = val.length;

        System.out.println("Items: (val=60, wt=10), (val=100, wt=20), (val=120, wt=30)");
        System.out.println("Capacity: " + W);

        System.out.println("\nRecursion: " + knapRecur(n, W, val, wt));

        int[][] memo = new int[n + 1][W + 1];
        for (int i = 0; i <= n; i++)
            for (int w = 0; w <= W; w++)
                memo[i][w] = -1;
        System.out.println("Memoization: " + knapMemo(n, W, val, wt, memo));

        System.out.println("\nTabulation:");
        System.out.println("Max Value: " + knapTab(W, val, wt));
        // Expected: 220
    }
}
```

---

# TARGET SUM SUBSET (SUBSET SUM)

## Problem
Given an array `arr[]` and a target sum `sum`, is there a subset whose elements sum to exactly `sum`?

## Think About It
For each element, we have two choices: include it or exclude it.
- `subsetSum(arr, n, sum)` = `subsetSum(arr, n-1, sum)` (skip) OR `subsetSum(arr, n-1, sum - arr[n-1])` (include)

This is a 0/1 Knapsack variant where value = weight = arr[i], and we check for EXACT sum.

```java
public class SubsetSum {

    // ---- RECURSION (NAIVE) ----
    public static boolean subsetSumRecur(int[] arr, int n, int sum) {
        // Base: sum = 0 -> empty subset always works
        if (sum == 0) return true;
        // Base: no items left but sum > 0 -> impossible
        if (n == 0) return false;

        // If current element > sum, skip it
        if (arr[n - 1] > sum) {
            return subsetSumRecur(arr, n - 1, sum);
        }

        // Try: skip element OR include element
        return subsetSumRecur(arr, n - 1, sum) ||
               subsetSumRecur(arr, n - 1, sum - arr[n - 1]);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static boolean subsetSumMemo(int[] arr, int n, int sum, Boolean[][] memo) {
        if (sum == 0) return true;
        if (n == 0) return false;

        if (memo[n][sum] != null) {
            return memo[n][sum];
        }

        if (arr[n - 1] > sum) {
            memo[n][sum] = subsetSumMemo(arr, n - 1, sum, memo);
        } else {
            memo[n][sum] = subsetSumMemo(arr, n - 1, sum, memo) ||
                           subsetSumMemo(arr, n - 1, sum - arr[n - 1], memo);
        }

        return memo[n][sum];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static boolean subsetSumTab(int[] arr, int sum) {
        int n = arr.length;

        // dp[i][s] = can we make sum 's' using first 'i' elements?
        boolean[][] dp = new boolean[n + 1][sum + 1];

        // Sum = 0 is always possible (empty subset)
        for (int i = 0; i <= n; i++) {
            dp[i][0] = true;
        }

        // No elements can only make sum 0 (already set above)
        // dp[0][s] for s>0 stays false (default)

        // Fill the table
        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= sum; s++) {
                if (arr[i - 1] <= s) {
                    // Can we make sum 's' by skipping OR including element i-1?
                    dp[i][s] = dp[i - 1][s] || dp[i - 1][s - arr[i - 1]];
                } else {
                    // Element too big, must skip
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        // Print table
        System.out.println("\nSubset Sum DP Table:");
        System.out.print("    ");
        for (int s = 0; s <= sum; s++) System.out.printf("%4d", s);
        System.out.println();
        for (int i = 0; i <= n; i++) {
            System.out.printf("%4d ", i);
            for (int s = 0; s <= sum; s++) {
                System.out.printf("%4s", dp[i][s] ? "T" : "F");
            }
            System.out.println();
        }

        return dp[n][sum];
    }

    public static void main(String[] args) {
        int[] arr = {3, 34, 4, 12, 5, 2};
        int sum = 9;

        System.out.println("Array: [3, 34, 4, 12, 5, 2], Target: " + sum);
        System.out.println("Recursion: " + subsetSumRecur(arr, arr.length, sum));

        Boolean[][] memo = new Boolean[arr.length + 1][sum + 1];
        System.out.println("Memoization: " + subsetSumMemo(arr, arr.length, sum, memo));

        System.out.println("Tabulation: " + subsetSumTab(arr, sum));
        // Expected: true (3+4+2=9, or 4+5=9)
    }
}
```

---

# PARTITION EQUAL SUBSET SUM

## Problem
Given an array, can you partition it into TWO subsets with EQUAL sum?

## Think About It
- First, total sum must be EVEN (odd sum can't be split equally)
- Target = totalSum / 2
- Now it's just SUBSET SUM with target = totalSum/2!

```java
public class PartitionEqualSubsetSum {

    // Uses subset sum tabulation (same logic)
    public static boolean canPartition(int[] nums) {
        int totalSum = 0;
        for (int num : nums) totalSum += num;

        // If odd, impossible
        if (totalSum % 2 != 0) return false;

        int target = totalSum / 2;
        return SubsetSum.subsetSumTab(nums, target);
    }

    // ---- FULL TABULATION (written explicitly) ----
    public static boolean canPartitionFull(int[] nums) {
        int totalSum = 0;
        for (int num : nums) totalSum += num;

        if (totalSum % 2 != 0) return false;

        int target = totalSum / 2;
        int n = nums.length;

        boolean[][] dp = new boolean[n + 1][target + 1];

        // Sum 0 always possible
        for (int i = 0; i <= n; i++) dp[i][0] = true;

        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= target; s++) {
                if (nums[i - 1] <= s) {
                    dp[i][s] = dp[i - 1][s] || dp[i - 1][s - nums[i - 1]];
                } else {
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        return dp[n][target];
    }

    public static void main(String[] args) {
        int[] nums = {1, 5, 11, 5};

        System.out.println("Array: [1, 5, 11, 5]");
        System.out.println("Can partition equally? " + canPartition(nums));
        // Expected: true (1+5+5=11, and 11=11)

        int[] nums2 = {1, 2, 3, 5};
        System.out.println("Array: [1, 2, 3, 5]");
        System.out.println("Can partition equally? " + canPartition(nums2));
        // Expected: false
    }
}
```

# UNBOUNDED KNAPSACK

## Problem
Same as 0/1 Knapsack, but now you can take UNLIMITED copies of each item! (That's why it's called "unbounded")

## Key Difference from 0/1 Knapsack:
- **0/1 Knapsack**: `dp[i][w] = max(dp[i-1][w], val[i-1] + dp[i-1][w-wt[i-1]])`
  — After using item i-1, you move to row i-1 (can't reuse item)
- **Unbounded Knapsack**: `dp[i][w] = max(dp[i-1][w], val[i-1] + dp[i][w-wt[i-1]])`
  — After using item i-1, you stay in row i (can use item again!)

Same column index change: `i-1` vs `i` — that's the ONLY difference!

```java
public class UnboundedKnapsack {

    // ---- RECURSION (NAIVE) ----
    public static int unboundedRecur(int n, int W, int[] val, int[] wt) {
        if (n == 0 || W == 0) {
            return 0;
        }

        if (wt[n - 1] > W) {
            return unboundedRecur(n - 1, W, val, wt);
        }

        // Skip item
        int skip = unboundedRecur(n - 1, W, val, wt);
        // Take item — NOTICE: we call with n (not n-1) because we can reuse!
        int take = val[n - 1] + unboundedRecur(n, W - wt[n - 1], val, wt);

        return Math.max(skip, take);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int unboundedMemo(int n, int W, int[] val, int[] wt, int[][] memo) {
        if (n == 0 || W == 0) {
            return 0;
        }

        if (memo[n][W] != -1) {
            return memo[n][W];
        }

        if (wt[n - 1] > W) {
            memo[n][W] = unboundedMemo(n - 1, W, val, wt, memo);
        } else {
            int skip = unboundedMemo(n - 1, W, val, wt, memo);
            int take = val[n - 1] + unboundedMemo(n, W - wt[n - 1], val, wt, memo);
            memo[n][W] = Math.max(skip, take);
        }

        return memo[n][W];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int unboundedTab(int W, int[] val, int[] wt) {
        int n = val.length;
        int[][] dp = new int[n + 1][W + 1];

        for (int i = 1; i <= n; i++) {
            for (int w = 1; w <= W; w++) {
                if (wt[i - 1] <= w) {
                    // KEY difference from 0/1: dp[i][w-wt[i-1]] NOT dp[i-1][w-wt[i-1]]
                    dp[i][w] = Math.max(
                        dp[i - 1][w],
                        val[i - 1] + dp[i][w - wt[i - 1]]  // Stay on row i (reuse allowed!)
                    );
                } else {
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        return dp[n][W];
    }

    public static void main(String[] args) {
        int[] val = {10, 40, 50, 70};
        int[] wt = {1, 3, 4, 5};
        int W = 8;

        System.out.println("Unbounded Knapsack");
        System.out.println("Items: (val=10, wt=1), (40,3), (50,4), (70,5)");
        System.out.println("Capacity: " + W);

        System.out.println("Recursion: " + unboundedRecur(val.length, W, val, wt));
        int[][] memo = new int[val.length + 1][W + 1];
        for (int i = 0; i <= val.length; i++)
            for (int w = 0; w <= W; w++)
                memo[i][w] = -1;
        System.out.println("Memoization: " + unboundedMemo(val.length, W, val, wt, memo));
        System.out.println("Tabulation: " + unboundedTab(W, val, wt));
    }
}
```

---

# ROD CUTTING

## Problem
You have a rod of length `n` and a price array `price[i]` where `price[i]` is the price of a rod of length `i+1`. Cut the rod into pieces to maximize profit. You can cut any number of pieces of any lengths.

## Think About It
This is EXACTLY Unbounded Knapsack!
- Rod length = Knapsack capacity
- Piece lengths = item weights (1 to n)
- Prices = item values
- You can use unlimited pieces of each length

```java
public class RodCutting {

    // ---- RECURSION (NAIVE) ----
    // maxProfit(length) = max price obtainable from rod of given length
    public static int cutRodRecur(int[] price, int n) {
        if (n <= 0) return 0;

        int maxVal = Integer.MIN_VALUE;

        // Try cutting a piece of length i+1
        for (int i = 0; i < n; i++) {
            // Cut piece of length (i+1), get price[i], then recurse on remaining length
            int val = price[i] + cutRodRecur(price, n - (i + 1));
            maxVal = Math.max(maxVal, val);
        }

        return maxVal;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int cutRodMemo(int[] price, int n, int[] memo) {
        if (n <= 0) return 0;
        if (memo[n] != -1) return memo[n];

        int maxVal = Integer.MIN_VALUE;
        for (int i = 0; i < n; i++) {
            int val = price[i] + cutRodMemo(price, n - (i + 1), memo);
            maxVal = Math.max(maxVal, val);
        }

        memo[n] = maxVal;
        return memo[n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int cutRodTab(int[] price, int n) {
        // dp[i] = max profit from rod of length i
        int[] dp = new int[n + 1];

        // dp[0] = 0 (no rod, no profit)

        // Build bottom-up: rod lengths 1, 2, ..., n
        for (int len = 1; len <= n; len++) {
            int maxVal = Integer.MIN_VALUE;
            // Try all possible first cuts
            for (int cut = 0; cut < len; cut++) {
                // Cut piece of length (cut+1) with price[cut]
                // Remaining length = len - (cut+1)
                int val = price[cut] + dp[len - (cut + 1)];
                maxVal = Math.max(maxVal, val);
            }
            dp[len] = maxVal;
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int[] price = {1, 5, 8, 9, 10, 17, 17, 20};
        int n = 8;

        System.out.println("Rod Cutting");
        System.out.println("Length: " + n);
        System.out.println("Prices: [1, 5, 8, 9, 10, 17, 17, 20]");

        System.out.println("Recursion: " + cutRodRecur(price, n));

        int[] memo = new int[n + 1];
        java.util.Arrays.fill(memo, -1);
        System.out.println("Memoization: " + cutRodMemo(price, n, memo));

        System.out.println("Tabulation: " + cutRodTab(price, n));
        // Expected: 22 (cut into 2+6: 5+17=22)
    }
}
```

---

# COIN CHANGE (NUMBER OF WAYS)

## Problem
Given unlimited coins of certain denominations and a target amount, find the NUMBER OF WAYS to make the amount. Order doesn't matter (combinations, not permutations).

## Think About It
This is Unbounded Knapsack where:
- Coin denominations = item weights
- We're counting NUMBER of ways to reach exact sum
- Recurrence: ways(i, sum) = ways(i-1, sum) + ways(i, sum - coins[i-1])

```java
public class CoinChangeWays {

    // ---- RECURSION (NAIVE) ----
    public static int countWaysRecur(int[] coins, int n, int sum) {
        // Base: sum = 0 -> 1 way (use no coins)
        if (sum == 0) return 1;
        // Base: no coins left but sum > 0 -> no way
        if (n == 0) return 0;

        // If coin > sum, skip it
        if (coins[n - 1] > sum) {
            return countWaysRecur(coins, n - 1, sum);
        }

        // Skip coin + use coin (stay at n because unlimited)
        return countWaysRecur(coins, n - 1, sum) +
               countWaysRecur(coins, n, sum - coins[n - 1]);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int countWaysMemo(int[] coins, int n, int sum, int[][] memo) {
        if (sum == 0) return 1;
        if (n == 0) return 0;

        if (memo[n][sum] != -1) return memo[n][sum];

        if (coins[n - 1] > sum) {
            memo[n][sum] = countWaysMemo(coins, n - 1, sum, memo);
        } else {
            memo[n][sum] = countWaysMemo(coins, n - 1, sum, memo) +
                           countWaysMemo(coins, n, sum - coins[n - 1], memo);
        }

        return memo[n][sum];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int countWaysTab(int[] coins, int sum) {
        int n = coins.length;
        int[][] dp = new int[n + 1][sum + 1];

        // Sum 0: 1 way (empty set of coins)
        for (int i = 0; i <= n; i++) dp[i][0] = 1;

        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= sum; s++) {
                if (coins[i - 1] <= s) {
                    // Skip coin OR use coin (stay at i for reuse)
                    dp[i][s] = dp[i - 1][s] + dp[i][s - coins[i - 1]];
                } else {
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        return dp[n][sum];
    }

    public static void main(String[] args) {
        int[] coins = {1, 2, 3};
        int sum = 4;

        System.out.println("Coin Change (Number of Ways)");
        System.out.println("Coins: [1, 2, 3], Amount: " + sum);

        System.out.println("Recursion: " + countWaysRecur(coins, coins.length, sum));

        int[][] memo = new int[coins.length + 1][sum + 1];
        for (int i = 0; i <= coins.length; i++)
            for (int s = 0; s <= sum; s++)
                memo[i][s] = -1;
        System.out.println("Memoization: " + countWaysMemo(coins, coins.length, sum, memo));

        System.out.println("Tabulation: " + countWaysTab(coins, sum));
        // Expected: 4
        // Ways: {1,1,1,1}, {1,1,2}, {1,3}, {2,2}
    }
}
```

# COIN CHANGE (MINIMUM COINS)

## Problem
Given unlimited coins of certain denominations and a target amount, find the MINIMUM NUMBER of coins needed to make the amount. If impossible, return -1.

## Think About It
This is different from "number of ways" — we want MINIMUM coins.
- For each coin, either take it (add 1 to count) or skip it
- `minCoins(sum) = 1 + min(minCoins(sum - coin) for each coin <= sum)`

```java
public class CoinChangeMin {

    // ---- RECURSION (NAIVE) ----
    public static int minCoinsRecur(int[] coins, int sum) {
        // Base: sum = 0 -> 0 coins needed
        if (sum == 0) return 0;

        int result = Integer.MAX_VALUE;

        // Try every coin
        for (int coin : coins) {
            if (coin <= sum) {
                int subResult = minCoinsRecur(coins, sum - coin);
                // If a solution exists, take min
                if (subResult != Integer.MAX_VALUE) {
                    result = Math.min(result, 1 + subResult);
                }
            }
        }

        return result;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minCoinsMemo(int[] coins, int sum, int[] memo) {
        if (sum == 0) return 0;
        if (memo[sum] != -1) return memo[sum];

        int result = Integer.MAX_VALUE;
        for (int coin : coins) {
            if (coin <= sum) {
                int subResult = minCoinsMemo(coins, sum - coin, memo);
                if (subResult != Integer.MAX_VALUE) {
                    result = Math.min(result, 1 + subResult);
                }
            }
        }

        memo[sum] = result;
        return memo[sum];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minCoinsTab(int[] coins, int sum) {
        // dp[s] = min coins to make amount s
        int[] dp = new int[sum + 1];

        // Initialize with a large number (sentinel for "impossible")
        java.util.Arrays.fill(dp, Integer.MAX_VALUE);
        dp[0] = 0; // 0 coins to make amount 0

        // Build bottom-up
        for (int s = 1; s <= sum; s++) {
            for (int coin : coins) {
                if (coin <= s && dp[s - coin] != Integer.MAX_VALUE) {
                    dp[s] = Math.min(dp[s], 1 + dp[s - coin]);
                }
            }
        }

        return dp[sum] == Integer.MAX_VALUE ? -1 : dp[sum];
    }

    public static void main(String[] args) {
        int[] coins = {1, 2, 5};
        int sum = 11;

        System.out.println("Coin Change (Minimum Coins)");
        System.out.println("Coins: [1, 2, 5], Amount: " + sum);

        int res = minCoinsRecur(coins, sum);
        System.out.println("Recursion: " + (res == Integer.MAX_VALUE ? -1 : res));

        int[] memo = new int[sum + 1];
        java.util.Arrays.fill(memo, -1);
        int memoRes = minCoinsMemo(coins, sum, memo);
        System.out.println("Memoization: " + (memoRes == Integer.MAX_VALUE ? -1 : memoRes));

        System.out.println("Tabulation: " + minCoinsTab(coins, sum));
        // Expected: 3 (5+5+1=11)
    }
}
```

---

# LONGEST COMMON SUBSEQUENCE (LCS)

## Problem
Given two strings, find the length of the LONGEST subsequence that appears in BOTH strings. A subsequence is a sequence that can be derived by deleting some characters WITHOUT changing order.

Example: "abcde" and "ace" -> LCS = "ace" (length 3)

## The DP Table Explained
For strings X = "abcde" and Y = "ace":

```
    0   a   c   e
0   0   0   0   0
a   0   1   1   1
b   0   1   1   1
c   0   1   2   2
d   0   1   2   2
e   0   1   2   3
```

**How to read:** dp[i][j] = LCS of X[0...i-1] and Y[0...j-1]

**Rule:** If chars match, dp[i][j] = 1 + dp[i-1][j-1] (diagonal + 1)
If not, dp[i][j] = max(dp[i-1][j], dp[i][j-1]) (max of left/above)

```java
public class LCS {

    // ---- RECURSION (NAIVE) ----
    public static int lcsRecur(String X, String Y, int m, int n) {
        // Base: empty string -> LCS is 0
        if (m == 0 || n == 0) return 0;

        // If last characters match
        if (X.charAt(m - 1) == Y.charAt(n - 1)) {
            return 1 + lcsRecur(X, Y, m - 1, n - 1);
        }

        // If not, take max of removing from X or removing from Y
        return Math.max(
            lcsRecur(X, Y, m - 1, n),
            lcsRecur(X, Y, m, n - 1)
        );
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int lcsMemo(String X, String Y, int m, int n, int[][] memo) {
        if (m == 0 || n == 0) return 0;

        if (memo[m][n] != -1) return memo[m][n];

        if (X.charAt(m - 1) == Y.charAt(n - 1)) {
            memo[m][n] = 1 + lcsMemo(X, Y, m - 1, n - 1, memo);
        } else {
            memo[m][n] = Math.max(
                lcsMemo(X, Y, m - 1, n, memo),
                lcsMemo(X, Y, m, n - 1, memo)
            );
        }

        return memo[m][n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int lcsTab(String X, String Y) {
        int m = X.length();
        int n = Y.length();
        int[][] dp = new int[m + 1][n + 1];

        // dp[0][*] and dp[*][0] are 0 by default

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }

        // Print table
        System.out.println("\nLCS DP Table:");
        System.out.print("    ");
        for (int j = 0; j <= n; j++) System.out.printf("%4c", j == 0 ? ' ' : Y.charAt(j - 1));
        System.out.println();
        for (int i = 0; i <= m; i++) {
            System.out.printf("%4c ", i == 0 ? ' ' : X.charAt(i - 1));
            for (int j = 0; j <= n; j++) {
                System.out.printf("%4d", dp[i][j]);
            }
            System.out.println();
        }

        return dp[m][n];
    }

    // BONUS: Print the actual LCS string
    public static String getLCS(String X, String Y) {
        int m = X.length(), n = Y.length();
        int[][] dp = new int[m + 1][n + 1];

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }

        // Backtrack to find the actual subsequence
        StringBuilder sb = new StringBuilder();
        int i = m, j = n;
        while (i > 0 && j > 0) {
            if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                sb.append(X.charAt(i - 1));
                i--;
                j--;
            } else if (dp[i - 1][j] > dp[i][j - 1]) {
                i--;
            } else {
                j--;
            }
        }

        return sb.reverse().toString();
    }

    public static void main(String[] args) {
        String X = "abcde";
        String Y = "ace";

        System.out.println("LCS of \"" + X + "\" and \"" + Y + "\"");

        System.out.println("Recursion: " + lcsRecur(X, Y, X.length(), Y.length()));

        int[][] memo = new int[X.length() + 1][Y.length() + 1];
        for (int i = 0; i <= X.length(); i++)
            for (int j = 0; j <= Y.length(); j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + lcsMemo(X, Y, X.length(), Y.length(), memo));

        System.out.println("Tabulation: " + lcsTab(X, Y));
        System.out.println("Actual LCS: " + getLCS(X, Y));
        // Expected: 3, "ace"
    }
}
```

---

# LONGEST COMMON SUBSTRING

## Problem
Find the length of the LONGEST substring (CONTIGUOUS characters) common to both strings.

## Key Difference from LCS:
- LCS: characters don't need to be contiguous, dp = 1 + dp[i-1][j-1] on match
- Substring: MUST be contiguous, dp = 0 on mismatch (break the chain!)

```java
public class LongestCommonSubstring {

    // ---- TABULATION (BOTTOM-UP) ----
    public static int longestCommonSubstring(String X, String Y) {
        int m = X.length(), n = Y.length();
        int[][] dp = new int[m + 1][n + 1];
        int maxLen = 0;
        int endIdx = 0; // To reconstruct the substring

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                    // Extend the common substring
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                    if (dp[i][j] > maxLen) {
                        maxLen = dp[i][j];
                        endIdx = i; // End position in X
                    }
                }
                // On mismatch: dp[i][j] stays 0 (break the chain)
                // This is the KEY difference from LCS!
            }
        }

        // Print table
        System.out.println("\nLongest Common Substring DP Table:");
        System.out.print("    ");
        for (int j = 0; j <= n; j++) System.out.printf("%4c", j == 0 ? ' ' : Y.charAt(j - 1));
        System.out.println();
        for (int i = 0; i <= m; i++) {
            System.out.printf("%4c ", i == 0 ? ' ' : X.charAt(i - 1));
            for (int j = 0; j <= n; j++) {
                System.out.printf("%4d", dp[i][j]);
            }
            System.out.println();
        }

        // Reconstruct the substring
        String substr = X.substring(endIdx - maxLen, endIdx);
        System.out.println("Longest common substring: \"" + substr + "\"");

        return maxLen;
    }

    public static void main(String[] args) {
        String X = "abcde";
        String Y = "abfce";

        System.out.println("Strings: \"" + X + "\", \"" + Y + "\"");
        System.out.println("Length: " + longestCommonSubstring(X, Y));
    }
}
```

---

# LONGEST INCREASING SUBSEQUENCE (LIS)

## Problem
Find the length of the longest subsequence where elements are in strictly increasing order.

Example: [10, 9, 2, 5, 3, 7, 101, 18] -> LIS = [2, 5, 7, 101] (length 4)

## Approach
For each element at position `i`, look at all previous elements `j < i`. If `arr[j] < arr[i]`, then we can extend the LIS ending at `j` to include `arr[i]`. Take the max.

```java
public class LIS {

    // ---- RECURSION (NAIVE) ----
    // lisEndingAt(i) = LIS length ending at index i
    public static int lisEndingAtRecur(int[] arr, int i) {
        // Base: each element is at least length 1 by itself
        int max = 1;

        // Check all previous elements
        for (int j = 0; j < i; j++) {
            if (arr[j] < arr[i]) {
                // We can extend the LIS ending at j
                max = Math.max(max, 1 + lisEndingAtRecur(arr, j));
            }
        }

        return max;
    }

    public static int lisRecur(int[] arr) {
        int n = arr.length;
        int max = 0;
        for (int i = 0; i < n; i++) {
            max = Math.max(max, lisEndingAtRecur(arr, i));
        }
        return max;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int lisEndingAtMemo(int[] arr, int i, int[] memo) {
        if (memo[i] != -1) return memo[i];

        int max = 1;
        for (int j = 0; j < i; j++) {
            if (arr[j] < arr[i]) {
                max = Math.max(max, 1 + lisEndingAtMemo(arr, j, memo));
            }
        }

        memo[i] = max;
        return memo[i];
    }

    public static int lisMemo(int[] arr) {
        int n = arr.length;
        int[] memo = new int[n];
        java.util.Arrays.fill(memo, -1);
        int max = 0;
        for (int i = 0; i < n; i++) {
            max = Math.max(max, lisEndingAtMemo(arr, i, memo));
        }
        return max;
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int lisTab(int[] arr) {
        int n = arr.length;
        // dp[i] = LIS length ending at index i
        int[] dp = new int[n];

        // Each element alone has LIS length 1
        java.util.Arrays.fill(dp, 1);

        // For each element, check all previous elements
        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (arr[j] < arr[i]) {
                    // We can extend the LIS ending at j
                    dp[i] = Math.max(dp[i], 1 + dp[j]);
                }
            }
        }

        // Answer is the maximum in dp
        int max = 0;
        for (int val : dp) {
            max = Math.max(max, val);
        }

        return max;
    }

    // ---- BINARY SEARCH APPROACH (O(n log n)) ----
    // This is an advanced optimization using patience sorting
    public static int lisBinarySearch(int[] arr) {
        // tails[i] = smallest possible tail of LIS of length i+1
        int[] tails = new int[arr.length];
        int len = 0;

        for (int x : arr) {
            // Binary search to find where x fits in tails
            int left = 0, right = len;
            while (left < right) {
                int mid = left + (right - left) / 2;
                if (tails[mid] < x) {
                    left = mid + 1;
                } else {
                    right = mid;
                }
            }
            tails[left] = x;
            if (left == len) len++;
        }

        return len;
    }

    public static void main(String[] args) {
        int[] arr = {10, 9, 2, 5, 3, 7, 101, 18};

        System.out.println("Array: [10, 9, 2, 5, 3, 7, 101, 18]");
        System.out.println("Recursion: " + lisRecur(arr));
        System.out.println("Memoization: " + lisMemo(arr));
        System.out.println("Tabulation: " + lisTab(arr));
        System.out.println("Binary Search: " + lisBinarySearch(arr));
        // Expected: 4 (2, 5, 7, 101)
    }
}
```

# EDIT DISTANCE (LEVENSHTEIN DISTANCE)

## Problem
Given two strings, find the MINIMUM number of operations (insert, delete, replace) to convert one string into another.

## Think About It
At each position (i, j):
1. If chars match: dp[i][j] = dp[i-1][j-1] (no operation needed)
2. If not: min of:
   - DELETE from word1: 1 + dp[i-1][j]
   - INSERT into word1: 1 + dp[i][j-1]
   - REPLACE: 1 + dp[i-1][j-1]

```java
public class EditDistance {

    // ---- RECURSION (NAIVE) ----
    public static int editDistRecur(String s1, String s2, int m, int n) {
        // If s1 is empty, insert all of s2 (n operations)
        if (m == 0) return n;
        // If s2 is empty, delete all of s1 (m operations)
        if (n == 0) return m;

        // If last chars match, move both pointers
        if (s1.charAt(m - 1) == s2.charAt(n - 1)) {
            return editDistRecur(s1, s2, m - 1, n - 1);
        }

        // Try delete, insert, replace — take minimum
        int delete = 1 + editDistRecur(s1, s2, m - 1, n);
        int insert = 1 + editDistRecur(s1, s2, m, n - 1);
        int replace = 1 + editDistRecur(s1, s2, m - 1, n - 1);

        return Math.min(delete, Math.min(insert, replace));
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int editDistMemo(String s1, String s2, int m, int n, int[][] memo) {
        if (m == 0) return n;
        if (n == 0) return m;

        if (memo[m][n] != -1) return memo[m][n];

        if (s1.charAt(m - 1) == s2.charAt(n - 1)) {
            memo[m][n] = editDistMemo(s1, s2, m - 1, n - 1, memo);
        } else {
            int delete = 1 + editDistMemo(s1, s2, m - 1, n, memo);
            int insert = 1 + editDistMemo(s1, s2, m, n - 1, memo);
            int replace = 1 + editDistMemo(s1, s2, m - 1, n - 1, memo);
            memo[m][n] = Math.min(delete, Math.min(insert, replace));
        }

        return memo[m][n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int editDistTab(String s1, String s2) {
        int m = s1.length(), n = s2.length();
        int[][] dp = new int[m + 1][n + 1];

        // Base: empty string cases
        for (int i = 0; i <= m; i++) dp[i][0] = i; // Delete all
        for (int j = 0; j <= n; j++) dp[0][j] = j; // Insert all

        // Fill table
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1];
                } else {
                    dp[i][j] = 1 + Math.min(
                        dp[i - 1][j],     // Delete from s1
                        Math.min(
                            dp[i][j - 1], // Insert into s1 (or delete from s2)
                            dp[i - 1][j - 1] // Replace
                        )
                    );
                }
            }
        }

        // Print table
        System.out.println("\nEdit Distance DP Table:");
        System.out.print("      ");
        for (int j = 0; j <= n; j++) System.out.printf("%4c", j == 0 ? '#' : s2.charAt(j - 1));
        System.out.println();
        for (int i = 0; i <= m; i++) {
            System.out.printf("%4c ", i == 0 ? '#' : s1.charAt(i - 1));
            for (int j = 0; j <= n; j++) {
                System.out.printf("%4d", dp[i][j]);
            }
            System.out.println();
        }

        return dp[m][n];
    }

    public static void main(String[] args) {
        String s1 = "horse";
        String s2 = "ros";

        System.out.println("Edit Distance: \"" + s1 + "\" -> \"" + s2 + "\"");
        System.out.println("Recursion: " + editDistRecur(s1, s2, s1.length(), s2.length()));

        int[][] memo = new int[s1.length() + 1][s2.length() + 1];
        for (int i = 0; i <= s1.length(); i++)
            for (int j = 0; j <= s2.length(); j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + editDistMemo(s1, s2, s1.length(), s2.length(), memo));

        System.out.println("Tabulation: " + editDistTab(s1, s2));
        // Expected: 3
        // horse -> rorse (replace h->r)
        // rorse -> rose (delete second r)
        // rose -> ros (delete e)
    }
}
```

---

# STRING CONVERSION (INSERT/DELETE ONLY)

## Problem
Find minimum number of INSERT and DELETE operations to convert string X to string Y (REPLACE not allowed).

## Think About It
1. Find LCS of X and Y (characters that are already in place)
2. Delete from X: |X| - |LCS|
3. Insert into X: |Y| - |LCS|
4. Total = |X| + |Y| - 2*|LCS|

```java
public class StringConversion {

    public static int stringConversionMinOps(String X, String Y) {
        int lcsLen = LCS.lcsTab(X, Y);

        int deletes = X.length() - lcsLen;
        int inserts = Y.length() - lcsLen;

        System.out.println("LCS length: " + lcsLen);
        System.out.println("Deletes needed: " + deletes);
        System.out.println("Inserts needed: " + inserts);

        return deletes + inserts;
    }

    public static void main(String[] args) {
        String X = "abcdef";
        String Y = "acbdf";

        System.out.println("Convert \"" + X + "\" to \"" + Y + "\"");
        System.out.println("Total operations: " + stringConversionMinOps(X, Y));
        // LCS = "acdf" (length 4)
        // Deletes: 6-4 = 2 (delete 'b', 'e')
        // Inserts: 5-4 = 1 (insert 'b')
        // Total: 3
    }
}
```

---

# WILDCARD MATCHING

## Problem
Given a string `s` and a pattern `p` with wildcards:
- `?` matches ANY SINGLE character
- `*` matches ANY SEQUENCE (including empty)

Return true if the pattern matches the entire string.

## Think About It
At (i, j) comparing s[i-1] and p[j-1]:
1. If chars match or p[j-1] == '?': dp[i][j] = dp[i-1][j-1]
2. If p[j-1] == '*': dp[i][j] = dp[i][j-1] (* matches empty) OR dp[i-1][j] (* matches one more char)

```java
public class WildcardMatching {

    // ---- RECURSION (NAIVE) ----
    public static boolean isMatchRecur(String s, String p, int m, int n) {
        // Both empty -> match
        if (m == 0 && n == 0) return true;
        // Pattern empty but string not -> no match
        if (n == 0) return false;
        // String empty: only matches if pattern is all '*'
        if (m == 0) {
            for (int i = 0; i < n; i++) {
                if (p.charAt(i) != '*') return false;
            }
            return true;
        }

        char sc = s.charAt(m - 1);
        char pc = p.charAt(n - 1);

        if (pc == '*') {
            // * matches empty (dp[i][j-1]) OR * matches one char (dp[i-1][j])
            return isMatchRecur(s, p, m, n - 1) ||
                   isMatchRecur(s, p, m - 1, n);
        } else if (pc == '?' || sc == pc) {
            return isMatchRecur(s, p, m - 1, n - 1);
        }

        return false;
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static boolean isMatchTab(String s, String p) {
        int m = s.length(), n = p.length();
        boolean[][] dp = new boolean[m + 1][n + 1];

        // Both empty
        dp[0][0] = true;

        // Empty string with pattern: only if all '*'
        for (int j = 1; j <= n; j++) {
            if (p.charAt(j - 1) == '*') {
                dp[0][j] = dp[0][j - 1];
            }
        }

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                char sc = s.charAt(i - 1);
                char pc = p.charAt(j - 1);

                if (pc == '*') {
                    // * matches empty (dp[i][j-1]) OR matches one char (dp[i-1][j])
                    dp[i][j] = dp[i][j - 1] || dp[i - 1][j];
                } else if (pc == '?' || sc == pc) {
                    dp[i][j] = dp[i - 1][j - 1];
                }
                // else: false (default)
            }
        }

        return dp[m][n];
    }

    public static void main(String[] args) {
        String[][] tests = {
            {"aa", "a"},
            {"aa", "*"},
            {"cb", "?a"},
            {"adceb", "*a*b"},
            {"acdcb", "a*c?b"}
        };

        for (String[] test : tests) {
            String s = test[0], p = test[1];
            boolean match1 = isMatchRecur(s, p, s.length(), p.length());
            boolean match2 = isMatchTab(s, p);
            System.out.println("isMatch(\"" + s + "\", \"" + p + "\") = " + match1 + " / " + match2);
        }
    }
}
```

---

# MATRIX CHAIN MULTIPLICATION (MCM)

## Problem
Given an array `arr[]` representing dimensions of matrices (matrix i has dimensions arr[i-1] x arr[i]), find the MINIMUM number of scalar multiplications needed to multiply the chain.

Example: arr = [10, 20, 30, 40, 30] -> 4 matrices: 10x20, 20x30, 30x40, 40x30

## Think About It
We need to PARENTHESIZE the multiplication to minimize cost. Different parenthesizations give different costs.

For matrices A (pxq) and B (qxr), multiplication cost = p x q x r.

MCM recurrence:
- `mcm(i, j)` = min cost to multiply matrices i through j
- If i == j: cost = 0 (only one matrix)
- Otherwise: try all possible split points k from i to j-1
- `mcm(i, j) = min(mcm(i, k) + mcm(k+1, j) + arr[i-1] * arr[k] * arr[j])`

```java
public class MCM {

    // ---- RECURSION (NAIVE) ----
    // mcmRecur(i, j) = min cost to multiply matrices i through j (1-indexed)
    public static int mcmRecur(int[] arr, int i, int j) {
        // Single matrix: no multiplication needed
        if (i == j) return 0;

        int minCost = Integer.MAX_VALUE;

        // Try every possible split point
        for (int k = i; k < j; k++) {
            // Cost = cost to multiply left chain + right chain + cost to combine
            int cost = mcmRecur(arr, i, k) +
                       mcmRecur(arr, k + 1, j) +
                       arr[i - 1] * arr[k] * arr[j];
            minCost = Math.min(minCost, cost);
        }

        return minCost;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int mcmMemo(int[] arr, int i, int j, int[][] memo) {
        if (i == j) return 0;

        if (memo[i][j] != -1) return memo[i][j];

        int minCost = Integer.MAX_VALUE;
        for (int k = i; k < j; k++) {
            int cost = mcmMemo(arr, i, k, memo) +
                       mcmMemo(arr, k + 1, j, memo) +
                       arr[i - 1] * arr[k] * arr[j];
            minCost = Math.min(minCost, cost);
        }

        memo[i][j] = minCost;
        return memo[i][j];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int mcmTab(int[] arr) {
        int n = arr.length; // Number of matrices = n - 1
        int[][] dp = new int[n][n];

        // dp[i][j] = min cost for matrices i..j
        // i == j case is 0 (already initialized)

        // Length of chain: 2, 3, ..., n-1
        for (int len = 2; len < n; len++) {
            for (int i = 1; i < n - len + 1; i++) {
                int j = i + len - 1;
                dp[i][j] = Integer.MAX_VALUE;

                for (int k = i; k < j; k++) {
                    int cost = dp[i][k] + dp[k + 1][j] +
                               arr[i - 1] * arr[k] * arr[j];
                    dp[i][j] = Math.min(dp[i][j], cost);
                }
            }
        }

        // Print table
        System.out.println("\nMCM DP Table:");
        for (int i = 1; i < n; i++) {
            for (int j = 1; j < n; j++) {
                if (i <= j && dp[i][j] > 0) {
                    System.out.println("dp[" + i + "][" + j + "] = " + dp[i][j]);
                }
            }
        }

        return dp[1][n - 1];
    }

    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 30};
        int n = arr.length;

        System.out.println("Matrix dimensions:");
        for (int i = 1; i < n; i++) {
            System.out.println("  A" + i + ": " + arr[i - 1] + "x" + arr[i]);
        }

        System.out.println("\nRecursion: " + mcmRecur(arr, 1, n - 1));

        int[][] memo = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + mcmMemo(arr, 1, n - 1, memo));

        System.out.println("Tabulation: " + mcmTab(arr));
    }
}
```

# PALINDROME PARTITIONING

## Problem
Given a string, partition it into substrings such that EVERY substring is a palindrome. Find the MINIMUM number of cuts needed.

Example: "nitin" -> 0 cuts (already palindrome)
Example: "aab" -> 1 cut ("aa" | "b")

## Think About It
Let `minCut(i, j)` = min cuts for substring s[i...j].
- If s[i...j] is palindrome: 0 cuts needed
- Else: try every split point k from i to j-1, take min

```java
public class PalindromePartitioning {

    // Helper: check if substring s[i...j] is palindrome
    private static boolean isPalindrome(String s, int i, int j) {
        while (i < j) {
            if (s.charAt(i) != s.charAt(j)) return false;
            i++;
            j--;
        }
        return true;
    }

    // ---- RECURSION (NAIVE) ----
    public static int minCutRecur(String s, int i, int j) {
        // Single character or palindrome: 0 cuts
        if (i >= j || isPalindrome(s, i, j)) return 0;

        int minCuts = Integer.MAX_VALUE;

        for (int k = i; k < j; k++) {
            int cuts = 1 + minCutRecur(s, i, k) + minCutRecur(s, k + 1, j);
            minCuts = Math.min(minCuts, cuts);
        }

        return minCuts;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minCutMemo(String s, int i, int j, int[][] memo) {
        if (i >= j || isPalindrome(s, i, j)) return 0;

        if (memo[i][j] != -1) return memo[i][j];

        int minCuts = Integer.MAX_VALUE;
        for (int k = i; k < j; k++) {
            int cuts = 1 + minCutMemo(s, i, k, memo) + minCutMemo(s, k + 1, j, memo);
            minCuts = Math.min(minCuts, cuts);
        }

        memo[i][j] = minCuts;
        return memo[i][j];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minCutTab(String s) {
        int n = s.length();

        // pal[i][j] = true if s[i...j] is palindrome
        boolean[][] pal = new boolean[n][n];

        // Every single character is a palindrome
        for (int i = 0; i < n; i++) pal[i][i] = true;

        // Fill palindrome table for longer substrings
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i < n - len + 1; i++) {
                int j = i + len - 1;
                if (len == 2) {
                    pal[i][j] = (s.charAt(i) == s.charAt(j));
                } else {
                    pal[i][j] = (s.charAt(i) == s.charAt(j)) && pal[i + 1][j - 1];
                }
            }
        }

        // dp[i] = min cuts for s[0...i]
        int[] dp = new int[n];

        for (int i = 0; i < n; i++) {
            if (pal[0][i]) {
                dp[i] = 0; // Already palindrome from start
            } else {
                dp[i] = Integer.MAX_VALUE;
                for (int j = 0; j < i; j++) {
                    if (pal[j + 1][i]) {
                        dp[i] = Math.min(dp[i], 1 + dp[j]);
                    }
                }
            }
        }

        return dp[n - 1];
    }

    public static void main(String[] args) {
        String s = "aab";

        System.out.println("String: \"" + s + "\"");
        System.out.println("Recursion: " + minCutRecur(s, 0, s.length() - 1));

        int n = s.length();
        int[][] memo = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + minCutMemo(s, 0, n - 1, memo));

        System.out.println("Tabulation: " + minCutTab(s));
        // Expected: 1 ("aa" | "b")
    }
}
```

---

# MINIMUM PARTITIONING (MIN SUBSET SUM DIFF)

## Problem
Given an array, partition it into TWO subsets such that the ABSOLUTE difference of their sums is MINIMIZED.

## Think About It
- Calculate total sum
- We need to find a subset with sum as close to `totalSum/2` as possible
- This is SUBSET SUM problem: find all achievable sums up to totalSum/2
- The closest achievable sum to totalSum/2 gives the min difference

```java
public class MinimumPartitioning {

    // ---- TABULATION ----
    public static int minDiffTab(int[] nums) {
        int totalSum = 0;
        for (int num : nums) totalSum += num;

        int target = totalSum / 2;
        int n = nums.length;

        // dp[i][s] = can we make sum 's' with first 'i' elements?
        boolean[][] dp = new boolean[n + 1][target + 1];

        // Sum 0 is always achievable
        for (int i = 0; i <= n; i++) dp[i][0] = true;

        // Fill subset sum table
        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= target; s++) {
                if (nums[i - 1] <= s) {
                    dp[i][s] = dp[i - 1][s] || dp[i - 1][s - nums[i - 1]];
                } else {
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        // Find the largest achievable sum <= target
        int sum1 = 0;
        for (int s = target; s >= 0; s--) {
            if (dp[n][s]) {
                sum1 = s;
                break;
            }
        }

        int sum2 = totalSum - sum1;
        return Math.abs(sum2 - sum1);
    }

    public static void main(String[] args) {
        int[] nums = {1, 6, 11, 5};

        System.out.println("Array: [1, 6, 11, 5]");
        System.out.println("Min difference: " + minDiffTab(nums));
        // Expected: 1
        // Subset 1: {1, 6, 5} = 12, Subset 2: {11} = 11, diff = 1
    }
}
```

---

# BOOLEAN PARENTHESIZATION

## Problem
Given a boolean expression with symbols (T, F) and operators (&, |, ^), find the NUMBER OF WAYS to parenthesize it so that it evaluates to TRUE.

Example: "T|T&F^T" — count ways to add parentheses to get TRUE

## Think About It
This is MCM-like. At each operator, we split the expression into left and right parts, then count ways for each.

For operator `&`: waysTrue = leftTrue * rightTrue
For operator `|`: waysTrue = total - (leftFalse * rightFalse)
For operator `^`: waysTrue = leftTrue*rightFalse + leftFalse*rightTrue

```java
public class BooleanParenthesization {

    // ---- RECURSION (NAIVE) ----
    // countWays(s, i, j, isTrue) = ways to evaluate s[i...j] to isTrue
    public static int countWaysRecur(String s, int i, int j, boolean isTrue) {
        // Base: single character
        if (i == j) {
            if (isTrue) return s.charAt(i) == 'T' ? 1 : 0;
            else return s.charAt(i) == 'F' ? 1 : 0;
        }

        int ways = 0;

        // Try each operator (at odd positions in string)
        for (int k = i + 1; k < j; k += 2) {
            char op = s.charAt(k);

            int leftTrue = countWaysRecur(s, i, k - 1, true);
            int leftFalse = countWaysRecur(s, i, k - 1, false);
            int rightTrue = countWaysRecur(s, k + 1, j, true);
            int rightFalse = countWaysRecur(s, k + 1, j, false);

            switch (op) {
                case '&':
                    if (isTrue) ways += leftTrue * rightTrue;
                    else ways += leftTrue * rightFalse + leftFalse * rightTrue + leftFalse * rightFalse;
                    break;
                case '|':
                    if (isTrue) ways += leftTrue * rightTrue + leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftFalse * rightFalse;
                    break;
                case '^':
                    if (isTrue) ways += leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftTrue * rightTrue + leftFalse * rightFalse;
                    break;
            }
        }

        return ways;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int countWaysMemo(String s, int i, int j, boolean isTrue, Integer[][][] memo) {
        if (i == j) {
            if (isTrue) return s.charAt(i) == 'T' ? 1 : 0;
            else return s.charAt(i) == 'F' ? 1 : 0;
        }

        int idx = isTrue ? 1 : 0;
        if (memo[i][j][idx] != null) return memo[i][j][idx];

        int ways = 0;
        for (int k = i + 1; k < j; k += 2) {
            char op = s.charAt(k);

            int leftTrue = countWaysMemo(s, i, k - 1, true, memo);
            int leftFalse = countWaysMemo(s, i, k - 1, false, memo);
            int rightTrue = countWaysMemo(s, k + 1, j, true, memo);
            int rightFalse = countWaysMemo(s, k + 1, j, false, memo);

            switch (op) {
                case '&':
                    if (isTrue) ways += leftTrue * rightTrue;
                    else ways += leftTrue * rightFalse + leftFalse * rightTrue + leftFalse * rightFalse;
                    break;
                case '|':
                    if (isTrue) ways += leftTrue * rightTrue + leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftFalse * rightFalse;
                    break;
                case '^':
                    if (isTrue) ways += leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftTrue * rightTrue + leftFalse * rightFalse;
                    break;
            }
        }

        memo[i][j][idx] = ways;
        return ways;
    }

    public static void main(String[] args) {
        String expr = "T|T&F^T";

        System.out.println("Expression: " + expr);
        System.out.println("Recursion: " + countWaysRecur(expr, 0, expr.length() - 1, true));

        int n = expr.length();
        Integer[][][] memo = new Integer[n][n][2];
        System.out.println("Memoization: " + countWaysMemo(expr, 0, n - 1, true, memo));
    }
}
```

# EGG DROPPING

## Problem
You have `k` eggs and a building with `n` floors. Find the MINIMUM number of attempts needed to find the CRITICAL floor (the highest floor from which an egg doesn't break). Eggs can break or survive.

## Think About It
At each floor `x`, an egg either:
1. **BREAKS**: you have k-1 eggs, need to check floors 1 to x-1
2. **SURVIVES**: you have k eggs, need to check floors x+1 to n

You want the floor choice that MINIMIZES the WORST-CASE attempts.

```
eggDrop(k, n) = min over all x of (1 + max(eggDrop(k-1, x-1), eggDrop(k, n-x)))
```

```java
public class EggDropping {

    // ---- RECURSION (NAIVE) ----
    public static int eggDropRecur(int k, int n) {
        // Base: 0 floors -> 0 attempts, 1 floor -> 1 attempt
        if (n == 0 || n == 1) return n;
        // Base: 1 egg -> must try all floors linearly
        if (k == 1) return n;

        int minAttempts = Integer.MAX_VALUE;

        // Try dropping from every floor
        for (int x = 1; x <= n; x++) {
            // Egg breaks: check floors below (x-1 floors, k-1 eggs)
            int breaks = eggDropRecur(k - 1, x - 1);
            // Egg survives: check floors above (n-x floors, k eggs)
            int survives = eggDropRecur(k, n - x);

            // Worst case of the two possibilities
            int worstCase = 1 + Math.max(breaks, survives);

            minAttempts = Math.min(minAttempts, worstCase);
        }

        return minAttempts;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int eggDropMemo(int k, int n, int[][] memo) {
        if (n == 0 || n == 1) return n;
        if (k == 1) return n;

        if (memo[k][n] != -1) return memo[k][n];

        int minAttempts = Integer.MAX_VALUE;
        for (int x = 1; x <= n; x++) {
            int breaks = eggDropMemo(k - 1, x - 1, memo);
            int survives = eggDropMemo(k, n - x, memo);
            minAttempts = Math.min(minAttempts, 1 + Math.max(breaks, survives));
        }

        memo[k][n] = minAttempts;
        return memo[k][n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int eggDropTab(int K, int N) {
        // dp[k][n] = min attempts with k eggs and n floors
        int[][] dp = new int[K + 1][N + 1];

        // 0 floors -> 0, 1 floor -> 1
        for (int k = 1; k <= K; k++) {
            dp[k][0] = 0;
            dp[k][1] = 1;
        }

        // 1 egg -> must try all floors linearly
        for (int n = 1; n <= N; n++) {
            dp[1][n] = n;
        }

        // Fill for remaining eggs and floors
        for (int k = 2; k <= K; k++) {
            for (int n = 2; n <= N; n++) {
                dp[k][n] = Integer.MAX_VALUE;
                // Try all floors
                for (int x = 1; x <= n; x++) {
                    int worstCase = 1 + Math.max(dp[k - 1][x - 1], dp[k][n - x]);
                    dp[k][n] = Math.min(dp[k][n], worstCase);
                }
            }
        }

        return dp[K][N];
    }

    // ---- OPTIMIZED TABULATION (with binary search) ----
    public static int eggDropTabOpt(int K, int N) {
        int[][] dp = new int[K + 1][N + 1];

        for (int k = 1; k <= K; k++) {
            dp[k][0] = 0;
            dp[k][1] = 1;
        }
        for (int n = 1; n <= N; n++) dp[1][n] = n;

        for (int k = 2; k <= K; k++) {
            for (int n = 2; n <= N; n++) {
                dp[k][n] = Integer.MAX_VALUE;
                int low = 1, high = n;
                while (low <= high) {
                    int mid = low + (high - low) / 2;
                    int breaks = dp[k - 1][mid - 1];
                    int survives = dp[k][n - mid];
                    int worstCase = 1 + Math.max(breaks, survives);
                    dp[k][n] = Math.min(dp[k][n], worstCase);
                    if (breaks < survives) {
                        low = mid + 1;
                    } else {
                        high = mid - 1;
                    }
                }
            }
        }

        return dp[K][N];
    }

    public static void main(String[] args) {
        int k = 2, n = 10;

        System.out.println("Eggs: " + k + ", Floors: " + n);
        System.out.println("Recursion: " + eggDropRecur(k, n));

        int[][] memo = new int[k + 1][n + 1];
        for (int i = 0; i <= k; i++)
            for (int j = 0; j <= n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + eggDropMemo(k, n, memo));

        System.out.println("Tabulation: " + eggDropTab(k, n));
        System.out.println("Tabulation Opt: " + eggDropTabOpt(k, n));
        // Expected: 4
    }
}
```

---

# DP ON TREES

## DIAMETER OF A BINARY TREE

### Problem
Find the longest path between any two nodes in a binary tree. The path may or may not pass through the root.

### Think About It
For each node, the diameter through that node = height(left) + height(right) + 1 (node itself). The overall diameter is the maximum of diameters through all nodes.

```java
// Tree node class
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;

    TreeNode(int val) {
        this.val = val;
    }
}

public class TreeDiameter {

    // Global variable to store max diameter found so far
    private static int maxDiameter;

    // Helper: returns height of tree rooted at node
    // AND updates maxDiameter
    private static int height(TreeNode node) {
        if (node == null) return 0;

        // Get height of left and right subtrees
        int leftHeight = height(node.left);
        int rightHeight = height(node.right);

        // Diameter through this node = leftHeight + rightHeight
        // (path goes from deepest left leaf to deepest right leaf through this node)
        maxDiameter = Math.max(maxDiameter, leftHeight + rightHeight);

        // Return height of this subtree
        return 1 + Math.max(leftHeight, rightHeight);
    }

    public static int diameterOfBinaryTree(TreeNode root) {
        maxDiameter = 0;
        height(root);
        return maxDiameter;
    }

    public static void main(String[] args) {
        // Build a test tree:
        //       1
        //      / \
        //     2   3
        //    / \
        //   4   5
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        System.out.println("Diameter of tree: " + diameterOfBinaryTree(root));
        // Expected: 3 (path 4->2->5, or 4->2->1->3, length = 3 edges)
    }
}
```

---

## MAX PATH SUM (ANY NODE TO ANY NODE)

### Problem
Find the maximum sum along any path in a binary tree. The path can start and end at any node.

### Think About It
For each node, the max path sum through that node = node.val + max(0, leftMax) + max(0, rightMax). We track the global maximum across all nodes.

```java
public class MaxPathSum {

    private static int maxSum;

    // Helper: returns max sum from this node down to any leaf
    // "max single path" = node.val + max(0, leftBest, rightBest)
    private static int maxPathDown(TreeNode node) {
        if (node == null) return 0;

        // Max sum from left (ignore negative paths)
        int left = Math.max(0, maxPathDown(node.left));
        // Max sum from right (ignore negative paths)
        int right = Math.max(0, maxPathDown(node.right));

        // Max path through this node (arch shape: left -> node -> right)
        maxSum = Math.max(maxSum, node.val + left + right);

        // Return max single path going down from this node
        return node.val + Math.max(left, right);
    }

    public static int maxPathSum(TreeNode root) {
        maxSum = Integer.MIN_VALUE;
        maxPathDown(root);
        return maxSum;
    }

    public static void main(String[] args) {
        //        -10
        //        /  \
        //       9   20
        //          /  \
        //         15   7
        TreeNode root = new TreeNode(-10);
        root.left = new TreeNode(9);
        root.right = new TreeNode(20);
        root.right.left = new TreeNode(15);
        root.right.right = new TreeNode(7);

        System.out.println("Max path sum: " + maxPathSum(root));
        // Expected: 42 (15 + 20 + 7 = 42)
    }
}
```

---

# CATALAN NUMBERS

## What are Catalan Numbers?
A sequence of natural numbers that appear in many counting problems.

Formula: `C(0) = 1`, `C(n+1) = sum(C(i) * C(n-i)) for i = 0 to n`

Sequence: 1, 1, 2, 5, 14, 42, 132, 429, 1430...

## Applications:
1. Number of BSTs with n nodes
2. Number of valid parentheses expressions with n pairs
3. Number of triangulations of a convex polygon
4. Number of mountain ranges
5. Number of full binary trees with n+1 leaves

```java
public class CatalanNumbers {

    // ---- RECURSION (NAIVE) ----
    public static int catalanRecur(int n) {
        if (n <= 1) return 1;

        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += catalanRecur(i) * catalanRecur(n - 1 - i);
        }

        return sum;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int catalanMemo(int n, int[] memo) {
        if (n <= 1) return 1;
        if (memo[n] != -1) return memo[n];

        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += catalanMemo(i, memo) * catalanMemo(n - 1 - i, memo);
        }

        memo[n] = sum;
        return memo[n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int catalanTab(int n) {
        int[] dp = new int[n + 1];
        dp[0] = 1;
        dp[1] = 1;

        for (int i = 2; i <= n; i++) {
            for (int j = 0; j < i; j++) {
                dp[i] += dp[j] * dp[i - 1 - j];
            }
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int n = 10;

        System.out.println("Catalan Numbers up to C(" + n + "):");
        for (int i = 0; i <= n; i++) {
            System.out.println("C(" + i + ") = " + catalanTab(i));
        }
    }
}
```

## COUNT BSTs WITH N NODES

### Problem
Given n nodes labeled 1 to n, how many structurally unique BSTs can be formed?

### Think About It
For each root k (1 to n):
- Left subtree has k-1 nodes -> C(k-1) BSTs
- Right subtree has n-k nodes -> C(n-k) BSTs
- Total for root k = C(k-1) * C(n-k)

This is EXACTLY the Catalan number! C(n) = sum(C(k-1) * C(n-k)) for k=1 to n

```java
public class CountBSTs {

    // Uses Catalan numbers formula
    public static int countBSTs(int n) {
        return CatalanNumbers.catalanTab(n);
    }

    // ---- DP TABULATION (explicit) ----
    public static int countBSTsTab(int n) {
        // dp[i] = number of BSTs with i nodes
        int[] dp = new int[n + 1];
        dp[0] = 1; // Empty tree
        dp[1] = 1; // Single node

        for (int i = 2; i <= n; i++) {
            for (int j = 0; j < i; j++) {
                // j nodes in left subtree, i-1-j nodes in right subtree
                dp[i] += dp[j] * dp[i - 1 - j];
            }
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int n = 5;

        System.out.println("Number of BSTs with " + n + " nodes: " + countBSTs(n));
        // Expected: 42

        System.out.println("\nBST counts for n = 0 to 10:");
        for (int i = 0; i <= 10; i++) {
            System.out.println("n=" + i + ": " + countBSTsTab(i));
        }
    }
}
```

---

## MOUNTAIN RANGES

### Problem
Given n pairs of up-strokes (/) and down-strokes (\), how many mountain ranges can you form that never go below sea level?

### Think About It
This is another Catalan number application! You need n up-strokes and n down-strokes, and at any point the number of up-strokes >= down-strokes.

Same as valid parentheses: up = open, down = close.

```java
public class MountainRanges {

    public static int countMountainRanges(int n) {
        return CatalanNumbers.catalanTab(n);
    }

    public static void main(String[] args) {
        int n = 4;

        System.out.println("Number of mountain ranges with " + n + " up/down pairs: " +
                           countMountainRanges(n));
        // Expected: 14 (C(4) = 14)
    }
}
```

---

## MINIMUM SCORE TRIANGULATION

### Problem
You have a convex polygon with n vertices labeled 0 to n-1, each with a value. Triangulate the polygon (connect non-adjacent vertices with chords). Score = sum of the product of 3 vertices in each triangle. Minimize the total score.

### Think About It
This is another Catalan/ MCM-like problem!
- Choose a triangle formed by vertices i, k, j (where i < k < j)
- This splits the polygon into two sub-polygons: i...k and k...j
- Score(i, j) = min(Score(i, k) + Score(k, j) + values[i] * values[k] * values[j])

```java
public class MinimumScoreTriangulation {

    // ---- RECURSION (NAIVE) ----
    public static int minScoreRecur(int[] values, int i, int j) {
        // Base: need at least 3 vertices for a triangle
        if (j - i < 2) return 0;

        int minScore = Integer.MAX_VALUE;
        for (int k = i + 1; k < j; k++) {
            int score = minScoreRecur(values, i, k) +
                        minScoreRecur(values, k, j) +
                        values[i] * values[k] * values[j];
            minScore = Math.min(minScore, score);
        }

        return minScore;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minScoreMemo(int[] values, int i, int j, int[][] memo) {
        if (j - i < 2) return 0;

        if (memo[i][j] != -1) return memo[i][j];

        int minScore = Integer.MAX_VALUE;
        for (int k = i + 1; k < j; k++) {
            int score = minScoreMemo(values, i, k, memo) +
                        minScoreMemo(values, k, j, memo) +
                        values[i] * values[k] * values[j];
            minScore = Math.min(minScore, score);
        }

        memo[i][j] = minScore;
        return memo[i][j];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minScoreTab(int[] values) {
        int n = values.length;
        int[][] dp = new int[n][n];

        // Fill for increasing length
        for (int len = 2; len < n; len++) {
            for (int i = 0; i < n - len; i++) {
                int j = i + len;
                dp[i][j] = Integer.MAX_VALUE;
                for (int k = i + 1; k < j; k++) {
                    dp[i][j] = Math.min(dp[i][j],
                        dp[i][k] + dp[k][j] + values[i] * values[k] * values[j]);
                }
            }
        }

        return dp[0][n - 1];
    }

    public static void main(String[] args) {
        int[] values = {1, 2, 3, 4};

        System.out.println("Polygon vertex values: [1, 2, 3, 4]");
        System.out.println("Recursion: " + minScoreRecur(values, 0, values.length - 1));

        int n = values.length;
        int[][] memo = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + minScoreMemo(values, 0, n - 1, memo));

        System.out.println("Tabulation: " + minScoreTab(values));
        // Expected: 18 (triangulate (0,1,2)=6 + (0,2,3)=12 = 18)
    }
}
```

---

# KADANE'S ALGORITHM (MAX SUBARRAY SUM)

## Problem
Find the maximum sum of any CONTIGUOUS subarray.

## Think About It
Instead of trying all subarrays (O(n^2)), we scan left to right. At each element, we decide:
- Start new subarray at this element -> nums[i]
- Extend existing subarray -> currentSum + nums[i]

If `currentSum` becomes negative, it's better to start fresh (because a negative sum only hurts future sums).

```java
public class KadaneAlgorithm {

    // ---- KADANE'S ALGORITHM (THE BEST DP FOR THIS) ----
    public static int maxSubarraySum(int[] nums) {
        // maxEndingHere = max sum of subarray ENDING at current position
        // maxSoFar = overall max sum seen so far

        int maxEndingHere = nums[0];
        int maxSoFar = nums[0];

        for (int i = 1; i < nums.length; i++) {
            // Either extend the subarray or start fresh
            maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
            // Update global maximum
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }

        return maxSoFar;
    }

    // ---- KADANE'S WITH SUBARRAY INDICES ----
    public static int[] maxSubarrayWithIndices(int[] nums) {
        int maxEndingHere = nums[0];
        int maxSoFar = nums[0];
        int start = 0, end = 0;
        int tempStart = 0;

        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > maxEndingHere + nums[i]) {
                // Start new subarray at i
                maxEndingHere = nums[i];
                tempStart = i;
            } else {
                // Extend current subarray
                maxEndingHere = maxEndingHere + nums[i];
            }

            if (maxEndingHere > maxSoFar) {
                maxSoFar = maxEndingHere;
                start = tempStart;
                end = i;
            }
        }

        return new int[]{maxSoFar, start, end};
    }

    // ---- DP TABULATION approach ----
    public static int maxSubarrayDP(int[] nums) {
        int n = nums.length;
        // dp[i] = max subarray sum ENDING at index i
        int[] dp = new int[n];
        dp[0] = nums[0];
        int max = dp[0];

        for (int i = 1; i < n; i++) {
            // Either extend previous subarray or start here
            dp[i] = Math.max(nums[i], dp[i - 1] + nums[i]);
            max = Math.max(max, dp[i]);
        }

        return max;
    }

    public static void main(String[] args) {
        int[] nums = {-2, 1, -3, 4, -1, 2, 1, -5, 4};

        System.out.println("Array: [-2, 1, -3, 4, -1, 2, 1, -5, 4]");
        System.out.println("Kadane's Algorithm: " + maxSubarraySum(nums));
        // Expected: 6 (subarray [4, -1, 2, 1])

        int[] result = maxSubarrayWithIndices(nums);
        System.out.println("Max sum: " + result[0] + ", from index " + result[1] + " to " + result[2]);

        System.out.println("DP approach: " + maxSubarrayDP(nums));
    }
}
```

---

# SEGMENT TREES

## WHAT IS A SEGMENT TREE?

Imagine you have an array and you need to answer MANY range queries (like "what's the sum from index 2 to 7?") AND also update elements frequently.

### Naive approach:
- Query: loop from i to j — O(n) per query
- Update: just change the element — O(1)
- For q queries: O(q * n) — SLOW

### Segment Tree approach:
- Pre-process the array into a tree structure where each node represents a segment (range) of the array
- Query: O(log n) — MUCH faster
- Update: O(log n) — also fast

### Structure:
- Root = entire array [0, n-1]
- Left child = left half, Right child = right half
- Leaf nodes = single elements

```
                [0,5]
              /       \
          [0,2]        [3,5]
         /     \       /    \
      [0,1]   [2,2] [3,4]  [5,5]
     /    \          /   \
  [0,0] [1,1]    [3,3] [4,4]
```

## SEGMENT TREE FOR RANGE SUM

```java
public class SegmentTreeSum {

    private int[] tree; // Tree array (size = 4 * n)
    private int n;      // Size of original array

    // Constructor: builds the segment tree
    public SegmentTreeSum(int[] arr) {
        this.n = arr.length;
        tree = new int[4 * n]; // 4*n is safe for any n
        build(arr, 0, 0, n - 1);
    }

    // ---- BUILD SEGMENT TREE ----
    // node = current node index in tree array
    // start, end = range in original array this node represents
    private void build(int[] arr, int node, int start, int end) {
        // Leaf node: represents a single element
        if (start == end) {
            tree[node] = arr[start];
            return;
        }

        int mid = start + (end - start) / 2;
        int leftChild = 2 * node + 1;
        int rightChild = 2 * node + 2;

        // Build left and right subtrees
        build(arr, leftChild, start, mid);
        build(arr, rightChild, mid + 1, end);

        // Internal node: sum of its children
        tree[node] = tree[leftChild] + tree[rightChild];
    }

    // ---- RANGE SUM QUERY ----
    // query(l, r) = sum of arr[l...r]
    public int query(int l, int r) {
        return query(0, 0, n - 1, l, r);
    }

    private int query(int node, int start, int end, int l, int r) {
        // Case 1: No overlap — return 0
        if (r < start || l > end) {
            return 0;
        }

        // Case 2: Complete overlap — return this node's value
        if (l <= start && end <= r) {
            return tree[node];
        }

        // Case 3: Partial overlap — recurse on children
        int mid = start + (end - start) / 2;
        int leftChild = 2 * node + 1;
        int rightChild = 2 * node + 2;

        int leftSum = query(leftChild, start, mid, l, r);
        int rightSum = query(rightChild, mid + 1, end, l, r);

        return leftSum + rightSum;
    }

    // ---- POINT UPDATE ----
    // update(idx, val) = set arr[idx] = val
    public void update(int idx, int val) {
        update(0, 0, n - 1, idx, val);
    }

    private void update(int node, int start, int end, int idx, int val) {
        // Leaf node: update value
        if (start == end) {
            tree[node] = val;
            return;
        }

        int mid = start + (end - start) / 2;
        int leftChild = 2 * node + 1;
        int rightChild = 2 * node + 2;

        // Recurse on the correct child
        if (idx <= mid) {
            update(leftChild, start, mid, idx, val);
        } else {
            update(rightChild, mid + 1, end, idx, val);
        }

        // Recompute this node's value after child updates
        tree[node] = tree[leftChild] + tree[rightChild];
    }

    // Print tree (for debugging)
    public void printTree() {
        System.out.print("Segment Tree: ");
        for (int i = 0; i < 4 * n; i++) {
            System.out.print(tree[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11};

        System.out.println("Array: [1, 3, 5, 7, 9, 11]");

        SegmentTreeSum segTree = new SegmentTreeSum(arr);
        segTree.printTree();

        System.out.println("Sum of range [1, 3]: " + segTree.query(1, 3));
        // Expected: 3 + 5 + 7 = 15

        System.out.println("Sum of range [0, 5]: " + segTree.query(0, 5));
        // Expected: 36

        System.out.println("Updating index 2 to value 10...");
        segTree.update(2, 10);
        // Array is now: [1, 3, 10, 7, 9, 11]

        System.out.println("Sum of range [1, 3]: " + segTree.query(1, 3));
        // Expected: 3 + 10 + 7 = 20
    }
}
```

---

## SEGMENT TREE FOR RANGE MINIMUM QUERY (RMQ)

```java
public class SegmentTreeMin {

    private int[] tree;
    private int n;

    public SegmentTreeMin(int[] arr) {
        this.n = arr.length;
        tree = new int[4 * n];
        build(arr, 0, 0, n - 1);
    }

    // ---- BUILD ----
    private void build(int[] arr, int node, int start, int end) {
        if (start == end) {
            tree[node] = arr[start];
            return;
        }

        int mid = start + (end - start) / 2;
        int left = 2 * node + 1;
        int right = 2 * node + 2;

        build(arr, left, start, mid);
        build(arr, right, mid + 1, end);

        // For range MIN: store the minimum of children
        tree[node] = Math.min(tree[left], tree[right]);
    }

    // ---- QUERY (RANGE MINIMUM) ----
    public int query(int l, int r) {
        return query(0, 0, n - 1, l, r);
    }

    private int query(int node, int start, int end, int l, int r) {
        // No overlap: return INFINITY (so it doesn't affect min)
        if (r < start || l > end) {
            return Integer.MAX_VALUE;
        }

        // Complete overlap
        if (l <= start && end <= r) {
            return tree[node];
        }

        int mid = start + (end - start) / 2;
        int left = 2 * node + 1;
        int right = 2 * node + 2;

        int leftMin = query(left, start, mid, l, r);
        int rightMin = query(right, mid + 1, end, l, r);

        return Math.min(leftMin, rightMin);
    }

    // ---- POINT UPDATE ----
    public void update(int idx, int val) {
        update(0, 0, n - 1, idx, val);
    }

    private void update(int node, int start, int end, int idx, int val) {
        if (start == end) {
            tree[node] = val;
            return;
        }

        int mid = start + (end - start) / 2;
        int left = 2 * node + 1;
        int right = 2 * node + 2;

        if (idx <= mid) {
            update(left, start, mid, idx, val);
        } else {
            update(right, mid + 1, end, idx, val);
        }

        tree[node] = Math.min(tree[left], tree[right]);
    }

    public static void main(String[] args) {
        int[] arr = {2, 5, 1, 8, 3, 7};

        System.out.println("Array: [2, 5, 1, 8, 3, 7]");

        SegmentTreeMin segTree = new SegmentTreeMin(arr);

        System.out.println("Min of range [0, 2]: " + segTree.query(0, 2));
        // Expected: 1 (min of 2, 5, 1)

        System.out.println("Min of range [2, 5]: " + segTree.query(2, 5));
        // Expected: 1 (min of 1, 8, 3, 7)

        System.out.println("Min of range [3, 4]: " + segTree.query(3, 4));
        // Expected: 3 (min of 8, 3)

        System.out.println("Updating index 2 to value 10...");
        segTree.update(2, 10);
        // Array is now: [2, 5, 10, 8, 3, 7]

        System.out.println("Min of range [0, 2]: " + segTree.query(0, 2));
        // Expected: 2 (min of 2, 5, 10)
    }
}
```

---

## LAZY PROPAGATION IN SEGMENT TREES

### Problem with Range Updates
What if we need to update a RANGE (not just a single point)? Like "add 5 to all elements from index 2 to 7"?

If we do point updates for each element, that's O(n log n) per range update — SLOW.

### Lazy Propagation = The Smart Way
Instead of updating all nodes immediately, we "postpone" updates. When a node's entire segment needs updating, we:
1. Update the node itself
2. Mark it as "lazy" (has pending updates)
3. Only propagate to children when needed (during a query or partial update)

```java
public class SegmentTreeLazy {

    private int[] tree; // Segment tree
    private int[] lazy; // Lazy propagation array
    private int n;

    public SegmentTreeLazy(int[] arr) {
        this.n = arr.length;
        tree = new int[4 * n];
        lazy = new int[4 * n]; // All 0 initially (no pending updates)
        build(arr, 0, 0, n - 1);
    }

    // ---- BUILD ----
    private void build(int[] arr, int node, int start, int end) {
        if (start == end) {
            tree[node] = arr[start];
            return;
        }

        int mid = start + (end - start) / 2;
        build(arr, 2 * node + 1, start, mid);
        build(arr, 2 * node + 2, mid + 1, end);
        tree[node] = tree[2 * node + 1] + tree[2 * node + 2];
    }

    // ---- LAZY UPDATE HELPER ----
    // Apply pending lazy update to a node and push to children
    private void applyLazy(int node, int start, int end) {
        if (lazy[node] != 0) {
            // Apply the pending update to this node
            // For sum: add lazy[node] to each element in range
            tree[node] += (end - start + 1) * lazy[node];

            // If not leaf, propagate lazy value to children
            if (start != end) {
                lazy[2 * node + 1] += lazy[node];
                lazy[2 * node + 2] += lazy[node];
            }

            // Clear this node's lazy
            lazy[node] = 0;
        }
    }

    // ---- RANGE UPDATE (add val to all elements in [l, r]) ----
    public void rangeUpdate(int l, int r, int val) {
        rangeUpdate(0, 0, n - 1, l, r, val);
    }

    private void rangeUpdate(int node, int start, int end, int l, int r, int val) {
        // Apply any pending lazy updates FIRST
        applyLazy(node, start, end);

        // No overlap
        if (r < start || l > end) return;

        // Complete overlap — update this node and mark lazy
        if (l <= start && end <= r) {
            tree[node] += (end - start + 1) * val;

            // If not leaf, mark children as lazy
            if (start != end) {
                lazy[2 * node + 1] += val;
                lazy[2 * node + 2] += val;
            }

            return;
        }

        // Partial overlap — recurse
        int mid = start + (end - start) / 2;
        rangeUpdate(2 * node + 1, start, mid, l, r, val);
        rangeUpdate(2 * node + 2, mid + 1, end, l, r, val);

        // After children updated, recompute this node
        tree[node] = tree[2 * node + 1] + tree[2 * node + 2];
    }

    // ---- RANGE SUM QUERY (with lazy consideration) ----
    public int rangeSum(int l, int r) {
        return rangeSum(0, 0, n - 1, l, r);
    }

    private int rangeSum(int node, int start, int end, int l, int r) {
        // Apply pending lazy before anything
        applyLazy(node, start, end);

        // No overlap
        if (r < start || l > end) return 0;

        // Complete overlap
        if (l <= start && end <= r) return tree[node];

        // Partial overlap
        int mid = start + (end - start) / 2;
        int leftSum = rangeSum(2 * node + 1, start, mid, l, r);
        int rightSum = rangeSum(2 * node + 2, mid + 1, end, l, r);

        return leftSum + rightSum;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8};

        System.out.println("Array: [1, 2, 3, 4, 5, 6, 7, 8]");

        SegmentTreeLazy segTree = new SegmentTreeLazy(arr);

        System.out.println("Sum [0, 7]: " + segTree.rangeSum(0, 7));
        // Expected: 36

        System.out.println("Sum [2, 4]: " + segTree.rangeSum(2, 4));
        // Expected: 3+4+5 = 12

        System.out.println("\nAdding +10 to range [2, 5]...");
        segTree.rangeUpdate(2, 5, 10);
        // Array is now: [1, 2, 13, 14, 15, 16, 7, 8]

        System.out.println("Sum [2, 4]: " + segTree.rangeSum(2, 4));
        // Expected: 13+14+15 = 42

        System.out.println("Sum [0, 7]: " + segTree.rangeSum(0, 7));
        // Expected: 36 + 40 (4 elements * 10) = 76

        System.out.println("\nAdding +20 to range [0, 2]...");
        segTree.rangeUpdate(0, 2, 20);
        // Array is now: [21, 22, 33, 14, 15, 16, 7, 8]

        System.out.println("Sum [0, 3]: " + segTree.rangeSum(0, 3));
        // Expected: 21+22+33+14 = 90
    }
}
```

---

## WHEN TO USE LAZY PROPAGATION?

| Operation | Normal Segment Tree | Lazy Segment Tree |
|-----------|-------------------|-------------------|
| Point update | O(log n) | O(log n) |
| Range update | O(n log n) | O(log n) |
| Range query | O(log n) | O(log n) |

Use lazy propagation when you need RANGE UPDATES (not just point updates).

---

# FENWICK TREE (BINARY INDEXED TREE / BIT)

## What is a Fenwick Tree?

A tree structure that efficiently handles PREFIX SUM queries and point updates.

### Key Concept: Index Based on LSB (Least Significant Bit)
Each index `i` stores the sum of a range ending at `i`. The range length = 2^k where k is the position of the LSB of i.

```
Index:    1   2   3   4   5   6   7   8
Binary:   1  10  11 100 101 110 111 1000
LSB:     2^0 2^1 2^0 2^2 2^0 2^1 2^0 2^3
Range:   1   1-2  3  1-4  5  5-6  7  1-8
```

### Operations:
- **Update**: Add value at index i, propagate to ancestors (i += LSB(i))
- **Prefix Sum**: Sum of [0...i], visit ancestors (i -= LSB(i))
- **Range Sum**: prefixSum(r) - prefixSum(l-1)

```java
public class FenwickTree {

    private int[] bit; // Binary Indexed Tree (1-indexed internally)
    private int n;

    // Constructor: build BIT from array
    public FenwickTree(int[] arr) {
        this.n = arr.length;
        bit = new int[n + 1]; // 1-indexed, index 0 is dummy

        // Initialize with zeros, then add each element
        for (int i = 0; i < n; i++) {
            add(i, arr[i]);
        }
    }

    // Helper: get least significant bit
    private int LSB(int x) {
        return x & (-x); // Isolates the lowest set bit
    }

    // ---- POINT UPDATE: add delta at index idx (0-indexed) ----
    public void add(int idx, int delta) {
        // Convert to 1-indexed
        int i = idx + 1;

        // Traverse up the tree, adding delta to all ancestors
        while (i <= n) {
            bit[i] += delta;
            i += LSB(i); // Go to parent
        }
    }

    // ---- PREFIX SUM: sum of arr[0...idx] ----
    public int prefixSum(int idx) {
        int i = idx + 1; // Convert to 1-indexed
        int sum = 0;

        // Traverse down, collecting sums
        while (i > 0) {
            sum += bit[i];
            i -= LSB(i); // Remove LSB to go to next range
        }

        return sum;
    }

    // ---- RANGE SUM: sum of arr[l...r] ----
    public int rangeSum(int l, int r) {
        if (l == 0) return prefixSum(r);
        return prefixSum(r) - prefixSum(l - 1);
    }

    // ---- POINT UPDATE: set arr[idx] = val ----
    public void set(int idx, int val) {
        // Current value at idx
        int current = rangeSum(idx, idx);
        // Add the difference
        add(idx, val - current);
    }

    // Print BIT (for debugging)
    public void printBIT() {
        System.out.print("BIT: ");
        for (int i = 1; i <= n; i++) {
            System.out.print(bit[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr = {3, 2, -1, 6, 5, 4, -3, 3, 7, 2, 3};

        System.out.println("Array: [3, 2, -1, 6, 5, 4, -3, 3, 7, 2, 3]");

        FenwickTree ft = new FenwickTree(arr);
        ft.printBIT();

        System.out.println("Prefix sum up to index 4: " + ft.prefixSum(4));
        // Expected: 3+2+(-1)+6+5 = 15

        System.out.println("Range sum [2, 6]: " + ft.rangeSum(2, 6));
        // Expected: (-1)+6+5+4+(-3) = 11

        System.out.println("Adding +10 at index 3...");
        ft.add(3, 10);
        // Array is now: [3, 2, -1, 16, 5, 4, -3, 3, 7, 2, 3]

        System.out.println("Prefix sum up to index 4: " + ft.prefixSum(4));
        // Expected: 3+2+(-1)+16+5 = 25

        System.out.println("Setting index 5 to value 0...");
        ft.set(5, 0);
        // Array is now: [3, 2, -1, 16, 5, 0, -3, 3, 7, 2, 3]

        System.out.println("Range sum [2, 6]: " + ft.rangeSum(2, 6));
        // Expected: (-1)+16+5+0+(-3) = 17
    }
}
```

---

## FENWICK TREE vs SEGMENT TREE

| Feature | Fenwick Tree (BIT) | Segment Tree |
|---------|-------------------|-------------|
| Build | O(n) | O(n) |
| Point Update | O(log n) | O(log n) |
| Range Update | Not directly supported | O(log n) with lazy |
| Prefix Query | O(log n) | O(log n) |
| Range Query | O(log n) | O(log n) |
| Memory | n+1 | 4n |
| Code Complexity | Very simple | More complex |

**When to use Fenwick Tree:**
- You only need prefix sums and point updates
- You want simpler, shorter code
- Memory is a concern

**When to use Segment Tree:**
- You need range updates (with lazy propagation)
- You need range minimum/maximum queries
- You need more complex queries (like range min + range sum)

---

# CONCLUSION

## DP Decision Flowchart

1. **Can you brute-force recursively?** Yes -> It might be a DP problem
2. **Are there overlapping subproblems?** Yes -> DP will help
3. **Does the problem have optimal substructure?** Yes -> DP applies
4. **Which approach?**
   - Start with **Recursion** to understand the recurrence relation
   - Add **Memoization** to make it fast (top-down)
   - Convert to **Tabulation** if you want iterative (bottom-up)

## Common DP Patterns

| Pattern | Example | Recurrence |
|---------|---------|------------|
| Fibonacci-like | Climbing Stairs | dp[i] = dp[i-1] + dp[i-2] |
| 0/1 Knapsack | Subset Sum | dp[i][w] = max(dp[i-1][w], val + dp[i-1][w-wt]) |
| Unbounded Knapsack | Coin Change | dp[i][w] = max(dp[i-1][w], val + dp[i][w-wt]) |
| LCS | Edit Distance | dp[i][j] = max(dp[i-1][j], dp[i][j-1]) or 1+dp[i-1][j-1] |
| MCM | Boolean Parenthesization | dp[i][j] = min(dp[i][k] + dp[k+1][j] + cost) |
| Catalan | BST Count | dp[n] = sum(dp[j] * dp[n-1-j]) |
| Kadane | Max Subarray | dp[i] = max(arr[i], dp[i-1] + arr[i]) |

## Final Tips for Beginners

1. **Always draw the recursion tree first** — see the overlapping subproblems
2. **Always write the recursive solution first** — understand the recurrence
3. **Memoization is just recursion + cache** — easiest transition
4. **Tabulation is filling a table bottom-up** — often fastest
5. **For 2D DP, draw the table** — see the pattern of how cells relate
6. **Practice, practice, practice** — DP is a skill that develops over time

## Tree Data Structure Summary

| Structure | Build | Point Update | Range Query | Range Update |
|-----------|-------|-------------|-------------|-------------|
| Array (naive) | O(n) | O(1) | O(n) | O(n) |
| Prefix Sum array | O(n) | O(n) | O(1) | O(n) |
| Segment Tree | O(n) | O(log n) | O(log n) | O(log n) with lazy |
| Fenwick Tree (BIT) | O(n) | O(log n) | O(log n) | Not supported |

---

**This concludes the comprehensive guide to Dynamic Programming, Segment Trees, and Fenwick Trees.**
**Every concept is explained from first principles with full Java code including main methods.**
**Every DP problem shows all three approaches: Recursion, Memoization, and Tabulation.**
**Every data structure comes with build, query, and update operations demonstrated.**

---

# SEGMENT TREES

## WHAT IS A SEGMENT TREE?

Imagine you have an array and you need to answer MANY range queries (like "what's the sum from index 2 to 7?") AND also update elements frequently.

### Naive approach:
- Query: loop from i to j — O(n) per query
- Update: just change the element — O(1)
- For q queries: O(q * n) — SLOW

### Segment Tree approach:
- Pre-process the array into a tree structure where each node represents a segment (range) of the array
- Query: O(log n) — MUCH faster
- Update: O(log n) — also fast

### Structure:
- Root = entire array [0, n-1]
- Left child = left half, Right child = right half
- Leaf nodes = single elements

```
                [0,5]
              /       \
          [0,2]        [3,5]
         /     \       /    \
      [0,1]   [2,2] [3,4]  [5,5]
     /    \          /   \
  [0,0] [1,1]    [3,3] [4,4]
```

## SEGMENT TREE FOR RANGE SUM

```java
public class SegmentTreeSum {

    private int[] tree; // Tree array (size = 4 * n)
    private int n;      // Size of original array

    // Constructor: builds the segment tree
    public SegmentTreeSum(int[] arr) {
        this.n = arr.length;
        tree = new int[4 * n]; // 4*n is safe for any n
        build(arr, 0, 0, n - 1);
    }

    // ---- BUILD SEGMENT TREE ----
    // node = current node index in tree array
    // start, end = range in original array this node represents
    private void build(int[] arr, int node, int start, int end) {
        // Leaf node: represents a single element
        if (start == end) {
            tree[node] = arr[start];
            return;
        }

        int mid = start + (end - start) / 2;
        int leftChild = 2 * node + 1;
        int rightChild = 2 * node + 2;

        // Build left and right subtrees
        build(arr, leftChild, start, mid);
        build(arr, rightChild, mid + 1, end);

        // Internal node: sum of its children
        tree[node] = tree[leftChild] + tree[rightChild];
    }

    // ---- RANGE SUM QUERY ----
    // query(l, r) = sum of arr[l...r]
    public int query(int l, int r) {
        return query(0, 0, n - 1, l, r);
    }

    private int query(int node, int start, int end, int l, int r) {
        // Case 1: No overlap — return 0
        if (r < start || l > end) {
            return 0;
        }

        // Case 2: Complete overlap — return this node's value
        if (l <= start && end <= r) {
            return tree[node];
        }

        // Case 3: Partial overlap — recurse on children
        int mid = start + (end - start) / 2;
        int leftChild = 2 * node + 1;
        int rightChild = 2 * node + 2;

        int leftSum = query(leftChild, start, mid, l, r);
        int rightSum = query(rightChild, mid + 1, end, l, r);

        return leftSum + rightSum;
    }

    // ---- POINT UPDATE ----
    // update(idx, val) = set arr[idx] = val
    public void update(int idx, int val) {
        update(0, 0, n - 1, idx, val);
    }

    private void update(int node, int start, int end, int idx, int val) {
        // Leaf node: update value
        if (start == end) {
            tree[node] = val;
            return;
        }

        int mid = start + (end - start) / 2;
        int leftChild = 2 * node + 1;
        int rightChild = 2 * node + 2;

        // Recurse on the correct child
        if (idx <= mid) {
            update(leftChild, start, mid, idx, val);
        } else {
            update(rightChild, mid + 1, end, idx, val);
        }

        // Recompute this node's value after child updates
        tree[node] = tree[leftChild] + tree[rightChild];
    }

    // Print tree (for debugging)
    public void printTree() {
        System.out.print("Segment Tree: ");
        for (int i = 0; i < 4 * n; i++) {
            System.out.print(tree[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11};

        System.out.println("Array: [1, 3, 5, 7, 9, 11]");

        SegmentTreeSum segTree = new SegmentTreeSum(arr);
        segTree.printTree();

        System.out.println("Sum of range [1, 3]: " + segTree.query(1, 3));
        // Expected: 3 + 5 + 7 = 15

        System.out.println("Sum of range [0, 5]: " + segTree.query(0, 5));
        // Expected: 36

        System.out.println("Updating index 2 to value 10...");
        segTree.update(2, 10);
        // Array is now: [1, 3, 10, 7, 9, 11]

        System.out.println("Sum of range [1, 3]: " + segTree.query(1, 3));
        // Expected: 3 + 10 + 7 = 20
    }
}
```

---

## SEGMENT TREE FOR RANGE MINIMUM QUERY (RMQ)

```java
public class SegmentTreeMin {

    private int[] tree;
    private int n;

    public SegmentTreeMin(int[] arr) {
        this.n = arr.length;
        tree = new int[4 * n];
        build(arr, 0, 0, n - 1);
    }

    // ---- BUILD ----
    private void build(int[] arr, int node, int start, int end) {
        if (start == end) {
            tree[node] = arr[start];
            return;
        }

        int mid = start + (end - start) / 2;
        int left = 2 * node + 1;
        int right = 2 * node + 2;

        build(arr, left, start, mid);
        build(arr, right, mid + 1, end);

        // For range MIN: store the minimum of children
        tree[node] = Math.min(tree[left], tree[right]);
    }

    // ---- QUERY (RANGE MINIMUM) ----
    public int query(int l, int r) {
        return query(0, 0, n - 1, l, r);
    }

    private int query(int node, int start, int end, int l, int r) {
        // No overlap: return INFINITY (so it doesn't affect min)
        if (r < start || l > end) {
            return Integer.MAX_VALUE;
        }

        // Complete overlap
        if (l <= start && end <= r) {
            return tree[node];
        }

        int mid = start + (end - start) / 2;
        int left = 2 * node + 1;
        int right = 2 * node + 2;

        int leftMin = query(left, start, mid, l, r);
        int rightMin = query(right, mid + 1, end, l, r);

        return Math.min(leftMin, rightMin);
    }

    // ---- POINT UPDATE ----
    public void update(int idx, int val) {
        update(0, 0, n - 1, idx, val);
    }

    private void update(int node, int start, int end, int idx, int val) {
        if (start == end) {
            tree[node] = val;
            return;
        }

        int mid = start + (end - start) / 2;
        int left = 2 * node + 1;
        int right = 2 * node + 2;

        if (idx <= mid) {
            update(left, start, mid, idx, val);
        } else {
            update(right, mid + 1, end, idx, val);
        }

        tree[node] = Math.min(tree[left], tree[right]);
    }

    public static void main(String[] args) {
        int[] arr = {2, 5, 1, 8, 3, 7};

        System.out.println("Array: [2, 5, 1, 8, 3, 7]");

        SegmentTreeMin segTree = new SegmentTreeMin(arr);

        System.out.println("Min of range [0, 2]: " + segTree.query(0, 2));
        // Expected: 1 (min of 2, 5, 1)

        System.out.println("Min of range [2, 5]: " + segTree.query(2, 5));
        // Expected: 1 (min of 1, 8, 3, 7)

        System.out.println("Min of range [3, 4]: " + segTree.query(3, 4));
        // Expected: 3 (min of 8, 3)

        System.out.println("Updating index 2 to value 10...");
        segTree.update(2, 10);
        // Array is now: [2, 5, 10, 8, 3, 7]

        System.out.println("Min of range [0, 2]: " + segTree.query(0, 2));
        // Expected: 2 (min of 2, 5, 10)
    }
}
```

---

## LAZY PROPAGATION IN SEGMENT TREES

### Problem with Range Updates
What if we need to update a RANGE (not just a single point)? Like "add 5 to all elements from index 2 to 7"?

If we do point updates for each element, that's O(n log n) per range update — SLOW.

### Lazy Propagation = The Smart Way
Instead of updating all nodes immediately, we "postpone" updates. When a node's entire segment needs updating, we:
1. Update the node itself
2. Mark it as "lazy" (has pending updates)
3. Only propagate to children when needed (during a query or partial update)

```java
public class SegmentTreeLazy {

    private int[] tree; // Segment tree
    private int[] lazy; // Lazy propagation array
    private int n;

    public SegmentTreeLazy(int[] arr) {
        this.n = arr.length;
        tree = new int[4 * n];
        lazy = new int[4 * n]; // All 0 initially (no pending updates)
        build(arr, 0, 0, n - 1);
    }

    // ---- BUILD ----
    private void build(int[] arr, int node, int start, int end) {
        if (start == end) {
            tree[node] = arr[start];
            return;
        }

        int mid = start + (end - start) / 2;
        build(arr, 2 * node + 1, start, mid);
        build(arr, 2 * node + 2, mid + 1, end);
        tree[node] = tree[2 * node + 1] + tree[2 * node + 2];
    }

    // ---- LAZY UPDATE HELPER ----
    // Apply pending lazy update to a node and push to children
    private void applyLazy(int node, int start, int end) {
        if (lazy[node] != 0) {
            // Apply the pending update to this node
            // For sum: add lazy[node] to each element in range
            tree[node] += (end - start + 1) * lazy[node];

            // If not leaf, propagate lazy value to children
            if (start != end) {
                lazy[2 * node + 1] += lazy[node];
                lazy[2 * node + 2] += lazy[node];
            }

            // Clear this node's lazy
            lazy[node] = 0;
        }
    }

    // ---- RANGE UPDATE (add val to all elements in [l, r]) ----
    public void rangeUpdate(int l, int r, int val) {
        rangeUpdate(0, 0, n - 1, l, r, val);
    }

    private void rangeUpdate(int node, int start, int end, int l, int r, int val) {
        // Apply any pending lazy updates FIRST
        applyLazy(node, start, end);

        // No overlap
        if (r < start || l > end) return;

        // Complete overlap — update this node and mark lazy
        if (l <= start && end <= r) {
            tree[node] += (end - start + 1) * val;

            // If not leaf, mark children as lazy
            if (start != end) {
                lazy[2 * node + 1] += val;
                lazy[2 * node + 2] += val;
            }

            return;
        }

        // Partial overlap — recurse
        int mid = start + (end - start) / 2;
        rangeUpdate(2 * node + 1, start, mid, l, r, val);
        rangeUpdate(2 * node + 2, mid + 1, end, l, r, val);

        // After children updated, recompute this node
        tree[node] = tree[2 * node + 1] + tree[2 * node + 2];
    }

    // ---- RANGE SUM QUERY (with lazy consideration) ----
    public int rangeSum(int l, int r) {
        return rangeSum(0, 0, n - 1, l, r);
    }

    private int rangeSum(int node, int start, int end, int l, int r) {
        // Apply pending lazy before anything
        applyLazy(node, start, end);

        // No overlap
        if (r < start || l > end) return 0;

        // Complete overlap
        if (l <= start && end <= r) return tree[node];

        // Partial overlap
        int mid = start + (end - start) / 2;
        int leftSum = rangeSum(2 * node + 1, start, mid, l, r);
        int rightSum = rangeSum(2 * node + 2, mid + 1, end, l, r);

        return leftSum + rightSum;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8};

        System.out.println("Array: [1, 2, 3, 4, 5, 6, 7, 8]");

        SegmentTreeLazy segTree = new SegmentTreeLazy(arr);

        System.out.println("Sum [0, 7]: " + segTree.rangeSum(0, 7));
        // Expected: 36

        System.out.println("Sum [2, 4]: " + segTree.rangeSum(2, 4));
        // Expected: 3+4+5 = 12

        System.out.println("\nAdding +10 to range [2, 5]...");
        segTree.rangeUpdate(2, 5, 10);
        // Array is now: [1, 2, 13, 14, 15, 16, 7, 8]

        System.out.println("Sum [2, 4]: " + segTree.rangeSum(2, 4));
        // Expected: 13+14+15 = 42

        System.out.println("Sum [0, 7]: " + segTree.rangeSum(0, 7));
        // Expected: 36 + 40 (4 elements * 10) = 76

        System.out.println("\nAdding +20 to range [0, 2]...");
        segTree.rangeUpdate(0, 2, 20);
        // Array is now: [21, 22, 33, 14, 15, 16, 7, 8]

        System.out.println("Sum [0, 3]: " + segTree.rangeSum(0, 3));
        // Expected: 21+22+33+14 = 90
    }
}
```

---

## WHEN TO USE LAZY PROPAGATION?

| Operation | Normal Segment Tree | Lazy Segment Tree |
|-----------|-------------------|-------------------|
| Point update | O(log n) | O(log n) |
| Range update | O(n log n) | O(log n) |
| Range query | O(log n) | O(log n) |

Use lazy propagation when you need RANGE UPDATES (not just point updates).

---

# FENWICK TREE (BINARY INDEXED TREE / BIT)

## What is a Fenwick Tree?

A tree structure that efficiently handles PREFIX SUM queries and point updates.

### Key Concept: Index Based on LSB (Least Significant Bit)
Each index `i` stores the sum of a range ending at `i`. The range length = 2^k where k is the position of the LSB of i.

```
Index:    1   2   3   4   5   6   7   8
Binary:   1  10  11 100 101 110 111 1000
LSB:     2^0 2^1 2^0 2^2 2^0 2^1 2^0 2^3
Range:   1   1-2  3  1-4  5  5-6  7  1-8
```

### Operations:
- **Update**: Add value at index i, propagate to ancestors (i += LSB(i))
- **Prefix Sum**: Sum of [0...i], visit ancestors (i -= LSB(i))
- **Range Sum**: prefixSum(r) - prefixSum(l-1)

```java
public class FenwickTree {

    private int[] bit; // Binary Indexed Tree (1-indexed internally)
    private int n;

    // Constructor: build BIT from array
    public FenwickTree(int[] arr) {
        this.n = arr.length;
        bit = new int[n + 1]; // 1-indexed, index 0 is dummy

        // Initialize with zeros, then add each element
        for (int i = 0; i < n; i++) {
            add(i, arr[i]);
        }
    }

    // Helper: get least significant bit
    private int LSB(int x) {
        return x & (-x); // Isolates the lowest set bit
    }

    // ---- POINT UPDATE: add delta at index idx (0-indexed) ----
    public void add(int idx, int delta) {
        // Convert to 1-indexed
        int i = idx + 1;

        // Traverse up the tree, adding delta to all ancestors
        while (i <= n) {
            bit[i] += delta;
            i += LSB(i); // Go to parent
        }
    }

    // ---- PREFIX SUM: sum of arr[0...idx] ----
    public int prefixSum(int idx) {
        int i = idx + 1; // Convert to 1-indexed
        int sum = 0;

        // Traverse down, collecting sums
        while (i > 0) {
            sum += bit[i];
            i -= LSB(i); // Remove LSB to go to next range
        }

        return sum;
    }

    // ---- RANGE SUM: sum of arr[l...r] ----
    public int rangeSum(int l, int r) {
        if (l == 0) return prefixSum(r);
        return prefixSum(r) - prefixSum(l - 1);
    }

    // ---- POINT UPDATE: set arr[idx] = val ----
    public void set(int idx, int val) {
        // Current value at idx
        int current = rangeSum(idx, idx);
        // Add the difference
        add(idx, val - current);
    }

    // Print BIT (for debugging)
    public void printBIT() {
        System.out.print("BIT: ");
        for (int i = 1; i <= n; i++) {
            System.out.print(bit[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr = {3, 2, -1, 6, 5, 4, -3, 3, 7, 2, 3};

        System.out.println("Array: [3, 2, -1, 6, 5, 4, -3, 3, 7, 2, 3]");

        FenwickTree ft = new FenwickTree(arr);
        ft.printBIT();

        System.out.println("Prefix sum up to index 4: " + ft.prefixSum(4));
        // Expected: 3+2+(-1)+6+5 = 15

        System.out.println("Range sum [2, 6]: " + ft.rangeSum(2, 6));
        // Expected: (-1)+6+5+4+(-3) = 11

        System.out.println("Adding +10 at index 3...");
        ft.add(3, 10);
        // Array is now: [3, 2, -1, 16, 5, 4, -3, 3, 7, 2, 3]

        System.out.println("Prefix sum up to index 4: " + ft.prefixSum(4));
        // Expected: 3+2+(-1)+16+5 = 25

        System.out.println("Setting index 5 to value 0...");
        ft.set(5, 0);
        // Array is now: [3, 2, -1, 16, 5, 0, -3, 3, 7, 2, 3]

        System.out.println("Range sum [2, 6]: " + ft.rangeSum(2, 6));
        // Expected: (-1)+16+5+0+(-3) = 17
    }
}
```

---

## FENWICK TREE vs SEGMENT TREE

| Feature | Fenwick Tree (BIT) | Segment Tree |
|---------|-------------------|-------------|
| Build | O(n) | O(n) |
| Point Update | O(log n) | O(log n) |
| Range Update | Not directly supported | O(log n) with lazy |
| Prefix Query | O(log n) | O(log n) |
| Range Query | O(log n) | O(log n) |
| Memory | n+1 | 4n |
| Code Complexity | Very simple | More complex |

**When to use Fenwick Tree:**
- You only need prefix sums and point updates
- You want simpler, shorter code
- Memory is a concern

**When to use Segment Tree:**
- You need range updates (with lazy propagation)
- You need range minimum/maximum queries
- You need more complex queries (like range min + range sum)

---

# CONCLUSION

## DP Decision Flowchart

1. **Can you brute-force recursively?** Yes -> It might be a DP problem
2. **Are there overlapping subproblems?** Yes -> DP will help
3. **Does the problem have optimal substructure?** Yes -> DP applies
4. **Which approach?**
   - Start with **Recursion** to understand the recurrence relation
   - Add **Memoization** to make it fast (top-down)
   - Convert to **Tabulation** if you want iterative (bottom-up)

## Common DP Patterns

| Pattern | Example | Recurrence |
|---------|---------|------------|
| Fibonacci-like | Climbing Stairs | dp[i] = dp[i-1] + dp[i-2] |
| 0/1 Knapsack | Subset Sum | dp[i][w] = max(dp[i-1][w], val + dp[i-1][w-wt]) |
| Unbounded Knapsack | Coin Change | dp[i][w] = max(dp[i-1][w], val + dp[i][w-wt]) |
| LCS | Edit Distance | dp[i][j] = max(dp[i-1][j], dp[i][j-1]) or 1+dp[i-1][j-1] |
| MCM | Boolean Parenthesization | dp[i][j] = min(dp[i][k] + dp[k+1][j] + cost) |
| Catalan | BST Count | dp[n] = sum(dp[j] * dp[n-1-j]) |
| Kadane | Max Subarray | dp[i] = max(arr[i], dp[i-1] + arr[i]) |

## Final Tips for Beginners

1. **Always draw the recursion tree first** — see the overlapping subproblems
2. **Always write the recursive solution first** — understand the recurrence
3. **Memoization is just recursion + cache** — easiest transition
4. **Tabulation is filling a table bottom-up** — often fastest
5. **For 2D DP, draw the table** — see the pattern of how cells relate
6. **Practice, practice, practice** — DP is a skill that develops over time

## Tree Data Structure Summary

| Structure | Build | Point Update | Range Query | Range Update |
|-----------|-------|-------------|-------------|-------------|
| Array (naive) | O(n) | O(1) | O(n) | O(n) |
| Prefix Sum array | O(n) | O(n) | O(1) | O(n) |
| Segment Tree | O(n) | O(log n) | O(log n) | O(log n) with lazy |
| Fenwick Tree (BIT) | O(n) | O(log n) | O(log n) | Not supported |

---

**This concludes the comprehensive guide to Dynamic Programming, Segment Trees, and Fenwick Trees.**
**Every concept is explained from first principles with full Java code including main methods.**
**Every DP problem shows all three approaches: Recursion, Memoization, and Tabulation.**
**Every data structure comes with build, query, and update operations demonstrated.**
# JAVA DSA: DYNAMIC PROGRAMMING, SEGMENT TREES & FENWICK TREES

## FOR THE ABSOLUTE BEGINNER

This guide assumes you know basic Java (loops, arrays, methods, recursion). Everything else is explained from scratch. Every concept is first explained like you're 5, then we dive into code.

---

# PART 1: WHAT IS DYNAMIC PROGRAMMING?

## Imagine This...

You need to calculate the 50th number in the Fibonacci sequence. You write a recursive function. It works... but it's SLOW. Really slow. Like, won't-finish-in-your-lifetime slow.

What went wrong? The same calculation gets repeated MILLIONS of times. `fib(3)` gets calculated over and over and over.

**DP (Dynamic Programming)** is just a fancy name for: *"Hey, let's remember stuff we already calculated so we don't do it again."*

That's literally it.

## Two Magic Properties of DP Problems

### 1. Overlapping Subproblems
The big problem can be broken into smaller problems, AND those smaller problems are the SAME ones that keep appearing.

Like Fibonacci: `fib(5) = fib(4) + fib(3)`, and `fib(4) = fib(3) + fib(2)` — see how `fib(3)` appears in BOTH? That's overlapping.

### 2. Optimal Substructure
The optimal answer to the big problem can be built from optimal answers to the smaller problems.

Like: "What's the shortest path from A to C through B?" If you know the shortest path from A to B and B to C, you combine them. Simple.

## The Three Approaches

### Approach 1: Recursion (Naive) — "The Slow Way"
Just write the recursive formula as-is. No caching. SLOOOOOW.

### Approach 2: Memoization (Top-Down) — "The Smart Recursive Way"
Same recursion, but you STORE results in an array/table before returning. When the same call comes again, you just look up the stored value. FAST.

### Approach 3: Tabulation (Bottom-Up) — "The Loop Way"
Instead of recursion, you fill a table iteratively from smallest subproblem to biggest. NO recursion at all. OFTEN the fastest.

---

# FIBONACCI — THE HELLO WORLD OF DP

## Problem: Find the nth Fibonacci number
Fibonacci: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...
- fib(0) = 0
- fib(1) = 1
- fib(n) = fib(n-1) + fib(n-2)

---

### APPROACH 1: RECURSION (NAIVE)

```java
public class FibonacciRecursion {

    // This is the RAW recursive formula. Looks elegant. Runs like garbage.
    public static int fib(int n) {
        // Base cases: fib(0) = 0, fib(1) = 1
        if (n <= 1) {
            return n;
        }

        // Recursive case: fib(n) = fib(n-1) + fib(n-2)
        // Problem: for n=50, this calls itself BILLIONS of times
        int result = fib(n - 1) + fib(n - 2);
        return result;
    }

    public static void main(String[] args) {
        int n = 6;
        // Try changing n to 50 and watch your computer cry
        System.out.println("fib(" + n + ") = " + fib(n));
    }
}
```

**Time Complexity: O(2^n)** — exponentially BAD
**Space Complexity: O(n)** — call stack depth

**Why is it so slow?** Draw the call tree. `fib(5)` calls `fib(4)` and `fib(3)`. `fib(4)` calls `fib(3)` and `fib(2)`. Notice `fib(3)` is called TWICE. `fib(2)` is called THREE times. This duplication explodes exponentially.

---

### APPROACH 2: MEMOIZATION (TOP-DOWN DP)

```java
public class FibonacciMemoization {

    // We use a "memo" (memory) array to store already-computed values
    // Size: n+1 because we need indices 0 through n
    // Initialize with -1 (or any sentinel) to mean "not computed yet"
    public static int fib(int n, int[] memo) {
        // Base case
        if (n <= 1) {
            return n;
        }

        // MAGIC LINE: If we've already computed fib(n), just return it!
        // This is the entire point of DP — avoid recomputation
        if (memo[n] != -1) {
            return memo[n];
        }

        // Compute and STORE before returning
        memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
        return memo[n];
    }

    public static void main(String[] args) {
        int n = 50; // Try n=50 now — runs INSTANTLY

        // Create memo array, fill with -1 (means "not computed yet")
        int[] memo = new int[n + 1];
        for (int i = 0; i <= n; i++) {
            memo[i] = -1;
        }

        System.out.println("fib(" + n + ") = " + fib(n, memo));
    }
}
```

**Time Complexity: O(n)** — each number computed once!
**Space Complexity: O(n)** — memo array + call stack

**What changed?** Every `fib(k)` is computed exactly once. The second time we need it, we just read `memo[k]`. That's it. That's the whole secret of DP.

### APPROACH 3: TABULATION (BOTTOM-UP DP)

```java
public class FibonacciTabulation {

    // No recursion! We fill the table from bottom (small numbers) to top (n)
    public static int fib(int n) {
        if (n <= 1) {
            return n;
        }

        // Create table (tab) to store values
        int[] tab = new int[n + 1];

        // Base cases (the "bottom" of our bottom-up)
        tab[0] = 0;
        tab[1] = 1;

        // Fill upwards: tab[2], tab[3], ..., tab[n]
        // Each tab[i] depends ONLY on tab[i-1] and tab[i-2]
        // Those are ALREADY computed (we filled them in previous iterations)
        for (int i = 2; i <= n; i++) {
            tab[i] = tab[i - 1] + tab[i - 2];
        }

        return tab[n];
    }

    public static void main(String[] args) {
        int n = 50;
        System.out.println("fib(" + n + ") = " + fib(n));
    }
}
```

**Time Complexity: O(n)**
**Space Complexity: O(n)** but can be optimized to O(1)

**Space-optimized version (no array, just two variables):**

```java
public class FibonacciTabulationOptimized {

    public static int fib(int n) {
        if (n <= 1) {
            return n;
        }

        // We only need the LAST TWO values at any point
        int prev2 = 0; // fib(0)
        int prev1 = 1; // fib(1)

        for (int i = 2; i <= n; i++) {
            int curr = prev1 + prev2;
            prev2 = prev1; // Shift: old prev1 becomes new prev2
            prev1 = curr;  // Shift: new value becomes new prev1
        }

        return prev1;
    }

    public static void main(String[] args) {
        int n = 50;
        System.out.println("fib(" + n + ") = " + fib(n));
    }
}
```

**Space Complexity: O(1)** — just two variables!

---

# CLIMBING STAIRS

## Problem
You're climbing a staircase with `n` steps. Each time you can climb 1 or 2 steps. In how many DISTINCT ways can you reach the top?

## Think About It
- To reach step 0 (ground): 1 way (just stand there)
- To reach step 1: 1 way (1 step)
- To reach step 2: 2 ways (1+1 or 2)
- To reach step 3: You got here from step 2 (then took 1 step) OR from step 1 (then took 2 steps). So ways(3) = ways(2) + ways(1) = 2 + 1 = 3

**Pattern:** ways(n) = ways(n-1) + ways(n-2) — it's Fibonacci!

```java
public class ClimbingStairs {

    // ---- RECURSION (NAIVE) ----
    public static int climbRecur(int n) {
        // Base cases
        if (n == 0 || n == 1) {
            return 1; // Only 1 way to be at step 0 or 1
        }

        // To reach step n, you came from step n-1 (took 1 step)
        // OR from step n-2 (took 2 steps)
        return climbRecur(n - 1) + climbRecur(n - 2);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int climbMemo(int n, int[] memo) {
        if (n == 0 || n == 1) {
            return 1;
        }

        // If already computed, return stored value
        if (memo[n] != -1) {
            return memo[n];
        }

        // Compute, store, then return
        memo[n] = climbMemo(n - 1, memo) + climbMemo(n - 2, memo);
        return memo[n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int climbTab(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }

        int[] dp = new int[n + 1];
        dp[0] = 1; // 1 way to be at step 0
        dp[1] = 1; // 1 way to be at step 1

        // Fill bottom-up: step 2, 3, ..., n
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }

        return dp[n];
    }

    // ---- TABULATION (SPACE OPTIMIZED) ----
    public static int climbTabOpt(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }

        int prev2 = 1; // ways to reach step 0
        int prev1 = 1; // ways to reach step 1

        for (int i = 2; i <= n; i++) {
            int curr = prev1 + prev2;
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }

    public static void main(String[] args) {
        int n = 10;

        System.out.println("Recursion: climb(" + n + ") = " + climbRecur(n));

        int[] memo = new int[n + 1];
        java.util.Arrays.fill(memo, -1);
        System.out.println("Memoization: climb(" + n + ") = " + climbMemo(n, memo));

        System.out.println("Tabulation: climb(" + n + ") = " + climbTab(n));
        System.out.println("Tabulation Opt: climb(" + n + ") = " + climbTabOpt(n));
    }
}
```

---

# MIN COST CLIMBING STAIRS

## Problem
You're given an array `cost[]` where `cost[i]` is the cost to step onto step i. Once you pay, you can climb 1 or 2 steps. You start at step 0 or step 1 (your choice). Find the MINIMUM cost to reach the top (past the last step).

## Think About It
To reach step i, you came from step i-1 (cost = cost[i-1]) or step i-2 (cost = cost[i-2]). You want the MINIMUM cost so far plus the cost of the step you're STANDING on.

**Recurrence:** `minCost(i) = cost[i] + min(minCost(i-1), minCost(i-2))`

The TOP is past the last step, so answer is `min(minCost(n-1), minCost(n-2))`.

```java
public class MinCostClimbingStairs {

    // ---- RECURSION (NAIVE) ----
    // minCost(i) = minimum cost to reach step i (and pay its cost)
    public static int minCostRecur(int i, int[] cost) {
        // Base: step 0 or 1 — just pay the cost to stand here
        if (i == 0 || i == 1) {
            return cost[i];
        }

        // To reach step i: pay cost[i] PLUS the minimum of reaching i-1 or i-2
        int totalCost = cost[i] + Math.min(minCostRecur(i - 1, cost), minCostRecur(i - 2, cost));
        return totalCost;
    }

    // Wrapper for recursion approach
    public static int minCostClimbingStairsRecur(int[] cost) {
        int n = cost.length;
        // Top is past the last step, so we take min of reaching n-1 or n-2
        return Math.min(minCostRecur(n - 1, cost), minCostRecur(n - 2, cost));
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minCostMemo(int i, int[] cost, int[] memo) {
        if (i == 0 || i == 1) {
            return cost[i];
        }

        if (memo[i] != -1) {
            return memo[i];
        }

        memo[i] = cost[i] + Math.min(minCostMemo(i - 1, cost, memo), minCostMemo(i - 2, cost, memo));
        return memo[i];
    }

    public static int minCostClimbingStairsMemo(int[] cost) {
        int n = cost.length;
        int[] memo = new int[n];
        java.util.Arrays.fill(memo, -1);
        return Math.min(minCostMemo(n - 1, cost, memo), minCostMemo(n - 2, cost, memo));
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minCostClimbingStairsTab(int[] cost) {
        int n = cost.length;

        // dp[i] = min cost to reach step i (and pay its cost)
        int[] dp = new int[n];

        // Base cases
        dp[0] = cost[0];
        dp[1] = cost[1];

        // Fill bottom-up
        for (int i = 2; i < n; i++) {
            dp[i] = cost[i] + Math.min(dp[i - 1], dp[i - 2]);
        }

        // Answer: min of reaching step n-1 or skipping from n-2 to top
        return Math.min(dp[n - 1], dp[n - 2]);
    }

    // ---- TABULATION (SPACE OPTIMIZED) ----
    public static int minCostClimbingStairsOpt(int[] cost) {
        int n = cost.length;

        int prev2 = cost[0]; // dp[i-2]
        int prev1 = cost[1]; // dp[i-1]

        for (int i = 2; i < n; i++) {
            int curr = cost[i] + Math.min(prev1, prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return Math.min(prev1, prev2);
    }

    public static void main(String[] args) {
        int[] cost = {10, 15, 20, 25, 30};

        System.out.println("Recursion: " + minCostClimbingStairsRecur(cost));
        System.out.println("Memoization: " + minCostClimbingStairsMemo(cost));
        System.out.println("Tabulation: " + minCostClimbingStairsTab(cost));
        System.out.println("Tabulation Opt: " + minCostClimbingStairsOpt(cost));
    }
}
```

---

# HOUSE ROBBER

## Problem
You're a robber planning to rob houses on a street. Each house has a certain amount of money stashed. ADJACENT houses cannot be robbed on the same night (silent alarm system). Find the MAXIMUM amount you can rob.

## Think About It
At each house `i`, you have TWO choices:
1. **Rob it**: You get `nums[i]` + whatever you got up to house `i-2` (can't rob i-1)
2. **Skip it**: You get whatever you got up to house `i-1`

Take the MAX of these two options.

**Recurrence:** `rob(i) = max(rob(i-1), nums[i] + rob(i-2))`

```java
public class HouseRobber {

    // ---- RECURSION (NAIVE) ----
    // robRecur(i) = max money from houses [0...i]
    public static int robRecur(int i, int[] nums) {
        // Base: no houses left
        if (i < 0) {
            return 0;
        }

        // Option 1: Skip house i, take best from houses [0...i-1]
        int skip = robRecur(i - 1, nums);

        // Option 2: Rob house i, add its money, then take best from [0...i-2]
        int rob = nums[i] + robRecur(i - 2, nums);

        // Return whichever gives MORE money
        return Math.max(skip, rob);
    }

    public static int robRecurWrapper(int[] nums) {
        return robRecur(nums.length - 1, nums);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int robMemo(int i, int[] nums, int[] memo) {
        if (i < 0) {
            return 0;
        }

        if (memo[i] != -1) {
            return memo[i];
        }

        int skip = robMemo(i - 1, nums, memo);
        int rob = nums[i] + robMemo(i - 2, nums, memo);

        memo[i] = Math.max(skip, rob);
        return memo[i];
    }

    public static int robMemoWrapper(int[] nums) {
        int n = nums.length;
        int[] memo = new int[n];
        java.util.Arrays.fill(memo, -1);
        return robMemo(n - 1, nums, memo);
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int robTab(int[] nums) {
        int n = nums.length;

        if (n == 0) return 0;
        if (n == 1) return nums[0];

        // dp[i] = max money from houses [0...i]
        int[] dp = new int[n];

        // Base cases
        dp[0] = nums[0];                       // Only one house? Rob it
        dp[1] = Math.max(nums[0], nums[1]);    // Two houses? Take the richer one

        // For each subsequent house, decide: rob or skip?
        for (int i = 2; i < n; i++) {
            // Skip house i -> dp[i-1]
            // Rob house i  -> nums[i] + dp[i-2]
            dp[i] = Math.max(dp[i - 1], nums[i] + dp[i - 2]);
        }

        return dp[n - 1];
    }

    // ---- TABULATION (SPACE OPTIMIZED) ----
    public static int robOpt(int[] nums) {
        int n = nums.length;

        if (n == 0) return 0;
        if (n == 1) return nums[0];

        int prev2 = nums[0];          // dp[i-2]
        int prev1 = Math.max(nums[0], nums[1]); // dp[i-1]

        for (int i = 2; i < n; i++) {
            int curr = Math.max(prev1, nums[i] + prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }

    public static void main(String[] args) {
        int[] nums = {2, 7, 9, 3, 1};

        System.out.println("Houses: [2, 7, 9, 3, 1]");
        System.out.println("Recursion: " + robRecurWrapper(nums));
        System.out.println("Memoization: " + robMemoWrapper(nums));
        System.out.println("Tabulation: " + robTab(nums));
        System.out.println("Tabulation Opt: " + robOpt(nums));
        // Expected: 12 (rob house 0=2, house 2=9, house 4=1 => 2+9+1=12)
        // Or: rob house 1=7, house 3=3 => 10. Max is 12.
    }
}
```

# HOUSE ROBBER II (CIRCULAR)

## Problem
Same as House Robber BUT the houses are arranged in a CIRCLE. The first and last houses are adjacent.

## Think About It
Since house 0 and house n-1 are adjacent, we can't rob both. Solution: solve TWO linear House Robber problems:
1. Rob houses [0...n-2] (exclude last house)
2. Rob houses [1...n-1] (exclude first house)
3. Answer = max(option1, option2)

```java
public class HouseRobberII {

    // Helper: linear House Robber on a subarray
    private static int robLinear(int[] nums, int start, int end) {
        int prev2 = 0; // dp[i-2], starts as 0 for "no house"
        int prev1 = 0; // dp[i-1]

        for (int i = start; i <= end; i++) {
            int curr = Math.max(prev1, nums[i] + prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return prev1;
    }

    // ---- RECURSION (NAIVE) ----
    public static int robRecur(int[] nums) {
        int n = nums.length;
        if (n == 0) return 0;
        if (n == 1) return nums[0];
        if (n == 2) return Math.max(nums[0], nums[1]);

        // We use our linear rob helper with the two ranges
        // (Recursion on linear part is same as House Robber)
        return Math.max(
            HouseRobber.robRecurWrapper(java.util.Arrays.copyOfRange(nums, 0, n - 1)),
            HouseRobber.robRecurWrapper(java.util.Arrays.copyOfRange(nums, 1, n))
        );
    }

    // ---- TABULATION (using linear helper) ----
    public static int robTab(int[] nums) {
        int n = nums.length;
        if (n == 0) return 0;
        if (n == 1) return nums[0];
        if (n == 2) return Math.max(nums[0], nums[1]);

        // Case 1: Exclude last house
        int case1 = robLinear(nums, 0, n - 2);
        // Case 2: Exclude first house
        int case2 = robLinear(nums, 1, n - 1);

        return Math.max(case1, case2);
    }

    public static void main(String[] args) {
        int[] nums = {2, 3, 2};

        System.out.println("Houses (circular): [2, 3, 2]");
        System.out.println("Recursion: " + robRecur(nums));
        System.out.println("Tabulation: " + robTab(nums));
        // Expected: 3 (can't rob 0 and 2 since they're adjacent in circle)
        // Option 1: houses [0,1] = max(2,3) = 3
        // Option 2: houses [1,2] = max(3,2) = 3
        // Answer: 3
    }
}
```

---

# 0/1 KNAPSACK — THE CLASSIC DP PROBLEM

## Problem
You have a bag (knapsack) that can hold at most `W` weight. You have `n` items, each with a `weight` and a `value`. You can either take an item or leave it (0/1 choice — can't take fractions). Maximize the total value in your bag.

## Understanding the 2D Table

Let's say:
- Items: (val=60, wt=10), (val=100, wt=20), (val=120, wt=30)
- Capacity = 50

We build a table where:
- ROWS = items (0 to n)
- COLUMNS = capacity (0 to W)
- `dp[i][w]` = max value using first `i` items with capacity `w`

### How to read the table:
- `dp[0][w]` = 0 (no items, no value)
- `dp[i][0]` = 0 (no capacity, no value)
- For each cell: either skip item `i` (take value from above) or take item `i` (item value + value from row above at capacity minus item weight)

### Example table walkthrough:

```
Capacity ->    0   10   20   30   40   50
Item 0         0    0    0    0    0    0
Item 1(w10)    0   60   60   60   60   60
Item 2(w20)    0   60  100  160  160  160
Item 3(w30)    0   60  100  160  180  220
```

**How cell [3][50] = 220 is computed:**
- Skip item 3: above cell [2][50] = 160
- Take item 3: val[3] + dp[2][50-wt[3]] = 120 + dp[2][20] = 120 + 100 = 220
- Max(160, 220) = 220

```java
public class Knapsack01 {

    // ---- RECURSION (NAIVE) ----
    // knapRecur(n, W) = max value with first n items and capacity W
    public static int knapRecur(int n, int W, int[] val, int[] wt) {
        // Base: no items left or no capacity left
        if (n == 0 || W == 0) {
            return 0;
        }

        // If current item's weight exceeds remaining capacity, skip it
        if (wt[n - 1] > W) {
            return knapRecur(n - 1, W, val, wt);
        }

        // Option 1: Skip item n-1
        int skip = knapRecur(n - 1, W, val, wt);

        // Option 2: Take item n-1
        int take = val[n - 1] + knapRecur(n - 1, W - wt[n - 1], val, wt);

        return Math.max(skip, take);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int knapMemo(int n, int W, int[] val, int[] wt, int[][] memo) {
        if (n == 0 || W == 0) {
            return 0;
        }

        if (memo[n][W] != -1) {
            return memo[n][W];
        }

        if (wt[n - 1] > W) {
            memo[n][W] = knapMemo(n - 1, W, val, wt, memo);
        } else {
            int skip = knapMemo(n - 1, W, val, wt, memo);
            int take = val[n - 1] + knapMemo(n - 1, W - wt[n - 1], val, wt, memo);
            memo[n][W] = Math.max(skip, take);
        }

        return memo[n][W];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int knapTab(int W, int[] val, int[] wt) {
        int n = val.length;

        // dp[i][w] = max value using first i items with capacity w
        int[][] dp = new int[n + 1][W + 1];

        // i=0 or w=0 are already initialized to 0 (default in Java)

        // Fill the table bottom-up
        for (int i = 1; i <= n; i++) {
            for (int w = 1; w <= W; w++) {
                // If current item fits...
                if (wt[i - 1] <= w) {
                    // Max of: skip item vs take item
                    dp[i][w] = Math.max(
                        dp[i - 1][w],                                    // skip
                        val[i - 1] + dp[i - 1][w - wt[i - 1]]            // take
                    );
                } else {
                    // Item too heavy, must skip
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        // Print the DP table for learning
        System.out.println("DP Table (items vs capacity):");
        System.out.print("    ");
        for (int w = 0; w <= W; w++) {
            System.out.printf("%4d", w);
        }
        System.out.println();
        for (int i = 0; i <= n; i++) {
            System.out.printf("%4d ", i);
            for (int w = 0; w <= W; w++) {
                System.out.printf("%4d", dp[i][w]);
            }
            System.out.println();
        }

        return dp[n][W];
    }

    public static void main(String[] args) {
        int[] val = {60, 100, 120};
        int[] wt = {10, 20, 30};
        int W = 50;
        int n = val.length;

        System.out.println("Items: (val=60, wt=10), (val=100, wt=20), (val=120, wt=30)");
        System.out.println("Capacity: " + W);

        System.out.println("\nRecursion: " + knapRecur(n, W, val, wt));

        int[][] memo = new int[n + 1][W + 1];
        for (int i = 0; i <= n; i++)
            for (int w = 0; w <= W; w++)
                memo[i][w] = -1;
        System.out.println("Memoization: " + knapMemo(n, W, val, wt, memo));

        System.out.println("\nTabulation:");
        System.out.println("Max Value: " + knapTab(W, val, wt));
        // Expected: 220
    }
}
```

---

# TARGET SUM SUBSET (SUBSET SUM)

## Problem
Given an array `arr[]` and a target sum `sum`, is there a subset whose elements sum to exactly `sum`?

## Think About It
For each element, we have two choices: include it or exclude it.
- `subsetSum(arr, n, sum)` = `subsetSum(arr, n-1, sum)` (skip) OR `subsetSum(arr, n-1, sum - arr[n-1])` (include)

This is a 0/1 Knapsack variant where value = weight = arr[i], and we check for EXACT sum.

```java
public class SubsetSum {

    // ---- RECURSION (NAIVE) ----
    public static boolean subsetSumRecur(int[] arr, int n, int sum) {
        // Base: sum = 0 -> empty subset always works
        if (sum == 0) return true;
        // Base: no items left but sum > 0 -> impossible
        if (n == 0) return false;

        // If current element > sum, skip it
        if (arr[n - 1] > sum) {
            return subsetSumRecur(arr, n - 1, sum);
        }

        // Try: skip element OR include element
        return subsetSumRecur(arr, n - 1, sum) ||
               subsetSumRecur(arr, n - 1, sum - arr[n - 1]);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static boolean subsetSumMemo(int[] arr, int n, int sum, Boolean[][] memo) {
        if (sum == 0) return true;
        if (n == 0) return false;

        if (memo[n][sum] != null) {
            return memo[n][sum];
        }

        if (arr[n - 1] > sum) {
            memo[n][sum] = subsetSumMemo(arr, n - 1, sum, memo);
        } else {
            memo[n][sum] = subsetSumMemo(arr, n - 1, sum, memo) ||
                           subsetSumMemo(arr, n - 1, sum - arr[n - 1], memo);
        }

        return memo[n][sum];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static boolean subsetSumTab(int[] arr, int sum) {
        int n = arr.length;

        // dp[i][s] = can we make sum 's' using first 'i' elements?
        boolean[][] dp = new boolean[n + 1][sum + 1];

        // Sum = 0 is always possible (empty subset)
        for (int i = 0; i <= n; i++) {
            dp[i][0] = true;
        }

        // No elements can only make sum 0 (already set above)
        // dp[0][s] for s>0 stays false (default)

        // Fill the table
        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= sum; s++) {
                if (arr[i - 1] <= s) {
                    // Can we make sum 's' by skipping OR including element i-1?
                    dp[i][s] = dp[i - 1][s] || dp[i - 1][s - arr[i - 1]];
                } else {
                    // Element too big, must skip
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        // Print table
        System.out.println("\nSubset Sum DP Table:");
        System.out.print("    ");
        for (int s = 0; s <= sum; s++) System.out.printf("%4d", s);
        System.out.println();
        for (int i = 0; i <= n; i++) {
            System.out.printf("%4d ", i);
            for (int s = 0; s <= sum; s++) {
                System.out.printf("%4s", dp[i][s] ? "T" : "F");
            }
            System.out.println();
        }

        return dp[n][sum];
    }

    public static void main(String[] args) {
        int[] arr = {3, 34, 4, 12, 5, 2};
        int sum = 9;

        System.out.println("Array: [3, 34, 4, 12, 5, 2], Target: " + sum);
        System.out.println("Recursion: " + subsetSumRecur(arr, arr.length, sum));

        Boolean[][] memo = new Boolean[arr.length + 1][sum + 1];
        System.out.println("Memoization: " + subsetSumMemo(arr, arr.length, sum, memo));

        System.out.println("Tabulation: " + subsetSumTab(arr, sum));
        // Expected: true (3+4+2=9, or 4+5=9)
    }
}
```

---

# PARTITION EQUAL SUBSET SUM

## Problem
Given an array, can you partition it into TWO subsets with EQUAL sum?

## Think About It
- First, total sum must be EVEN (odd sum can't be split equally)
- Target = totalSum / 2
- Now it's just SUBSET SUM with target = totalSum/2!

```java
public class PartitionEqualSubsetSum {

    // Uses subset sum tabulation (same logic)
    public static boolean canPartition(int[] nums) {
        int totalSum = 0;
        for (int num : nums) totalSum += num;

        // If odd, impossible
        if (totalSum % 2 != 0) return false;

        int target = totalSum / 2;
        return SubsetSum.subsetSumTab(nums, target);
    }

    // ---- FULL TABULATION (written explicitly) ----
    public static boolean canPartitionFull(int[] nums) {
        int totalSum = 0;
        for (int num : nums) totalSum += num;

        if (totalSum % 2 != 0) return false;

        int target = totalSum / 2;
        int n = nums.length;

        boolean[][] dp = new boolean[n + 1][target + 1];

        // Sum 0 always possible
        for (int i = 0; i <= n; i++) dp[i][0] = true;

        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= target; s++) {
                if (nums[i - 1] <= s) {
                    dp[i][s] = dp[i - 1][s] || dp[i - 1][s - nums[i - 1]];
                } else {
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        return dp[n][target];
    }

    public static void main(String[] args) {
        int[] nums = {1, 5, 11, 5};

        System.out.println("Array: [1, 5, 11, 5]");
        System.out.println("Can partition equally? " + canPartition(nums));
        // Expected: true (1+5+5=11, and 11=11)

        int[] nums2 = {1, 2, 3, 5};
        System.out.println("Array: [1, 2, 3, 5]");
        System.out.println("Can partition equally? " + canPartition(nums2));
        // Expected: false
    }
}
```

# UNBOUNDED KNAPSACK

## Problem
Same as 0/1 Knapsack, but now you can take UNLIMITED copies of each item! (That's why it's called "unbounded")

## Key Difference from 0/1 Knapsack:
- **0/1 Knapsack**: `dp[i][w] = max(dp[i-1][w], val[i-1] + dp[i-1][w-wt[i-1]])`
  — After using item i-1, you move to row i-1 (can't reuse item)
- **Unbounded Knapsack**: `dp[i][w] = max(dp[i-1][w], val[i-1] + dp[i][w-wt[i-1]])`
  — After using item i-1, you stay in row i (can use item again!)

Same column index change: `i-1` vs `i` — that's the ONLY difference!

```java
public class UnboundedKnapsack {

    // ---- RECURSION (NAIVE) ----
    public static int unboundedRecur(int n, int W, int[] val, int[] wt) {
        if (n == 0 || W == 0) {
            return 0;
        }

        if (wt[n - 1] > W) {
            return unboundedRecur(n - 1, W, val, wt);
        }

        // Skip item
        int skip = unboundedRecur(n - 1, W, val, wt);
        // Take item — NOTICE: we call with n (not n-1) because we can reuse!
        int take = val[n - 1] + unboundedRecur(n, W - wt[n - 1], val, wt);

        return Math.max(skip, take);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int unboundedMemo(int n, int W, int[] val, int[] wt, int[][] memo) {
        if (n == 0 || W == 0) {
            return 0;
        }

        if (memo[n][W] != -1) {
            return memo[n][W];
        }

        if (wt[n - 1] > W) {
            memo[n][W] = unboundedMemo(n - 1, W, val, wt, memo);
        } else {
            int skip = unboundedMemo(n - 1, W, val, wt, memo);
            int take = val[n - 1] + unboundedMemo(n, W - wt[n - 1], val, wt, memo);
            memo[n][W] = Math.max(skip, take);
        }

        return memo[n][W];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int unboundedTab(int W, int[] val, int[] wt) {
        int n = val.length;
        int[][] dp = new int[n + 1][W + 1];

        for (int i = 1; i <= n; i++) {
            for (int w = 1; w <= W; w++) {
                if (wt[i - 1] <= w) {
                    // KEY difference from 0/1: dp[i][w-wt[i-1]] NOT dp[i-1][w-wt[i-1]]
                    dp[i][w] = Math.max(
                        dp[i - 1][w],
                        val[i - 1] + dp[i][w - wt[i - 1]]  // Stay on row i (reuse allowed!)
                    );
                } else {
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        return dp[n][W];
    }

    public static void main(String[] args) {
        int[] val = {10, 40, 50, 70};
        int[] wt = {1, 3, 4, 5};
        int W = 8;

        System.out.println("Unbounded Knapsack");
        System.out.println("Items: (val=10, wt=1), (40,3), (50,4), (70,5)");
        System.out.println("Capacity: " + W);

        System.out.println("Recursion: " + unboundedRecur(val.length, W, val, wt));
        int[][] memo = new int[val.length + 1][W + 1];
        for (int i = 0; i <= val.length; i++)
            for (int w = 0; w <= W; w++)
                memo[i][w] = -1;
        System.out.println("Memoization: " + unboundedMemo(val.length, W, val, wt, memo));
        System.out.println("Tabulation: " + unboundedTab(W, val, wt));
    }
}
```

---

# ROD CUTTING

## Problem
You have a rod of length `n` and a price array `price[i]` where `price[i]` is the price of a rod of length `i+1`. Cut the rod into pieces to maximize profit. You can cut any number of pieces of any lengths.

## Think About It
This is EXACTLY Unbounded Knapsack!
- Rod length = Knapsack capacity
- Piece lengths = item weights (1 to n)
- Prices = item values
- You can use unlimited pieces of each length

```java
public class RodCutting {

    // ---- RECURSION (NAIVE) ----
    // maxProfit(length) = max price obtainable from rod of given length
    public static int cutRodRecur(int[] price, int n) {
        if (n <= 0) return 0;

        int maxVal = Integer.MIN_VALUE;

        // Try cutting a piece of length i+1
        for (int i = 0; i < n; i++) {
            // Cut piece of length (i+1), get price[i], then recurse on remaining length
            int val = price[i] + cutRodRecur(price, n - (i + 1));
            maxVal = Math.max(maxVal, val);
        }

        return maxVal;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int cutRodMemo(int[] price, int n, int[] memo) {
        if (n <= 0) return 0;
        if (memo[n] != -1) return memo[n];

        int maxVal = Integer.MIN_VALUE;
        for (int i = 0; i < n; i++) {
            int val = price[i] + cutRodMemo(price, n - (i + 1), memo);
            maxVal = Math.max(maxVal, val);
        }

        memo[n] = maxVal;
        return memo[n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int cutRodTab(int[] price, int n) {
        // dp[i] = max profit from rod of length i
        int[] dp = new int[n + 1];

        // dp[0] = 0 (no rod, no profit)

        // Build bottom-up: rod lengths 1, 2, ..., n
        for (int len = 1; len <= n; len++) {
            int maxVal = Integer.MIN_VALUE;
            // Try all possible first cuts
            for (int cut = 0; cut < len; cut++) {
                // Cut piece of length (cut+1) with price[cut]
                // Remaining length = len - (cut+1)
                int val = price[cut] + dp[len - (cut + 1)];
                maxVal = Math.max(maxVal, val);
            }
            dp[len] = maxVal;
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int[] price = {1, 5, 8, 9, 10, 17, 17, 20};
        int n = 8;

        System.out.println("Rod Cutting");
        System.out.println("Length: " + n);
        System.out.println("Prices: [1, 5, 8, 9, 10, 17, 17, 20]");

        System.out.println("Recursion: " + cutRodRecur(price, n));

        int[] memo = new int[n + 1];
        java.util.Arrays.fill(memo, -1);
        System.out.println("Memoization: " + cutRodMemo(price, n, memo));

        System.out.println("Tabulation: " + cutRodTab(price, n));
        // Expected: 22 (cut into 2+6: 5+17=22)
    }
}
```

---

# COIN CHANGE (NUMBER OF WAYS)

## Problem
Given unlimited coins of certain denominations and a target amount, find the NUMBER OF WAYS to make the amount. Order doesn't matter (combinations, not permutations).

## Think About It
This is Unbounded Knapsack where:
- Coin denominations = item weights
- We're counting NUMBER of ways to reach exact sum
- Recurrence: ways(i, sum) = ways(i-1, sum) + ways(i, sum - coins[i-1])

```java
public class CoinChangeWays {

    // ---- RECURSION (NAIVE) ----
    public static int countWaysRecur(int[] coins, int n, int sum) {
        // Base: sum = 0 -> 1 way (use no coins)
        if (sum == 0) return 1;
        // Base: no coins left but sum > 0 -> no way
        if (n == 0) return 0;

        // If coin > sum, skip it
        if (coins[n - 1] > sum) {
            return countWaysRecur(coins, n - 1, sum);
        }

        // Skip coin + use coin (stay at n because unlimited)
        return countWaysRecur(coins, n - 1, sum) +
               countWaysRecur(coins, n, sum - coins[n - 1]);
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int countWaysMemo(int[] coins, int n, int sum, int[][] memo) {
        if (sum == 0) return 1;
        if (n == 0) return 0;

        if (memo[n][sum] != -1) return memo[n][sum];

        if (coins[n - 1] > sum) {
            memo[n][sum] = countWaysMemo(coins, n - 1, sum, memo);
        } else {
            memo[n][sum] = countWaysMemo(coins, n - 1, sum, memo) +
                           countWaysMemo(coins, n, sum - coins[n - 1], memo);
        }

        return memo[n][sum];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int countWaysTab(int[] coins, int sum) {
        int n = coins.length;
        int[][] dp = new int[n + 1][sum + 1];

        // Sum 0: 1 way (empty set of coins)
        for (int i = 0; i <= n; i++) dp[i][0] = 1;

        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= sum; s++) {
                if (coins[i - 1] <= s) {
                    // Skip coin OR use coin (stay at i for reuse)
                    dp[i][s] = dp[i - 1][s] + dp[i][s - coins[i - 1]];
                } else {
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        return dp[n][sum];
    }

    public static void main(String[] args) {
        int[] coins = {1, 2, 3};
        int sum = 4;

        System.out.println("Coin Change (Number of Ways)");
        System.out.println("Coins: [1, 2, 3], Amount: " + sum);

        System.out.println("Recursion: " + countWaysRecur(coins, coins.length, sum));

        int[][] memo = new int[coins.length + 1][sum + 1];
        for (int i = 0; i <= coins.length; i++)
            for (int s = 0; s <= sum; s++)
                memo[i][s] = -1;
        System.out.println("Memoization: " + countWaysMemo(coins, coins.length, sum, memo));

        System.out.println("Tabulation: " + countWaysTab(coins, sum));
        // Expected: 4
        // Ways: {1,1,1,1}, {1,1,2}, {1,3}, {2,2}
    }
}
```

# COIN CHANGE (MINIMUM COINS)

## Problem
Given unlimited coins of certain denominations and a target amount, find the MINIMUM NUMBER of coins needed to make the amount. If impossible, return -1.

## Think About It
This is different from "number of ways" — we want MINIMUM coins.
- For each coin, either take it (add 1 to count) or skip it
- `minCoins(sum) = 1 + min(minCoins(sum - coin) for each coin <= sum)`

```java
public class CoinChangeMin {

    // ---- RECURSION (NAIVE) ----
    public static int minCoinsRecur(int[] coins, int sum) {
        // Base: sum = 0 -> 0 coins needed
        if (sum == 0) return 0;

        int result = Integer.MAX_VALUE;

        // Try every coin
        for (int coin : coins) {
            if (coin <= sum) {
                int subResult = minCoinsRecur(coins, sum - coin);
                // If a solution exists, take min
                if (subResult != Integer.MAX_VALUE) {
                    result = Math.min(result, 1 + subResult);
                }
            }
        }

        return result;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minCoinsMemo(int[] coins, int sum, int[] memo) {
        if (sum == 0) return 0;
        if (memo[sum] != -1) return memo[sum];

        int result = Integer.MAX_VALUE;
        for (int coin : coins) {
            if (coin <= sum) {
                int subResult = minCoinsMemo(coins, sum - coin, memo);
                if (subResult != Integer.MAX_VALUE) {
                    result = Math.min(result, 1 + subResult);
                }
            }
        }

        memo[sum] = result;
        return memo[sum];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minCoinsTab(int[] coins, int sum) {
        // dp[s] = min coins to make amount s
        int[] dp = new int[sum + 1];

        // Initialize with a large number (sentinel for "impossible")
        java.util.Arrays.fill(dp, Integer.MAX_VALUE);
        dp[0] = 0; // 0 coins to make amount 0

        // Build bottom-up
        for (int s = 1; s <= sum; s++) {
            for (int coin : coins) {
                if (coin <= s && dp[s - coin] != Integer.MAX_VALUE) {
                    dp[s] = Math.min(dp[s], 1 + dp[s - coin]);
                }
            }
        }

        return dp[sum] == Integer.MAX_VALUE ? -1 : dp[sum];
    }

    public static void main(String[] args) {
        int[] coins = {1, 2, 5};
        int sum = 11;

        System.out.println("Coin Change (Minimum Coins)");
        System.out.println("Coins: [1, 2, 5], Amount: " + sum);

        int res = minCoinsRecur(coins, sum);
        System.out.println("Recursion: " + (res == Integer.MAX_VALUE ? -1 : res));

        int[] memo = new int[sum + 1];
        java.util.Arrays.fill(memo, -1);
        int memoRes = minCoinsMemo(coins, sum, memo);
        System.out.println("Memoization: " + (memoRes == Integer.MAX_VALUE ? -1 : memoRes));

        System.out.println("Tabulation: " + minCoinsTab(coins, sum));
        // Expected: 3 (5+5+1=11)
    }
}
```

---

# LONGEST COMMON SUBSEQUENCE (LCS)

## Problem
Given two strings, find the length of the LONGEST subsequence that appears in BOTH strings. A subsequence is a sequence that can be derived by deleting some characters WITHOUT changing order.

Example: "abcde" and "ace" -> LCS = "ace" (length 3)

## The DP Table Explained
For strings X = "abcde" and Y = "ace":

```
    0   a   c   e
0   0   0   0   0
a   0   1   1   1
b   0   1   1   1
c   0   1   2   2
d   0   1   2   2
e   0   1   2   3
```

**How to read:** dp[i][j] = LCS of X[0...i-1] and Y[0...j-1]

**Rule:** If chars match, dp[i][j] = 1 + dp[i-1][j-1] (diagonal + 1)
If not, dp[i][j] = max(dp[i-1][j], dp[i][j-1]) (max of left/above)

```java
public class LCS {

    // ---- RECURSION (NAIVE) ----
    public static int lcsRecur(String X, String Y, int m, int n) {
        // Base: empty string -> LCS is 0
        if (m == 0 || n == 0) return 0;

        // If last characters match
        if (X.charAt(m - 1) == Y.charAt(n - 1)) {
            return 1 + lcsRecur(X, Y, m - 1, n - 1);
        }

        // If not, take max of removing from X or removing from Y
        return Math.max(
            lcsRecur(X, Y, m - 1, n),
            lcsRecur(X, Y, m, n - 1)
        );
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int lcsMemo(String X, String Y, int m, int n, int[][] memo) {
        if (m == 0 || n == 0) return 0;

        if (memo[m][n] != -1) return memo[m][n];

        if (X.charAt(m - 1) == Y.charAt(n - 1)) {
            memo[m][n] = 1 + lcsMemo(X, Y, m - 1, n - 1, memo);
        } else {
            memo[m][n] = Math.max(
                lcsMemo(X, Y, m - 1, n, memo),
                lcsMemo(X, Y, m, n - 1, memo)
            );
        }

        return memo[m][n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int lcsTab(String X, String Y) {
        int m = X.length();
        int n = Y.length();
        int[][] dp = new int[m + 1][n + 1];

        // dp[0][*] and dp[*][0] are 0 by default

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }

        // Print table
        System.out.println("\nLCS DP Table:");
        System.out.print("    ");
        for (int j = 0; j <= n; j++) System.out.printf("%4c", j == 0 ? ' ' : Y.charAt(j - 1));
        System.out.println();
        for (int i = 0; i <= m; i++) {
            System.out.printf("%4c ", i == 0 ? ' ' : X.charAt(i - 1));
            for (int j = 0; j <= n; j++) {
                System.out.printf("%4d", dp[i][j]);
            }
            System.out.println();
        }

        return dp[m][n];
    }

    // BONUS: Print the actual LCS string
    public static String getLCS(String X, String Y) {
        int m = X.length(), n = Y.length();
        int[][] dp = new int[m + 1][n + 1];

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }

        // Backtrack to find the actual subsequence
        StringBuilder sb = new StringBuilder();
        int i = m, j = n;
        while (i > 0 && j > 0) {
            if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                sb.append(X.charAt(i - 1));
                i--;
                j--;
            } else if (dp[i - 1][j] > dp[i][j - 1]) {
                i--;
            } else {
                j--;
            }
        }

        return sb.reverse().toString();
    }

    public static void main(String[] args) {
        String X = "abcde";
        String Y = "ace";

        System.out.println("LCS of \"" + X + "\" and \"" + Y + "\"");

        System.out.println("Recursion: " + lcsRecur(X, Y, X.length(), Y.length()));

        int[][] memo = new int[X.length() + 1][Y.length() + 1];
        for (int i = 0; i <= X.length(); i++)
            for (int j = 0; j <= Y.length(); j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + lcsMemo(X, Y, X.length(), Y.length(), memo));

        System.out.println("Tabulation: " + lcsTab(X, Y));
        System.out.println("Actual LCS: " + getLCS(X, Y));
        // Expected: 3, "ace"
    }
}
```

---

# LONGEST COMMON SUBSTRING

## Problem
Find the length of the LONGEST substring (CONTIGUOUS characters) common to both strings.

## Key Difference from LCS:
- LCS: characters don't need to be contiguous, dp = 1 + dp[i-1][j-1] on match
- Substring: MUST be contiguous, dp = 0 on mismatch (break the chain!)

```java
public class LongestCommonSubstring {

    // ---- TABULATION (BOTTOM-UP) ----
    public static int longestCommonSubstring(String X, String Y) {
        int m = X.length(), n = Y.length();
        int[][] dp = new int[m + 1][n + 1];
        int maxLen = 0;
        int endIdx = 0; // To reconstruct the substring

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (X.charAt(i - 1) == Y.charAt(j - 1)) {
                    // Extend the common substring
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                    if (dp[i][j] > maxLen) {
                        maxLen = dp[i][j];
                        endIdx = i; // End position in X
                    }
                }
                // On mismatch: dp[i][j] stays 0 (break the chain)
                // This is the KEY difference from LCS!
            }
        }

        // Print table
        System.out.println("\nLongest Common Substring DP Table:");
        System.out.print("    ");
        for (int j = 0; j <= n; j++) System.out.printf("%4c", j == 0 ? ' ' : Y.charAt(j - 1));
        System.out.println();
        for (int i = 0; i <= m; i++) {
            System.out.printf("%4c ", i == 0 ? ' ' : X.charAt(i - 1));
            for (int j = 0; j <= n; j++) {
                System.out.printf("%4d", dp[i][j]);
            }
            System.out.println();
        }

        // Reconstruct the substring
        String substr = X.substring(endIdx - maxLen, endIdx);
        System.out.println("Longest common substring: \"" + substr + "\"");

        return maxLen;
    }

    public static void main(String[] args) {
        String X = "abcde";
        String Y = "abfce";

        System.out.println("Strings: \"" + X + "\", \"" + Y + "\"");
        System.out.println("Length: " + longestCommonSubstring(X, Y));
    }
}
```

---

# LONGEST INCREASING SUBSEQUENCE (LIS)

## Problem
Find the length of the longest subsequence where elements are in strictly increasing order.

Example: [10, 9, 2, 5, 3, 7, 101, 18] -> LIS = [2, 5, 7, 101] (length 4)

## Approach
For each element at position `i`, look at all previous elements `j < i`. If `arr[j] < arr[i]`, then we can extend the LIS ending at `j` to include `arr[i]`. Take the max.

```java
public class LIS {

    // ---- RECURSION (NAIVE) ----
    // lisEndingAt(i) = LIS length ending at index i
    public static int lisEndingAtRecur(int[] arr, int i) {
        // Base: each element is at least length 1 by itself
        int max = 1;

        // Check all previous elements
        for (int j = 0; j < i; j++) {
            if (arr[j] < arr[i]) {
                // We can extend the LIS ending at j
                max = Math.max(max, 1 + lisEndingAtRecur(arr, j));
            }
        }

        return max;
    }

    public static int lisRecur(int[] arr) {
        int n = arr.length;
        int max = 0;
        for (int i = 0; i < n; i++) {
            max = Math.max(max, lisEndingAtRecur(arr, i));
        }
        return max;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int lisEndingAtMemo(int[] arr, int i, int[] memo) {
        if (memo[i] != -1) return memo[i];

        int max = 1;
        for (int j = 0; j < i; j++) {
            if (arr[j] < arr[i]) {
                max = Math.max(max, 1 + lisEndingAtMemo(arr, j, memo));
            }
        }

        memo[i] = max;
        return memo[i];
    }

    public static int lisMemo(int[] arr) {
        int n = arr.length;
        int[] memo = new int[n];
        java.util.Arrays.fill(memo, -1);
        int max = 0;
        for (int i = 0; i < n; i++) {
            max = Math.max(max, lisEndingAtMemo(arr, i, memo));
        }
        return max;
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int lisTab(int[] arr) {
        int n = arr.length;
        // dp[i] = LIS length ending at index i
        int[] dp = new int[n];

        // Each element alone has LIS length 1
        java.util.Arrays.fill(dp, 1);

        // For each element, check all previous elements
        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (arr[j] < arr[i]) {
                    // We can extend the LIS ending at j
                    dp[i] = Math.max(dp[i], 1 + dp[j]);
                }
            }
        }

        // Answer is the maximum in dp
        int max = 0;
        for (int val : dp) {
            max = Math.max(max, val);
        }

        return max;
    }

    // ---- BINARY SEARCH APPROACH (O(n log n)) ----
    // This is an advanced optimization using patience sorting
    public static int lisBinarySearch(int[] arr) {
        // tails[i] = smallest possible tail of LIS of length i+1
        int[] tails = new int[arr.length];
        int len = 0;

        for (int x : arr) {
            // Binary search to find where x fits in tails
            int left = 0, right = len;
            while (left < right) {
                int mid = left + (right - left) / 2;
                if (tails[mid] < x) {
                    left = mid + 1;
                } else {
                    right = mid;
                }
            }
            tails[left] = x;
            if (left == len) len++;
        }

        return len;
    }

    public static void main(String[] args) {
        int[] arr = {10, 9, 2, 5, 3, 7, 101, 18};

        System.out.println("Array: [10, 9, 2, 5, 3, 7, 101, 18]");
        System.out.println("Recursion: " + lisRecur(arr));
        System.out.println("Memoization: " + lisMemo(arr));
        System.out.println("Tabulation: " + lisTab(arr));
        System.out.println("Binary Search: " + lisBinarySearch(arr));
        // Expected: 4 (2, 5, 7, 101)
    }
}
```

# EDIT DISTANCE (LEVENSHTEIN DISTANCE)

## Problem
Given two strings, find the MINIMUM number of operations (insert, delete, replace) to convert one string into another.

## Think About It
At each position (i, j):
1. If chars match: dp[i][j] = dp[i-1][j-1] (no operation needed)
2. If not: min of:
   - DELETE from word1: 1 + dp[i-1][j]
   - INSERT into word1: 1 + dp[i][j-1]
   - REPLACE: 1 + dp[i-1][j-1]

```java
public class EditDistance {

    // ---- RECURSION (NAIVE) ----
    public static int editDistRecur(String s1, String s2, int m, int n) {
        // If s1 is empty, insert all of s2 (n operations)
        if (m == 0) return n;
        // If s2 is empty, delete all of s1 (m operations)
        if (n == 0) return m;

        // If last chars match, move both pointers
        if (s1.charAt(m - 1) == s2.charAt(n - 1)) {
            return editDistRecur(s1, s2, m - 1, n - 1);
        }

        // Try delete, insert, replace — take minimum
        int delete = 1 + editDistRecur(s1, s2, m - 1, n);
        int insert = 1 + editDistRecur(s1, s2, m, n - 1);
        int replace = 1 + editDistRecur(s1, s2, m - 1, n - 1);

        return Math.min(delete, Math.min(insert, replace));
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int editDistMemo(String s1, String s2, int m, int n, int[][] memo) {
        if (m == 0) return n;
        if (n == 0) return m;

        if (memo[m][n] != -1) return memo[m][n];

        if (s1.charAt(m - 1) == s2.charAt(n - 1)) {
            memo[m][n] = editDistMemo(s1, s2, m - 1, n - 1, memo);
        } else {
            int delete = 1 + editDistMemo(s1, s2, m - 1, n, memo);
            int insert = 1 + editDistMemo(s1, s2, m, n - 1, memo);
            int replace = 1 + editDistMemo(s1, s2, m - 1, n - 1, memo);
            memo[m][n] = Math.min(delete, Math.min(insert, replace));
        }

        return memo[m][n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int editDistTab(String s1, String s2) {
        int m = s1.length(), n = s2.length();
        int[][] dp = new int[m + 1][n + 1];

        // Base: empty string cases
        for (int i = 0; i <= m; i++) dp[i][0] = i; // Delete all
        for (int j = 0; j <= n; j++) dp[0][j] = j; // Insert all

        // Fill table
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (s1.charAt(i - 1) == s2.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1];
                } else {
                    dp[i][j] = 1 + Math.min(
                        dp[i - 1][j],     // Delete from s1
                        Math.min(
                            dp[i][j - 1], // Insert into s1 (or delete from s2)
                            dp[i - 1][j - 1] // Replace
                        )
                    );
                }
            }
        }

        // Print table
        System.out.println("\nEdit Distance DP Table:");
        System.out.print("      ");
        for (int j = 0; j <= n; j++) System.out.printf("%4c", j == 0 ? '#' : s2.charAt(j - 1));
        System.out.println();
        for (int i = 0; i <= m; i++) {
            System.out.printf("%4c ", i == 0 ? '#' : s1.charAt(i - 1));
            for (int j = 0; j <= n; j++) {
                System.out.printf("%4d", dp[i][j]);
            }
            System.out.println();
        }

        return dp[m][n];
    }

    public static void main(String[] args) {
        String s1 = "horse";
        String s2 = "ros";

        System.out.println("Edit Distance: \"" + s1 + "\" -> \"" + s2 + "\"");
        System.out.println("Recursion: " + editDistRecur(s1, s2, s1.length(), s2.length()));

        int[][] memo = new int[s1.length() + 1][s2.length() + 1];
        for (int i = 0; i <= s1.length(); i++)
            for (int j = 0; j <= s2.length(); j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + editDistMemo(s1, s2, s1.length(), s2.length(), memo));

        System.out.println("Tabulation: " + editDistTab(s1, s2));
        // Expected: 3
        // horse -> rorse (replace h->r)
        // rorse -> rose (delete second r)
        // rose -> ros (delete e)
    }
}
```

---

# STRING CONVERSION (INSERT/DELETE ONLY)

## Problem
Find minimum number of INSERT and DELETE operations to convert string X to string Y (REPLACE not allowed).

## Think About It
1. Find LCS of X and Y (characters that are already in place)
2. Delete from X: |X| - |LCS|
3. Insert into X: |Y| - |LCS|
4. Total = |X| + |Y| - 2*|LCS|

```java
public class StringConversion {

    public static int stringConversionMinOps(String X, String Y) {
        int lcsLen = LCS.lcsTab(X, Y);

        int deletes = X.length() - lcsLen;
        int inserts = Y.length() - lcsLen;

        System.out.println("LCS length: " + lcsLen);
        System.out.println("Deletes needed: " + deletes);
        System.out.println("Inserts needed: " + inserts);

        return deletes + inserts;
    }

    public static void main(String[] args) {
        String X = "abcdef";
        String Y = "acbdf";

        System.out.println("Convert \"" + X + "\" to \"" + Y + "\"");
        System.out.println("Total operations: " + stringConversionMinOps(X, Y));
        // LCS = "acdf" (length 4)
        // Deletes: 6-4 = 2 (delete 'b', 'e')
        // Inserts: 5-4 = 1 (insert 'b')
        // Total: 3
    }
}
```

---

# WILDCARD MATCHING

## Problem
Given a string `s` and a pattern `p` with wildcards:
- `?` matches ANY SINGLE character
- `*` matches ANY SEQUENCE (including empty)

Return true if the pattern matches the entire string.

## Think About It
At (i, j) comparing s[i-1] and p[j-1]:
1. If chars match or p[j-1] == '?': dp[i][j] = dp[i-1][j-1]
2. If p[j-1] == '*': dp[i][j] = dp[i][j-1] (* matches empty) OR dp[i-1][j] (* matches one more char)

```java
public class WildcardMatching {

    // ---- RECURSION (NAIVE) ----
    public static boolean isMatchRecur(String s, String p, int m, int n) {
        // Both empty -> match
        if (m == 0 && n == 0) return true;
        // Pattern empty but string not -> no match
        if (n == 0) return false;
        // String empty: only matches if pattern is all '*'
        if (m == 0) {
            for (int i = 0; i < n; i++) {
                if (p.charAt(i) != '*') return false;
            }
            return true;
        }

        char sc = s.charAt(m - 1);
        char pc = p.charAt(n - 1);

        if (pc == '*') {
            // * matches empty (dp[i][j-1]) OR * matches one char (dp[i-1][j])
            return isMatchRecur(s, p, m, n - 1) ||
                   isMatchRecur(s, p, m - 1, n);
        } else if (pc == '?' || sc == pc) {
            return isMatchRecur(s, p, m - 1, n - 1);
        }

        return false;
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static boolean isMatchTab(String s, String p) {
        int m = s.length(), n = p.length();
        boolean[][] dp = new boolean[m + 1][n + 1];

        // Both empty
        dp[0][0] = true;

        // Empty string with pattern: only if all '*'
        for (int j = 1; j <= n; j++) {
            if (p.charAt(j - 1) == '*') {
                dp[0][j] = dp[0][j - 1];
            }
        }

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                char sc = s.charAt(i - 1);
                char pc = p.charAt(j - 1);

                if (pc == '*') {
                    // * matches empty (dp[i][j-1]) OR matches one char (dp[i-1][j])
                    dp[i][j] = dp[i][j - 1] || dp[i - 1][j];
                } else if (pc == '?' || sc == pc) {
                    dp[i][j] = dp[i - 1][j - 1];
                }
                // else: false (default)
            }
        }

        return dp[m][n];
    }

    public static void main(String[] args) {
        String[][] tests = {
            {"aa", "a"},
            {"aa", "*"},
            {"cb", "?a"},
            {"adceb", "*a*b"},
            {"acdcb", "a*c?b"}
        };

        for (String[] test : tests) {
            String s = test[0], p = test[1];
            boolean match1 = isMatchRecur(s, p, s.length(), p.length());
            boolean match2 = isMatchTab(s, p);
            System.out.println("isMatch(\"" + s + "\", \"" + p + "\") = " + match1 + " / " + match2);
        }
    }
}
```

---

# MATRIX CHAIN MULTIPLICATION (MCM)

## Problem
Given an array `arr[]` representing dimensions of matrices (matrix i has dimensions arr[i-1] x arr[i]), find the MINIMUM number of scalar multiplications needed to multiply the chain.

Example: arr = [10, 20, 30, 40, 30] -> 4 matrices: 10x20, 20x30, 30x40, 40x30

## Think About It
We need to PARENTHESIZE the multiplication to minimize cost. Different parenthesizations give different costs.

For matrices A (pxq) and B (qxr), multiplication cost = p x q x r.

MCM recurrence:
- `mcm(i, j)` = min cost to multiply matrices i through j
- If i == j: cost = 0 (only one matrix)
- Otherwise: try all possible split points k from i to j-1
- `mcm(i, j) = min(mcm(i, k) + mcm(k+1, j) + arr[i-1] * arr[k] * arr[j])`

```java
public class MCM {

    // ---- RECURSION (NAIVE) ----
    // mcmRecur(i, j) = min cost to multiply matrices i through j (1-indexed)
    public static int mcmRecur(int[] arr, int i, int j) {
        // Single matrix: no multiplication needed
        if (i == j) return 0;

        int minCost = Integer.MAX_VALUE;

        // Try every possible split point
        for (int k = i; k < j; k++) {
            // Cost = cost to multiply left chain + right chain + cost to combine
            int cost = mcmRecur(arr, i, k) +
                       mcmRecur(arr, k + 1, j) +
                       arr[i - 1] * arr[k] * arr[j];
            minCost = Math.min(minCost, cost);
        }

        return minCost;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int mcmMemo(int[] arr, int i, int j, int[][] memo) {
        if (i == j) return 0;

        if (memo[i][j] != -1) return memo[i][j];

        int minCost = Integer.MAX_VALUE;
        for (int k = i; k < j; k++) {
            int cost = mcmMemo(arr, i, k, memo) +
                       mcmMemo(arr, k + 1, j, memo) +
                       arr[i - 1] * arr[k] * arr[j];
            minCost = Math.min(minCost, cost);
        }

        memo[i][j] = minCost;
        return memo[i][j];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int mcmTab(int[] arr) {
        int n = arr.length; // Number of matrices = n - 1
        int[][] dp = new int[n][n];

        // dp[i][j] = min cost for matrices i..j
        // i == j case is 0 (already initialized)

        // Length of chain: 2, 3, ..., n-1
        for (int len = 2; len < n; len++) {
            for (int i = 1; i < n - len + 1; i++) {
                int j = i + len - 1;
                dp[i][j] = Integer.MAX_VALUE;

                for (int k = i; k < j; k++) {
                    int cost = dp[i][k] + dp[k + 1][j] +
                               arr[i - 1] * arr[k] * arr[j];
                    dp[i][j] = Math.min(dp[i][j], cost);
                }
            }
        }

        // Print table
        System.out.println("\nMCM DP Table:");
        for (int i = 1; i < n; i++) {
            for (int j = 1; j < n; j++) {
                if (i <= j && dp[i][j] > 0) {
                    System.out.println("dp[" + i + "][" + j + "] = " + dp[i][j]);
                }
            }
        }

        return dp[1][n - 1];
    }

    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 30};
        int n = arr.length;

        System.out.println("Matrix dimensions:");
        for (int i = 1; i < n; i++) {
            System.out.println("  A" + i + ": " + arr[i - 1] + "x" + arr[i]);
        }

        System.out.println("\nRecursion: " + mcmRecur(arr, 1, n - 1));

        int[][] memo = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + mcmMemo(arr, 1, n - 1, memo));

        System.out.println("Tabulation: " + mcmTab(arr));
    }
}
```

# PALINDROME PARTITIONING

## Problem
Given a string, partition it into substrings such that EVERY substring is a palindrome. Find the MINIMUM number of cuts needed.

Example: "nitin" -> 0 cuts (already palindrome)
Example: "aab" -> 1 cut ("aa" | "b")

## Think About It
Let `minCut(i, j)` = min cuts for substring s[i...j].
- If s[i...j] is palindrome: 0 cuts needed
- Else: try every split point k from i to j-1, take min

```java
public class PalindromePartitioning {

    // Helper: check if substring s[i...j] is palindrome
    private static boolean isPalindrome(String s, int i, int j) {
        while (i < j) {
            if (s.charAt(i) != s.charAt(j)) return false;
            i++;
            j--;
        }
        return true;
    }

    // ---- RECURSION (NAIVE) ----
    public static int minCutRecur(String s, int i, int j) {
        // Single character or palindrome: 0 cuts
        if (i >= j || isPalindrome(s, i, j)) return 0;

        int minCuts = Integer.MAX_VALUE;

        for (int k = i; k < j; k++) {
            int cuts = 1 + minCutRecur(s, i, k) + minCutRecur(s, k + 1, j);
            minCuts = Math.min(minCuts, cuts);
        }

        return minCuts;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minCutMemo(String s, int i, int j, int[][] memo) {
        if (i >= j || isPalindrome(s, i, j)) return 0;

        if (memo[i][j] != -1) return memo[i][j];

        int minCuts = Integer.MAX_VALUE;
        for (int k = i; k < j; k++) {
            int cuts = 1 + minCutMemo(s, i, k, memo) + minCutMemo(s, k + 1, j, memo);
            minCuts = Math.min(minCuts, cuts);
        }

        memo[i][j] = minCuts;
        return memo[i][j];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minCutTab(String s) {
        int n = s.length();

        // pal[i][j] = true if s[i...j] is palindrome
        boolean[][] pal = new boolean[n][n];

        // Every single character is a palindrome
        for (int i = 0; i < n; i++) pal[i][i] = true;

        // Fill palindrome table for longer substrings
        for (int len = 2; len <= n; len++) {
            for (int i = 0; i < n - len + 1; i++) {
                int j = i + len - 1;
                if (len == 2) {
                    pal[i][j] = (s.charAt(i) == s.charAt(j));
                } else {
                    pal[i][j] = (s.charAt(i) == s.charAt(j)) && pal[i + 1][j - 1];
                }
            }
        }

        // dp[i] = min cuts for s[0...i]
        int[] dp = new int[n];

        for (int i = 0; i < n; i++) {
            if (pal[0][i]) {
                dp[i] = 0; // Already palindrome from start
            } else {
                dp[i] = Integer.MAX_VALUE;
                for (int j = 0; j < i; j++) {
                    if (pal[j + 1][i]) {
                        dp[i] = Math.min(dp[i], 1 + dp[j]);
                    }
                }
            }
        }

        return dp[n - 1];
    }

    public static void main(String[] args) {
        String s = "aab";

        System.out.println("String: \"" + s + "\"");
        System.out.println("Recursion: " + minCutRecur(s, 0, s.length() - 1));

        int n = s.length();
        int[][] memo = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + minCutMemo(s, 0, n - 1, memo));

        System.out.println("Tabulation: " + minCutTab(s));
        // Expected: 1 ("aa" | "b")
    }
}
```

---

# MINIMUM PARTITIONING (MIN SUBSET SUM DIFF)

## Problem
Given an array, partition it into TWO subsets such that the ABSOLUTE difference of their sums is MINIMIZED.

## Think About It
- Calculate total sum
- We need to find a subset with sum as close to `totalSum/2` as possible
- This is SUBSET SUM problem: find all achievable sums up to totalSum/2
- The closest achievable sum to totalSum/2 gives the min difference

```java
public class MinimumPartitioning {

    // ---- TABULATION ----
    public static int minDiffTab(int[] nums) {
        int totalSum = 0;
        for (int num : nums) totalSum += num;

        int target = totalSum / 2;
        int n = nums.length;

        // dp[i][s] = can we make sum 's' with first 'i' elements?
        boolean[][] dp = new boolean[n + 1][target + 1];

        // Sum 0 is always achievable
        for (int i = 0; i <= n; i++) dp[i][0] = true;

        // Fill subset sum table
        for (int i = 1; i <= n; i++) {
            for (int s = 1; s <= target; s++) {
                if (nums[i - 1] <= s) {
                    dp[i][s] = dp[i - 1][s] || dp[i - 1][s - nums[i - 1]];
                } else {
                    dp[i][s] = dp[i - 1][s];
                }
            }
        }

        // Find the largest achievable sum <= target
        int sum1 = 0;
        for (int s = target; s >= 0; s--) {
            if (dp[n][s]) {
                sum1 = s;
                break;
            }
        }

        int sum2 = totalSum - sum1;
        return Math.abs(sum2 - sum1);
    }

    public static void main(String[] args) {
        int[] nums = {1, 6, 11, 5};

        System.out.println("Array: [1, 6, 11, 5]");
        System.out.println("Min difference: " + minDiffTab(nums));
        // Expected: 1
        // Subset 1: {1, 6, 5} = 12, Subset 2: {11} = 11, diff = 1
    }
}
```

---

# BOOLEAN PARENTHESIZATION

## Problem
Given a boolean expression with symbols (T, F) and operators (&, |, ^), find the NUMBER OF WAYS to parenthesize it so that it evaluates to TRUE.

Example: "T|T&F^T" — count ways to add parentheses to get TRUE

## Think About It
This is MCM-like. At each operator, we split the expression into left and right parts, then count ways for each.

For operator `&`: waysTrue = leftTrue * rightTrue
For operator `|`: waysTrue = total - (leftFalse * rightFalse)
For operator `^`: waysTrue = leftTrue*rightFalse + leftFalse*rightTrue

```java
public class BooleanParenthesization {

    // ---- RECURSION (NAIVE) ----
    // countWays(s, i, j, isTrue) = ways to evaluate s[i...j] to isTrue
    public static int countWaysRecur(String s, int i, int j, boolean isTrue) {
        // Base: single character
        if (i == j) {
            if (isTrue) return s.charAt(i) == 'T' ? 1 : 0;
            else return s.charAt(i) == 'F' ? 1 : 0;
        }

        int ways = 0;

        // Try each operator (at odd positions in string)
        for (int k = i + 1; k < j; k += 2) {
            char op = s.charAt(k);

            int leftTrue = countWaysRecur(s, i, k - 1, true);
            int leftFalse = countWaysRecur(s, i, k - 1, false);
            int rightTrue = countWaysRecur(s, k + 1, j, true);
            int rightFalse = countWaysRecur(s, k + 1, j, false);

            switch (op) {
                case '&':
                    if (isTrue) ways += leftTrue * rightTrue;
                    else ways += leftTrue * rightFalse + leftFalse * rightTrue + leftFalse * rightFalse;
                    break;
                case '|':
                    if (isTrue) ways += leftTrue * rightTrue + leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftFalse * rightFalse;
                    break;
                case '^':
                    if (isTrue) ways += leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftTrue * rightTrue + leftFalse * rightFalse;
                    break;
            }
        }

        return ways;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int countWaysMemo(String s, int i, int j, boolean isTrue, Integer[][][] memo) {
        if (i == j) {
            if (isTrue) return s.charAt(i) == 'T' ? 1 : 0;
            else return s.charAt(i) == 'F' ? 1 : 0;
        }

        int idx = isTrue ? 1 : 0;
        if (memo[i][j][idx] != null) return memo[i][j][idx];

        int ways = 0;
        for (int k = i + 1; k < j; k += 2) {
            char op = s.charAt(k);

            int leftTrue = countWaysMemo(s, i, k - 1, true, memo);
            int leftFalse = countWaysMemo(s, i, k - 1, false, memo);
            int rightTrue = countWaysMemo(s, k + 1, j, true, memo);
            int rightFalse = countWaysMemo(s, k + 1, j, false, memo);

            switch (op) {
                case '&':
                    if (isTrue) ways += leftTrue * rightTrue;
                    else ways += leftTrue * rightFalse + leftFalse * rightTrue + leftFalse * rightFalse;
                    break;
                case '|':
                    if (isTrue) ways += leftTrue * rightTrue + leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftFalse * rightFalse;
                    break;
                case '^':
                    if (isTrue) ways += leftTrue * rightFalse + leftFalse * rightTrue;
                    else ways += leftTrue * rightTrue + leftFalse * rightFalse;
                    break;
            }
        }

        memo[i][j][idx] = ways;
        return ways;
    }

    public static void main(String[] args) {
        String expr = "T|T&F^T";

        System.out.println("Expression: " + expr);
        System.out.println("Recursion: " + countWaysRecur(expr, 0, expr.length() - 1, true));

        int n = expr.length();
        Integer[][][] memo = new Integer[n][n][2];
        System.out.println("Memoization: " + countWaysMemo(expr, 0, n - 1, true, memo));
    }
}
```

# EGG DROPPING

## Problem
You have `k` eggs and a building with `n` floors. Find the MINIMUM number of attempts needed to find the CRITICAL floor (the highest floor from which an egg doesn't break). Eggs can break or survive.

## Think About It
At each floor `x`, an egg either:
1. **BREAKS**: you have k-1 eggs, need to check floors 1 to x-1
2. **SURVIVES**: you have k eggs, need to check floors x+1 to n

You want the floor choice that MINIMIZES the WORST-CASE attempts.

```
eggDrop(k, n) = min over all x of (1 + max(eggDrop(k-1, x-1), eggDrop(k, n-x)))
```

```java
public class EggDropping {

    // ---- RECURSION (NAIVE) ----
    public static int eggDropRecur(int k, int n) {
        // Base: 0 floors -> 0 attempts, 1 floor -> 1 attempt
        if (n == 0 || n == 1) return n;
        // Base: 1 egg -> must try all floors linearly
        if (k == 1) return n;

        int minAttempts = Integer.MAX_VALUE;

        // Try dropping from every floor
        for (int x = 1; x <= n; x++) {
            // Egg breaks: check floors below (x-1 floors, k-1 eggs)
            int breaks = eggDropRecur(k - 1, x - 1);
            // Egg survives: check floors above (n-x floors, k eggs)
            int survives = eggDropRecur(k, n - x);

            // Worst case of the two possibilities
            int worstCase = 1 + Math.max(breaks, survives);

            minAttempts = Math.min(minAttempts, worstCase);
        }

        return minAttempts;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int eggDropMemo(int k, int n, int[][] memo) {
        if (n == 0 || n == 1) return n;
        if (k == 1) return n;

        if (memo[k][n] != -1) return memo[k][n];

        int minAttempts = Integer.MAX_VALUE;
        for (int x = 1; x <= n; x++) {
            int breaks = eggDropMemo(k - 1, x - 1, memo);
            int survives = eggDropMemo(k, n - x, memo);
            minAttempts = Math.min(minAttempts, 1 + Math.max(breaks, survives));
        }

        memo[k][n] = minAttempts;
        return memo[k][n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int eggDropTab(int K, int N) {
        // dp[k][n] = min attempts with k eggs and n floors
        int[][] dp = new int[K + 1][N + 1];

        // 0 floors -> 0, 1 floor -> 1
        for (int k = 1; k <= K; k++) {
            dp[k][0] = 0;
            dp[k][1] = 1;
        }

        // 1 egg -> must try all floors linearly
        for (int n = 1; n <= N; n++) {
            dp[1][n] = n;
        }

        // Fill for remaining eggs and floors
        for (int k = 2; k <= K; k++) {
            for (int n = 2; n <= N; n++) {
                dp[k][n] = Integer.MAX_VALUE;
                // Try all floors
                for (int x = 1; x <= n; x++) {
                    int worstCase = 1 + Math.max(dp[k - 1][x - 1], dp[k][n - x]);
                    dp[k][n] = Math.min(dp[k][n], worstCase);
                }
            }
        }

        return dp[K][N];
    }

    // ---- OPTIMIZED TABULATION (with binary search) ----
    public static int eggDropTabOpt(int K, int N) {
        int[][] dp = new int[K + 1][N + 1];

        for (int k = 1; k <= K; k++) {
            dp[k][0] = 0;
            dp[k][1] = 1;
        }
        for (int n = 1; n <= N; n++) dp[1][n] = n;

        for (int k = 2; k <= K; k++) {
            for (int n = 2; n <= N; n++) {
                dp[k][n] = Integer.MAX_VALUE;
                int low = 1, high = n;
                while (low <= high) {
                    int mid = low + (high - low) / 2;
                    int breaks = dp[k - 1][mid - 1];
                    int survives = dp[k][n - mid];
                    int worstCase = 1 + Math.max(breaks, survives);
                    dp[k][n] = Math.min(dp[k][n], worstCase);
                    if (breaks < survives) {
                        low = mid + 1;
                    } else {
                        high = mid - 1;
                    }
                }
            }
        }

        return dp[K][N];
    }

    public static void main(String[] args) {
        int k = 2, n = 10;

        System.out.println("Eggs: " + k + ", Floors: " + n);
        System.out.println("Recursion: " + eggDropRecur(k, n));

        int[][] memo = new int[k + 1][n + 1];
        for (int i = 0; i <= k; i++)
            for (int j = 0; j <= n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + eggDropMemo(k, n, memo));

        System.out.println("Tabulation: " + eggDropTab(k, n));
        System.out.println("Tabulation Opt: " + eggDropTabOpt(k, n));
        // Expected: 4
    }
}
```

---

# DP ON TREES

## DIAMETER OF A BINARY TREE

### Problem
Find the longest path between any two nodes in a binary tree. The path may or may not pass through the root.

### Think About It
For each node, the diameter through that node = height(left) + height(right) + 1 (node itself). The overall diameter is the maximum of diameters through all nodes.

```java
// Tree node class
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;

    TreeNode(int val) {
        this.val = val;
    }
}

public class TreeDiameter {

    // Global variable to store max diameter found so far
    private static int maxDiameter;

    // Helper: returns height of tree rooted at node
    // AND updates maxDiameter
    private static int height(TreeNode node) {
        if (node == null) return 0;

        // Get height of left and right subtrees
        int leftHeight = height(node.left);
        int rightHeight = height(node.right);

        // Diameter through this node = leftHeight + rightHeight
        // (path goes from deepest left leaf to deepest right leaf through this node)
        maxDiameter = Math.max(maxDiameter, leftHeight + rightHeight);

        // Return height of this subtree
        return 1 + Math.max(leftHeight, rightHeight);
    }

    public static int diameterOfBinaryTree(TreeNode root) {
        maxDiameter = 0;
        height(root);
        return maxDiameter;
    }

    public static void main(String[] args) {
        // Build a test tree:
        //       1
        //      / \
        //     2   3
        //    / \
        //   4   5
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        System.out.println("Diameter of tree: " + diameterOfBinaryTree(root));
        // Expected: 3 (path 4->2->5, or 4->2->1->3, length = 3 edges)
    }
}
```

---

## MAX PATH SUM (ANY NODE TO ANY NODE)

### Problem
Find the maximum sum along any path in a binary tree. The path can start and end at any node.

### Think About It
For each node, the max path sum through that node = node.val + max(0, leftMax) + max(0, rightMax). We track the global maximum across all nodes.

```java
public class MaxPathSum {

    private static int maxSum;

    // Helper: returns max sum from this node down to any leaf
    // "max single path" = node.val + max(0, leftBest, rightBest)
    private static int maxPathDown(TreeNode node) {
        if (node == null) return 0;

        // Max sum from left (ignore negative paths)
        int left = Math.max(0, maxPathDown(node.left));
        // Max sum from right (ignore negative paths)
        int right = Math.max(0, maxPathDown(node.right));

        // Max path through this node (arch shape: left -> node -> right)
        maxSum = Math.max(maxSum, node.val + left + right);

        // Return max single path going down from this node
        return node.val + Math.max(left, right);
    }

    public static int maxPathSum(TreeNode root) {
        maxSum = Integer.MIN_VALUE;
        maxPathDown(root);
        return maxSum;
    }

    public static void main(String[] args) {
        //        -10
        //        /  \
        //       9   20
        //          /  \
        //         15   7
        TreeNode root = new TreeNode(-10);
        root.left = new TreeNode(9);
        root.right = new TreeNode(20);
        root.right.left = new TreeNode(15);
        root.right.right = new TreeNode(7);

        System.out.println("Max path sum: " + maxPathSum(root));
        // Expected: 42 (15 + 20 + 7 = 42)
    }
}
```

---

# CATALAN NUMBERS

## What are Catalan Numbers?
A sequence of natural numbers that appear in many counting problems.

Formula: `C(0) = 1`, `C(n+1) = sum(C(i) * C(n-i)) for i = 0 to n`

Sequence: 1, 1, 2, 5, 14, 42, 132, 429, 1430...

## Applications:
1. Number of BSTs with n nodes
2. Number of valid parentheses expressions with n pairs
3. Number of triangulations of a convex polygon
4. Number of mountain ranges
5. Number of full binary trees with n+1 leaves

```java
public class CatalanNumbers {

    // ---- RECURSION (NAIVE) ----
    public static int catalanRecur(int n) {
        if (n <= 1) return 1;

        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += catalanRecur(i) * catalanRecur(n - 1 - i);
        }

        return sum;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int catalanMemo(int n, int[] memo) {
        if (n <= 1) return 1;
        if (memo[n] != -1) return memo[n];

        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += catalanMemo(i, memo) * catalanMemo(n - 1 - i, memo);
        }

        memo[n] = sum;
        return memo[n];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int catalanTab(int n) {
        int[] dp = new int[n + 1];
        dp[0] = 1;
        dp[1] = 1;

        for (int i = 2; i <= n; i++) {
            for (int j = 0; j < i; j++) {
                dp[i] += dp[j] * dp[i - 1 - j];
            }
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int n = 10;

        System.out.println("Catalan Numbers up to C(" + n + "):");
        for (int i = 0; i <= n; i++) {
            System.out.println("C(" + i + ") = " + catalanTab(i));
        }
    }
}
```

## COUNT BSTs WITH N NODES

### Problem
Given n nodes labeled 1 to n, how many structurally unique BSTs can be formed?

### Think About It
For each root k (1 to n):
- Left subtree has k-1 nodes -> C(k-1) BSTs
- Right subtree has n-k nodes -> C(n-k) BSTs
- Total for root k = C(k-1) * C(n-k)

This is EXACTLY the Catalan number! C(n) = sum(C(k-1) * C(n-k)) for k=1 to n

```java
public class CountBSTs {

    // Uses Catalan numbers formula
    public static int countBSTs(int n) {
        return CatalanNumbers.catalanTab(n);
    }

    // ---- DP TABULATION (explicit) ----
    public static int countBSTsTab(int n) {
        // dp[i] = number of BSTs with i nodes
        int[] dp = new int[n + 1];
        dp[0] = 1; // Empty tree
        dp[1] = 1; // Single node

        for (int i = 2; i <= n; i++) {
            for (int j = 0; j < i; j++) {
                // j nodes in left subtree, i-1-j nodes in right subtree
                dp[i] += dp[j] * dp[i - 1 - j];
            }
        }

        return dp[n];
    }

    public static void main(String[] args) {
        int n = 5;

        System.out.println("Number of BSTs with " + n + " nodes: " + countBSTs(n));
        // Expected: 42

        System.out.println("\nBST counts for n = 0 to 10:");
        for (int i = 0; i <= 10; i++) {
            System.out.println("n=" + i + ": " + countBSTsTab(i));
        }
    }
}
```

---

## MOUNTAIN RANGES

### Problem
Given n pairs of up-strokes (/) and down-strokes (\), how many mountain ranges can you form that never go below sea level?

### Think About It
This is another Catalan number application! You need n up-strokes and n down-strokes, and at any point the number of up-strokes >= down-strokes.

Same as valid parentheses: up = open, down = close.

```java
public class MountainRanges {

    public static int countMountainRanges(int n) {
        return CatalanNumbers.catalanTab(n);
    }

    public static void main(String[] args) {
        int n = 4;

        System.out.println("Number of mountain ranges with " + n + " up/down pairs: " +
                           countMountainRanges(n));
        // Expected: 14 (C(4) = 14)
    }
}
```

---

## MINIMUM SCORE TRIANGULATION

### Problem
You have a convex polygon with n vertices labeled 0 to n-1, each with a value. Triangulate the polygon (connect non-adjacent vertices with chords). Score = sum of the product of 3 vertices in each triangle. Minimize the total score.

### Think About It
This is another Catalan/ MCM-like problem!
- Choose a triangle formed by vertices i, k, j (where i < k < j)
- This splits the polygon into two sub-polygons: i...k and k...j
- Score(i, j) = min(Score(i, k) + Score(k, j) + values[i] * values[k] * values[j])

```java
public class MinimumScoreTriangulation {

    // ---- RECURSION (NAIVE) ----
    public static int minScoreRecur(int[] values, int i, int j) {
        // Base: need at least 3 vertices for a triangle
        if (j - i < 2) return 0;

        int minScore = Integer.MAX_VALUE;
        for (int k = i + 1; k < j; k++) {
            int score = minScoreRecur(values, i, k) +
                        minScoreRecur(values, k, j) +
                        values[i] * values[k] * values[j];
            minScore = Math.min(minScore, score);
        }

        return minScore;
    }

    // ---- MEMOIZATION (TOP-DOWN) ----
    public static int minScoreMemo(int[] values, int i, int j, int[][] memo) {
        if (j - i < 2) return 0;

        if (memo[i][j] != -1) return memo[i][j];

        int minScore = Integer.MAX_VALUE;
        for (int k = i + 1; k < j; k++) {
            int score = minScoreMemo(values, i, k, memo) +
                        minScoreMemo(values, k, j, memo) +
                        values[i] * values[k] * values[j];
            minScore = Math.min(minScore, score);
        }

        memo[i][j] = minScore;
        return memo[i][j];
    }

    // ---- TABULATION (BOTTOM-UP) ----
    public static int minScoreTab(int[] values) {
        int n = values.length;
        int[][] dp = new int[n][n];

        // Fill for increasing length
        for (int len = 2; len < n; len++) {
            for (int i = 0; i < n - len; i++) {
                int j = i + len;
                dp[i][j] = Integer.MAX_VALUE;
                for (int k = i + 1; k < j; k++) {
                    dp[i][j] = Math.min(dp[i][j],
                        dp[i][k] + dp[k][j] + values[i] * values[k] * values[j]);
                }
            }
        }

        return dp[0][n - 1];
    }

    public static void main(String[] args) {
        int[] values = {1, 2, 3, 4};

        System.out.println("Polygon vertex values: [1, 2, 3, 4]");
        System.out.println("Recursion: " + minScoreRecur(values, 0, values.length - 1));

        int n = values.length;
        int[][] memo = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                memo[i][j] = -1;
        System.out.println("Memoization: " + minScoreMemo(values, 0, n - 1, memo));

        System.out.println("Tabulation: " + minScoreTab(values));
        // Expected: 18 (triangulate (0,1,2)=6 + (0,2,3)=12 = 18)
    }
}
```

---

# KADANE'S ALGORITHM (MAX SUBARRAY SUM)

## Problem
Find the maximum sum of any CONTIGUOUS subarray.

## Think About It
Instead of trying all subarrays (O(n^2)), we scan left to right. At each element, we decide:
- Start new subarray at this element -> nums[i]
- Extend existing subarray -> currentSum + nums[i]

If `currentSum` becomes negative, it's better to start fresh (because a negative sum only hurts future sums).

```java
public class KadaneAlgorithm {

    // ---- KADANE'S ALGORITHM (THE BEST DP FOR THIS) ----
    public static int maxSubarraySum(int[] nums) {
        // maxEndingHere = max sum of subarray ENDING at current position
        // maxSoFar = overall max sum seen so far

        int maxEndingHere = nums[0];
        int maxSoFar = nums[0];

        for (int i = 1; i < nums.length; i++) {
            // Either extend the subarray or start fresh
            maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
            // Update global maximum
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }

        return maxSoFar;
    }

    // ---- KADANE'S WITH SUBARRAY INDICES ----
    public static int[] maxSubarrayWithIndices(int[] nums) {
        int maxEndingHere = nums[0];
        int maxSoFar = nums[0];
        int start = 0, end = 0;
        int tempStart = 0;

        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > maxEndingHere + nums[i]) {
                // Start new subarray at i
                maxEndingHere = nums[i];
                tempStart = i;
            } else {
                // Extend current subarray
                maxEndingHere = maxEndingHere + nums[i];
            }

            if (maxEndingHere > maxSoFar) {
                maxSoFar = maxEndingHere;
                start = tempStart;
                end = i;
            }
        }

        return new int[]{maxSoFar, start, end};
    }

    // ---- DP TABULATION approach ----
    public static int maxSubarrayDP(int[] nums) {
        int n = nums.length;
        // dp[i] = max subarray sum ENDING at index i
        int[] dp = new int[n];
        dp[0] = nums[0];
        int max = dp[0];

        for (int i = 1; i < n; i++) {
            // Either extend previous subarray or start here
            dp[i] = Math.max(nums[i], dp[i - 1] + nums[i]);
            max = Math.max(max, dp[i]);
        }

        return max;
    }

    public static void main(String[] args) {
        int[] nums = {-2, 1, -3, 4, -1, 2, 1, -5, 4};

        System.out.println("Array: [-2, 1, -3, 4, -1, 2, 1, -5, 4]");
        System.out.println("Kadane's Algorithm: " + maxSubarraySum(nums));
        // Expected: 6 (subarray [4, -1, 2, 1])

        int[] result = maxSubarrayWithIndices(nums);
        System.out.println("Max sum: " + result[0] + ", from index " + result[1] + " to " + result[2]);

        System.out.println("DP approach: " + maxSubarrayDP(nums));
    }
}
```
