### Recollecting some things:
- **Compilation**: faster execution , but no platform independence
- **Interpretation**: platform independence, but  slower execution speed.

- Here in Java, it uses best of both the worlds, i.e it uses compilation and interpretation to achieve platform independence without compromising on speed.

### About platform independence in JAVA:
- Source_code -> java_compiler -> byte_code -> JVM -> results
- So JVM mimics the role of an interpreter, and so it also has to be installed specific to the platform.

	Eg:
		 source_code [Hello.java]
		 compilation [javac Hello.java]
		 Java_byte_code [Hello.class]
		 Interpretation [java Hello]

- On call to "java Hello" and interpreter gets loaded into the memory first which then loads the Hello.class.
- Note: The interpreter is platform dependent, but the Java-Byte code is platform independent


### About speed in JAVA:
- Byte-code interpretation is faster because byte-code is compact, compiled and optimized.
- compact, as good as machine code
- compiled, so syntax and semantics check is already taken care of.
- Java also uses Just-in-Time[JIT] compilation.
- Compactness of byte allows quick transfer across networks

### JVM:
- It is an abstract computing machine. i.e like  a real computing machine it has an instruction which it executes. Instruction set, here, is Java byte-code 
- Like a real computing machine, JVM manipulates the memory at runtime. Runtime, here, is the time the program starts executing.
- Core responsibilities of JVM include, loading & interpretating byte-code, security, automatic memory management.

### JIT compilation:
- As the bytecode is interpreted, JVM monitors frequency of each piece of executed bytecode and some of the code is more frequently executed called the "hotspots". These hotspots are given to a subcomponent of JVM called JIT compiler.
- JIT compiler converts these hotspots to machine-code and this machine code is then cached, i.e it is saved in memory. In future the cached machine-code is directly executed resulting in much faster performance and rest of the code is still interpreted by Java interpreter. So JIT compilation is also called as dynamic compilation