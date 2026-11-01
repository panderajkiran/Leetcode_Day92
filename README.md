# Leetcode_Day92
# Day 92 – Ransom Note

**LeetCode Problem:** [383. Ransom Note](https://leetcode.com/problems/ransom-note/)

**Difficulty:** Easy  
**Topics:** String, Hash Table, Counting  
**Language:** Java

## Problem Statement

Given two strings, `ransomNote` and `magazine`, return `true` if the ransom note can be constructed using the letters available in the magazine.

Each letter in the magazine can only be used once.

## Approach: Frequency Array

I used an integer array of size 26 to track the frequency of each lowercase English letter.

1. Create an array `freq[26]` initialized with zeros.
2. Traverse the magazine string and count each character.
3. Traverse the ransomNote string.
4. If a required character has a frequency of zero, return `false`.
5. Otherwise, decrease its frequency because that character has been used.
6. If all characters are available, return `true`.

## Java Solution

```java
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        int freq[] = new int[26];

        for(char c : magazine.toCharArray()) {
            freq[c - 'a']++;
        }

        for(char c : ransomNote.toCharArray()) {
            if(freq[c - 'a'] == 0) {
                return false;
            }
            freq[c - 'a']--;
        }

        return true;
    }
}
```

## Complexity Analysis

- **Time Complexity:** O(n + m), where n is the length of `magazine` and m is the length of `ransomNote`.
- **Space Complexity:** O(1), because the frequency array always contains 26 elements.

## What I Learned

- How to count character frequencies using an array.
- How to use `toCharArray()` to iterate through a string.
- Why decreasing the frequency is important to avoid using the same character more than once.
- How frequency counting can solve string problems efficiently.

## Takeaway

Having the right resources is not enough; we also need to know how to use them wisely. Just like in this problem, every character has a limited purpose and availability.

**Day 92 completed! A little more practice, a little more confidence.**
