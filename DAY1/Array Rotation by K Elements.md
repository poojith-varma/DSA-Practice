Problem Statement:

# Array Rotation by K Elements

**Difficulty:** Medium

## Problem Statement

You are given an array $Arr[]$ of $N$ integers and a positive integer $K$. The goal is to split the array into two parts after the $K^{th}$ position (index $K-1$) and move the left part (the first $K$ elements) to the end of the array.

Essentially, this is a **left rotation** of the array by $K$ positions.

### Input Format

* An integer $N$ representing the size of the array.
* $N$ space-separated integers representing the array elements.
* An integer $K$ representing the split point.

### Output Format

* The rotated array elements displayed on a single line.

### Constraints

* $1 \le N \le 10^5$
* $0 \le K \le N$
* $-10^9 \le Arr[i] \le 10^9$

---

### Sample Input 0

```
5
10 20 30 40 50
2

```

### Sample Output 0

```
30 40 50 10 20

```

### Explanation 0

1. **Original Array:** `[10, 20, 30, 40, 50]`
2. **Split after K=2:**
* Left Sub-array (first 2 elements): `[10, 20]`
* Right Sub-array (remaining elements): `[30, 40, 50]`


3. **Rearrange:** Move the Left Sub-array to the end of the Right Sub-array.
4. **Final Result:** `30 40 50 10 20`

---

### Hints

* To solve this without using extra space, you can use the Triple Reversal technique:
1. Reverse the first $K$ elements.
2. Reverse the remaining $N-K$ elements.
3. Reverse the entire array.


* Note: If $K$ can be greater than $N$, you should handle it by updating $K = K \pmod N$.

Code:

``` java

class Solution {
    public static int[] rotateArray(int n, int[] arr, int k) {
        int[] ans = new int[n];
        int index = 0;

        k = k % n;

        for(int i = k; i < n; i++){
            ans[index] = arr[i];
            index++;
        }

        for(int i = 0; i<k; i++){
            ans[index] = arr[i];
            index++;
        }

        return ans;
}
}


```
