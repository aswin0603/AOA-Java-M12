
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 30-08-2025
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Check if the string is empty and return "" if true.
2. Loop through each character as a potential palindrome center.
3. Expand around the center for both odd and even length palindromes.
4. Update start and end indices if a longer palindrome is found.
5. Return the substring from start to end as the longest palindrome.  

## Program:
```java
import java.util.Scanner;

public class Solution {
    public String longestPalindrome(String s) {
        if (s == null || s.length() < 1) return "";

        int start = -1, end = -2;
        for (int i = 0; i < s.length(); i++) {
            int len1 = expandFromCenter(s, i, i);
            int len2 = expandFromCenter(s, i, i + 1);
            int len = Math.max(len1, len2);
            int newStart = i - (len - 1) / 2;
            int newEnd = i + len / 2;
            if (len > end - start + 1) {
                start = newStart;
                end = newEnd;
            }
        }
        return s.substring(start, end + 1);
    }

    private int expandFromCenter(String s, int left, int right) {
        while (left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) {
            left--;
            right++;
        }
        return right - left - 1;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}

```

## Output:
<img width="793" height="132" alt="image" src="https://github.com/user-attachments/assets/b8226126-1dd3-44d3-80fe-33fb5195250e" />



## Result:
The program successfully implemented and the expected output is verified.


```
Developed by: ASWIN B
Register Number:  212224110007
```
