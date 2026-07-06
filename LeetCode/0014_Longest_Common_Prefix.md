# 0014. Longest Common Prefix

**Problem Name:** Longest Common Prefix  
**Difficulty:** Easy

---

## Question

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

---

## My Solution

```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if (strs.empty())
            return "";

        string prefix = strs[0];

        for (int i = 1; i < strs.size(); i++) {
            while (strs[i].find(prefix) != 0) {
                prefix.pop_back();

                if (prefix.empty())
                    return "";
            }
        }

        return prefix;
    }
};
```

---

## Complexity

| Metric | Value |
|--------|-------|
| **Time Complexity** | `O(n × m)` |
| **Space Complexity** | `O(1)` |

---

## What I Learned

This problem taught me that not every string problem requires comparing characters one by one.

My first thought was to check each character across all strings, but I learned that it's much simpler to assume the first string is the common prefix and keep reducing it until every string starts with it.

Using built-in string functions like `find()` and `pop_back()` made the solution much cleaner and helped me understand how useful standard library functions can be.

---

## Personal Notes

Although this is an easy problem, it introduced a simple but effective string manipulation technique.

The main takeaway for me was learning how to shrink a possible answer instead of building it from scratch. This approach is easy to understand, efficient, and is a useful pattern for many string-related interview problems.

---

**Status:** Solved ✅
