
# Skill assessment - 2

## AIM
Write an assembly language program in 8051 to generate a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM


```
ORG 0000H
MAIN: MOV TMOD, #10H   
      CLR P0.5         
AGAIN: MOV TH1, #9EH   
        MOV TL1, #58H   
        SETB TR1        
WAIT:   JNB TF1, WAIT  
        CLR TR1         
        CLR TF1         
        CPL P0.5        
        SJMP AGAIN      
END
```

### OUTPUT:

<img width="1919" height="1140" alt="Screenshot 2025-10-24 215455" src="https://github.com/user-attachments/assets/4397b901-520f-4abc-b4af-0c32dd6e319d" />

<img width="1919" height="1141" alt="Screenshot 2025-10-24 215505" src="https://github.com/user-attachments/assets/6e04f850-9c23-4dfe-9337-92c3ef1db6e2" />

### RESULT:
Thus a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously using 8051 KEIL was done and shown the output.
