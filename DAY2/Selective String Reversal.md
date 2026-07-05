Problem Statement:

# Selective String Reversal

**Difficulty:** Easy

## Problem Statement

You are given a string `str` containing alphanumeric characters (0-9, a-z, A-Z). Your task is to reverse the string while keeping the positions of all numeric digits **unaltered**. Only the alphabetic letters should change their positions according to the reversal logic.

### Input Format

* A single string `str` consisting of letters and numbers.

### Output Format

* A single string where letters are reversed and numbers remain in their original indices.

---

### Sample Input 0

```
a1b2igh3

```

### Sample Output 0

```
h1g2iba3

```

### Explanation 0

* **Original:** `a 1 b 2 i g h 3`
* **Indices of numbers:** `1, 3, 7` (values: `1`, `2`, `3`).
* **Letters to reverse:** `a`, `b`, `i`, `g`, `h`.
* **Reversed letters:** `h`, `g`, `i`, `b`, `a`.
* **Result:** `h 1 g 2 i b a 3`.

---

### Hints

* Use the Two-Pointer Technique. Place one pointer at the start and one at the end of the string. Move them toward each other, but only swap characters if both pointers are currently pointing at letters. If a pointer hits a number, skip it.

Code:

``` java

class Solution {
    public static String reverseLettersOnly(String str) {
        char[] arr = str.toCharArray();
        int left = 0;
        int right = arr.length - 1;

        while(left<right){
            if(Character.isDigit(arr[left])){
                left++;
            }
            else if(Character.isDigit(arr[right])){
                right--;
            }
            else{
                char temp = arr[left];
                arr[left] = arr[right];
                arr[right] = temp;

                left++;
                right--;
            }
        }


        return new String(arr);
    }
}


```
