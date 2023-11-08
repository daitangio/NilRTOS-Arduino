# About assembly
asm instruction is used for the port switch functions, which need to 'swap' two thread stack.
We added comments to make it better to understand.
## How to understand the assembly code
You can use
    make diasm
to generare a '.lss' file to see generated assembly code

## How works asm instruction


gcc asm instruction is divided by colons (:) in 4 parts:

    asm(code : output operand list : input operand list : clobber list);

Explanation:
1. Assembly instruction
2. A list of  output operands, separated by commas
3. A comma separated list of input operands
4. "Clobbered registers"

Example of instruction:

    asm("in %0, %1" : "=r" (value) : "I" (PORTD) : );

The following instruction:

    asm ("" : : : "r18", "r19", "r20", "r21", "r22", "r23", "r24", \
                "r25", "r26", "r27", "r30", "r31");  

ask the compiler to "preserve" register 18-31 with clobbers.

If you are using registers, which had not been passed as operands, you need to inform the compiler about this. The following example will do an atomic increment. It increments an 8-bit value pointed to by a pointer variable in one go, without being interrupted by an interrupt routine or another thread in a multithreaded environment. Note, that we must use a pointer,because the incremented value needs to be stored before interrupts are enabled.

    asm volatile(
        "cli"         "\n\t"
        "ld r24, %a0" "\n\t"
        "inc r24"     "\n\t"
        "st %a0, r24" "\n\t"
        "sei"         "\n\t"
        :
        : "e" (ptr)
        : "r24"
    );

The special clobber "memory" informs the compiler that the assembler code may modify any memory location. It forces the compiler to update all variables for which the contents are currently held in a register before executing the assembler code. And of course, everything has to be reloaded again after this code.

## References: 
https://www.nongnu.org/avr-libc/user-manual/inline_asm.html
http://www.freesoftware.fsf.org/avr-libc/