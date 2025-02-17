# Philosophers Project

## Description:
The **Philosophers** project simulates the classic "Dining Philosophers" problem, which is used to teach concepts of concurrency and synchronization. The problem involves a group of philosophers sitting at a table, each with a bowl of spaghetti. To eat, a philosopher needs two forks, one on their left and one on their right. However, each philosopher can only pick up one fork at a time, and they must avoid deadlock and resource contention.

The goal of the project is to simulate this scenario using threads and locks, ensuring that the philosophers can eat without causing deadlock or race conditions. The challenge is to implement a solution where all philosophers can eat and think without blocking each other or creating a system hang.

## Project Requirements:
- **Philosophers**: A set number of philosophers (at least 2) sit around a table. They alternate between thinking and eating.

- **Forks**: There are the same number of forks as philosophers, and each philosopher needs two forks to eat.

- **Simulation**: Philosophers will wait for forks to be available and attempt to pick them up. They eat for a specified amount of time, then put down the forks and resume thinking.

### Constraints:
- No philosopher should starve. They must all be able to eat eventually.
- No deadlock should occur, meaning no philosopher should ever be in a situation where they are holding one fork and waiting for another indefinitely.
- There must be no race conditions, where two philosophers try to pick up the same fork simultaneously.

## Key Restrictions & Challenges:
- **Concurrency and Threads**:  
  The project requires implementing a multithreaded solution, where each philosopher is a separate thread. Handling concurrency is challenging, especially managing shared resources (the forks) without causing issues like deadlock, starvation, or race conditions.

- **Synchronization**:  
  The solution involves using mutexes and condition variables (or semaphores) to ensure proper synchronization. Philosophers must be able to pick up and put down forks without interfering with each other, which requires careful coordination using locking mechanisms.

- **Deadlock Prevention**:  
  A critical challenge is to prevent deadlock, where two or more philosophers wait indefinitely for a fork. A deadlock-free solution typically requires a strategy like ordering the fork picking process or using a resource hierarchy to avoid circular wait conditions.

- **Starvation Prevention**:  
  Another problem to solve is starvation, where a philosopher might never get the chance to eat because they are repeatedly blocked by other philosophers. The solution must ensure that all philosophers have a fair chance to eat.

- **Resource Contention**:  
  Philosophers must pick up forks in a way that minimizes the risk of contention—where two philosophers try to access the same fork at the same time. Using mutexes or locks around the forks ensures only one philosopher can hold each fork at any time.

## How to Run:

To compile and run the program:

1. **Compile the program**: Use `make` to compile the program.

```bash
make
```
2. **Test the program**:
   Commandline execution and arguments is as following: 
   ./philo <number_of_philosophers> <time_to_die> <time_to_eat> <time_to_sleep>
   For example:
```bash
./philo 5 800 200 200
