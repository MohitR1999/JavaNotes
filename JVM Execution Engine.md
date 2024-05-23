- This is the central component of JVM
- Execution engine is responsible to execute java class files
- Execution engine mainly contains two components, interpreter and JIT (Just in Time) compiler
#### Interpreter
- It is responsible to read bytecode and interpret into machine code (native code) and execute that machine code line by line
- The problem with interpreter is, it interprets every time even if same method is invoked multiple times, which reduces performance of the system
- To overcome this problem, some people introduced JIT compilers in Java 1.1 version
#### JIT Compiler
- The main purpose of JIT compiler is to improve performance
- Internally JIT compiler maintains a separate count for every method
- Whenever JVM comes across any method call, first that method will be interpreted normally by the interpreter, and JIT compiler increments the corresponding count variable
- This process will be continued for every method.
- Once any method count reaches threshold value, then JIT compiler identifies that method is a repeatedly used method (Hot Spot)
- Immediately JIT compiler compiles that method and generates the corresponding native code
- Next time whenever JVM comes across that method call, then JVM uses native code directly and executes it instead of interpreting once again so that performance of the system will be improved
- The threshold count varies from JVM to JVM
- Some advanced JIT compilers will recompile generated native code if count reaches threshold value second time, so that more optimized machine code will be generated
- Internally, profiler, which is the part of JIT compiler is responsible to identify hot spots
- JVM interprets whole program atleast once
- JIT compilation is applicable only for repeatedly required methods, not for every method
#### Java Native Interface (JNI)
- JNI acts as mediator for java method calls and corresponding native libraries, that is, JNI is responsible to provide information about native libraries to the JVM.
- Native method library provides or holds native libraries' information