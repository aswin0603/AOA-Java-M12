
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 20-08-2025
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Start the program and import the `Scanner` and `Arrays` classes.
2. Read the number of children `n` and their greed factors into array `g`.
3. Read the number of cookies `m` and their sizes into array `s`.
4. Sort both arrays and use two pointers to compare greed and cookie size.
5. Count and display the maximum number of children who can be content with the available cookies.
   

## Program:
```java
import java.util.*;

public class AssignCookies {
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int child=0;
        int cookie=0;
        int content=0;
        while(child<g.length && cookie < s.length)
        {
            if(s[cookie]>=g[child])
            {
                content++;
                child++;
            }
            cookie++;
        }
        return content;
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
<img width="295" height="269" alt="image" src="https://github.com/user-attachments/assets/08f1a809-db7f-49d1-9e23-e265e21d22f6" />



## Result:
The program successfully print all the numbers from 1 to N. 

```
Developed by: ASWIN B
Register Number:  212224110007
```
