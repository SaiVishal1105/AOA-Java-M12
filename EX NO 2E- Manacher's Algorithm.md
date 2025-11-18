
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 11-09-2025
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm:
1. Input: String s. Initialize start = 0, end = 0.

2. Iterate over each index i in s.

3. Expand around center: Check for odd-length palindrome (center at i) and even-length palindrome (center between i and i+1).

4. Update: If a longer palindrome is found during expansion, update start and end indices.

5. Output: Return substring s.substring(start, end + 1) as the longest palindromic substring.


## Program:
```
Developed by:  SAI VISHAL D
Register Number: 212223230180


import java.util.Scanner;

public class Solution {

    public String longestPalindrome(String s) {
        if (s == null || s.length() < 1) return "";

        int start = 0, end = 0;

        for (int i = 0; i < s.length(); i++) {
            int left = i, right = i;
            while (left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) {
                if (right - left > end - start) {
                    start = left;
                    end = right;
                }
                left--;
                right++;
            }

            left = i;
            right = i + 1;
            while (left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) {
                if (right - left > end - start) {
                    start = left;
                    end = right;
                }
                left--;
                right++;
            }
        }

        return s.substring(start, end + 1);
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

<img width="913" height="217" alt="image" src="https://github.com/user-attachments/assets/0e96e080-e672-45f4-93c4-5361f134e743" />




## Result:
The program successfully implemented and the expected output is verified.
