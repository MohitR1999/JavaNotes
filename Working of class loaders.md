[[Class loader diagram.canvas|Class loader diagram]]
- Class loader follows **delegation hierarchy** principle
- Whenever JVM comes across a particular class, first it will check whether the corresponding .class file is already loaded or not. If it is already loaded in method area, then JVM will consider that loaded class
- If it is not loaded, then JVM requests class loader subsystem to load the particular class.
- Then class loader subsystem handovers the request to Application class loader
- Application class loader delegates the request to extension class loader
- Extension class loader in turn delegates the request to bootstrap class loader
- Bootstrap class loader will search in bootstrap class path. If it is available, then the corresponding .class file will be loaded by bootstrap class loader. If it is not available, then bootstrap class loader delegates the request to extension class loader.
- Extension class loader will search in extension class path. If it is available, then it will be loaded, otherwise extension class loader delegates the request to application class loader.
- Application class loader will search in application class path. If it is available, then it will be loaded, otherwise we will get runtime exception saying, *NoClassDefFoundError* or *ClassNotFoundException* 