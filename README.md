# Baboon-concurrency-problem

This repository contains the logic and code for the baboon problem asked in OS Midsem, IIIT Hyderabad

## Logic
- We use an alternate policy to have a deadlock-free and starvation-free system. 
- A mutex is used to prevent multiple threads executing critcial sections simulataneously. 
- To avoid deadlock we ensured that the travelling variable can be positive for only one side at a time. To achieve this, whenever the variable is upadted, a mutex lock must be acquired.
- To avoid starvation, the alternate policy followed is based on the idea of to stop crossing a rope as soon as baboons start waiting on the other side. 
- It becomes the responsibility of the last baboon (crossed from the rope) to signal waiting baboons on either side according to the condition in the code.

## How to run

The program can be compiled using the below command
```(shell)
$ gcc q7.c -lpthread
$ ./a.out
```
The program expects to type the number of baboons that came.
It will randomly assign direction to them.

Example Input: 
```(shell)
Enter the number of baboons: 4
```

Example Output:
```(shell)
1 Baboon came from 1 direction
1 is waiting from 1 direction to get the rope
1 Baboon started to cross from 1 direction
4 Baboon came from 1 direction
4 is waiting from 1 direction to get the rope
3 Baboon came from 1 direction
3 is waiting from 1 direction to get the rope
4 Baboon started to cross from 1 direction
2 Baboon came from 0 direction
2 is waiting from 0 direction to get the rope
1 Baboon crossed the rope from 1 direction
4 Baboon crossed the rope from 1 direction
2 Baboon started to cross from 0 direction
2 Baboon crossed the rope from 0 direction
3 Baboon started to cross from 1 direction
3 Baboon crossed the rope from 1 direction
```