
# EX 1C Job Sequencing using Greedy Approach
## DATE: 21-08-2025
## AIM:
You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
1. Start the program and import the `Scanner` and `Arrays` classes.
2. Read the number of jobs `n` and input each job’s `id`, `deadline`, and `profit`.
3. Sort all jobs in descending order based on profit to prioritize high-profit jobs.
4. Assign jobs to available slots before their deadlines, ensuring only one job per time slot.
5. Count the total scheduled jobs and sum up their profits, then display both values as output.   

## Program:
```java
import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        Arrays.sort(jobs,(a,b)->b.profit-a.profit);
        boolean[] timeslot = new boolean[n+1];
        int total=0;
        int jobcnt=0;
        for(Job job : jobs){
            for(int j=Math.min(n, job.deadline);j>0;j--){
                if(!timeslot[j]){
                    timeslot[j] = true;
                    total += job.profit;
                    jobcnt++;
                    break;
                }
            }
        }
        return new int[]{jobcnt, total};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}

```

## Output:
<img width="328" height="346" alt="image" src="https://github.com/user-attachments/assets/4bd04ae1-4584-4d0f-8c45-84b3b9271715" />



## Result:
The program successfully implemented and the expected output is verified.

```
Developed by: ASWIN B
Register Number:  212224110007
```
