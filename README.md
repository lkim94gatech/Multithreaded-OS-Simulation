# Multithreaded OS Simulation

This repository contains a **Multithreaded Operating System Simulator** for managing process scheduling and execution. The project simulates core OS functionalities, including scheduling algorithms, context switching, and process state transitions.

---

## Files Included

### Core Modules
- **os-sim.c**: Implements the main OS simulation logic and CPU simulation.
- **os-sim.h**: Header file for core simulation functions and data structures.
- **student.c**: Contains the implementation of the CPU scheduler and its related handlers.
- **student.h**: Header file for scheduler function declarations.

### Supporting Modules
- **process.c**: Implements process creation and manipulation.
- **process.h**: Header file defining process-related functions and data structures.

---

## Overview

The project simulates how an operating system manages processes across multiple CPUs. It supports different scheduling algorithms and tracks processes through various states, including **READY**, **RUNNING**, **WAITING**, and **TERMINATED**.

### Features
1. **Process Scheduling**:
   - Implements scheduling algorithms like:
     - **First-In-First-Out (FIFO)**
     - **Round-Robin (RR)**
     - **Longest Remaining Time First (LRTF)**
   - Handles preemption and context switching.

2. **Multithreading**:
   - Simulates multiple CPUs using threads.
   - Ensures thread safety with mutexes and condition variables.

3. **Process State Management**:
   - Tracks process transitions between states.
   - Handles events like I/O completion, time slice expiration, and termination.

---

## Setup Instructions

### Prerequisites
- **C Compiler**: GCC or Clang
- **Make**: For building the project
- **POSIX-Compatible Environment**: For threading support

### Steps

1. **Clone the Repository**:
   ```bash
   git clone <repository_url>
   cd os-simulation
   ```
2. **Compile the code**:
   ```bash
   make
   ```
3. **Run the Simulation**:
   ```bash
   ./os-sim <#CPUs> [ -l | -r <time slice> ]
   ```
4. **Clean Up**:
   ```bash
   meake clean
   ```

## Modules Breakdown

### Core Modules

- **os-sim.c**  
  **Purpose**: Main simulator logic.  
  - Handles CPU execution and process scheduling.

- **student.c**  
  **Purpose**: Implements the scheduler and its related handlers.  
  **Key Functions**:
  - `idle()`: Blocks the CPU until a process is ready.
  - `preempt()`: Handles time slice expiration.
  - `yield()`: Manages I/O-bound process yields.
  - `terminate()`: Marks processes as terminated.
  - `wake_up()`: Wakes up processes waiting on I/O.

---

### Supporting Modules

- **process.c**  
  **Purpose**: Manages process creation and manipulation.

---

## Testing

### Functionalities

1. **Process Scheduling**:
   - Validate the behavior of FIFO, Round-Robin, and LRTF scheduling.
   - Analyze CPU utilization and process throughput.

2. **Multithreading**:
   - Ensure thread safety by testing with varying CPU counts.
   - Validate the behavior of mutexes and condition variables.

3. **Process States**:
   - Test transitions between `READY`, `RUNNING`, `WAITING`, and `TERMINATED`.

4. **Edge Cases**:
   - Test with:
     - Zero processes.
     - High CPU count.
     - Frequent context switching.
