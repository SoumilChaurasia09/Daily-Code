# 0001. Two Sum

**Problem Name:** Two Sum  
**Difficulty:** Easy

---

## Question

Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to the target.

You may assume that each input has exactly one solution, and you may not use the same element twice.

---

## My Solution

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp;

        for (int i = 0; i < nums.size(); i++) {
            int diff = target - nums[i];

            if (mp.find(diff) != mp.end()) {
                return {mp[diff], i};
            }

            mp[nums[i]] = i;
        }

        return {};
    }
};
```

---

## Complexity

| Metric | Value |
|--------|-------|
| **Time Complexity** | `O(n)` |
| **Space Complexity** | `O(n)` |

---

## What I Learned

This problem taught me that not every problem needs to be solved by checking every possible pair.

My first instinct was to use two nested loops, which works but has a time complexity of `O(n²)`. After thinking about it, I realized I only needed a way to quickly check whether the required number had already been seen.

Using a hash map made the solution much more efficient by reducing the time complexity to `O(n)`. It also helped me understand how trading a little extra memory for faster execution can be a smart optimization.

---

## Personal Notes

Although this is considered an easy problem, it introduces one of the most useful concepts in DSA—using a hash map for constant-time lookups.

This is a pattern I'll likely encounter in many future problems involving pairs, complements, or fast searching. More importantly, it reminded me to think beyond the most obvious solution and always ask, *"Can this be done in a better way?"*

---

**Status:** Solved ✅
