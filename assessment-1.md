# DSA Fundamentals — Assessment 1

**Coverage:** Modules 1, 2, 3 and Topic 4.1  
**Type:** Programming  
**Languages:** Java, Python  
**Duration:** 90 minutes  
**Total Marks:** 100

## Question 1 — Calculate Daily Sales Difference

**Marks:** 10

### Problem Description
A shopkeeper records the sales made yesterday and today.

Write a program to find the difference between the two sales amounts and determine whether today's sales increased, decreased, or remained unchanged.

The difference must always be a non-negative number.

### Input Format
A single line containing two space-separated integers: yesterday's sales and today's sales.

### Output Format
Print two lines:

```text
Difference: X
Status: Increased
```

The status must be `Increased`, `Decreased`, or `Unchanged` as appropriate.

### Constraints
- 0 ≤ sales ≤ 100000
- Both sales values are integers.

### Sample Input
```text
1200 1500
```

### Sample Output
```text
Difference: 300
Status: Increased
```

### Sample Explanation
Today's sales are 300 higher than yesterday's sales.

### Test Cases

**Test Case 1**

Input:
```text
1200 1500
```
Output:
```text
Difference: 300
Status: Increased
```

**Test Case 2**

Input:
```text
2000 1750
```
Output:
```text
Difference: 250
Status: Decreased
```

**Test Case 3**

Input:
```text
900 900
```
Output:
```text
Difference: 0
Status: Unchanged
```

**Test Case 4**

Input:
```text
0 450
```
Output:
```text
Difference: 450
Status: Increased
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int yesterday = sc.nextInt();
        int today = sc.nextInt();

        // Write your code here

        sc.close();
    }
}
```

### Python Boilerplate
```python
yesterday, today = map(int, input().split())

# Write your code here
```

---

## Question 2 — Count Students Above Class Average

**Marks:** 15

### Problem Description
A trainer has recorded the assessment marks of students in a batch.

Write a program to calculate the class average and print how many students scored strictly above that average. Students scoring exactly the average must not be counted.

### Input Format
- First line: Integer `n`, the number of students.
- Second line: `n` space-separated integers representing their marks.

### Output Format
```text
Students above average: X
```

### Constraints
- 1 ≤ n ≤ 100
- 0 ≤ marks[i] ≤ 100

### Sample Input
```text
5
40 60 80 50 70
```

### Sample Output
```text
Students above average: 2
```

### Sample Explanation
The average is 60. Only 80 and 70 are strictly greater than 60.

### Test Cases

**Test Case 1**

Input:
```text
5
40 60 80 50 70
```
Output:
```text
Students above average: 2
```

**Test Case 2**

Input:
```text
4
10 10 10 10
```
Output:
```text
Students above average: 0
```

**Test Case 3**

Input:
```text
3
20 40 90
```
Output:
```text
Students above average: 1
```

**Test Case 4**

Input:
```text
1
75
```
Output:
```text
Students above average: 0
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] marks = new int[n];

        for (int i = 0; i < n; i++) {
            marks[i] = sc.nextInt();
        }

        int result = countAboveAverage(marks);
        System.out.println("Students above average: " + result);

        sc.close();
    }

    public static int countAboveAverage(int[] marks) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate
```python
def count_above_average(marks):
    # Write your code here
    return 0

n = int(input())
marks = list(map(int, input().split()))

print("Students above average:", count_above_average(marks))
```

---

## Question 3 — Arrange Available Seats First

**Marks:** 15

### Problem Description
A training centre maintains a list of seats. Each value represents either an available seat or a student occupying a seat:

- `0` indicates an available seat.
- A positive number represents the student ID occupying that seat.

Write a program to rearrange the array so that all available seats appear first, followed by student IDs in their original relative order.

Do not sort the student IDs. Modify the existing array.

### Input Format
- First line: Integer `n`.
- Second line: `n` space-separated integers.

### Output Format
Print the rearranged array as space-separated integers on one line.

### Constraints
- 1 ≤ n ≤ 100
- 0 ≤ arr[i] ≤ 1000

### Sample Input
```text
6
12 0 25 0 18 0
```

### Sample Output
```text
0 0 0 12 25 18
```

### Sample Explanation
Three seats are available. They appear first, while student IDs 12, 25, and 18 keep their original order.

### Test Cases

**Test Case 1**

Input:
```text
6
12 0 25 0 18 0
```
Output:
```text
0 0 0 12 25 18
```

**Test Case 2**

Input:
```text
4
5 8 3 9
```
Output:
```text
5 8 3 9
```

**Test Case 3**

Input:
```text
5
0 0 0 0 0
```
Output:
```text
0 0 0 0 0
```

**Test Case 4**

Input:
```text
7
4 0 2 0 9 1 0
```
Output:
```text
0 0 0 4 2 9 1
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] seats = new int[n];

        for (int i = 0; i < n; i++) {
            seats[i] = sc.nextInt();
        }

        arrangeSeats(seats);

        for (int i = 0; i < n; i++) {
            if (i > 0) {
                System.out.print(" ");
            }
            System.out.print(seats[i]);
        }
        System.out.println();

        sc.close();
    }

    public static void arrangeSeats(int[] seats) {
        // Write your code here
    }
}
```

### Python Boilerplate
```python
def arrange_seats(seats):
    # Modify the existing list
    pass

n = int(input())
seats = list(map(int, input().split()))

arrange_seats(seats)
print(*seats)
```

---

## Question 4 — Create a Character Position Code

**Marks:** 15

### Problem Description
A system creates an identification code from a word. For every character, it adds that character followed by its position in the word, starting at 1.

For example, `cat` becomes `c1a2t3`.

Write a program to generate this code while keeping all characters in their original order.

### Input Format
A single line containing a lowercase word.

### Output Format
Print the generated character position code.

### Constraints
- 1 ≤ length of word ≤ 30
- The word contains lowercase English letters only.

### Sample Input
```text
code
```

### Sample Output
```text
c1o2d3e4
```

### Sample Explanation
Each character is followed by its one-based position.

### Test Cases

**Test Case 1**

Input:
```text
code
```
Output:
```text
c1o2d3e4
```

**Test Case 2**

Input:
```text
java
```
Output:
```text
j1a2v3a4
```

**Test Case 3**

Input:
```text
a
```
Output:
```text
a1
```

**Test Case 4**

Input:
```text
banana
```
Output:
```text
b1a2n3a4n5a6
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String word = sc.next();

        String result = createCode(word);
        System.out.println(result);

        sc.close();
    }

    public static String createCode(String word) {
        // Write your code here
        return "";
    }
}
```

### Python Boilerplate
```python
def create_code(word):
    # Write your code here
    return ""

word = input().strip()
print(create_code(word))
```

---

## Question 5 — Find the Longest Character Streak

**Marks:** 15

### Problem Description
An application records user activity using lowercase letters. When the same letter appears continuously, it forms a streak.

Write a program to find the length of the longest continuous streak of identical characters.

Only consecutive occurrences count. The same character appearing elsewhere does not extend an earlier streak.

### Input Format
A single line containing a lowercase word.

### Output Format
```text
Longest streak: X
```

### Constraints
- 1 ≤ length of word ≤ 1000
- The word contains lowercase English letters only.

### Sample Input
```text
aaabbbbbcc
```

### Sample Output
```text
Longest streak: 5
```

### Sample Explanation
The longest continuous group contains five `b` characters.

### Test Cases

**Test Case 1**

Input:
```text
aaabbbbbcc
```
Output:
```text
Longest streak: 5
```

**Test Case 2**

Input:
```text
abcd
```
Output:
```text
Longest streak: 1
```

**Test Case 3**

Input:
```text
zzzzzz
```
Output:
```text
Longest streak: 6
```

**Test Case 4**

Input:
```text
aabbbaaac
```
Output:
```text
Longest streak: 3
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String word = sc.next();

        int result = longestStreak(word);
        System.out.println("Longest streak: " + result);

        sc.close();
    }

    public static int longestStreak(String word) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate
```python
def longest_streak(word):
    # Write your code here
    return 0

word = input().strip()
print("Longest streak:", longest_streak(word))
```

---

## Question 6 — Count Matching Starting Characters

**Marks:** 15

### Problem Description
A typing application compares an original word with the word typed by a student.

It checks both words from left to right and counts how many characters match continuously from the beginning. The comparison stops at the first mismatch or when either word ends.

Write a program to print the number of matching starting characters.

### Input Format
- First line: Original word.
- Second line: Typed word.

### Output Format
```text
Matching characters: X
```

### Constraints
- 1 ≤ length of each word ≤ 200
- Words contain lowercase English letters only.

### Sample Input
```text
program
progress
```

### Sample Output
```text
Matching characters: 5
```

### Sample Explanation
The first five characters, `progr`, match. The next characters are different.

### Test Cases

**Test Case 1**

Input:
```text
program
progress
```
Output:
```text
Matching characters: 5
```

**Test Case 2**

Input:
```text
apple
apply
```
Output:
```text
Matching characters: 4
```

**Test Case 3**

Input:
```text
java
python
```
Output:
```text
Matching characters: 0
```

**Test Case 4**

Input:
```text
code
coder
```
Output:
```text
Matching characters: 4
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String original = sc.next();
        String typed = sc.next();

        int result = countMatching(original, typed);
        System.out.println("Matching characters: " + result);

        sc.close();
    }

    public static int countMatching(String original, String typed) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate
```python
def count_matching(original, typed):
    # Write your code here
    return 0

original = input().strip()
typed = input().strip()

print("Matching characters:", count_matching(original, typed))
```

---

## Question 7 — Verify Ordered Delivery Checkpoints

**Marks:** 15

### Problem Description
A delivery service records the checkpoint IDs visited by a delivery vehicle. A supervisor provides a smaller list of required checkpoints.

The vehicle successfully completes the required route if every required checkpoint appears in the visit history in the same order. Other checkpoints may appear in between.

Write a program to determine whether the required checkpoints were completed in order. Each occurrence in the visit history can match at most one required checkpoint.

### Input Format
- First line: Integer `n`, the number of visited checkpoints.
- Second line: `n` space-separated checkpoint IDs.
- Third line: Integer `m`, the number of required checkpoints.
- Fourth line: `m` space-separated required checkpoint IDs.

### Output Format
Print `VALID` if all required checkpoints are found in the correct order; otherwise print `INVALID`.

### Constraints
- 1 ≤ n, m ≤ 100
- 1 ≤ checkpoint ID ≤ 1000
- Checkpoint IDs may repeat.
- Repeated required IDs must match different occurrences in the visited list.

### Sample Input
```text
6
10 30 20 40 50 60
3
10 20 50
```

### Sample Output
```text
VALID
```

### Sample Explanation
Required checkpoints 10, 20, and 50 all appear in the visit history in the correct order.

### Test Cases

**Test Case 1**

Input:
```text
6
10 30 20 40 50 60
3
10 20 50
```
Output:
```text
VALID
```

**Test Case 2**

Input:
```text
4
10 20 30 40
3
30 10 40
```
Output:
```text
INVALID
```

**Test Case 3**

Input:
```text
5
5 8 5 9 5
3
5 5 5
```
Output:
```text
VALID
```

**Test Case 4**

Input:
```text
3
2 4 6
4
2 4 6 8
```
Output:
```text
INVALID
```

### Java Boilerplate
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] visited = new int[n];

        for (int i = 0; i < n; i++) {
            visited[i] = sc.nextInt();
        }

        int m = sc.nextInt();
        int[] required = new int[m];

        for (int i = 0; i < m; i++) {
            required[i] = sc.nextInt();
        }

        boolean result = checkRoute(visited, required);

        if (result) {
            System.out.println("VALID");
        } else {
            System.out.println("INVALID");
        }

        sc.close();
    }

    public static boolean checkRoute(int[] visited, int[] required) {
        // Write your code here
        return false;
    }
}
```

### Python Boilerplate
```python
def check_route(visited, required):
    # Write your code here
    return False

n = int(input())
visited = list(map(int, input().split()))

m = int(input())
required = list(map(int, input().split()))

if check_route(visited, required):
    print("VALID")
else:
    print("INVALID")
```
