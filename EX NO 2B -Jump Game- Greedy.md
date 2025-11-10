
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 20-08-2025
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Start the program and import the `Scanner` class to take user input.  
2. Read the size of the array `n` and input the array elements.  
3. Initialize a variable `maxReach` to track the farthest index that can be reached.  
4. Iterate through the array, updating `maxReach` and checking if the current index exceeds it.  
5. If traversal completes without exceeding `maxReach`, print that the last index can be reached; otherwise, print false.

## Program:
```java
import java.util.Scanner;

public class MinJumpToEnd {
    public static int minimumJumps(int[] nums) {
        if(nums.length <= 1)return 0;
        if(nums[0] == 0)return -1;
        
        int jumps = 0;
        int curr = 0;
        int far = 0;
        
        for(int i=0; i<nums.length-1; i++){
            far = Math.max(far, i+nums[i]);
            
            if (i == curr){
                jumps++;
                curr = far;
                
                if (curr >= nums.length-1)break;
            }
        }
        
        return curr>=nums.length-1?jumps:-1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}

```

## Output:
<img width="906" height="242" alt="image" src="https://github.com/user-attachments/assets/1dcb27ab-5c8b-485a-9738-0f9fbd340adf" />



## Result:
The program successfully implemented and the expected output is verified.


```
Developed by: ASWIN B
Register Number:  212224110007
```
