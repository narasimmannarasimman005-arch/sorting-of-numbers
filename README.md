# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)

```asm
ORG 0000H
LJMP MAIN

ORG 0030H
MAIN:
    MOV R0, #04H
OUTER_LOOP:
    MOV R1, #04H
    MOV R2, #40H
INNER_LOOP:
    MOV A, R2
    MOV R3, A
    INC R3
    
    MOV A, @R2
    MOV B, A
    
    MOV A, R3
    MOV R4, A
    MOV A, @R4
    
    CLR C
    SUBB A, B
    JNC NO_SWAP
    
    MOV A, @R2
    MOV B, A
    MOV A, @R4
    MOV @R2, A
    MOV A, B
    MOV @R4, A
NO_SWAP:
    INC R2
    DJNZ R1, INNER_LOOP
    DJNZ R0, OUTER_LOOP

HERE: SJMP HERE
END




```
## OUTPUT(Ascending order)

<img width="870" height="392" alt="image" src="https://github.com/user-attachments/assets/6fbff8dd-c350-453e-974f-66abe11a1e04" />


---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)

```asm
ORG 0000H
LJMP MAIN

ORG 0030H
MAIN:
    MOV R0, #04H
OUTER_LOOP:
    MOV R1, #04H
    MOV R2, #40H
INNER_LOOP:
    MOV A, R2
    MOV R3, A
    INC R3
    
    MOV A, @R2
    MOV B, A
    
    MOV A, R3
    MOV R4, A
    MOV A, @R4
    
    CLR C
    SUBB A, B
    JC NO_SWAP
    
    MOV A, @R2
    MOV B, A
    MOV A, @R4
    MOV @R2, A
    MOV A, B
    MOV @R4, A
NO_SWAP:
    INC R2
    DJNZ R1, INNER_LOOP
    DJNZ R0, OUTER_LOOP

HERE: SJMP HERE
END




```
## OUTPUT(Descending order)

<img width="877" height="353" alt="image" src="https://github.com/user-attachments/assets/fcf3068d-6f97-406f-81aa-7eea10a703d9" />


---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.

