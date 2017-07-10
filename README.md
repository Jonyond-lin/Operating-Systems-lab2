# Operating Systems lab2

This is my lab 2 for Operating System Principles course in XMU. The assignment guide see [Nachos Project Guide] of V22.0202-001 in New York University.

In this lab, I implement mutexes and condition variables first. Then use them to implement a multithreaded table and a bounded buffer. You can read guide for details.

## Installation
Now, you are in top directory. So, please enter into `threads` directory first.

```
cd threads
```

Compile the project.

```
make depend
make
```

Run the nachos. For part 1 "Implementing Mutexes and Condition Variables", you can use

```
./nachos -q 3 -t [num_threads] -n [num_items] -e [type_of_error]
```
where

- `-q 3`: test the doubly-linked list using  synchronization primitives
- `-t`: number of threads
- `-n`: number of items inserted into list by one thread
- `-e`: No. of error

For part 2 "Implementing a Multithreaded Table", you can use

```
./nachos -q 4 -t [num_threads] -n [num_items] -s [table_size]     -e [type_of_error]     -a [allow_synchronous_primitives(0 for FALSE/1 for TRUE)]
```
where

- `-q 4`: test the multithreaded table
- `-t`: number of `Allocater`, `Getter` and `Releaser`, here we assume that the amount of them are equal for simplicity
- `-n`: number of loops that each thread allocates, gets and releases items
- `-s`: the size of table
- `-e`: No. of error
- `-a`: whether using synchronization primitives or not

For part 3 "Implementing a Bounded Buffer", we provide two solutions. First, we use monitor. You can use

```
./nachos -q 5 -t [num_threads] -n [num_items] -s [table_size]     -e [type_of_error]     -a [allow_synchronous_primitives(0 for FALSE/1 for TRUE)]
```
where

- `-q 5`: test the bounded buffer implemented by monitor
- `-t`: number of `Producer` and `Writer`, here we assume that the amount of them are equal for simplicity
- `-n`: number of loops that each thread reads and writes items
- `-s`: the size of buffer
- `-e`: No. of error
- `-a`: whether using synchronization primitives or not

Secondly, we use semaphore. You can use

```
./nachos -q 6 -t [num_threads] -n [num_items] -s [table_size]        -e [type_of_error]        -a [allow_synchronous_primitives(0 for FALSE/1 for TRUE)]
```

The explaination of command-line parameters is the same to the first implementation.

## Acknowledgment
Dasong Chen, Jinbin Tan and Hao Dong assisted me to finish this assignment. Prof. Wei Zheng put forward constructive suggestions. Thanks for their effort.

[Nachos Project Guide]: http://www.cs.nyu.edu/courses/spring05/V22.0202-001/nachos-labs.pdf