
# EX 2D Pattern Matching using Naive Approach.
## DATE: 30-08-2025
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
1. Start the program and import the `Scanner` class to take input.
2. Read the text string and the pattern string from the user.
3. Calculate the lengths of both the text and the pattern.
4. Slide the pattern over the text one character at a time and compare each substring with the pattern.
5. Print the starting index each time the pattern matches completely within the text. 

## Program:
```java
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
        String text = scanner.nextLine();
        String pattern = scanner.nextLine();
        search(text, pattern);
        scanner.close();
    }
}

```

## Output:
<img width="729" height="200" alt="image" src="https://github.com/user-attachments/assets/a2550493-e562-4f0b-9341-6482f38a96b5" />



## Result:
The program successfully implemented and the expected output is verified.

```
Developed by: ASWIN B
Register Number:  212224110007
```
