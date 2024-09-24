## ENSE 352 - Fundamentals of Computer Systems Architectures - Laboratory

# Lab 2: Control Flow Statements 

### University of Regina
### Faculty of Engineering and Applied Science - Software Systems Engineering

### Lab Instructor: [Trevor Douglas](mailto:trevor.douglas@uregina.ca)

## Objective

The objective of this lab is to introduce the students to ARM assembly using control flow statements and instructions.

## Background

### Program Counter - R15

- The Program Counter is a register that contains the address of the current instruction.
- During normal logical flow the Program Counter increments according to the instructions implemented in order.
- After a branch or subroutine call the Program Counter will contain the “jumped to “ address.
- You are able to access this register from your code by using R15 or PC.


### The Stack

- Remember the stack pointer (R13) points to the top of stack.
- A typical stack is an area of computer memory with a fixed origin and a variable size. 
- A stack pointer, usually in the form of a hardware register, points to the most recently referenced location on the stack
- A stack is used to hold information as your program runs.  
 
 It is also used to:
 - Keep track of where you were during a branch or sub routine call.
 - Pass parameters to subroutines. 
 - Anything you would like saved.

The two operations applicable to all stacks are:
- a push operation, in which a data item is placed at the location pointed to by the stack pointer, and the address in the stack pointer is adjusted by the size of the data item.  Push {R1},  or Push{R1,R2,R3}
- a pop or pull operation: a data item at the current location pointed to by the stack pointer is removed, and the stack pointer is adjusted by the size of the data item. Pop {R1}, or Pop{R1,R2,R3}

### Sample Stack
<table>
  <tr>
    <td> <img src="Stack.png"  alt="Stack" width = 364px height = 432px ></td>
  </tr>
</table>

### Looping example

<details>
<summary>expand loop.s</summary>

in `loop.s`

```assembly

  MOV  R0, #0    ;initialize R0 as our counter

  ;Start of the loop
Start
  
  ; Stuff you may want to do in your loop

  
  ADD   R0, #1      ; Increment the counter
  CMP   R0, #16     ; How many times to loop
  BNE    Start      ; Loop back if not done


  ;What about checking R0 being zero or not zero using the Z flag:


  CBZ	R0, loopZero
  ;; or
  CBNZ	R0, loopNotZero

```
</details>

### Link Register R14 and Subroutines

The link register is used to store the return program counter  when a subroutine or function is called.  To Branch (or call) a subroutine using the Branch and update Link Register.

```assembly
  BL function   ; Branch to a subroutine and place the return address in the Link Register.
                ; The Link Register will contain the address of the code after the Branch
                ; instruction.



function        ; This is the label or name of the subroutine.

  BX LR         ; Branch back to the Link Register address.

```


