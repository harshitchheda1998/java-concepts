## Class & objects:
- Most fundamental units in an object-oriented Programming
- Helps model real-world scenarios in a natural way
	- Eg: student ---(register)----> course ---(offered by)---> department
- Objects have : State & Behavior
- A Class defines the state and behaviors that its objects can have
- So, all objects are simply instances of its class
- Meaning, classes are like blueprints and objects are its instances.
- In Classes, variables define the state and methods define the behavior, and so, both variables and methods are called members of the class.
- A class apart from variables and methods can have, member classes and members interfaces.
- So a class in general has, variables & methods, member classes(nested classes) & member interfaces.

## Java's Reserved Keywords:
- class, interface, enum, abstract, implements, extends, this, super
- byte, short, char, int, long, float, double, boolean
- break, continue, for, do, while, if, else, new, switch, default, case, goto
- try, catch, final, assert, throw, throws
- package, import
- public, private, protected
- synchronized, instanceof, return, transient, static, void, finally, strictfp, volatile, const, native


## Basic's:
- Comments
		- double slash (//)
				- ignores rest of the line
				- single-line comments or to disable single line of code
		- block quotes ( /* */ )
				- ignore everything between the quotes
				- multi-line comments for detailed code description or disable large areas of code

- Everything is case-sensitive
		- Variable "test" is different from "Test"

- Naming rules:
		- Classes, methods and Variables names:
				- Must start with letter, underscore or $
				- other subsequent characters after it can contain letters, numbers, underscore or $
				- cannot use reserved keywords for naming


### Variables:
- Containers that store objects state information
- They can hold raw data or object references
- All variables have a type associated with them which determines what type of data they can hold
- They also determine what kind of operations can be performed based on the variable type
- The type of the object is determined when the object is created first time and that type cannot be changed thereafter, and so Java is a statically type language.
- We can get compilation error is these cases, as the type checking is occurring at compile type. Hence referred as static-type checking
- Advantages of static-type checking over dynamic-type checking, it allows early detection of mistakes

- Declaration: **<type> <name> [=literal or expression];**
- Declaration statements can appear anywhere in the class

- Reinitialization: **<variable-name> = literal or expression;**

### Static-Type Checking:
- Static typing helps in earlier detection of programming mistakes as it allows 
variable types to be checked at compile time itself. With dynamic type 
checking, majority of type checking is performed at runtime. Due to this there 
are chances for programming mistakes to make their way into runtime 
environment. Let's consider the following example, The code is 
written in Python, which is dynamically typed. 

	 def silly(a): 
	 	if a > 0: 
	 		print 'Hi' 
	 	else: 
	 		print 5 + '3' 

If the method silly is invoked with a value greater than 0, then we are good 
and the string 'Hi' gets printed. However, if 0 or a negative number is passed 
as input, then we get a runtime error as addition operation is applied on a 
numeric & a non-numeric value. This will not happen in Java as the statement 
corresponding print 5 + '3' would give a compilation error.

- Static typing is also helpful during method overloading. With method 
overloading, we can have multiple versions of the same method in the same 
class. For example, the following two methods are named as foo in the same 
class. This is possible because the methods accept different input data, i.e., 
one is accepting an integer as input while the other is accepting character 
data. Without static type checking, method overloading wouldn't be possible.

	void foo(int i) { ... } 
	void foo(char c) {... }

- Maintainability is another advantage. Some people believe that code 
refactoring is tedious in dynamically-typed languages like JavaScript. Note that 
code refactoring means restructuring existing code without changing its 
external behavior

### Variable-Kinds:
- Instance variables
		- declared directly within the body of the class. They are not declared within class 	members such as methods. In other words, they are declared at class level and not at method level
		- Represents object state specific to each object of the class.
		- If not initialized explicitly get a default value.
		- Cannot be reinitialized directly within the class. But can be reinitialized within class members like methods. In other words, they can be reinitialized at method level and not class level.
- Static Variables
		- declared directly within the body of the class with keyword "static".. They are not 		declared within class members such as methods. In other words, they are declared 		at class level and not at method level
		- They are also referred to as Class variables. In other words, the static variable is 				associated with the class and is shared by all objects of the class. "One copy 				per class"
		- If not initialized explicitly get a default value.
		- Cannot be reinitialized directly within the class. But can be reinitialized within class 		members like methods. In other words, they can be reinitialized at method level 			and not class level.
- Local variables
		- Declared within methods. They also include method parameters(They are the ones you see 		in parentheses after the method name). They are temporary and they as long as the 		method is getting executed. So they are not accessible outside method.
		- They don't get default values if not initialized explicitly. Its not necessary that you 		initialize the local variable at the declaration, but it is required to be 		initialized before you start using it;

- Instance variables & static variables are also called as "fields" or "attributes(more 			associated with instance variables)"

Example: basics/DemoVariableKinds.java

Variable Types:
- Primitive
		- 8 Primitive Types
				- boolean
				- Number
						- Integer
						- byte
						- short
						- int
						- long
						- Floating-Point
						- float
						- double
						- Character
						- char
		- Except for boolean rest of the primitives are numeric datatypes(even char, since it is 		internally assigned as an unsigned integer)
		- Java developers designed different Integer Datatypes(byte,short,int,long) to avoid 				memory wastage in resource-constraint devices since variables are nothing but 				containers so we cannot have 1 large container to store a small value.
- Object References.

### Integers
- Whole or fixed-point numbers.
- Java Internally uses "Sign's two complement" for data representation
- Types
		- byte -> bit depth(8) -> value range(-2^7 to {2^7}-1) -> default value(0)
		- short -> bit depth(16) -> value range(-2^15 to {2^15}-1) -> default value(0)
		- int -> bit depth(32) -> value range(-2^31 to {2^31}-1) -> default value(0)
		- long -> bit depth(64) -> value range(-2^63 to {2^63}-1) -> default value(0)

	Examples:
	byte b = 100;
	short s = 1000;
	int i = -10000;
> Here an integer literal is getting assigned. The code will throw compiler error if the value falls outside the range.

	long l = 1000000L;
> Here a long literal is getting assigned. "L" is required if value above integer literal range. "L" can also be in lowercase.

Other Integer Literal Formats:

			int y = 0x41; //hexadecimal { y = 65 (4*16^1 + 1*16^0)}
			int y = 0b01000001; //binary { y = 65 }. "b" can also be in uppercase
			int y = 0101; //octal { y = 65 }
			int y = 1_23_456; // underscores for readability(like commas). Can be only used between digits.
- Underscores can also be used with hexadecimal/octal/binary formats.
- "L" can also be used with hexadecimal/octal/binary formats.

Examples:

	int x=5, y=6; //multiple same datatypes variables can be declared & initialized in a single statement.
	int x, y=6; // If the variable x is at class level, then a default value of 0 gets initialized.
				  // If the variable x is at method level, then x needs to be initialized before use.
	int x = y = 99; // y is first reassigned to 99 and then x to 99

### Floating-point Numbers
- Real Numbers
- Java internally uses "IEEE 754 floating point" scheme for data representation
- Types
		- float -> bit depth(32) -> value range(-3.4E38 to 3.4E38) -> default (0.0f)
		- double -> bit depth(64) -> value range(-1.7E308 to 1.7E308) -> default (0.0d)
			(more precise than float)

Examples:

	float f = 123.4f; // "f" is required. "f" can also be in uppercase
	double d = 123.4d; // "d" is optional. "d" can also be in uppercase
	float e = 1.39e-23f // can also represented using exponential notation

Rules:
- Item 48:
		- Avoid float & double if exact answers are required.
		- float & double are ill-suited for monetary calculations. Instead Use "BigDecimal" class
- floating-point arithmetic is not as fast as integer arithmetic.
- Stick with int or double
		- double's preciseness can be useful like in neural networks.
- Use byte, short, float only if memory saving is important.

### Character
- Single letter characters
- Uses "16-bit unsigned integer" & "UTF-16(16-bit Unicode)" scheme for data representation.
- char -> bit depth(16) -> value range(0 to {2^16}-1) -> default value(\u0000). '\u' is 	unicode escape sequence
- Eg: 'A' -> \u0041 -> 4*16^1 + 1^16^0 -> 65
- We can also perform arithmetic operations on char variables.

Examples:

	char c = 'A'; // character literal should always be in single quotes
	char c = 65; // prints A. Internally char is represented as unsigned integer.
	char c = '\u0041'; // can be used when we want to use certain characters which are not 		available on keyboard like emojis
	char c = 0x41; // hexadecimal notation
	char c = 0b01000001; // binary notation

Example: basics/DemoPrimitives.java

### Boolean Type
- Binary datatypes
- boolean -> bit depth(JVM specific) -> value range(true or false) -> default(false)

Examples:

	boolean result = true;

### Type casting
- Useful when assign variable or literal of one type to variable of another type
		Eg: int <- long or int <- byte
- Only possible between numeric datatypes i.e numeric-to-numeric. Therefore, we cannot cast 	anything to boolean or vice-versa.
- Types
- Implicit Casting
		- Useful when assigning a variable of smaller type to a larger type
			["widening conversion"]
		- Sometimes compiler itself does the implicit casting
		  Eg: int x = 65; -> long y = x;
		- Order of implicit casting:
				
											byte -> short -> int -> long -> float -> double
												  	 char ____|^				
												  			 
- Explicit Casting
		- Useful when assigning a variable of larger type to a smaller type
			["narrowing conversion"]
		- Order of explicit casting:
		
					byte <- short <- int <- long <- float <- double
					^||      ||       |
					 ======>char <____|
			char has unsigned integer range(0 to {2^16}-1) and for short its (-2^15 			to {2^15}-1) so any casting between short <-> char is explicit
				
				  Examples:
				  - long y = 42;
				    int x = (int) y;
				    - Here the cast on the right(in parentheses) should match or be lower than 					the variable type on the left
				    - If we don't specific the cast here, we will get a compile-time error even 			though 42 is well within the range of int. Since, the value 42 gets 			assigned at runtime and not at compile time and so compiler is unaware of 			it.
				  - byte b = 65;
				    char c = (char) b;
				    - Here "widening & narrowing is performed". First byte is converted to int 			and then int is narrowed down to char
				  - char c = 65; 
				    - Here we don't need to cast as 65(int) is getting assigned at compile time 				to char and 65 is well within the range of char. Had it be an expression 			on the right then an explicit casting would have been required.
					Eg: int x = 65;
					    char c = (char) x;
				 - short s = 'A'; //no explicit casting is required as integer value for 'A' get 				assigned at compile time and 65('A') is well within the range of short
				 
- Information loss in Explicit casting:

		Out-of-range assignment
	  					Eg: byte narrowedByte = (byte) 123456; //result is 64
						Since JVM the value is outside of byte range and so JVM discards all the bits 		excluding the lower 8 bits
								
		Truncation
						Eg: Floating-point to integer/char will always truncate.
						int x = (int) 3.14f; // x = 3
						int y = (int) 0.9; // y = 0
						char c = (char) 65.5; // c = 'A'

#### Use-cases for casting:
- Implicit casting
	
				float f1 = 3.133f;
				float f2 = 4.135f;
				go(f1,f2);
		
				go(double d1, double d2){
					......}

- Explicit casting

		double avg = (2 + 3)/2; // 2.0 and not 2.5..which is wrong
			Since we are adding 2 int-literals and then dividing by an int literal
		double avg = (double) (2+3)/2; // 2.5

Example : basics/DemoPrimitiveTypeCasting.java

### Object References

	Student s = new Student();
- Here "Student s" means allocate space for reference variable
- Here "new Student()" means allocate space for new student object in memory
- Finally, memory address of the object is assigned to the reference variable

Where are objects stored?
- All objects live in heap

- Bit depth for object references is JVM specific. Bit depth of object reference might be different on different JVMs. However, bit depth of all objects in a JVM will be same.

- Default value for object reference is null;
- One can face NullPointer exception if tried to invoke some members of a object reference.

### Statements
- Statements are commands to be executed.
- All statements should end with semicolon
- Type of statements
		- Declare a variable [Declaration statement]
		- Change the variable value [Expression statements]
		- Control flow statement
		- Invoke a method
- A Statement generally changes the program state
- A statement generally involves one or more expressions(expressions which get evaluated to a 	single value)

		Eg: int count = x*getCount();
		Here x, getCount(), x* getCount(), count = x* getCount() are all simple/compound 		expressions
- Only Declaration statements can be used at class level. We will get a compile-time error if we 	try using other statement types directly within the class body.
- Other statement types can be part of some methods or constructors or initializer blocks of 	class.

### Arrays
- Array is a data-structure (collection of relatable data)
- Container object that holds fixed values of single type
		- Array is a Java object so will be stored in heap
		- The number of items which the array can store is decided at array creation and cannot 		be changed thereafter
		- Can only store values of a single datatypes
		- An Array can store a collection of primitives or objects references of same type

Creating an Array

		int[] myArray = new int[7]; //Each element by default be 0 as it is an integer Array
		//Initializing the Array
		myArray[0] = 9;
		
		int[] myArray; // null since Array is an object
		int[] myArray = new int[]{1,2,3}; // No need to explicitly define the size. the size is 		automatically inferred from the number of elements used to initialize the array. 	Specifying the size here will lead to compile-time error.
		 
		int[] myArray = {1,2,3};
		int myArray[]; //legal to have square braces with variable name then element type

- length field can be used to get the size of array. `` myArray.length ``
- Accessing outside of array can lead to runtime error.

	Student[] students = new Student[2]; // Array can also store object references. Since each 	element is an object reference the default value for each element will be null;
	//Initializing the Array
	students[0] = new Student();
	//Initializing the Array-element state
	students[0].name = "john";

- Accessing elements in an array is fast, since they follow linear layout for faster random access -> O(1) because they are stored next to each other.
- Searching an element in an array will take linear time -> O(n)

Example: basics/DemoArrays.java

2D array:

- Creating an 2D array

	int[][] myArray = new int[4][2]; // int[rows][cols] ... Array of Array of int. In reality its a 1D array in memory
	// Initializing the Array
	myArray[0][1] = 9;
	 
	int[][] myArray = new int[][]{{1,2}, {3,4}};
	
	int[][] myArray = new int[2][];
	myArray[0] = new int[5];
	myArray[1] = new int[2]; //creates a 2D array with irregular cols. Can be used to 		avoid storing duplicate values in symmetric matrices.

- length field can be used to get the size of array. { myArray.length , myArray[0].length}
- Referencing a 2D array:

	int[] row = myArray[1];

### Methods
- Define the behavior of an object.
- Methods represent self-contained logic which can be used many times.
- Caller invokes a method and provides some input if required by the method. The method computes some result and returns the output back to the caller.
Syntax:

		returnType methodName(type param1, type param2, ...){
			...
			return someValue;
		}
		
- ``type param1,type param2,...`` are called parameters or formal parameters. Parameter can either be primitive or object reference. Value returned by method can also be primitive or object reference

- In Java, methodName together with the parameterList are referred to as "method signature".

- When the caller invokes the method by providing the parameters, those parameters are called as arguments or actual parameters.

- Return types:
		- void
				- Returns Nothing
				- Developers can still use ``return;`` as last statement and is optional to use such a statement.
		- Can be a primitive or Object Reference
				- A Return statement is a must else we can face a compile-time error.
				
Examples:

		int getId(){
			byte x = 5;
			return x; //compatible due to implicit casting
		}
		
		byte getId(){
			int x = 5;
			return (byte)x; //incompatible so explicit casting
		}
		
		//method declaration
		int search(int[] list, int key){
			...
		}
		
		//method invocation
		search(new int[]{5,13,12,1}, 1);
		search({5,13,12,1}, 1); // compile-time error...such kind of array declaration is not allowed in method invocation
		
- Benefits of methods:
		- Avoid code duplicacy
		- Helps with divide and conquer approach
				- Helps in software reusability
				- Clean and readable code
				
- Method Types:
		- Instance methods
				- These are object-level methods and deal with behavior of objects.
				- Invocation: ``objectRef.methodName()``
				- Affect object state
		- Static Methods
				- Keyword "static" is used in method declaration.
				- These are class-level methods and don't deal with objects state.
				- They don't have access to either instance variables or instance methods. Can generate compile time error if tried
				- Can access static variables or other static methods.
				Invocation: ``className.methodName()``

> A Class can have both type of methods.	
				
- Passing Data to methods:
		- Java uses pass-by-Value mechanism to pass data during method invocation.
		- Primitives in memory
				- ``int id = 100; //id stores 3 details (logical name, memory address, value) since its a primitive variable``
		- Object References in memory
				- ``Student s = new Student(); // Here s is simply object reference so it only stores memory address of object created by new Student()``
				- First an object is created by new Student(). and stored at some memory address. Then that memory address is stored stored as the value for the object reference. So here **s** stores 3 details (logical name, memory address, object memory address as value)
		- So when we invoke any method by providing arguments. In reality a copy of the actual variables are passed to the method. So if a primitive is passed as an argument then a copy of the value is passed to the method. Whereas if a object reference is passed as an argument then  a copy of the object memory address is passed to the method	
		
- Method Overloading
		- Multiple versions of a method in same class.
		- same name but different input data or parameter list
		- There should be change in number of parameters or parameter types or both
		- Changing only the return type does not work
		- Both instance & static methods can be overloaded.
		
Examples:

		boolean updateProfile(int newId){}
		boolean updateProfile(int[] newId){}
		boolean updateProfile(int newId, char gender){}
		boolean updateProfile(char gender, int newId){}// flipping of parameters is also valid 
		
		void overload(int i){}
		void overload(byte b){}
		overload(23); // since we are passing an int literal so the method matching the exact requirement will get invoked which is overload(int i)
		byte b = 23;
		overload(b); // since we are passing a byte argument so the method matching the exact requirement will get invoked which is overload(byte i)
		
		void overload(int i){}
		void overload(short s){}
		byte b = 23;
		overload(b); // Since we are passing a byte argument so the method matching the exact requirement will get invoked, if not present the method with the next slightly bigger container will get invoked i.e overload(short s)
		
Invalid Examples:

		void updateProfile(int newId);
		boolean updateProfile(int newId); // compile-time error for duplicate method present
		void updateProfile(int id); // compile-time error for duplicate method present
		static void updateProfile(int newId); // compile-time error for duplicate method present. So simply adding static keyword is also not considered method overloading.
		
- Method varargs(variable-length arguments)
		- This parameter can take variable number of arguments.i.e the count of arguments can either be 0,1, or more
		- This argument has to be the last parameter in the list.
		- Can also be the only parameter in the method
		- Syntax: Three dots following the parameter-type
				- ``foo(boolean flag, int... items)``
		- Invocation:
				- Array: ``foo(true , int[]{1,2,3})``
				- Comma-separated arguments: ``foo(true,1,2,3)``. Here the compiler implicitly converts the list as an array. Which means the varargs in method definition is eventually considered an Array of huge size.
				- Omitted: ``foo(true)``
			- Gives an illusion, that the method is infinitely loaded.
		- Varargs Restrictions:
			- Must be last parameter. So the example ``foo(int... items, boolean flag)`` is illegal
			- Only one varags parameter. So the example ``foo(boolean flag, int.. v1, int... v2)`` is illegal
		- Why varargs can't we use ``foo(boolean flag, int[] items)``?
				Provides clean, simpler and flexible invocation.
					- Flexible: ``foo(true, 1,2,3)``, we can pass coma separated values as well
					- Clean and simple: If we have no more arguments we can simply omit by not passing the last argument.
		- Java uses varargs in ``printf(String  format, Object... args)``
				- ``System.out.printf("DOB:%d/%d/%d", 1,1,1998);``
		- It complete fine to replace the ``static void main(String[] args)`` in the main method with ``static void main(String... args)``.

- Varargs & Method overloading

		foo(boolean flag, int... items);
		foo(boolean flag, int[] items); // compile-time error for duplicate method signatures
		
> If there are bunch of other overloaded methods then method with varargs will be the last one to be matched in preference.

### Constructors
- Runs on method creation
- Mostly used to initialize object's state.
- Syntax: **ClassName(type param1, type param2, ...){...}**
- Like method, a constructor can also have a varargs parameter

Example:

		class Student{
			int id;
			//constructor
			Student(int newId){
				id = newId;
			}
		}
		
		//Constructor Invocation
		Student s = new Student(1001);	

- If we don't define any constructor for a class, then the compiler automatically inserts a constructor without any parameters. Also called a no-args constructor and becomes the default constructor. But if there is a constructor(with 0,1, or more parameters) defined for a class then compiler does not define a constructor for that class.

Example:

		class Student{
			int id;
		}
		
		//Constructor Invocation
		Student s = new Student();//Here compiler automatically inserts a no-args constructor in JAVA-byte code
		
		---------------------
		class Student{
			int id;
			//constructor
			Student(int newId){
				id = newId;
			}
		}
		
		//Constructor Invocation
		Student s = new Student(1001);
		Student s = new Student(); //illegal, since the constructor is not present and compiler does not insert a no-args constructor due to the presence of another constructor.
		
- Constructor Overloading
		- Same overloading rules as methods.
			- Parameter list must be different.
		- Why constructor overloading?
			- To create objects with different capabilities.
- Constructor chaining:
		- Can be implemented using this keyword

Example:

		class User{
			int id;
			String name;
			int salary;
			
			User(int userId , String userName){
				id = userId;
				name = userName;
			}
			User(int userId , String userName, int userSalary){
				this(useriId, userName);
				salary = userSalary;
			}
		}
		
		- Can help in avoiding duplicate code.
		- this keyword restrictions for constructor referencing:
				- Must be the first statement
				- There can only be one-this-per-constructor
				- Cannot use instance variables as  arguments since, they might have yet been initialized
				- There can be no recursive invocation to the same constructor to avoid infinite looping.
				
- Since a constructor does not return anything, we can only use a return statement without any returning value like we use for void

- "this" Reference
	- If an object wants to reference its own members then it can use the **this** reference.
	- Syntax: **this.someVariable** or **this.someMethod()**
	- We can also reference the members directly. Then why use ``this`` reference?
			- Can be used to access the instance variables which get hidden(shadowed) by local variables( when local & instance variables have same name) which could be defined in a method or constructor.
	- Cannot be used within static methods since, 'this' deals with object state.
			
Example:

		class Student{
			int id;
			String name;
			
			void updateProfile(int newId, String name){
				id = newId;
				this.name = name; // Here the local variable name is shadowing the instance variable so, any updation on the variable will lead to local variable getting change. To avoid this we use 'this' reference.
			}
		}

- Example on Reinitializing Object References:
	- When we assign one object reference to another, then a copy of the value which the original object reference holds gets assigned to the new object reference.
Example:

		class Student{
			int id;
			
			Student(int newId){
				id = newId;
			}
		}
		
		Student s1 = new Student(10); // new Student(10) -> memoryAddress: 1000, value = 10
											// s1 -> memoryAddress: 1001, value = 1000(address of 'new Student(10)' object)
		Student s2 = new Student(111); // new Student(111) -> memoryAddress: 1002, value = 111
											// s2 -> memoryAddress: 1003, value = 1002(address of 'new Student(111)' object)
		Student s3 = new Student(200); // new Student(200) -> memoryAddress: 1004, value = 200
											// s3 -> memoryAddress: 1005, value = 1004(address of 'new Student(200)' object)
		s3 = s2;// a copy of s2 is made which hold details -> memoryAddress: 1003, value = 1002(address of 'new Student(111)' object) and the value gets assigned to s3
											// s3 -> memoryAddress: 1005, value = 1002(address of 'new Student(111)' object)
		s2 = s1;// a copy of s1 is made which hold details -> memoryAddress: 1001, value = 1000(address of 'new Student(10)' object) and the value gets assigned to s2
											// s2 -> memoryAddress: 1003, value = 1000(address of 'new Student(10)' object)
											
											
		/* final Result
		 *	memoryAddress				Value
		 *	 1000						new Student(10);
		 *	 1001 -> s1				1000 -> address of new Student(10)
		 *	 1002						new Student(111);
		 *	 1003 -> s2				1000 -> address of new Student(10)
		 *	 1004						new Student(200);
		 *	 1005 -> s3				1002 -> address of new Student(111)
		 *
		 * The object at 1004 is not referenced by anyone(orphaned) and so JAVA's automatic GC cleans up the heap to release the object
		 */									