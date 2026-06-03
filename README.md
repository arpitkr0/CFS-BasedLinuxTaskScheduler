# CFS-Based Linux Task Scheduler

A Linux task scheduler implemented in C++ that simulates CPU scheduling behavior using concepts from the Linux Completely Fair Scheduler (CFS). The project explores process scheduling, resource allocation, fairness, and virtual runtime-based task selection.

## Features

- CFS-inspired scheduling algorithm
- CPU-bound and I/O-bound task simulation
- Virtual Runtime (`vruntime`) based scheduling
- Priority and weight-based CPU allocation
- Runqueue management using a priority queue
- Scheduling visualization and analysis

---

## Concepts Implemented

### Operating Systems

- CPU Scheduling
- Process Management
- Runqueue Management
- Fair Scheduling
- Resource Allocation

### Scheduling Algorithms

- Completely Fair Scheduler (CFS)
- Priority-Based Scheduling
- Virtual Runtime Tracking
- Time Slice Allocation

---

## System Design

```text
Tasks
  |
  v
+----------------+
| Runqueue (Min) |
+----------------+
        |
        v
Select Task with
Lowest vruntime
        |
        v
Execute Task
        |
        v
Update vruntime
        |
        v
Reinsert into Queue
```

The scheduler always selects the task with the smallest virtual runtime, ensuring fair CPU distribution across workloads.

---

## Tech Stack

- C++
- STL Priority Queue
- CMake
- Linux

---

## Key Components

### CPU-Bound Tasks

- Execute continuously until completion.
- Consume CPU time and update `vruntime`.

### I/O-Bound Tasks

- Simulate I/O wait periods.
- Re-enter the scheduler after wait completion.
- Demonstrate scheduler behavior under mixed workloads.

### Runqueue

- Maintains runnable tasks ordered by `vruntime`.
- Ensures fair task selection.

---

## Building and Running

### Clone Repository

```bash
git clone <repository-url>
cd linux-task-scheduler
```

### Build

```bash
mkdir build
cd build
cmake ..
make
```

### Run

```bash
./cfs-scheduler
```

### Generate Scheduling Plots

```bash
python3 plot.py
```

---

## Learning Outcomes

Through this project, I gained practical experience with:

- Linux scheduling internals
- Completely Fair Scheduler (CFS)
- Process prioritization and fairness
- Priority queues and scheduling data structures
- CPU-bound vs I/O-bound workload behavior
- Operating system resource management

---

## Future Improvements

- Multi-core scheduling support
- Additional scheduling algorithms (FCFS, Round Robin, SJF)
- Real-time scheduling policies
- Interactive scheduler visualization
- Performance benchmarking across workloads


