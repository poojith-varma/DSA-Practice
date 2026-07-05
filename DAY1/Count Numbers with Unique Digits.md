Problem Statement:
# Count Numbers with Unique Digits

## Problem Statement

You are given two non-negative integers $n1$ and $n2$, where $n1 \le n2$. Your task is to find the total number of integers within the inclusive range $[n1, n2]$ that have **no repeated digits**.

A number is considered to have no repeated digits if every digit from 0 to 9 appears at most once in that number.

### Input Format

* Two space-separated non-negative integers representing $n1$ and $n2$.

### Output Format

* A single integer representing the count of unique-digit numbers in the range.

### Constraints

* $0 \le n1 \le n2 \le 10^6$

---

### Sample Input 0

```
11 15

```

### Sample Output 0

```
4

```

### Explanation 0

* The range is `[11, 12, 13, 14, 15]`.
* The number `11` has the digit '1' repeated twice.
* The numbers `12`, `13`, `14`, and `15` all have unique digits.
* Total count = `4`.

---

### Hints
* To check if a number has repeated digits, extract each digit using modulo arithmetic (`% 10`). Use a boolean frequency array of size 10 to keep track of seen digits. If you encounter a digit that has already been marked true, the number is invalid.


Code:

``` java
class Solution {
    public static int countUniqueDigitNumbers(int n1, int n2) {
        int ans = 0;
        
        for(int i=n1; i<=n2; i++){
            boolean[] seen = new boolean[10];
            boolean repeated = false;

            int num = i;

            while(num>0){
                int digit = num%10;
                if (seen[digit]){
                    repeated = true;
                    break;
                }

                seen[digit] = true;
                num = num/10;
            }

            if(!repeated){
                ans++;
            }
        }

        return ans;
    }
}


```
