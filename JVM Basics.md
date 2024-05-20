#### Virtual machines
- A virtual machine is a software simulation of a machine that can perform operations like a physical machine
- There are two types of virtual machines:
	- **Hardware based/System based** 
		- It provides several logical systems on the same computer with strong isolation from each other, that is, on one physical machine we are defining multiple logical machines. 
		- The main advantage of hardware based virtual machines is hardware resource sharing and improves utilization of hardware resources. Examples: KVM (Kernel Based Virtual Machine for Linux systems), VMWare, Xen, Cloud computing
	- **Application based/Process based:**
		- These virtual machines act as runtime engines to run a particular programming language application.
		- Example: **JVM (Java Virtual Machine)** acts as runtime engine to run Java based applications
		- Example: **PVM (Parrot Virtual Machine)** acts as runtime engine to run Perl based applications
		- Example: **CLR (Common Language Runtime)** acts as runtime engine to run .NET based applications
#### Java Virtual Machine (JVM)
- JVM is a part of JRE and it is responsible to load and run java class files
- Architecture of JVM : [[Basic JVM architecture.canvas|Basic JVM architecture]]