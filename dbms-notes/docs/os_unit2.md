# Process

- A **process** is a **program in execution**, meaning it is actively running in the system.
- The execution of a process follows a **sequential flow** of instructions.
- A process is the **basic unit of work** that the operating system manages.
- When a program is loaded into memory, it becomes a **process**.
- A **program** is a **passive entity** (a file containing instructions stored on a disk, such as an executable file).
- A **process** is an **active entity** (has a program counter tracking the next instruction to execute).

## Process Memory Layout

- process in memory-SHDT
    
    ![image.png](attachment:3c2b64d0-d7f4-4c29-bc0e-71840afcf4b6:image.png)
    
1. **`Stack`** → Stores temporary data such as function parameters, return addresses, and local variables.
2. **`Heap`** → Holds dynamically allocated memory during runtime.
3. **`Data`** → Contains global and static variables.
4. **`Text`** → Includes the program's executable code, the current activity (Program Counter value), and processor registers.

# CPU Scheduling 
- CPU scheduling decisions take place under one of four conditions:
    1. running → waiting 
        1. When a process switches from the running state to the waiting state, such as for an I/O request or invocation of the wait( ) system call.
    2. running → ready 
        1. When a process switches from the running state to the ready state, for example in response to an interrupt.
    3. waiting → ready
        1. When a process switches from the waiting state to the ready state, say at completion of I/O or a return from wait( ).
    4. When a process terminates.
- For conditions 1 and 4 there is no choice - A new process must be selected.
- For conditions 2 and 3 there is a choice - To either continue running the current process, or select a different one.
- If scheduling takes place only under conditions 1 and 4, the system is said to be ***non-preemptive***, or ***cooperative***. Under these conditions, once a process starts running it keeps running, until it either voluntarily blocks or until it finishes. Otherwise the system is said to be ***preemptive.***

### Scheduling Queues

- **Job queue –** It contains all of the system’s processes.
- **Ready queue –** This queue maintains a list of all processes in the main memory that are ready to run. This queue is always filled with new processes.
- **Device queue –** This queue is made up of processes that are stalled owing to the lack of an I/O device.

# Thread States 
- In an operating system, a **thread** is a lightweight unit of execution within a process.
- As an application executes, threads transition through various state managed by the OS scheduler.
    
    ![image.png](attachment:313eeb31-ea89-4005-a123-6baa3523cebe:image.png)
    
1. **Create State:**
    - When an application initiates a task, it creates a thread.
    - At this point, the thread is in the **New** state, where it is defined but not yet active. Resources (e.g., memory for the stack) are allocated during initialization.
2. **Ready State:**
    - After creation, the thread is assigned necessary resources (e.g., network access, memory) and enters the **Ready** state.
    - It joins the scheduler’s ready queue, waiting for CPU allocation. The thread is fully prepared but not yet executing.
3. **Running State:**
    - When the thread scheduler assigns the CPU to the thread, it transitions from **Ready** to **Running**.
    - In this state, the thread actively executes its instructions. This is the only state where actual processing occurs.
4. **Waiting State:**
    - If the thread depends on an external event beyond its control (e.g., completion of another process or a signal from another thread), it moves from **Running** to **Waiting**.
    - The thread remains in this state until the specific event occurs, after which it returns to **Ready**.
    - **Key Characteristic**: The wait time is often tied to a specific condition or signal, not a fixed duration.
5. **Delayed State:**
    - When the application intentionally pauses the thread for a set period, it transitions from **Running** to **Delayed** (or **Sleeping**).
    - **Example**: In an alarm clock app, after ringing, the thread “sleeps” for a predefined interval (e.g., 5 minutes) before ringing again if not stopped.
    - Once the delay expires, the thread returns to **Ready**.
    - **Key Characteristic**: The delay duration is explicitly specified (e.g., via a sleep() call).
6. **Blocked State:**
    - When the thread issues an I/O request (e.g., reading from a file or waiting for user input) and cannot proceed until it completes, it shifts from **Running** to **Blocked**.
    - It remains blocked until the I/O operation finishes, then transitions back to **Ready**.
    - **Key Characteristic**: The wait time is indeterminate, depending on external factors like user action or hardware speed
7. **Finished State:**
    - Once the thread completes its task (e.g., finishes execution or is explicitly stopped), it moves from **Running** to **Finished** (or **Terminated**).
    - Resources are deallocated, and the thread ceases to exist. A new thread must be created for further work

---

# **Models of Multithreads**
- Multithreading allows the execution of multiple parts of a program at the same time.
- These parts are known as threads and are lightweight processes available within the process.
- Therefore, multithreading leads to maximum utilization of the CPU by multitasking.
- Multithreading models define how user threads are mapped to kernel threads

### **One to One**

![image.png](attachment:97bbf6ae-5992-4d41-aae9-2d6af3af1188:image.png)

- Each user thread is mapped to a separate kernel thread.
- Enables **true parallel execution** on multiprocessor systems.
- When one thread makes a **blocking system call**, other threads can still execute.
- ex: Windows, Linux (Pthreads), Solaris

**Disadvantages:**

- Creating a user thread requires a corresponding kernel thread, which increases system overhead.
- A large number of kernel threads can **burden the system**, leading to performance limitations.

### **Many to One**

![image.png](attachment:44be0186-6ed8-424e-a73f-1424a739ddcf:image.png)

- Multiple user threads are mapped to a **single kernel thread**.
- Thread management is handled in **user space**, making it efficient with low overhead.
- ex: early java green threads

**Disadvantages:**

- If one thread makes a **blocking system call**, the entire process gets blocked.
- **No true parallel execution**, as only one thread can access the kernel at a time.

### **Many to Many**

![image.png](attachment:2aff1c04-eebe-4395-b526-ec73e1e128cc:image.png)

- Multiple user threads are mapped to an **equal or fewer number of kernel threads**.
- The OS dynamically schedules kernel threads, balancing concurrency and efficiency.
- Supports **true parallel execution** on multiprocessor systems.
- ex: Solaris, modern Linux with NPTL

**Advantages:**

- Avoids the overhead of the One-to-One model while allowing multiple user threads to execute.
- Overcomes the blocking issue of the Many-to-One model.

# Shortest Job First 
SJF/SJN is a scheduling policy that selects the waiting process with the smallest execution time to exe next

- It can be pre-emptive(SRTF) or non-preemptive(SJF)
- It is a greedy algorithm
- All the processes according to the arrival time.

**Advantages:**

- Reduces the average waiting time.
- Provides optimal turnaround time.
- Suitable for the jobs running in batches, where run times are already known.

**Disadvantages:**

- May lead to starvation for longer processes
- Completion time must be known earlier, but sometimes it is hard to predict.
1. **Non-Preemptive: SJF**

| **Process** | **AT** | **BT** | **CT** | **TAT** | **WT** |
| --- | --- | --- | --- | --- | --- |
| P1 | 0 | 7 | 7 | 7 | 0 |
| P2 | 2 | 4 | 14 | 12 | 8 |
| P3 | 4 | 1 | 8 | 4 | 3 |
| P4 | 5 | 2 | 10 | 5 | 3 |

1. **Preemptive: SRTF**

| **Process** | **AT** | **BT** | **CT** | **TAT** | **WT** |
| --- | --- | --- | --- | --- | --- |
| P1 | 0 | 7 | 7 | 7 | 0 |
| P2 | 2 | 4 | 14 | 12 | 8 |
| P3 | 4 | 1 | 8 | 4 | 3 |
| P4 | 5 | 2 | 10 | 5 | 3 |

```c 
#include <stdio.h>

struct Process {
    int p, bt;
};

int main() {
    int n, w[100], tot[100], i, j, awt = 0, atot = 0;
    float avwt, avtot;
    struct Process sjf[100], temp;

    // Taking the number of processes as input
    printf("Enter the number of Processes: ");
    scanf("%d", &n);

    // Taking burst time input
    for (i = 0; i < n; i++) {
        printf("Enter the Burst time for Process %d: ", i + 1);
        scanf("%d", &sjf[i].bt);
        sjf[i].p = i + 1; // Assigning process ID
    }

    // Sorting processes based on burst time (SJF Logic)
    for (i = 0; i < n - 1; i++) {
        for (j = i + 1; j < n; j++) {
            if (sjf[j].bt < sjf[i].bt) {
                temp = sjf[i];
                sjf[i] = sjf[j];
                sjf[j] = temp;
            }
        }
    }

    // Initial waiting time and turnaround time calculation
    w[0] = 0;                  // First process has 0 waiting time
    tot[0] = sjf[0].bt;        // First turnaround time = burst time

    // Computing turnaround time for other processes
    for (i = 1; i < n; i++) {
        w[i] = tot[i - 1];     
		        // Waiting time = previous turnaround time
        tot[i] = w[i] + sjf[i].bt; 
		        // Turnaround time = waiting time + burst time

        awt += w[i];  // Accumulate total waiting time
        atot += tot[i]; // Accumulate total turnaround time
    }

    // Calculating averages
    avwt = (float)awt / n;
    avtot = (float)atot / n;

    // Printing results
    printf("\n\nProcessId\tWaiting Time\tTurnaround Time");
    for (i = 0; i < n; i++) {
        printf("\n\t%d\t\t%d\t\t%d", sjf[i].p, w[i], tot[i]);
    }

    printf("\n\nTotal Waiting Time: %d", awt);
    printf("\nTotal Turnaround Time: %d", atot);
    printf("\nAverage Waiting Time: %.2f", avwt);
    printf("\nAverage Turnaround Time: %.2f\n", avtot);

    return 0;
}

```

Enter the number of Processes: 4
Enter the Burst time for Process 1: 6
Enter the Burst time for Process 2: 8
Enter the Burst time for Process 3: 7
Enter the Burst time for Process 4: 3

| ProcessID  | Waiting Time | Turnaround Time |
| --- | --- | --- |
| 4 | 0 | 3 |
| 1 | 3 | 9 |
| 3 | 9 | 16 |
| 2 | 16 | 24 |

Total Waiting Time: 28
Total Turnaround Time: 52
Average Waiting Time: 7.00
Average Turnaround Time: 13.00

# Process Control Block

- A **Process Control Block (PCB)** is a data structure maintained by the Operating System for every process.
- It is also known as a **Task Control Block** and is identified by a unique **Process ID (PID)**.
- The PCB stores all essential information required to manage and track a process, such as its current state, CPU registers, scheduling details, and memory management information.
- Whenever a process transitions between states (**New, Ready, Running, Blocked, or Terminated**), the OS updates the PCB to reflect the process's current status.
- The PCB ensures efficient process scheduling, resource allocation, and execution management.

## **Components of PCB**

- pcb
    
    ![Screenshot 2025-03-03 at 7.14.14 PM.png](attachment:8349b7f0-6ccd-4acd-a721-0744bed0c8ff:Screenshot_2025-03-03_at_7.14.14_PM.png)
    
1. **`Process State`** – Indicates the current state of the process (New, Ready, Running, Waiting, or Terminated).
2. **`Process ID (PID)`** – A unique number assigned to identify the process.
3. **`Program Counter`** – Holds the memory address of the next instruction to be executed.

4.**`CPU Registers`** – Stores processor registers used by the process, including accumulators, index registers, stack pointers, and general-purpose registers.

5.**`CPU Scheduling Information`** – Contains scheduling details like process priority, pointers to scheduling queues, and other scheduling parameters.

6.**`Memory Management Information`**– Stores memory-related details such as page tables, segment tables, base and limit registers, depending on the memory management system in use.

7.**`Accounting Information`** – Tracks resource usage, including CPU time, process execution limits, and account details.

8.**`List of Open Files**` – Maintains a record of all files currently associated with the process.

9.**`I/O Status Information`** – Lists the I/O devices and files used by the process.

### **Location of PCB in Memory**

- The **Process Control Block** is stored in a protected memory area to prevent unauthorized access.
- Some operating systems place the PCB at the **beginning of the kernel stack** for the process, ensuring security and efficient access by the OS
---