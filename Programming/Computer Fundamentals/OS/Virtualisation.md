1. Allowing many programs to seemingly run at once is what we call *virtualizing the CPU*
2. Virtualizing memory
3. To implement virtualization of the CPU, and to implement it well, the OS will need both some *low-level machinery* and some *high-level intelligence.* We call the low-level machinery **mechanisms
4. On top of these mechanisms resides some of the intelligence in the OS, in the form of *policies*. Policies are algorithms for making some kind of decision within the OS. For example, given a number of possible programs to run on a CPU, which program should the OS run?

# Process API: 
1. fork(): system call that asks the kernel to duplicate the current process and return diff values to the two resulting processes
	1. Both child and parent process run concurrently
	2. The newly-created process (called the child, in contrast to the creating parent) doesn’t start running at main(), like you might expect (note, the “hello, world” message only got printed out once); rather, it just comes into life as if it had called fork() itself.
2. wait(): wait for a child process to die 
3. exec(): to run a different program from any program . *It does not create a new process; rather, it transforms the currently running program (formerly p3) into a different running program (wc)"

# Limited Direct Execution:
## Restricted Operations:
1. User Mode / Kernel Mode : System calls are used by the user to use kernel
2. Trap Table 