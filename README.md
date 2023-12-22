# whatis-asyncio
what is async programming and asyncio library

### Concurrency
* Concurrency means executing multiple tasks at the same time but not necessarily simultaneously.

### Parallelism
* Parallelism means that an application splits its tasks up into smaller subtasks which can be processed in parallel, for instance on multiple CPUs at the exact same time.
Parallelism does not require two tasks to exist. It literally physically run parts of tasks OR multiple tasks, at the same time using the multi-core infrastructure of CPU, by assigning one core to each task or sub-task.
 
### diff
Parallelism requires hardware with multiple processing units, essentially. In single-core CPU, you may get concurrency but NOT parallelism. Parallelism is a specific kind of concurrency where tasks are really executed simultaneously.
Parallelism is simultaneous execution of processes on a multiple cores per CPU or multiple CPUs (on a single motherboard) . Concurrency is when Parallelism is achieved on a single core/CPU by using scheduling algorithms that divides the CPU's time (time-slice).

### what is asynchronous programming 
Asynchronous programming is a technique that enables your program to start a potentially long-running task and still be able to be responsive to other events while that task runs, rather than having to wait until that task has finished.

### what is asyncio 
According to Python Docs, “Asyncio is a library to write concurrent code using the async/await syntax using one thread.”
