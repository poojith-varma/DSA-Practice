Problem statement:
# Multiples of 10 to the End

**Difficulty:** Medium

## Problem Statement

You are given an array $Arr[]$ of $N$ integers. Your task is to rearrange the array such that all numbers that are **multiples of 10** are moved to the end of the array.

**Important Condition:**

* The relative order of numbers that are *not* multiples of 10 must be preserved.
* The relative order of numbers that *are* multiples of 10 must also be preserved.

### Input Format

* An integer $N$ representing the size of the array.
* $N$ space-separated integers representing the array elements.

### Output Format

* The rearranged array elements displayed on a single line.

### Constraints

* $1 \le N \le 10^5$
* $0 \le Arr[i] \le 10^9$

---

### Sample Input 0

```
9
10 12 5 40 30 7 5 9 10

```

### Sample Output 0

```
12 5 7 5 9 10 40 30 10

```

### Explanation 0

1. **Original Array:** `[10, 12, 5, 40, 30, 7, 5, 9, 10]`
2. **Non-multiples of 10 (in order):** `[12, 5, 7, 5, 9]`
3. **Multiples of 10 (in order):** `[10, 40, 30, 10]`
4. **Combined:** `12 5 7 5 9` + `10 40 30 10` = `12 5 7 5 9 10 40 30 10`.

---

### Hints

* Think of this as a filtering problem. You can iterate through the array twice: first to collect all numbers that are not divisible by 10, and then again to collect all numbers that are divisible by 10. To keep it $O(N)$ and $O(1)$ extra space (if printing directly), simply loop and print non-multiples first, then loop again and print the multiples.




Code:

class Solution {
    public static int[] solvemoveMultiplesOfTen(int n, int[] arr) {
        int[] ans = new int[n];
        int index = 0;
        for(int i=0; i<n; i++){
                if(arr[i]%10 != 0){
                ans[index] = arr[i];
                index++;
                }           
        }

        for(int i=0; i<n; i++){
            if(arr[i]%10 == 0){
                ans[index] = arr[i];
                index++;
            }
        }

        return ans;
    }
}
