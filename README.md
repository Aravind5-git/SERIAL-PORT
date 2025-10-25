
# Skill assessment - 1 

## AIM
Write an assembly language program in 8051 to find the largest number from a given set of N numbers stored in memory. Display the result in AL register.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM


```
ORG 0000H
iMOV R0, #30H
MOV R1, #05H
MOV A, @R0
INC R0
DEC R1
LOOP: MOV B, @R0
      CJNE A, B, CHECK
      SJMP NEXT
CHECK: JNC NEXT     
       MOV A, B     
NEXT: INC R0
      DJNZ R1, LOOP
MOV P1, A           
HERE: SJMP HERE
END
```

### OUTPUT:

<img width="1919" height="1144" alt="Screenshot 2025-10-24 212854" src="https://github.com/user-attachments/assets/e1ca7cb7-6112-48f4-a372-8db6dafe71a6" />


### RESULT:
Thus the largest number from a given set of N numbers using 8051 KEIL was done and shown the output in AL register.
