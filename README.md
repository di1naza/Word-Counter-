# Word-Counter-
Word Counter Problem implemented on C and Linux using POSIX Multithreading and Semaphores
The goal of this project:
1. Learn how to synchronize the execution of processes and coordinate the use of shared
memory segment with POSIX Semaphores.
2. Learn how to improve the efficiency of process execution using multi-threaded programming
with POSIX Thread.
3. Learn to understand the file system and related directory/file operations.


Problem 1
1.1 Introduction
This problem aims to help you understand how the shared memory and semaphores are used between
processes based on problem1.c. In this program, we use three types of variables, i.e., the global
variable (global_param in line 17), the local variable (local_param in line 29), and the shared memory
variables (shared_param_p, shared_param_c in line 30). The values of all variables are initialized to
0 (the shared memory is automatically initialized).
We use the fork() system call to create a new child process. After that, the parent process and this child
process will execute their own code independently and concurrently. The parent process catches an
input parameter in the command line from terminal (see 2. How to run). The input parameter should
be an eight-digit decimal number, such as the student ID. Then the parent process assigns the value
of the input parameter to the three types of variables. The child process tries to get the input parameter
by reading the values of these variables and print them in terminal. We use the semaphore (named
PARAM_ACCESS_SEMAPHORE) created by sem_open() to coordinate the operations on the
variables between the processes. With this semaphore, we can achieve that only one process can access
the variables at any time, i.e., mutual exclusion.




Problem 2
2.1 Introduction
In this problem, you are required to implement a word counter with two processes to automatically
count the number of words in text files (with suffix .txt). You should achieve this with a C program
that uses two processes (named parent process and child process respectively, both of which use only
one thread). The parent process reads text files (with suffix .txt) under the given directory (which can
be obtained from the input parameter of this program). Then the child process counts the number of
words in those text files. Two processes communicate with each other using a shared memory (the
limited size is 1MB).




In Problem 2, both the parent and child processes have only one thread. When the given directory
contains many text files, or the text files have a large size of content, it would be inefficient. In this
problem, you are asked to extend your program implemented in Problem 2 with multi-threaded
programming. 
