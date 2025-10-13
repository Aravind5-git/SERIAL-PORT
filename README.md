
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B' 
 WAIT:JNB TI, WAIT
 CLR TI 
 END
```
```
#include<reg51.h>
void main(void)
{
TMOD=0X20; //TIMER 1, MODE 2
TH1=0XFA;
SCON=0X50;
TR1=1;
while(1)
{
SBUF='A';
while(TI==0);
T1=0;
}
}
```
### (ii) Serial Port to Transfer a Message
```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ B,AGAIN
END
```
```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="Aravind L S";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<12;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}
```
### OUTPUT:

(i) Serial Port Transfer a Single Character

![WhatsApp Image 2025-10-13 at 22 40 36_8be847ab](https://github.com/user-attachments/assets/0cb20f5c-72c7-43a6-bf94-082be07ebceb)

![WhatsApp Image 2025-10-13 at 22 40 36_e1bbc6cf](https://github.com/user-attachments/assets/c69a4f16-c6e5-4794-a223-974776a4b205)

(ii) Serial Port to Transfer a Message

![WhatsApp Image 2025-10-13 at 22 40 36_924494ee](https://github.com/user-attachments/assets/a0adf0c1-33de-409c-8834-539e25eda911)

![WhatsApp Image 2025-10-13 at 22 40 36_3f913208](https://github.com/user-attachments/assets/58817cc4-e6d1-487d-8d01-7785ee25db49)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
