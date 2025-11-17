
# EX 1C Job Sequencing using Greedy Approach
## DATE: 04-09-2025
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm:

1. Input: Array of Job objects with id, deadline, and profit.

2. Sort jobs in descending order of profit.

3. Initialize: slot[] array to track occupied time slots, countJobs = 0, totalProfit = 0.

4. Assign jobs: For each job, check from job.deadline down to 1; if a slot is free, assign job, increment countJobs, add profit to totalProfit, and mark slot occupied.

5. Output: Return [countJobs, totalProfit] as result. 

## Program:
```
Developed by: SAI VISHAL D
Register Number: 212223230180


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
        // Type Your Code Here.
         Arrays.sort(jobs, (a, b) -> b.profit - a.profit);

        int maxDeadline = 0;
        for (Job job : jobs) {
            maxDeadline = Math.max(maxDeadline, job.deadline);
        }

        boolean[] slot = new boolean[maxDeadline + 1];
        int countJobs = 0, totalProfit = 0;

        for (Job job : jobs) {
            for (int t = job.deadline; t > 0; t--) {
                if (!slot[t]) {
                    slot[t] = true;
                    countJobs++;
                    totalProfit += job.profit;
                    break;
                }
            }
        }

        return new int[]{countJobs, totalProfit};
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


<img width="450" height="446" alt="image" src="https://github.com/user-attachments/assets/80dd92fb-1a14-477c-91cc-64e691a837a0" />



## Result:
The program successfully implemented and the expected output is verified.
