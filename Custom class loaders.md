#### Need of customized class loaders
- Default class loaders will load .class file only once, even though we are using it multiple times in our program
- After loading .class file, if it is modified outside, then default class loader won't load updated version of .class file (Because .class file already available in method area)
- We can resolve this problem by defining our own customized class loader
- The main advantage of customized class loader is we can control class loading mechanism based on our requirement
- Example: We can load .class file separately every time so that updated version is available to our program
#### How to define customized class loaders
```java
public class CustClassLoader extends ClassLoader {
	@Override
	public Class loadClass(String className) throws ClassNotFoundException {
		// check for updates & load updated .class file and 
		// return corresponding class
	}
}

class Client {
	public static void main(String[] args) {
		Dog d = new Dog(); // loaded using default classloader
		CustClassLoader cl = new CustClassLoader();
		cl.loadClass("Dog"); // loaded using customized class loader
		// more code
	}
}
```
- We can define our own customized class loader by extending ```java.lang.ClassLoader``` class
- While developing web servers and application servers, usually we can go for customized class loaders to customize class loading mechanism
- What is the need of ```ClassLoader``` class? We can use ```java.lang.ClassLoader``` to define our own class loaders
- Every class loader should be child class of ```java.lang.ClassLoader``` class either directly or indirectly. Hence this class acts as base class for all customized class loaders