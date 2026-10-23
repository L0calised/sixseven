Lecture 1
OS??
- resource management
	- physical & logical
- Isolation provider
- Service provider
Functions of OS
- Process management
- Memory management
- File system management

BIOS / UEFI diff?
- firmware
	- embedded in hardware - in Low Level Lang - in ROM
- BIOS -
	- 16 bit
	- max 2TB -storage can access
	- sequentially scanning of hardware
- UEFI 
	- 32-64bit
	- 9.4 ZB - can access
	- parallel scanning of hardware

Linux Boot seq?
- Pre-initialization 
	- press power button - generate address where firmware is
	- platform check - check if everything working - memory/processor - will use cache as RAM 
	- 
- DXE (Driver Execution Env.)
	- initialize cache - for use of RAM
	- load UEFI drivers - load parallelly
	- initialize RAM
- BDS (Boot Device Selection phase )
	- find boot loader to load
	- secure boot - will chcek if its an authentic bootLoader
- TSL phase (Transient System loading )
	- load os - Linux kernel image
	- load initRamFs file
- Runtime phase
	-  decompress image (kernel) 
	- hard disk is not mounted(leaded) and drivers are inside hardDrive - chicken egg problem?
		- FIX - use **initRamFs file** to create a temp env(hard drive like) in RAM
	- 1st process it loads systemD - processId=1
		- adopt orphan precess - has no parent
		- RIPing zombie processes - remoce zombie processes - parent hasent ACKNOWLEDGE the child process has closed
		- Socket activation - each service runs on different sockets- handled by systemD

Ring0 - kernel
Ring1 - OS
Ring2 - device drivers
Ring3 - User space
- least privileges
we run program -> program need to intract with hardware - it changes to kernel mode(privilege mode) and we can no longer control this process 

Application <- user 
MiddleWare
Kernel
Hardware

Lecture 2
System call 
- (when the mode need to be switch for  a process) 
- privilege switch (kernel mode -> user mode)
- system call initiated (write/ read ) 
- system call handler (handles the result)
- strace - record system calls
- https://elixir.bootlin.com/linux/v6.17/source/kernel

monolithic kernel or microkernel?
- monolithic - most modules part of kernel(driver,)->larger size  load at same time - slower
- 
batch os ->  i/o through punch card 

multi-programming / multi-tasking differ?
- programs may of differnet useres
- cpu switch only switch when curent program voluntarily pause  
- multi programs can't excute at a time - single core cpu
- nodeJS
multi-tasking
- programs of same owner 
- time slicing
	- time decided for each task - t
	- t >>  -> it act as  FCFS, so we avoid that
- cloud native os - latest
Artos OS


Lecture 3
PROCESS MANAGEMENT

PCB/TCB (process/task control block) - contains info about a process 
- memory management
- scheduling
- context switching 
- resource allocation
degree of multiprogramming - no. of process in main memory 
CPU bound procssees
I/O bound procssees

JOB scheduler/ LTS (Long term scheduler) - selects which program will load on ram 
MID-term scheduler - if the ram is full then this scheduler will decide which process to remove from ram

context switching?
cpu switching?
- convoy effect - (priority to higher priority tasks) FIX?
	- first come first serve (FCFS)
		- if two process arrive at same time - check burst time - lower pID 
	- shortest job first (SJF)
	- shortest remaining  time first (SRTF)
	- priority scheduling first 
	- Round Robin (RR)
- cpu utilisation?
- turn-around time?
- response time?
- preemptive(allows the system to interrupt a running process and reallocate the CPU to another task) or nonpreemptive process
- ideal time?


LECTURE 4
question?
I/O burst time can be overlapaped - more ten 2 process can be send for i/o at a time
primitive /non-primitive 

cpu ideal time in percentage?
- itle/total * 100
cpu utilisation in percentage
- (total - idle) / total * 100
waiting time?
- extra time taken for a process to run?
average waiting time?
turning around time?
no. of times context swwitcching?
- how many times process switch from one to another

cooperative  process - process that needd another proces to communicate (dependent)
- inter process communicate
- 
independent process

