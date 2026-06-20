# LeetCode 81 - Search in Rotated Sorted Array II

## Problem Statement

There is an integer array `nums` sorted in non-decreasing order and then rotated at an unknown pivot.

Given the array `nums` and an integer `target`, return `true` if `target` exists in the array, or `false` otherwise.

Unlike LeetCode 33, this array **may contain duplicates**.

---

## Example 1

Input:
nums = [2,5,6,0,0,1,2]
target = 0

Output:
true

---

## Example 2

Input:
nums = [2,5,6,0,0,1,2]
target = 3

Output:
false

---

## Example 3

Input:
nums = [1,0,1,1,1]
target = 0

Output:
true

---

## Approach (Brute Force)

1. Traverse the array from left to right.
2. Compare each element with the target.
3. If the target is found, return `true`.
4. If the traversal completes without finding the target, return `false`.

---

## Java Solution

```java
class Solution {
    public boolean search(int[] nums, int target) {
        int n = nums.length;

        for (int i = 0; i < n; i++) {
            if (nums[i] == target) {
                return true;
            }
        }

        return false;
    }
}
```

---

## Dry Run

Input:

nums = [2,5,6,0,0,1,2]
target = 0

| i | nums[i] | Found? |
|---|---------|---------|
| 0 | 2 | No |
| 1 | 5 | No |
| 2 | 6 | No |
| 3 | 0 | Yes |

Return `true`.

---

## Complexity Analysis

### Time Complexity

- O(n)

In the worst case, every element may need to be checked.

### Space Complexity

- O(1)

No extra space is used.

---

## Key Insight

The brute-force solution simply scans the array and checks whether the target exists. While easy to implement, it does not utilize the sorted and rotated structure of the array. An optimized Binary Search solution can perform better on average, though duplicates may degrade the worst-case complexity to O(n).
