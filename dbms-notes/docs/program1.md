# Program 1: Unix System Calls

---

- **A system call** is a programmatic way in which a computer program requests a service from the kernel of the operating system it is executed on.
- A system call is a way for programs to **interact with the operating system**.
- System call **provides** the services of the operating system to the user programs via the Application Program Interface (API).
- System calls are the only entry points into the kernel system and are executed in **kernel mode**.

---

## **Fork()**

### **Theory**

- The `fork()` system call in Unix/Linux is used to create a **new child process** by duplicating the **parent process**.
- The child process receives a copy of the parent’s memory, file descriptors, and execution state.
- Both parent and child processes run the same program but have different **process IDs**.
- Return values of `fork()`:
  - **Negative value** → Fork failed.
  - **Zero** → Returned to the newly created child process.
  - **Positive value** → Returned to the parent process (PID of the child).
- Number of processes = $2^n$, where `n` is the number of times fork is called.
- Number of child processes = $2^n - 1$.

### **Algorithm**

1. Declare variable `pid`.
2. Call `fork()`.
3. If `pid < 0`, print `"Fork failed"`.
4. If `pid == 0`, execute child process using `execlp()`.
5. If `pid > 0`, parent waits for child using `wait()`.
6. Print `"Child complete"`.

### **Program**

``` c
//FORK
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>

int main()
{
    int id, childid;
    id = getpid(); // Get the process ID

    if ((childid = fork()) > 0) // Fork the process and check if it's the parent
    {
        printf("\nI'm in the parent process %d", getpid());
    }
    else if (childid == 0) // Check if it's the child process
    {
        printf("\nI'm in the child process %d", getpid());
    }
    else
    {
        printf("\nFork failed!");
    }

    return 0;
} 
```



---

## **Factorial Using Fork()**

### **Algorithm**

1. Start.
2. Input number `n`.
3. Call `fork()`.
4. If return value is `0` (child):
   - Initialize `fact = 1`.
   - Loop from 1 to `n`, compute factorial.
   - Print result.
5. If return value > 0 (parent):
   - Print `"Child is calculating factorial"`.
6. End.


### **Program**

 
 ``` c
 //FACTORIAL 
    #include <stdio.h>
    #include <unistd.h>

    int main() {
        int n, i;
        long long fact = 1;

        printf("Enter a number: ");
        scanf("%d", &n);

        int pid = fork();

        if (pid == 0) {
            for (i = 1; i <= n; i++) {
                fact *= i;
            }
            printf("Child: Factorial of %d is %lld\n", n, fact);
        } else {
            printf("Parent: I created a child to calculate factorial.\n");
        }
        return 0;
    }
 ```

---

## **Process Hierarchy using Fork()**

### **Algorithm**

- Call fork() → creates Process A.
- If return = 0:
- Print "I am A" with PID and PPID.
- Call fork() → create Process B.
- If return = 0:
- Print "I am B" with PID and PPID.
- Call fork() → create Process C.
- If return = 0:
- Print "I am C" with PID and PPID.

### **Program**
```c
//HIERARCHY 

#include <stdio.h>
#include <unistd.h>

int main() {
    int pid;

    pid = fork();  // Create process A

    if (pid == 0) {
        // This is Process A
        printf("I am A (PID: %d), Parent: %d\n", getpid(), getppid());

        int pid1 = fork();  // A creates B

        if (pid1 == 0) {
            // This is Process B
            printf("I am B (PID: %d), Parent: %d\n", getpid(), getppid());

            int pid2 = fork();  // B creates C

            if (pid2 == 0) {
                // This is Process C
                printf("I am C (PID: %d), Parent: %d\n", getpid(), getppid());
            }
        }
    }

    return 0;
} 
```
 
 

---



## **Wait()** 

### **Theory**

- The wait() system call is used by a parent process to pause execution until one of its child processes terminates.
- It helps:
    - Synchronize parent and child.
    - Prevent zombie processes.
    - Ensure parent waits for child to finish.

### **Program**
```c
// WAIT()

#include <stdio.h>
#include <sys/types.h>
#include <sys/wait.h>  // for wait()
#include <unistd.h>    // for fork()

int main() {
    int i = 0, pid;

    pid = fork();

    if (pid == 0) {
        // Child process
        printf("Child process:\n");
        for (i = 0; i < 5; i++)
            printf("%d\n", i);
    } else {
        // Parent process
        wait(NULL);  // Wait for child to finish
        printf("Parent process:\n");
        for (i = 10; i < 15; i++)
            printf("%d\n", i);

        printf("Process ends.\n");
    }

    return 0;
}

```
   

---

## **Exec()** 
### **Theory**

- The exec family replaces the current running process with a new program.
- After a successful exec, the current process image is replaced and does not return.

### **Program**

```c 
//EXEC()
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>

int main(int argc, char *argv[]) {
    printf("before execv\n");
    execv("/bin/date", argv);   // Replace process with date command
    printf("after execv\n");    // Will not execute if execv is successful
    return 0;
}

```


---

## **Sleep()**
### **Theory**

- The sleep() system call suspends execution of the process for a given number of seconds.
- Used to introduce delays in program execution.

### **Program**

```c
// SLEEP 
#include <stdio.h>
#include <unistd.h>

int main() {
    printf("Program starts...\n");

    printf("Sleeping for 5 seconds...\n");
    sleep(5);   // process sleeps for 5 seconds

    printf("Woke up after sleep!\n");

    return 0;
}

```



---













