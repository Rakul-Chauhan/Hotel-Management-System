# Hotel Management System

This project is a Hotel Management System implemented using POSIX-compliant C programs utilizing various Operating System concepts such as process creation, inter-process communication (IPC) using pipes and shared memory, and error handling. The system simulates a hotel environment where different entities like Admin, Hotel Manager, Tables, Customers, and Waiters are represented as processes.

## Table of Contents

- [Problem Statement](#problem-statement)
- [System Overview](#system-overview)
- [Requirements](#requirements)
- [File Descriptions](#file-descriptions)
- [How to Run](#how-to-run)
- [Details](#Details)

## Problem Statement

The objective of this assignment is to use various OS concepts to create a hotel management system application. The system consists of the following parts:
1. Table Processes
2. Waiter Processes
3. Hotel Manager Process
4. Admin Process

![image](https://github.com/Rakul-Chauhan/Hotel-Management-System/assets/139129716/5a08055e-2b7f-4626-8adf-b1e6273c61df)

## System Overview

- **Table Process:** Each table in the hotel is a separate process. A table process can have multiple customer processes (child processes), each representing a customer sitting at the table.
- **Customer Process:** A customer process takes food orders and communicates with the table process using pipes.
- **Waiter Process:** Each waiter process is responsible for a specific table and calculates the total bill amount based on orders received.
- **Hotel Manager Process:** This process oversees the total earnings of the hotel and handles termination upon receiving a termination signal from the admin process.
- **Admin Process:** This process is responsible for initiating the closure of the hotel.

## Requirements

- Ubuntu 22.04 or compatible Linux environment
- GCC compiler for compiling the C programs

## File Descriptions

- `table.c`: Implementation of the table process.
- `waiter.c`: Implementation of the waiter process.
- `hotelmanager.c`: Implementation of the hotel manager process.
- `admin.c`: Implementation of the admin process.
- `menu.txt`: Pre-defined menu file.
- `earnings.txt`: Output file to record earnings from different tables.

## How to Run

1. **Compile the programs:**
   ```sh
   gcc -o table table.c
   gcc -o waiter waiter.c
   gcc -o hotelmanager hotelmanager.c
   gcc -o admin admin.c
2. **Run the hotel manager process:**
    ```sh
    ./hotelmanager
3. **Run the admin process:**
    ```sh
    ./admin
4. **Run table processes in separate terminals (up to 10):**
    ```sh
    ./table
5. **Run waiter processes in separate terminals (up to 10):**
    ```sh
    ./waiter

**Running Instructions:**
- When running a table process, you will be prompted to enter a unique table number and the number of customers at the table.
- Customer processes will prompt for food orders based on menu.txt.
- The waiter process will calculate the total bill and communicate with the table process and hotel manager.
- The hotel manager will keep track of earnings and handle termination upon receiving a signal from the admin process.    

## Details
For more details on the implementation, refer to the comments in the source code files.
