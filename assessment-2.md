# Assessment 2

**Questions:** 7 | **Total Marks:** 100 | **Suggested Duration:** 90 minutes

**Supported Languages:** Java and Python

**Instructions:** Read each scenario carefully. Complete the missing function in the supplied starter code. The input and output formats are fixed. Do not print additional messages.


---

## Question 1: Missing Inventory Scans

**Marks:** 10

### Problem Description

A supermarket receives a delivery with a printed list of expected product IDs. At the unloading station, a scanner records the IDs of products that were actually received. Both lists are sorted in increasing order because the warehouse system stores them in that format. Every ID is unique within each list, and every scanned ID belongs to the expected list.

During a busy delivery, a box may be left on the truck. The supervisor does not need the full list of missing boxes; they only need the **number of expected products that were not scanned**. Write a program that compares the two lists and returns that number. A product is missing only if it appears in the expected list but not the scanned list. Do not assume that the two lists have the same length.

### Input Format

First line: integer n (expected products).
Second line: n sorted distinct product IDs.
Third line: integer m (scanned products).
Fourth line: m sorted distinct product IDs, if m > 0.

### Output Format

Print one integer: the number of missing products.

### Constraints

1 ≤ n ≤ 100000; 0 ≤ m ≤ n; 1 ≤ IDs ≤ 1000000; both lists strictly increasing; scanned IDs are a subset of expected IDs.

### Sample Input

```text
5
11 13 17 20 25
3
11 17 25
```

### Sample Output

```text
2
```

### Sample Explanation

The expected list contains IDs 13 and 20 that did not appear in the scanned list.

### Test Cases

**Test Case 1**

Input:

```text
5
11 13 17 20 25
3
11 17 25
```

Expected Output:

```text
2
```

**Test Case 2**

Input:

```text
4
1 2 3 4
4
1 2 3 4
```

Expected Output:

```text
0
```

**Test Case 3**

Input:

```text
3
4 8 12
0
```

Expected Output:

```text
3
```

**Test Case 4**

Input:

```text
6
2 4 6 8 10 12
2
4 12
```

Expected Output:

```text
4
```

**Test Case 5**

Input:

```text
1
99
1
99
```

Expected Output:

```text
0
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n=sc.nextInt();
        int[] expected=new int[n];
        for(int i=0;i<n;i++) expected[i]=sc.nextInt();
        int m=sc.nextInt();
        int[] scanned=new int[m];
        for(int i=0;i<m;i++) scanned[i]=sc.nextInt();
        System.out.println(missingCount(expected, scanned));
        sc.close();
    }

    public static int missingCount(int[] expected, int[] scanned) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def missingCount(expected, scanned):
    # Write your code here
    return 0

n=int(input())
expected=list(map(int,input().split()))
m=int(input())
scanned=list(map(int,input().split())) if m else []
print(missingCount(expected, scanned))
```


---

## Question 2: Delivery Route With Limited Detours

**Marks:** 15

### Problem Description

A courier company assigns a driver a set of priority locations that must be visited in a particular order. The vehicle GPS records every location visited throughout the trip as a string of uppercase letters, where each letter represents one location. A second string contains the priority stops in their required order.

The company allows the driver to pass through ordinary locations between two consecutive priority stops, but to save fuel it allows **at most k ordinary visits between each pair of matched consecutive priority stops**. Visits before the first matched priority stop and after the last one do not count towards this limit. Each recorded position may be used only once. Determine whether there is a way to match every priority location in order without exceeding the detour limit between any consecutive matches. For this assessment, each priority location letter appears at most once in the recorded route, so its match is unambiguous.

### Input Format

First line: recorded route string.
Second line: priority route string.
Third line: integer k.

### Output Format

Print VALID if the priority route can be matched within the detour limit; otherwise print INVALID.

### Constraints

1 ≤ route length ≤ 1000; 1 ≤ priority length ≤ 26; strings use uppercase A–Z; characters in priority are distinct and each occurs at most once in route; 0 ≤ k ≤ 1000.

### Sample Input

```text
AXBYCZ
ABC
1
```

### Sample Output

```text
VALID
```

### Sample Explanation

A to B has one extra location X; B to C has one extra location Y, which is allowed when k = 1.

### Test Cases

**Test Case 1**

Input:

```text
AXBYCZ
ABC
1
```

Expected Output:

```text
VALID
```

**Test Case 2**

Input:

```text
AXXBYCZ
ABC
1
```

Expected Output:

```text
INVALID
```

**Test Case 3**

Input:

```text
ABC
ABC
0
```

Expected Output:

```text
VALID
```

**Test Case 4**

Input:

```text
ZABCD
AD
1
```

Expected Output:

```text
INVALID
```

**Test Case 5**

Input:

```text
LMNOP
MP
2
```

Expected Output:

```text
VALID
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String route=sc.next();
        String priority=sc.next();
        int k=sc.nextInt();
        System.out.println(validRoute(route, priority, k) ? "VALID" : "INVALID");
        sc.close();
    }

    public static boolean validRoute(String route, String priority, int k) {
        // Write your code here
        return false;
    }
}
```

### Python Boilerplate

```python
def validRoute(route, priority, k):
    # Write your code here
    return False

route=input().strip()
priority=input().strip()
k=int(input())
print("VALID" if validRoute(route, priority, k) else "INVALID")
```


---

## Question 3: Damaged Pair Audit

**Marks:** 15

### Problem Description

A warehouse places fragile packages in one straight row before loading a truck. The packages are intended to have symmetric safety labels: the label of the first package should equal the label of the last package, the second should equal the second from the end, and so on.

After loading preparation, an auditor discovers that some symmetric pairs do not match. The auditor can replace the label on **one package in a mismatching pair** so the pair matches. The auditor wants to know the minimum number of individual package labels that must be changed to make the complete row symmetric. For a row with an odd number of packages, the middle package does not need a matching partner. Return the required number of replacements.

### Input Format

A single nonempty string of uppercase letters representing labels from left to right.

### Output Format

Print one integer: the minimum number of label replacements.

### Constraints

1 ≤ length ≤ 100000; labels are uppercase A–Z.

### Sample Input

```text
ABXCA
```

### Sample Output

```text
1
```

### Sample Explanation

Only one mirrored pair has different labels, so one label replacement is sufficient.

### Test Cases

**Test Case 1**

Input:

```text
ABXCA
```

Expected Output:

```text
1
```

**Test Case 2**

Input:

```text
ABBA
```

Expected Output:

```text
0
```

**Test Case 3**

Input:

```text
ABCDE
```

Expected Output:

```text
2
```

**Test Case 4**

Input:

```text
A
```

Expected Output:

```text
0
```

**Test Case 5**

Input:

```text
AXYZYA
```

Expected Output:

```text
2
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String labels=sc.next();
        System.out.println(minLabelChanges(labels));
        sc.close();
    }

    public static int minLabelChanges(String labels) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def minLabelChanges(labels):
    # Write your code here
    return 0

labels=input().strip()
print(minLabelChanges(labels))
```


---

## Question 4: Clean Up a Shared Access Code

**Marks:** 15

### Problem Description

Employees often copy an access code from an internal chat message. To make long codes easier to read, some staff insert hyphens, periods, or spaces between characters. The official verification system compares only letters and digits, and it treats uppercase and lowercase letters as the same.

Given two copied versions of an access code, determine whether they represent the **same sequence of letters and digits** after ignoring spaces, hyphens and periods. The order of the remaining characters must stay unchanged. For example, a code that contains the letters A, B and digit 7 in that order must not match a code containing B, A and 7. The inputs can have different lengths and may consist entirely of separators.

### Input Format

First line: first copied code (may contain spaces).
Second line: second copied code (may contain spaces).

### Output Format

Print MATCH if the meaningful character sequences are identical, otherwise MISMATCH.

### Constraints

0 ≤ each line length ≤ 100000; characters are English letters, digits, spaces, hyphens or periods.

### Sample Input

```text
AB-12.C
a b 1 2 c
```

### Sample Output

```text
MATCH
```

### Sample Explanation

Removing separators and ignoring letter case leaves AB12C in both inputs.

### Test Cases

**Test Case 1**

Input:

```text
AB-12.C
a b 1 2 c
```

Expected Output:

```text
MATCH
```

**Test Case 2**

Input:

```text
A-B.7
AB8
```

Expected Output:

```text
MISMATCH
```

**Test Case 3**

Input:

```text
---
 . -
```

Expected Output:

```text
MATCH
```

**Test Case 4**

Input:

```text
ab-12
ba12
```

Expected Output:

```text
MISMATCH
```

**Test Case 5**

Input:

```text
X9.
x-9
```

Expected Output:

```text
MATCH
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String first=sc.nextLine();
        String second=sc.nextLine();
        System.out.println(codesMatch(first, second) ? "MATCH" : "MISMATCH");
        sc.close();
    }

    public static boolean codesMatch(String first, String second) {
        // Write your code here
        return false;
    }
}
```

### Python Boilerplate

```python
def codesMatch(first, second):
    # Write your code here
    return False

first=input()
second=input()
print("MATCH" if codesMatch(first, second) else "MISMATCH")
```


---

## Question 5: Parcel Weight Range

**Marks:** 15

### Problem Description

A shipping company pairs two parcels to share a delivery vehicle. Each parcel has an integer weight. For safety, the **combined weight of a pair must be between L and R, inclusive**. The operations team keeps parcel weights sorted in nondecreasing order, and multiple parcels can have the same weight.

Count how many different pairs of parcel **positions** satisfy the allowed combined weight range. Pair (i, j) is considered only when i < j. Two parcels of the same weight are still different parcels if they occupy different positions, so each eligible index pair counts separately. Return the total number of pairs. Large lists can produce an answer greater than the range of a 32-bit integer.

### Input Format

First line: n.
Second line: n sorted parcel weights.
Third line: L and R.

### Output Format

Print one integer: the number of eligible position pairs.

### Constraints

2 ≤ n ≤ 100000; 0 ≤ weight ≤ 100000; 0 ≤ L ≤ R ≤ 200000.

### Sample Input

```text
5
1 2 3 4 5
5 6
```

### Sample Output

```text
4
```

### Sample Explanation

Four pairs have sums of 5 or 6: (1,4), (1,5), (2,3) and (2,4).

### Test Cases

**Test Case 1**

Input:

```text
5
1 2 3 4 5
5 6
```

Expected Output:

```text
4
```

**Test Case 2**

Input:

```text
4
2 2 2 2
4 4
```

Expected Output:

```text
6
```

**Test Case 3**

Input:

```text
3
1 1 1
5 10
```

Expected Output:

```text
0
```

**Test Case 4**

Input:

```text
2
4 7
11 11
```

Expected Output:

```text
1
```

**Test Case 5**

Input:

```text
5
0 0 0 0 0
0 0
```

Expected Output:

```text
10
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n=sc.nextInt();
        int[] weights=new int[n];
        for(int i=0;i<n;i++) weights[i]=sc.nextInt();
        int low=sc.nextInt();
        int high=sc.nextInt();
        System.out.println(countEligiblePairs(weights, low, high));
        sc.close();
    }

    public static long countEligiblePairs(int[] weights, int low, int high) {
        // Write your code here
        return 0L;
    }
}
```

### Python Boilerplate

```python
def countEligiblePairs(weights, low, high):
    # Write your code here
    return 0

n=int(input())
weights=list(map(int,input().split()))
low,high=map(int,input().split())
print(countEligiblePairs(weights, low, high))
```


---

## Question 6: Choose Two Security Gates

**Marks:** 15

### Problem Description

A shopping mall has security gates placed along a straight corridor. Each gate has a different numbered position. The mall wants to install exactly two monitoring devices at two different gates. To cover a large portion of the corridor, the devices should be as far apart as possible, but the sum of their battery requirements must be **at most B**.

You are given battery requirements in a sorted nondecreasing array, where array indexes represent gate positions along the corridor. Find the maximum distance between the indexes of two gates that satisfy the battery limit. If no pair can satisfy the limit, return -1. Equal battery requirements are allowed, and the physical distance is measured by index difference, not battery difference.

### Input Format

First line: n.
Second line: n sorted battery requirements.
Third line: B, the maximum combined battery requirement.

### Output Format

Print the maximum feasible index distance, or -1 if there is no feasible pair.

### Constraints

2 ≤ n ≤ 100000; 0 ≤ battery[i] ≤ 100000; array sorted nondecreasing; 0 ≤ B ≤ 200000.

### Sample Input

```text
5
1 2 4 7 9
10
```

### Sample Output

```text
4
```

### Sample Explanation

The first and fifth gates have a combined battery requirement of 10 and index distance 4.

### Test Cases

**Test Case 1**

Input:

```text
5
1 2 4 7 9
10
```

Expected Output:

```text
4
```

**Test Case 2**

Input:

```text
4
5 6 7 8
9
```

Expected Output:

```text
-1
```

**Test Case 3**

Input:

```text
4
1 2 3 4
5
```

Expected Output:

```text
3
```

**Test Case 4**

Input:

```text
2
0 0
0
```

Expected Output:

```text
1
```

**Test Case 5**

Input:

```text
5
2 2 2 2 2
4
```

Expected Output:

```text
4
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n=sc.nextInt();
        int[] battery=new int[n];
        for(int i=0;i<n;i++) battery[i]=sc.nextInt();
        int limit=sc.nextInt();
        System.out.println(maxGateDistance(battery, limit));
        sc.close();
    }

    public static int maxGateDistance(int[] battery, int limit) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def maxGateDistance(battery, limit):
    # Write your code here
    return 0

n=int(input())
battery=list(map(int,input().split()))
limit=int(input())
print(maxGateDistance(battery, limit))
```


---

## Question 7: Emergency Barrier Coverage

**Marks:** 15

### Problem Description

An event organizer places temporary barriers in a row. Every barrier has a height, representing how strongly it can resist a crowd pushing against it. A safety team may select any two barriers as the boundaries of a protected zone. The protection score of that zone is the **smaller boundary height multiplied by the number of spaces between the two barriers**. For example, barriers at indexes 1 and 5 have four spaces of index distance between them.

However, the event has a safety requirement: **both selected barriers must be at least H units tall**. Among all pairs meeting the minimum-height requirement, return the largest protection score. If fewer than two barriers meet the minimum height, return 0. Use the original barrier positions; do not reorder the heights.

### Input Format

First line: n.
Second line: n barrier heights.
Third line: minimum allowed height H.

### Output Format

Print the maximum protection score, or 0 if no pair qualifies.

### Constraints

2 ≤ n ≤ 100000; 0 ≤ height[i] ≤ 100000; 0 ≤ H ≤ 100000; result fits in signed 64-bit integer.

### Sample Input

```text
5
2 6 3 5 1
4
```

### Sample Output

```text
10
```

### Sample Explanation

The barriers of heights 6 and 5 are two indexes apart, so their score is 5 × 2 = 10.

### Test Cases

**Test Case 1**

Input:

```text
5
2 6 3 5 1
4
```

Expected Output:

```text
10
```

**Test Case 2**

Input:

```text
4
1 2 3 4
5
```

Expected Output:

```text
0
```

**Test Case 3**

Input:

```text
2
7 7
7
```

Expected Output:

```text
7
```

**Test Case 4**

Input:

```text
5
5 1 2 1 5
5
```

Expected Output:

```text
20
```

**Test Case 5**

Input:

```text
3
0 0 0
0
```

Expected Output:

```text
0
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n=sc.nextInt();
        int[] heights=new int[n];
        for(int i=0;i<n;i++) heights[i]=sc.nextInt();
        int minimum=sc.nextInt();
        System.out.println(maxSafeCoverage(heights, minimum));
        sc.close();
    }

    public static long maxSafeCoverage(int[] heights, int minimum) {
        // Write your code here
        return 0L;
    }
}
```

### Python Boilerplate

```python
def maxSafeCoverage(heights, minimum):
    # Write your code here
    return 0

n=int(input())
heights=list(map(int,input().split()))
minimum=int(input())
print(maxSafeCoverage(heights, minimum))
```
