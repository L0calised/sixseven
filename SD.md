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
