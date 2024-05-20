- A Java application can communicate with JVM by using ```Runtime``` object.
- ```Runtime``` class is present in ```java.lang``` package and it is a singleton class.
- We can create ```Runtime``` object as : ```Runtime r = Runtime.getRuntime();```
- Once we get ```Runtime``` object, we can call following methods on the object:
	- ```maxMemory()```: It returns number of bytes of maximum memory allocated to the heap
	- ```totalMemory()```: It returns number of bytes of total memory allocated to the heap (initial memory)
	- ```freeMemory```: It returns number of bytes of free memory present in the heap
#### Code example for JVM statistics
```java
public class App {
	public static void main(String[] args) throws Exception {
		Runtime r = Runtime.getRuntime();
		double mb = 1024 * 1024;
		System.out.println("In bytes ===================");
		System.out.printf("Max memory: %s Bytes\n", r.maxMemory());
		System.out.printf("Initial memory: %s Bytes\n", r.totalMemory());
		System.out.printf("Free memory: %s Bytes\n", r.freeMemory());
		System.out.printf("Consumed memory: %s Bytes\n", (r.totalMemory() -r.freeMemory()));
		System.out.println("In megabytes ===================");
		System.out.printf("Max memory: %s MB\n", r.maxMemory() / mb);
		System.out.printf("Initial memory: %s MB\n", r.totalMemory() / mb);
		System.out.printf("Free memory: %s MB\n", r.freeMemory() / mb);
		System.out.printf("Consumed memory: %s MB\n", (r.totalMemory() - r.freeMemory()) / mb);
	}
}
```
#### How to set maximum and minimum heap sizes
- Heap memory is finite memory, but based on our requirements, we can set maximum and minimum heap sizes, i.e, we can increase or decrease the heap size based on our requirements
- We can use following flags with java command:
	- To set maximum heap memory, use the following command: ```java -Xmx512m <ClassName>```. This will set maximum heap size as 512 MB.
	- To set minimum heap memory (the initial memory to start with) , use the following command: ```java -Xms64m <ClassName>```. This will set minimum heap size as 64 MB. This will change output of method ```totalMemory()```
	- Example: ```java -Xmx512m -Xms64m App```
		- Output: 
			```bash 
			In megabytes ===================
			Max memory: 455.5 MB
			Initial memory: 61.5 MB
			Free memory: 60.53984069824219 MB
			Consumed memory: 0.9601593017578125 MB
```
