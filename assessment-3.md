# Assessment 3

**Programming assessment | 7 questions | 100 marks | Suggested duration: 100 minutes**

**Supported languages:** Java and Python

Complete the missing method in the supplied boilerplate. Follow the exact input and output formats. Do not add interactive prompts.


---

## Question 1: Delivery Wallet Balance

**Difficulty:** Easy | **Marks:** 10

### Problem Description

A delivery partner starts the day with a wallet balance. Every completed order may add an incentive, while a refund or penalty reduces the balance. The company wants to display the greatest wallet balance visible at any moment, including the balance before the first transaction. Write the program that reads the starting balance and the chronological changes, then reports the highest balance reached. The highest balance may be the starting balance when every subsequent change is negative. Do not confuse the largest single transaction with the highest balance.

### Input Format

First line: n and the starting balance. Second line: n signed transaction changes.

### Output Format

Print the highest wallet balance reached.

### Constraints

1 ≤ n ≤ 100000; -10000 ≤ initial balance ≤ 10000; -10000 ≤ each change ≤ 10000.

### Sample Input

```text
5 100
-20 60 -10 15 -50
```

### Sample Output

```text
145
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
5 100
-20 60 -10 15 -50
```

Expected output:
```text
145
```

**Test Case 2**

Input:
```text
3 50
-5 -10 -2
```

Expected output:
```text
50
```

**Test Case 3**

Input:
```text
4 -10
5 5 -3 2
```

Expected output:
```text
0
```

**Test Case 4**

Input:
```text
1 0
100
```

Expected output:
```text
100
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt(), initial=sc.nextInt();
        int[] changes=new int[n];
        for(int i=0;i<n;i++) changes[i]=sc.nextInt();
        System.out.println(highestBalance(initial, changes));
        sc.close();
    }

    public static long highestBalance(int initial, int[] changes) {
        // Write your code here
        return 0L;
    }
}
```

### Python Boilerplate

```python
def highest_balance(initial, changes):
    # Write your code here
    return 0

n, initial=map(int,input().split())
changes=list(map(int,input().split()))
print(highest_balance(initial, changes))
```


---

## Question 2: Store Visitor Milestones

**Difficulty:** Easy | **Marks:** 10

### Problem Description

A store manager tracks how many customers enter each hour. At closing time, the manager needs to count how many hourly checkpoints had a cumulative visitor count greater than or equal to a daily milestone. For example, once the cumulative total reaches the milestone, that hour and any later hour also qualify because hourly entries are nonnegative. Count qualifying hour-end checkpoints, not individual visitors or the total number of customers.

### Input Format

First line: n and milestone k. Second line: n nonnegative hourly counts.

### Output Format

Print the number of hour-end checkpoints whose cumulative count is at least k.

### Constraints

1 ≤ n ≤ 100000; 0 ≤ k ≤ 1000000000; 0 ≤ each hourly count ≤ 10000.

### Sample Input

```text
5 10
2 3 5 1 4
```

### Sample Output

```text
3
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
5 10
2 3 5 1 4
```

Expected output:
```text
3
```

**Test Case 2**

Input:
```text
4 20
1 2 3 4
```

Expected output:
```text
0
```

**Test Case 3**

Input:
```text
3 0
0 0 0
```

Expected output:
```text
3
```

**Test Case 4**

Input:
```text
4 6
6 0 2 1
```

Expected output:
```text
4
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt(); long milestone=sc.nextLong();
        int[] visits=new int[n];
        for(int i=0;i<n;i++) visits[i]=sc.nextInt();
        System.out.println(countMilestones(visits, milestone));
        sc.close();
    }

    public static int countMilestones(int[] visits, long milestone) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def count_milestones(visits, milestone):
    # Write your code here
    return 0

n, milestone=map(int,input().split())
visits=list(map(int,input().split()))
print(count_milestones(visits, milestone))
```


---

## Question 3: Energy Usage Report

**Difficulty:** Medium | **Marks:** 15

### Problem Description

A smart-building dashboard records electricity used each hour. For an audit, the supervisor sends several inclusive hour ranges and wants the electricity used during each range, in the original request order. Hour indexes begin at 1. All readings are nonnegative. Return the sum for each requested range on a separate line; repeated ranges must produce repeated answers. The application may receive many requests, so avoid unnecessarily recalculating every range from the beginning.

### Input Format

First line: n and q. Second line: n hourly readings. Next q lines: L R (inclusive, one-based).

### Output Format

For every query, print its range total on a separate line.

### Constraints

1 ≤ n,q ≤ 100000; 0 ≤ reading ≤ 10000; 1 ≤ L ≤ R ≤ n.

### Sample Input

```text
5 3
2 4 1 3 5
1 3
2 5
4 4
```

### Sample Output

```text
7
13
3
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
5 3
2 4 1 3 5
1 3
2 5
4 4
```

Expected output:
```text
7
13
3
```

**Test Case 2**

Input:
```text
3 2
0 0 0
1 3
2 2
```

Expected output:
```text
0
0
```

**Test Case 3**

Input:
```text
4 2
10 20 30 40
1 4
3 4
```

Expected output:
```text
100
70
```

**Test Case 4**

Input:
```text
1 1
7
1 1
```

Expected output:
```text
7
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt(), q=sc.nextInt();
        int[] readings=new int[n];
        for(int i=0;i<n;i++) readings[i]=sc.nextInt();
        int[][] queries=new int[q][2];
        for(int i=0;i<q;i++){queries[i][0]=sc.nextInt();queries[i][1]=sc.nextInt();}
        long[] result=rangeUsage(readings, queries);
        for(int i=0;i<result.length;i++){
            if(i>0) System.out.print(" ");
            System.out.print(result[i]);
        }
        System.out.println();
        sc.close();
    }

    public static long[] rangeUsage(int[] readings, int[][] queries) {
        // Write your code here
        return new long[0];
    }
}
```

### Python Boilerplate

```python
def range_usage(readings, queries):
    # Write your code here
    return []

n,q=map(int,input().split())
readings=list(map(int,input().split()))
queries=[tuple(map(int,input().split())) for _ in range(q)]
print(*range_usage(readings, queries))
```


---

## Question 4: Balanced Campaign Handover

**Difficulty:** Medium | **Marks:** 15

### Problem Description

A marketing team assigns a daily workload score to each employee in a fixed line. They want to identify an employee who can act as a handover point: the combined workload of employees strictly before that person must equal the workload of employees strictly after that person. The employee’s own workload is excluded from both sums. Scores may be positive, negative, or zero because adjustments can be credits. If multiple employees meet the condition, report the earliest one using zero-based indexing. If nobody qualifies, report -1.

### Input Format

First line: n. Second line: n signed workload scores.

### Output Format

Print the smallest zero-based qualifying index, or -1.

### Constraints

1 ≤ n ≤ 100000; -10000 ≤ score ≤ 10000.

### Sample Input

```text
5
2 3 1 4 1
```

### Sample Output

```text
2
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
5
2 3 1 4 1
```

Expected output:
```text
2
```

**Test Case 2**

Input:
```text
3
1 2 3
```

Expected output:
```text
-1
```

**Test Case 3**

Input:
```text
1
99
```

Expected output:
```text
0
```

**Test Case 4**

Input:
```text
4
0 0 0 0
```

Expected output:
```text
0
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int[] scores=new int[n];
        for(int i=0;i<n;i++) scores[i]=sc.nextInt();
        System.out.println(handoverIndex(scores));
        sc.close();
    }

    public static int handoverIndex(int[] scores) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def handover_index(scores):
    # Write your code here
    return 0

n=int(input())
scores=list(map(int,input().split()))
print(handover_index(scores))
```


---

## Question 5: Factory Defect-Free Batches

**Difficulty:** Medium | **Marks:** 15

### Problem Description

A factory uses 1 for a successful inspection and 0 for a failed inspection. It must determine, for each production position, whether every *other* inspection in the day was successful. Produce an array: 1 if all inspections except the current one were successful, otherwise 0. The factory cannot assume there is at most one failure. This models the effect of removing one position from the combined quality result; the output must include one number for each input position and handle multiple failures.

### Input Format

First line: n. Second line: n values, each 0 or 1.

### Output Format

Print n space-separated integers.

### Constraints

2 ≤ n ≤ 100000; each inspection is 0 or 1.

### Sample Input

```text
4
1 0 1 1
```

### Sample Output

```text
0 1 0 0
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
4
1 0 1 1
```

Expected output:
```text
0 1 0 0
```

**Test Case 2**

Input:
```text
3
1 1 1
```

Expected output:
```text
1 1 1
```

**Test Case 3**

Input:
```text
4
0 1 0 1
```

Expected output:
```text
0 0 0 0
```

**Test Case 4**

Input:
```text
2
0 1
```

Expected output:
```text
1 0
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int[] inspections=new int[n];
        for(int i=0;i<n;i++) inspections[i]=sc.nextInt();
        int[] result=otherInspections(inspections);
        for(int i=0;i<result.length;i++){
            if(i>0) System.out.print(" ");
            System.out.print(result[i]);
        }
        System.out.println();
        sc.close();
    }

    public static int[] otherInspections(int[] inspections) {
        // Write your code here
        return new int[0];
    }
}
```

### Python Boilerplate

```python
def other_inspections(inspections):
    # Write your code here
    return []

n=int(input())
inspections=list(map(int,input().split()))
print(*other_inspections(inspections))
```


---

## Question 6: Balanced Multiplication Checkpoints

**Difficulty:** Medium | **Marks:** 20

### Problem Description

A manufacturing line has a multiplier attached to every production stage. For any selected stage, managers compare the product of all multipliers strictly before it against the product of all multipliers strictly after it. The selected stage is excluded from both sides. A checkpoint is balanced when those two products are equal. The product of an empty side is defined as 1. Count how many stages are balanced. Multiplier values may be negative or zero, and zero must be treated as an ordinary multiplier, not skipped. Return only the number of balanced checkpoints, rather than the individual left and right products. This is a checkpoint-verification problem, not an array-of-products problem.

### Input Format

First line: n. Second line: n signed multiplier values.

### Output Format

Print the number of balanced checkpoints.

### Constraints

1 ≤ n ≤ 30; -2 ≤ multiplier ≤ 2; the product of any consecutive portion fits in a signed 64-bit integer.

### Sample Input

```text
3
2 1 2
```

### Sample Output

```text
1
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
3
2 1 2
```

Expected output:
```text
1
```

**Test Case 2**

Input:
```text
3
1 1 1
```

Expected output:
```text
3
```

**Test Case 3**

Input:
```text
3
0 2 0
```

Expected output:
```text
1
```

**Test Case 4**

Input:
```text
1
-2
```

Expected output:
```text
1
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int[] values=new int[n];
        for(int i=0;i<n;i++) values[i]=sc.nextInt();
        System.out.println(balancedCheckpoints(values));
        sc.close();
    }

    public static int balancedCheckpoints(int[] values) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def balanced_checkpoints(values):
    # Write your code here
    return 0

n=int(input())
values=list(map(int,input().split()))
print(balanced_checkpoints(values))
```


---

## Question 7: Event Budget Split

**Difficulty:** Medium | **Marks:** 15

### Problem Description

An event manager lists signed net costs for the activities of an event, where positive values are expenses and negative values are sponsorship credits. The manager wants a boundary between consecutive activities such that the net total on the left equals the net total on the right. Every activity must belong to exactly one side, so the split must be after at least one activity and before the last activity. If multiple boundaries work, print the earliest boundary as the one-based number of activities on the left. Print -1 if no boundary exists. Unlike a handover point, no activity is excluded from the totals.

### Input Format

First line: n. Second line: n signed net costs.

### Output Format

Print the earliest valid split position (one-based count of left-side activities), or -1.

### Constraints

2 ≤ n ≤ 100000; -10000 ≤ cost ≤ 10000.

### Sample Input

```text
4
2 3 1 6
```

### Sample Output

```text
3
```

### Sample Explanation

The shown output follows the requirements for the supplied input. Check that values are calculated and printed in the specified order.

### Test Cases

**Test Case 1**

Input:
```text
4
2 3 1 6
```

Expected output:
```text
3
```

**Test Case 2**

Input:
```text
4
1 2 3 6
```

Expected output:
```text
3
```

**Test Case 3**

Input:
```text
3
1 2 4
```

Expected output:
```text
-1
```

**Test Case 4**

Input:
```text
4
0 0 0 0
```

Expected output:
```text
1
```

### Java Boilerplate

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int[] costs=new int[n];
        for(int i=0;i<n;i++) costs[i]=sc.nextInt();
        System.out.println(budgetSplit(costs));
        sc.close();
    }

    public static int budgetSplit(int[] costs) {
        // Write your code here
        return 0;
    }
}
```

### Python Boilerplate

```python
def budget_split(costs):
    # Write your code here
    return 0

n=int(input())
costs=list(map(int,input().split()))
print(budget_split(costs))
```
