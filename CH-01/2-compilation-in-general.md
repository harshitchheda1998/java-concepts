### Machine Language (machine code) (native code):
- Computer understands instructions.
- Instructions comprise of 0's & 1's
- Programs comprise of set of instructions which machine can understand
- Very difficult for programs to develop programs in machine language.

### Assembly Language:
- Provides certain higher levels notations to write instructions.
- Assemblers help to convert assembly language to machine language.

### High-Level Language:
- Machine language & Assembly language are called low-level languages since they deal with details like memory location.
- Programmers wanted to develop a program in a more easier way which also hides the low-level details.
- Use English-like words , mathematical notations and punctuation.
- Programming languages like C, C++, Java, C#
- Source code is the term which is used for code which is expressed in programming language
- The machine code is the executed by CPU of the machine for produce the results.


### Compilation:
- Compilers convert source code to target language. The target language can be machine code, or byte code or another programming language.
- verifies the syntax and semantics of source code.
- Performs some code optimization for faster execution.
- Generates machine code from intermediate optimized code.
- Flow : source_code -> compiler -> machine_code -> CPU -> results


### Interpreter:
- Flow : source_code -> interpreter -> results
- There is direct executes the source code to produce the results.
- While in compilation, CPU converts machine code into results, whereas in interpretation the interpreter converts source code into results.
	- Note: Interpreter is also a program that needs to be ran to produce the results.
- So, interpreter is a virtual machine which simulates a CPU
- Interpreter works the same way the CPU executes the instructions by using the fetch-and-execute cycle the catch being the instructions here are source code statements.

### Compilation steps:
    CPU <-------- *fetch instruction* ---------- Memory <---- * 010101...* --------- HardDisk(program) 
    | ^               			      | ^
    | |                                           | |
    | |_________ *fetch instr data* ______________| |
    |__________ *return result* ____________________|

- Program gets loaded in the memory as instructions
- CPU fetches the instruction from the memory
- CPU also fetches the data required by that particular instruction
- CPU executes and stores the result data back to memory
- The cycle continues till all the instructions are executed.


### Interpretation steps:
- Fetches the next program step from source code
- understands what other things are necessary to carry out the statement
- The above two steps are same as what we do in compilation
- The next step is executing the program step. Here, interpreter maintains a library of "pre-compiled machine code". So while executing, the interpreter executes the appropriate pre-compiled machine code that corresponds to the program statement. So the interpreter is not generating a machine code, but it simply uses its own pre-compiled machine to accomplish what the source code directs.

- So interpreter helps to achieve platform independence. The prerequisites being, that the interpreter specific to the platform should be present on the machine and the same source code can be executed on any of the platform.

To Sum up, the advantages of interpreter are:
- Platform independence
- No compilation step needed.
- Code is easier to update, if some issue occurs

The disadvantages being:
- Slower than compilation in orders  of magnitude because of costly memory access operation, while in compilation this gets handled by using registers which results in code which runs very fast.
- Source code has to be reinterpreted every single time it is ran
- Interpreter being a program as well has to be loaded in the memory along with source code.