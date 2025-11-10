
# EX 2D Pattern Matching using Naive Approach.
## DATE: 08-09-2025
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12
## Algorithm
1.Input: Text string text and pattern string pattern.

2. Compute lengths: n = text.length(), m = pattern.length().

3. Iterate over text from i = 0 to i = n - m.

4. Check match: For each position i, compare text[i..i+m-1] with pattern; if all characters match, report index i.

5. Output: Print all starting indices where the pattern is found in the text.  

## Program:
```
Developed by: NISHA D
Register Number: 212223230143

import java.util.Scanner;

public class NaivePatternSearch {

    public static void search(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();

        for (int i = 0; i <= n - m; i++) {
            int j;
            for (j = 0; j < m; j++) {
                if (text.charAt(i + j) != pattern.charAt(j)) {
                    break;
                }
            }
            if (j == m) {
                System.out.println("Pattern found at index " + i);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input from the user
        String text = scanner.nextLine();
        String pattern = scanner.nextLine();

        // Search for pattern in the text
        search(text, pattern);

        scanner.close();
    }
}

```

## Output:

<img width="856" height="292" alt="image" src="https://github.com/user-attachments/assets/30ee4805-71e7-4576-8ce6-44e296ab6504" />




## Result:
The program successfully implemented and the expected output is verified.
