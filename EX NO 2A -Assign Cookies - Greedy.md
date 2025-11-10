
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE:28-08-2025
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Input: Two arrays, g[] (children's greed) and s[] (cookie sizes).

2. Sort both arrays in ascending order.

3. Initialize pointers i = 0 (children) and j = 0 (cookies).

4. Iterate: While both pointers are in range, if s[j] >= g[i], assign cookie to child (i++), always move to next cookie (j++).

5. Output: Number of content children (i).

## Program:
```
Developed by: NISHA D
Register Number: 212223230143


import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int i = 0,j = 0;
        while(i < g.length && j < s.length)
        {
            if(s[j] >= g[i])
            {
            i++;
            }
            j++;
            }
            return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}

```

## Output:

<img width="390" height="382" alt="image" src="https://github.com/user-attachments/assets/96c83219-ad7f-43a7-ab07-c9808e0a6d65" />




## Result:
The program to Assign Cookies using Greedy Algorithm executed successfully . 
