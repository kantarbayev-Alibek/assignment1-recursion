README.md (готовый шаблон)
# Assignment 1 – Recursion

**Student:** Alibek  
**Group:** SE-2513

---

## 📌 Summary
This project demonstrates the implementation of 10 tasks using **recursion in Java**.  
All solutions were developed **without loops** (`for`, `while`, `do-while`) and rely solely on recursive calls.  
Each task was tested successfully, and screenshots of the outputs are included.  
The assignment helped me understand recursion deeply, including **base cases** and **recursive problem solving**.

---

## 🧪 Part 1: Recursion with Numbers

### Task 1: Print Digits
**Description:** Print each digit of a number on a separate line using recursion.

**Code:**
```java
printD(5481);

Output:![Task 1 Screenshot](screenshots/task1.png)


Task 2: Average of Elements

Description: Calculate the sum of array elements recursively and find the average.

Code:

int[] arr = {3, 2, 4, 1};
System.out.println(average(arr));

Output:![Task 2 Screenshot](screenshots/task2.png)


Task 3: Prime Number Check

Description: Check if a number is prime using recursion.

Code:

int num = 7;
if (Prime(num, 2)) System.out.println("Prime");
else System.out.println("Composite");

Output:![Task 3 Screenshot](screenshots/task3.png)


Task 4: Factorial

Description: Calculate factorial of a number using recursion.

Code:

System.out.println(factorial(5));

Output:![Task 4 Screenshot](screenshots/task4.png)


🔢 Part 2: Recursion with Sequences
Task 5: Fibonacci Number

Description: Find the n-th Fibonacci number recursively.

Code:

System.out.println(fibonacci(5));
System.out.println(fibonacci(17));

Output:![Task 5 Screenshot](screenshots/task5.png)


Task 6: Power Function

Description: Calculate a^n using recursion.

Code:

System.out.println(power(2, 10));

Output:![Task 6 Screenshot](screenshots/task6.png)


Task 7: Reverse Array Output

Description: Print elements of an array in reverse order recursively.

Code:

int[] arr2 = {1, 4, 6, 2};
Reverse(arr2, arr2.length - 1);

Output:![Task 7 Screenshot](screenshots/task7.png)


🔤 Part 3: Recursion with Strings
Task 8: Check Digits in String

Description: Check if a string contains only digits.

Code:

String s = "123456";
System.out.println(Digits(s, 0) ? "Yes" : "No");

Output:![Task 8 Screenshot](screenshots/task8.png)


Task 9: Count Characters

Description: Count the number of characters in a string recursively.

Code:

System.out.println(count("hello"));
System.out.println(count("recursion"));

Output:![Task 9 Screenshot](screenshots/task9.png)


Task 10: Greatest Common Divisor (GCD)

Description: Find the GCD of two numbers recursively using Euclidean Algorithm.

Code:

System.out.println(gcd(32, 48));
System.out.println(gcd(10, 7));

Output:![Task 10 Screenshot](screenshots/task10.png)


✅ Conclusion

All tasks were implemented using recursion without loops.
Base cases and recursive calls were used correctly.
The project helped me understand recursion deeply and improved my problem-solving skills.
git init
git add .
git commit -m "Assignment 1 – Recursion with screenshots"
git branch -M main
git remote add origin https://github.com/kantarbayev-Alibek/assignment1-recursion
git push -u origin main
public class Main {

    public static void main(String[] args) {

        // Task 1
        System.out.println("Task 1:");
        printD(5481);

        // Task 2
        System.out.println("\nTask 2:");
        int[] arr = {3, 2, 4, 1};
        System.out.println(average(arr));

        // Task 3
        System.out.println("\nTask 3:");
        int num = 7;
        if (Prime(num, 2)) System.out.println("Prime");
        else System.out.println("Composite");

        // Task 4
        System.out.println("\nTask 4:");
        System.out.println(factorial(5));

        // Task 5
        System.out.println("\nTask 5:");
        System.out.println(fibonacci(5));
        System.out.println(fibonacci(17));

        // Task 6
        System.out.println("\nTask 6:");
        System.out.println(power(2, 10));

        // Task 7
        System.out.println("\nTask 7:");
        int[] arr2 = {1, 4, 6, 2};
        Reverse(arr2, arr2.length - 1);

        // Task 8
        System.out.println("\nTask 8:");
        String s = "123456";
        System.out.println(Digits(s, 0) ? "Yes" : "No");

        // Task 9
        System.out.println("\nTask 9:");
        System.out.println(count("hello"));
        System.out.println(count("recursion"));

        // Task 10
        System.out.println("\nTask 10:");
        System.out.println(gcd(32, 48));
        System.out.println(gcd(10, 7));
    }

    // Task 1
    public static void printD(int n) {
        if (n < 10) {
            System.out.println(n);
        } else {
            printD(n / 10);
            System.out.println(n % 10);
        }
    }

    // Task 2
    public static int sumArr(int[] arr, int n) {
        if (n == 0) return 0;
        return sumArr(arr, n - 1) + arr[n - 1];
    }

    public static double average(int[] arr) {
        return (double) sumArr(arr, arr.length) / arr.length;
    }

    // Task 3
    public static boolean Prime(int n, int i) {
        if (n <= 2) return (n == 2);
        if (n % i == 0) return false;
        if (i * i > n) return true;
        return Prime(n, i + 1);
    }

    // Task 4
    public static int factorial(int n) {
        if (n == 0) return 1;
        return n * factorial(n - 1);
    }

    // Task 5
    public static int fibonacci(int n) {
        if (n == 0) return 0;
        if (n == 1) return 1;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    // Task 6
    public static int power(int a, int n) {
        if (n == 0) return 1;
        return a * power(a, n - 1);
    }

    // Task 7
    public static void Reverse(int[] arr, int n) {
        if (n < 0) return;
        System.out.println(arr[n]);
        Reverse(arr, n - 1);
    }

    // Task 8
    public static boolean Digits(String s, int i) {
        if (i == s.length()) return true;
        if (!Character.isDigit(s.charAt(i))) return false;
        return Digits(s, i + 1);
    }

    // Task 9
    public static int count(String s) {
        if (s.equals("")) return 0;
        return 1 + count(s.substring(1));
    }

    // Task 10
    public static int gcd(int a, int b) {
        if (b == 0) return a;
        return gcd(b, a % b);
    }
}
