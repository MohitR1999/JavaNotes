Class loader subsystem contains following types of class loaders:
1. **Bootrstrap class loader/ Primordial class loader**
	1. Bootstrap class loader is responsible to load core java API classes, that is, the classes present in *rt.jar*. 
	2. The location *jdk/jre/lib/* is called bootstrap classpath. Bootstrap class loader is responsible for loading classes from bootstrap classpath
	3. Bootstrap class loader is available with every JVM
	4. It is implemented in native languages like C/C++ and not implemented in java
2. **Extension class loader**
	1. Extension class loader is the child class of Bootstrap class loader.
	2. Extension class loader is responsible to load classes from extension classpath (*jdk/jre/lib/ext/.jar*)
	3. Extension class loader is implemented in java and the corresponding .class file is **sun.misc.Launcher$ExtClassLoader.class**
3. **Application class loader/System class loader**
	1. Application class loader is the child class of extension class loader
	2. This class loader is responsible to load classes from application class path
	3. It internally uses environment variable classpath
	4. Application class loader is also implemented in java and the corresponding .class file is **sun.misc.Launcher$AppClassLoader.class**