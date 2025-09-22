# **Operating System** 
- An Operating System(OS) is a software that manages and handles hardware and software resources of a computing device.
- It provides a user interface and enables communication between computer hardware and software
- Responsible for managing and controlling all the activities and sharing of computer resources among different running applications.

     ![image.png](attachment:feb01200-c6dd-4b8a-8185-56ab9fef8c51:image.png)
        
- Example: Linux, Unix, Windows 11, Android, macOS
- **Kernal:**
    - The software that contains the core components of the OS is called the **kernel**
    - It is responsible for all major operations and interaction with the hardware.
    - A low-level Software that includes all the basic functions like processor management, memory management, file management, etc.
- **Shell:**
    - Shell is an interface of an OS. It can be command line interface or a graphical user interface.
    - User interacts with an OS using shell. Application programs can also use shell interface to interact with underlying OS.

---

# **OS: Generations**

- 0th Generation
    - 1940 - early 1950s
    - vacuum tubes and plug boards
- 1st Generation
    - 1951-1956
    - transistors and batch systems
- 2nd Generation
    - 1956-196
    - Integrated Circuits and multi programming
- 3rd Generation
    - 1964-1979
    - personal computers
---

# **Computer System Operation**

- A modern say general purpose computer consists of one or more CPU and a number of device controllers connected through a common bus that provides access to shared memory
- Each device controller is in charge of a specific type of device
- The CPU and the dc can execute concurrently, competing for memory cycles
- To ensure orderly access to the shared memory, a memory controller is provided who’s function is to synchronise access to the memory

- **CPU:**
    - Executes instructions and processes data.
    - Components:
        - **Control Unit (CU):** Directs data flow.
        - **Arithmetic Logic Unit (ALU):** Performs arithmetic and logical operations.
        - **Registers:** Store temporary data for quick access.
- **Memory (Primary Storage):**
    - **RAM (Random Access Memory)**: Volatile, fast storage for active programs/data.
    - **ROM (Read-Only Memory)**: Non-volatile, stores firmware (e.g., BIOS).
- **I/O Devices:**
    - Keyboards, mice, monitors, printers, etc.
    - Managed via **device drivers** (software that interfaces with hardware).
- **Storage Devices (Secondary Storage):**
    - HDDs, SSDs, USB drives (non-volatile, slower than RAM).
- **Buses:**
    - Communication channels between components (e.g., data bus, address bus).
- **Bootstrap Program:**
    - bootstrap program is loaded at power-up or
    reboot
    - Typically stored in ROM or EPROM, generally
    known as firmware
    - Initialises all aspects of system
    - Loads operating system kernel and and starts execution
- **Interrupt:**
    - The occurence of an event is usually signalled by an interrupt from hardware or software
    - hardware may trigger an interrupt at any time by sending a signal to the CPU using the system bus
- **System Call:**
    - Software may trigger an interrupt by executing a special operation called as a system call(monitor call)

---

# **I/O Structure**

A large portion of an operating system’s code is dedicated to managing I/O due to its importance in ensuring system reliability and performance. Additionally, the diverse nature of devices requires efficient handling mechanisms.

## **Basic I/O Mechanism**

1. **System Components**:
    - A general-purpose computer system consists of a **CPU** and multiple **device controllers**, which are connected through a **common bus**.
    - Each **device controller** has:
        - **Local buffer storage** for temporary data holding.
        - **General-purpose registers** for control and status information.
2. **Role of Device Controllers**:
    - The **device controller** manages data transfer between the **peripheral device** and its **local buffer storage**.
    - The **OS communicates** with the device controller using a **device driver**, which acts as an interface between the OS and hardware.
    - Each **device controller has a corresponding device driver**, which understands its specific operations and provides a uniform interface to the OS.

## **I/O Operation Flow**

1. The **OS initiates an I/O operation** by instructing the **device driver** to load the necessary registers within the **device controller**.
2. The **device controller** examines the register contents to determine the required action.
3. The controller **transfers data** from the peripheral device to the **local buffer**.
4. Upon completion, the **device controller sends an interrupt** to notify the OS that the operation is finished.
5. The **device driver handles the interrupt**, completes the necessary processing, and **returns control to the OS**.

- **Interrupt-Driven I/O**:
    - Suitable for transferring **small amounts of data**.
    - However, it generates a **high overhead** for bulk data transfers (e.g., disk I/O) because an **interrupt is triggered for each byte of data**.
- **Direct Memory Access (DMA)**:
    - Used for transferring **large blocks of data** efficiently.
    - The **device controller** is responsible for moving an entire block of data **directly between the device and memory** without CPU intervention.
    - The CPU only receives **one interrupt per block** (instead of one per byte), reducing overhead.
    - While DMA is in progress, the **CPU remains free** to perform other tasks, improving overall system efficiency.
---

# **Storage Structure**

A storage system provides:

1. **Storing data** for later retrieval.
2. **Holding data** until accessed.

The key differences between various storage types are:

- Speed (faster storage is generally more expensive).
- Cost per bit ****(decreases as we move down the hierarchy).
- Size (higher levels store less data, lower levels store more).
- Volatility (some storage types lose data when power is lost).
- **Registers:**
    - located inside the CPU, these store data in bits and can be accessed quickly
    - It can hold small amount of data (32 to 64 bits)
    - It is volatile in nature
    - ex: instruction Register (IR), Accumulator, Stack Pointer.
- **Cache:**
    - Located in between CPU and RAM. It is faster that RAM but slower than registers
    - It stores frequently accessed data and instructions to speed up processing and reduces access to the slower main memory
    - It is volatile in nature
- **Main Memory[RAM]:**
    - It is directly accessible by CPU
    - It is slower than cache but faster than secondary storage
    - It is volatile in nature and holds active processes, programs, and data currently in use.
    - **Dynamic RAM (DRAM):** Used in main memory, slower than SRAM.
    - **Static RAM (SRAM):** Faster but used mainly for cache memory.

**Secondary Storage:**

Used for data backup, archival storage, and infrequently accessed data.Non volatile in nature 

- **Solid-State Drive (SSD):**
    - The SSD have several variants but in general are faster than Magnetic disk and are non-volatile
    - Uses flash memory, faster but expensive.
- **Magnetic Disk**
    - **Hard Disk Drive (HDD):** Uses spinning magnetic disks, slower but cheaper

**Tertiary Storage:** 

Used for long-term storage, offline storage, and backups.

External devices, cloud, or offline storage.

- **Optical Disk**
    - Used for media storage and backups.
- **Magnetic Tapes**
    - Used for long-term data storage.
---

# **OS: Structures** 

- An operating system is a structure that allows the user application programs to interact with the system hardware
- Since the operating system is such a complex structure, it should be created with utmost care so it can be used and modified easily.
- An easy way to do this is to create the operating system in parts.
- Each of these parts should be well defined with clear inputs, outputs and functions.

## Simple Structure 
- Lacks a well-defined structure and is typically implemented as a monolithic system.
- Functions are not separated into distinct modules, leading to direct interaction between components.
- example: MS-DOS
- Provides basic functionalities with minimal separation.
- Kernel and application programs interact without clear boundaries, making the system efficient but hard to maintain.
- **Advantages:** Fast execution due to fewer layers.
- **Disadvantages:** Difficult to extend and debug due to tight coupling.

## Layered Structure 
- An OS can be broken into pieces and retain much more control over the system.
- In this structure, the OS is broken into a number of layers (levels).
- The bottom layer (layer 0) is the hardware, and the topmost layer (layer N) is the user interface.
- These layers are so designed that each layer uses the functions of the lower-level layers
- One problem with the layered structure is that each layer needs to be carefully defined. This is necessary because the upper layers can only use the functionalities of the layers below them.
- **Advantages**
    - **High Customizable** - Being layered, each layer implmentation can be customized easily. A new functionality can be added without impacting other modules as well
    - **Verifiable** - Being modular, each layer can be verified and debugged easily.
- **Disadvantages**
    - **Less Performant** - A layered structured operating system is less performant as compared to basic structured operating system.
    - **Complex designing** - Each layer is to planned carefully as each layer communicates with lower layer only and a good design process is required to create a layered operating system.
## Micro Kernal Structure 

- In micro-kernel, we have multiple kernels each one specilized in particular service
- Each microkernel is developed independent to the other one and makes system more stable
- If one kernel fails the operating sytem will keep working with other kernel's functionalities.
- **Advantages**
    - **Reliable and Stable** - As multiple kernels are working simultaneously, chances of failure of operating sytem is very less. If one functionlity is down, operating system can still provide other functionalities using stable kernels
    - **Maintainability** - Being small sized kernels, code size is maintainable. One can enhance a microkernel code base without impacting other microkernel code base.
- **Disadvantages**
    - **Complex to Design** - Such a microkernel based architecture is difficult to design.
    - **Performance Degradation** - Multi kernel, Multi-modular communication may hamper the performance as compared to monolith architecture.
## Modular Structure 
- It is considered as the best approach for an OS. It involves designing of a modular kernel.
- The kernel has only a set of core components and other services are added as dynamically loadable modules to the kernel either during runtime or boot time.
- It resembles layered structure due to the fact that each kernel has defined and protected interfaces, but it is more flexible than a layered structure as a module can call any other module.
- **Advantages:**
    - **High Customizable** - Being modular, each module implmentation can be customized easily. A new functionality can be added without impacting other modules as well.
    - **Verifiable** - Being modular, each layer can be verified and debugged easily.
- **Disadvantages:**
    - **Less Performant** - A modular structured operating system is less performant as compared to basic structured operating system.
    - **Complex designing** - Each module is to planned carefully as each module communicates with kernal. A communication API is to be devised to facilitate the communication.
---
# **OS: Types**

## Batch OS 
- This type of operating system does not interact with the computer directly.
- There is an operator which takes similar jobs having the same requirements and groups them into batches.
- It is the responsibility of the operator to sort jobs with similar needs.
- Batch OS is designed to manage and execute a large number of jobs  sequentially without user intervention and efficiently by processing them in groups
- IBM introduced FORTRAN IBSYS 7096 for this
- **Example:** Payroll Systems, Bank Statements, etc.
- **Advantages**
    - Multiple users can share the batch systems.
    - It is easy to manage large work repeatedly in batch systems.
    
- **Disadvantages**
    - CPU is not used efficiently. When the current process is doing IO, CPU is free and could be utilised by other processes waiting.
    - The other jobs will have to wait for an unknown time if any job fails.
    - In batch os, average response time increases as all processes are processed one by one.

## Multi-Programming OS 
- Multiprogramming OS allows multiple programs to be **loaded into memory and executed concurrently**, maximizing **CPU utilization**.
- It was developed to overcome the limitations of Batch OS, where the CPU often remained idle while waiting for I/O operations.
- The OS manages their execution based on **priority and availability of resources**.
- The OS divides memory among different programs using **partitioning techniques** (Fixed or Dynamic Partitioning).
- If one process is waiting for I/O (e.g., reading from a disk), the CPU switches to another process.This process of switching between programs is called **context switching**.This reduces CPU idle time and increases throughput.
- **Advantages**
    - Maximises CPU Utilisation
    - Increases Throughput
    - Efficient Resource Management
- **Disadvantages**
    - Requires efficient allocation of memory to multiple programs.
    - Higher Response Time since some processes may have to wait longer for CPU time.
    - Risk of Deadlock as multiple processes may wait for resources indefinitely.

## Multi-Taksing OS
- It is a type of Multiprogramming system with every process running in round robin manner where not only are multiple programs loaded into memory, but they are also executed **concurrently with time-sharing**.
- The OS **allocates a fixed time slice** to each process
- The time that each task gets to execute is called quantum. After this time interval is over OS forcibly switches over to the next process.

- **Advantages**
    - Ensures that no process keeps the CPU idle for long.
    - Improves user experience by switching between tasks quickly.
    - Users can run multiple applications simultaneously.
- **Disadvantages**
    - Risk of overloading as too many processes can slow down performance.
    - Running multiple applications consumes more memory.
    - Requires advanced scheduling and memory management.


## Multi-Processing OS 
- a type of Operating System in which more than one CPU is used for the execution of resources.
- It betters the throughput of the System.
- **Advantages**
    - It increases the throughput of the system as processes can be parallelized.
    - As it has several processors, so, if one processor fails, we can proceed with another processor.

## Time Sharing OS 
- The time interval required to process and respond to inputs is very small. This time interval is called **response time.**
- **Real-time systems** are used when there are time requirements that are very strict like missile systems,ATC, robots, etc.
- **Hard Real-Time OS** are meant for applications where time constraints are very strict and even the shortest possible delay is not acceptable
- **Soft Real-Time OS** are for applications where time-constraint is less strict

## Distributed OS 
- These types of operating system is a recent advancement in the world of computer technology and are being widely accepted all over the world and, that too, at a great pace.
- Various autonomous interconnected computers communicate with each other using a shared communication network.
- Independent systems possess their own memory unit and CPU. These are referred to as loosely coupled systems or distributed systems These systems’ processors differ in size and function.
- The major benefit of working with these types of the operating system is that it is always possible that one user can access the files or software which are not actually present on his system but some other system connected within this network i.e., remote access is enabled within the devices connected in that network.
- **Advantages**
    - Failure of one will not affect the other network communication, as all systems are independent of each other.
    - Electronic mail increases the data exchange speed.
    - Since resources are being shared, computation is highly fast and durable.
    - Load on host computer reduces.
    - These systems are easily scalable as many systems can be easily added to the network.
    - Delay in data processing reduces.
- **Disadvantages**
    - Failure of the main network will stop the entire communication.
    - To establish distributed systems the language is used not well-defined yet.
    - These types of systems are not readily available as they are very expensive. Not only that the underlying software is highly complex and not understood well yet.
---

# **OS: Servies**
An operating system provides a variety of essential services that help users and system programs interact with hardware efficiently. These services ensure system usability, resource management, and process control

1. **Program Execution:**
    - The OS ensures smooth execution of user programs and system processes.
    - Loads programs into memory for execution.
    - Allocates CPU time for execution.
    - Handles process creation, termination, and scheduling.
    - Provides a mechanism for process communication.
    - Provides a mechanism for deadlock handling.
2. **Resource Allocation:**
    - The OS allocates system resources efficiently among processes.
    - **CPU Scheduling:** Determines which process gets CPU time.
    - **Memory Allocation:** Assigns RAM space dynamically.
    - **Disk Management:** Allocates storage space for files.
    - **Device Management:** Handles I/O device sharing.
3. **Communication:**
    - Processes need to communicate for data sharing and coordination. The OS provides mechanisms for Inter-Process Communication (IPC).
    - **Shared Memory:** Processes share a common memory space for exchanging data.
    - **Message Passing:** Processes send and receive messages through system calls.
4. **File System Manipulation:**
    - Handles the creation, deletion, and organization of files and directories.
    - **File Organization:** Stores and organizes data in a structured manner.
    - **Access Control:** Manages user permissions (Read, Write, Execute).
    - **File Operations:** Provides commands for opening, reading, writing, closing files.
    - **File Sharing & Security:** Ensures controlled access and protection of data
5. **I/O Operation:**
    - Coordinates input and output operations to communicate with hardware devices like keyboards, printers, and disk drives.
    - **Device Drivers:** Interfaces between OS and hardware devices.
    - **Buffering & Caching:** Temporarily stores data for smooth processing.
    - **Interrupt Handling:** Manages signals from devices to the CPU.
6. **Protection and Security:**
    - Safeguards the system against unauthorized access and threats
    - **Authentication:** Ensures only authorized users access the system.
    - **Encryption:** Protects data from unauthorized modifications.
    - **Access Control:** Implements user permissions and policies.
    - **Threat Detection:** Identifies and prevents viruses and malware.
7. **Error Detection:**
    - The OS constantly monitors the system for hardware and software errors to ensure reliable operation.
    - Logs errors for debugging.
    - Displays error messages to users.
    - Attempts error recovery (e.g., retries disk read/write operations).
    - Prevents faulty programs from affecting system stability.
8. **Accounting & Tracking:**
    - Monitors CPU, memory, and I/O usage.
    - Tracks user logins and activity.
    - Helps administrators optimize resource allocation.
    - Used in cloud computing for usage-based billing
9. **User Interface:**
    - Provides an interface for users to interact with the system.
    - **Command-Line Interface (CLI):** Uses text-based commands (e.g., Linux Terminal).
    - **Graphical User Interface (GUI):** Uses visual elements (e.g., Windows, macOS).
---

# **Dual Mode Operation**

**The dual mode operation ensures:**

1. **Protection of the OS** from faulty or malicious user programs.
2. **Protection of user programs** from interfering with each other.

This is achieved by restricting **certain critical operations** to a **privileged mode**.


## Modes of Operation:

A computer system operates in **two modes**:

- **User Mode**: Executes user applications with **restricted access** to system resources.
- **Kernel Mode (Supervisor Mode / System Mode / Privileged Mode)**: Executes **OS instructions** with **full access**to hardware and system resources.

A special hardware **mode bit** is used to indicate the current mode:

- **0 → Kernel Mode**
- **1 → User Mode**

If an attempt is made to execute a privileged instruction in user mode, the hardware does not execute the instruction but rather treats it as illegal and traps it to the OS


**Dual mode of an OS provides:**

- Security → Prevents unauthorized access to system resources.
- Stability → Protects the OS and user programs from errors and crashes
- Controlled Access → Ensures users can access system services safely.



## Working of Dual Mode Operation:

![image.png](attachment:6424f296-d606-44ec-a1e7-4fb32d162fed:image.png)

- There are two modes of operation **user mode** and **kernel mode** (supervisor mode, system mode, privileged mode)
- A bit mode called the **mode bit**, is added to the hardware of the computer to indicate the current mode: **kernel mode(0) and user mode(1)**
- When the computer system is executing on behalf of a user application it is in user mode.
- However, when an application requests a service from OS via a system call, the system transitions from user to kernel mode to full fill the request
- At system boot time, the hardware starts in kernel mode. The OS is then loaded and starts user applications in user mode.
- Whenever trap or interrupt occurs, the hardware switches from user mode to kernel (that is, changes the state of the mode bit to O).
- Thus, whenever the OS gains control of the computer, it is in kernel mode.
- The system always switches to user mode (by setting the mode bit to 1) before passing control user program.

---

# **Computer System Architerture**
Based on number of general purpose processes we have:
## Single System Processing 
- A single processor system contains only one processor.
- So only one process can be executed at a time and then the process is selected from the ready queue
- On a single processor system, there is one main CPU capable of executing a general purpose instruction , including instructions from user processes
- Almost all single processor systems have other special purpose processors as well
- All of these special purpose processors run a limited instruction set and do not run user processes

**Advantages:**

- Simple System Architecture
- Easier to develop and maintain

**Disadvantages:**

- Slower execution due to sequential processing
- High CPU load can cause performance bottlenecks
- Cannot execute multiple tasks simultaneously

## Multiple System Processing 
- A multiprocessing operating system is defined as a type of operating system that makes use of more than one CPU to improve performance
- Multiple processors work parallelly in multi-processing os to execute tasks concurrently.
- These processors are in close communication, sharing the computer bus and sometimes the clock, memory and peripheral devices

**Advantages:**

1. Increased throughput: Multiple processing systems improve throughput by executing multiple tasks simultaneously, reducing idle time, and optimizing resource utilization by 
    - *Parallel Execution:* tasks are divided among multiple CPUs and multiple processors execute different processes at the same time, reducing overall execution time and increasing efficiency
    - *Load Balancing*:the system distributes tasks evenly among processors to prevent bottlenecks and dynamic load balancing ensures that no processor remains idle while others are overloaded.
    - *Efficient Process Scheduling:* multiprocessing allows for better scheduling by making use of algorithms such as RR,SJF and priority scheduling
    - *Reduced Context Switching*: MP reduce the need for switching, leading to higher throughput
    - *Reduced Waiting time for IO operations:* while one processor handles computation, another can manage I/O operations, preventing idle time.
    - *Fault Tolerance and Redundancy:* If one processor fails, others continue processing, preventing system downtime and maintaining throughput.
2. Economy of scale - Multiprocessor systems can cost less than equivalent multiple single processor systems because they can share peripherals, mass storage and power supplies.

**Disadvantages:**

- Higher hardware and maintenance costs.
- Complexity in system design and synchronization.
- Requires special software to manage multiple processors

### Symmetric Multiple Processing

- Multiple processors share the same physical memory and operate under a single OS, with each processor having equal access to system resources.
- Each processor has its own set of registers as well as local or private cache
- All CPUs access the same memory, leading to efficient communication
- Tasks are distributed evenly among processors to improve performance.
- **Advantages:**
    - **Better Resource Utilization:** Each processor is able to work on a particular task and share the work load hence enhancing the performance.
    - **Scalability:** Additional processors can also be added to SMP systems hence they have a good potential for scaling.
    - **Fault Tolerance:** Due to the notion of distributed processing, where no single processor has control of the entire system, failure of one processor does not result in failure of the entire system
- **Disadvantages:**
    - **Complex Scheduling:** Tasks distribution among the multiple processors might be more challenging than the simple division of data among the cores and can involve logical functions of scheduling.
    - **Resource Contention:** Several processors might run for the same memory or I/O thus they might experience contention.
    - **Increased Hardware Costs:** SMP systems call for more elaborate hardware meant for the shared access between the processors and the memory and other system assets.


### Asymmetric Multiple Processing

- One processor acts as a *master* whereas remaining all processors act a *slaves*.
- Slave processors are assigned with ready to execute processes by the master processor.
- A ready queue is being maintained by master processor to provides with processes for slaves.
- In multiprocessing operating system a schedular is created by master process that assigns processes to be executed to slave processors.
- **Advantages:**
    - **Simplified Control:** Another advantage is that there is a single master processor who handles the task of scheduling so as to ensure co-ordination of tasks.
    - **Reduced Resource Conflicts:** This is made possible since only the master processor communicates with the operating system hence the conflicts between the processors are low.
- **Disadvantages:**
    - **Single Point of Failure:** Correspondingly, the operations of the system are largely contingent upon the master processor. When computer is splitter into master and other processors, if the master does not work, then the entire system can be non-operational.
    - **Less Efficient Resource Utilization:** Other subordinate processors may even remain idle due to the inability of master processor to assign tasks appropriately.

| **Feature** | **SMP** | **AMP** |
| --- | --- | --- |
| *Definition* | Multiple processors share the OS and have equal control over system tasks. | One master processor controls the system and assigns tasks to slave processors. |
| *Processor Equality* | All processors are equal. | Processors are not equal. |
| *OS Task Management* | Tasks are distributed among individual processors. | The master processor handles OS tasks. |
| *Processor Control* | All processors perform tasks independently. | The master processor assigns tasks to slave processors. |
| *Workload Distribution* | Dynamic; any processor can execute any task. | Fixed; tasks are pre-assigned to specific processors. |
| *Communication* | All processors communicate via shared memory. | No direct communication; master processor controls everything. |
| *Fault Tolerance* | High; if one processor fails, others can take over. | Low; failure of the master processor can halt the system. |
| *Efficiency* | High, as all processors share the workload equally. | Lower efficiency due to dependency on the master processor. |
| *Complexity* | More complex due to synchronization and resource sharing. | Simpler to implement since the master processor handles system tasks. |
| *Resource Sharing* | Shared memory and OS control among all processors. | Limited sharing; master processor manages system resources. |
| *Scalability* | Highly scalable; additional processors can be added easily. | Less scalable due to dependency on the master processor. |
| *Cost* | Expensive. | Relatively inexpensive. |
| *Examples* | Multi-core CPUs, modern servers, supercomputers. | Embedded systems, early multiprocessor systems, mobile devices. |

## Clustered Systems 
- Clustered systems are similar to parallel systems as they both have multiple CPUs.
- However a major difference is that clustered systems are created by two or more independent systems, with shared common storage and connected by a high-speed LAN, working together.
- Each node in the clustered systems contains the cluster software.
- This software monitors the cluster system and makes sure it is working as required.
- If any one of the nodes in the clustered system fail, then the rest of the nodes take control of its storage and resources and try to restart.

- **Advantages of Clustering Systems:**
1. **Fault Tolerance:**
    - The loss of one node does not result in the loss of the system.
    - They may even contain one or more nodes in hot standby mode which allows them to take the place of failed nodes.
2. **Performance:**
    - They work as a parallel unit and result in much better performance for the system.
3. **Scalability:**
    - It is easy to add a new node to the system.




### Asymmetric Clustered Systems 

- one of the nodes in the clustered system is in *hot standby mode* and all the others run the required applications.
- The hot standby mode is a failsafe in which a hot standby node is part of the system
- The hot standby node continuously monitors the server and if it fails, the hot standby node takes its place.

### Symmetric Clustered Systems

- In symmetric clustering system two or more nodes all run applications as well as monitor each other.
- This is more efficient than asymmetric system as it uses all the hardware and doesn't keep a node merely as a hot standby
- Such systems can supply significantly greater computational power than single processor or even SMP systems because they can run an application concurrently on all computers in the cluster, this involves a technique known as *parallelization* which divides a program into separate components that run in parallel on individual computers in the cluster

| **Feature** | **SPS** | **MPS** | **CS** |
| --- | --- | --- | --- |
| *Definition* | A system with a single processor executing tasks sequentially. | A system with multiple processors sharing workload within a single OS. | A group of interconnected computers working together as a single system. |
| *No of Processors* | One | More than one (Multiprocessing) | Multiple independent computers (nodes) |
| *Execution Type* | Sequential execution of tasks. | Parallel execution across multiple processors. | Distributed execution across multiple machines. |
| *Performance* | Slower due to sequential execution. | Faster due to shared processing. | Very high performance, used for large-scale computing. |
| *Fault Tolerance* | Low; system fails if the processor crashes. | Moderate; if one processor fails, others continue. | High; if one node fails, others continue processing. |
| *Resource Sharing* | No sharing, all tasks handled by one CPU. | Shared memory and resources among processors. | Nodes communicate and share workload via a network. |
| *Scalability* | Limited; performance improves only by upgrading the single CPU. | Scalable by adding more processors. | Highly scalable by adding more nodes. |
| *Cost* | Low; requires only a single processor. | Moderate; requires multiple processors in a single system. | High; requires multiple computers and networking infrastructure. |
| *Examples* | Traditional personal computers. | Multi-core processors, servers, supercomputers. | Cloud computing, data centers, high-performance computing clusters. |

---

# **System Calls**

- **A system call** is a programmatic way in which a computer program requests a service from the kernel of the operating system it is executed on
- A system call is a way for programs to **interact with the operating system**.
- System call **provides** the services of the operating system to the user programs via the Application Program Interface(API).
- System calls are the only entry points into the kernel system and are executed in kernel mode.

| **Type** | **Functions** | **Description** |
| --- | --- | --- |
| **Process Control** | End, abort | Terminates a process |
| *System calls related to creating, managing, and terminating processes.* | Load, execute | Loads a program into memory and runs it |
|  | Create process, terminate process | Starts or stops a process |
|  | Get process attributes, set process attributes | Retrieves or modifies process-related information |
|  | Wait for time | Pauses a process for a specified duration |
|  | Wait event, signal event | Synchronizes processes through events |
|  | Set and free memory | Allocates or deallocates memory |
| **File Management** | Create, delete | Creates or removes a file |
| *System calls for handling files and performing operations on them.* | Open, close | Opens or closes an existing file |
|  | Read, write, reposition | Reads from, writes to, or moves within a file |
|  | Get file attributes, set file attributes | Retrieves or modifies file metadata |
| **Device Management** | Request device, release device | Requests or releases access to a device |
| *System calls for interacting with hardware devices.* | Read, write, reposition | Performs I/O operations on a device |
|  | Get device attributes, set device attributes | Retrieves or modifies device settings |
|  | Logically attach or detach devices | Connects or disconnects a device |
| **Information Maintenance** | Get time or date, set time or date | Retrieves or updates the system clock |
| *System calls for retrieving or updating system-related information.* | Get system data, set system data | Reads or modifies system-level information |
|  | Get process, file, or device attributes | Retrieves attributes of system components |
|  | Set process, file, or device attributes | Modifies attributes of processes, files, or devices |
| **Communication** | Create, delete communication connection | Establishes or removes a communication channel |
| *System calls for interprocess and network communication.* | Send, receive messages | Transfers data between processes or over a network |
|  | Transfer status signal | Sends control signals between processes |
|  | Attach or detach remote devices | Connects or disconnects remote devices |

# **System Design and Implementation**

### Design Goals

- **Requirements** define properties which the finished system must have, and are a necessary first step in designing any large complex system.
    - **User requirements** are features that users care about and understand, and are written in commonly understood vernacular. They generally do not include any implementation details, and are written similar to the product description one might find on a sales brochure or the outside of a shrink-wrapped box.
    - **System requirements** are written for the developers, and include more details about implementation specifics, performance requirements, compatibility constraints, standards compliance, etc. These requirements serve as a "contract" between the customer and the developers, ( and between developers and subcontractors ), and can get quite detailed.
- Requirements for operating systems can vary greatly depending on the planned scope and usage of the system. ( Single user / multi-user, specialized system / general purpose, high/low security, performance needs, operating environment, etc. )

### Mechanisms and Policies

- Policies determine *what* is to be done. Mechanisms determine *how* it is to be implemented.
- If properly separated and implemented, policy changes can be easily adjusted without re-writing the code, just by adjusting parameters or possibly loading new data / configuration files. For example the relative priority of background versus foreground tasks.

### Implementation

- Traditionally OSes were written in assembly language. This provided direct control over hardware-related issues, but inextricably tied a particular OS to a particular HW platform.
- Recent advances in compiler efficiencies mean that most modern OSes are written in C, or more recently, C++. Critical sections of code are still written in assembly language, ( or written in C, compiled to assembly, and then fine-tuned and optimized by hand from there. )
- Operating systems may be developed using **emulators** of the target hardware, particularly if the real hardware is unavailable ( e.g. not built yet ), or not a suitable platform for development, ( e.g. smart phones, game consoles, or other similar devices. )