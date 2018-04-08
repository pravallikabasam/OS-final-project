# OS-final-project
Process Scheduling algorithms.

# MLFQ
===========================================================
  Simulating Multilevel-FeedBack-Scheduling-Queue-in-C++-
===========================================================

This application implements Multilevel Feedback Queue in C++ with two levels:
Level 1 : Fixed priority preemptive Scheduling
Level 2 : Round Robin Scheduling


===========================================================
                    SYSTEM DETAILS
===========================================================

1. Fixed priority preemptive Scheduling (Queue 1)
 * Priority 0 is highest priority.
 * Quantum : 4 unit time
 * Preemptive:
If one process e.g. P1 is scheduled and running , now another process with higher priority comes e.g. P2. New process(high priority)
process P2 preempts currently running process P1 and process P1 will go to second level queue.

2. Round Robin Scheduling (Queue 2)
* Quantum : 4 unit time
* All the processes in second level queue will complete their execution according to round robin scheduling.
* Queue 2 will be processed after Queue 1 becomes empty.
* Priority of Queue 2 has lower priority than in Queue 1.
===========================================================
                      INPUT FORMAT
===========================================================
<pid><burst_time><arrival_time><priority>

===========================================================
                      OUTPUT FORMAT
===========================================================

Set of sentences showing each line of the next step.


===========================================================
                      Sample Input :
===========================================================
 Enter total no. of processes :
4

 PROCESS [1] Enter process id : 1
 Enter burst time : 5
 Enter arrival time :
Note only multiples of 2 are allowed
 2
 Enter priority : 2

 PROCESS [2] Enter process id : 2
 Enter burst time : 4
 Enter arrival time :
Note only multiples of 2 are allowed
 4
 Enter priority : 0

 PROCESS [3] Enter process id : 3
 Enter burst time : 4
 Enter arrival time :
Note only multiples of 2 are allowed
 6
 Enter priority : 1

 PROCESS [4] Enter process id : 4
 Enter burst time : 6
 Enter arrival time :
Note only multiples of 2 are allowed
 0
 Enter priority : 3

===========================================================
                    Sample Output:
===========================================================
On tick 0 Adding P4 to Q1
                Tick 0, Q1 ticking P4[BurstTime=6-1=5]
                Tick 1, Q1 ticking P4[BurstTime=5-1=4]
On tick 2 Adding P1 to Q1
        Preempting P4[prio.=3] in Q1 and replacing it with P1[prio.=2]... P4 goes to Q2
                Tick 2, Q1 ticking P1[BurstTime=5-1=4]
                Tick 3, Q1 ticking P1[BurstTime=4-1=3]
On tick 4 Adding P2 to Q1
        Preempting P1[prio.=2] in Q1 and replacing it with P2[prio.=0]... P1 goes to Q2
                Tick 4, Q1 ticking P2[BurstTime=4-1=3]
                Tick 5, Q1 ticking P2[BurstTime=3-1=2]
On tick 6 Adding P3 to Q1
        Preempting P2[prio.=0] in Q1 and replacing it with P3[prio.=1]... P2 goes to Q2
                Tick 6, Q1 ticking P3[BurstTime=4-1=3]
                Tick 7, Q1 ticking P3[BurstTime=3-1=2]
                Tick 8, Q1 ticking P3[BurstTime=2-1=1]
                Tick 9, Q1 ticking P3[BurstTime=1-1=0]
Process 3 in Q1 finished at tick 9.
                Tick 10, Q2 ticking P1[BurstTime=3-1=2]
                Tick 11, Q2 ticking P1[BurstTime=2-1=1]
                Tick 12, Q2 ticking P2[BurstTime=2-1=1]
                Tick 13, Q2 ticking P2[BurstTime=1-1=0]
Process 2 in Q2 finished at tick 13.
                Tick 14, Q2 ticking P1[BurstTime=1-1=0]
Process 1 in Q2 finished at tick 14.
                Tick 15, Q2 ticking P4[BurstTime=4-1=3]
                Tick 16, Q2 ticking P4[BurstTime=3-1=2]
                Tick 17, Q2 ticking P4[BurstTime=2-1=1]
                Tick 18, Q2 ticking P4[BurstTime=1-1=0]
Process 4 in Q2 finished at tick 18.

Done
