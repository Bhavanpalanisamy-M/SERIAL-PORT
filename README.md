
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
MOV TH1, #0FDH
MOV SCON, #50H
SETB TR1
MAIN_LOOP:
MOV SBUF, #'B'
WAIT_TI:
JNB TI, WAIT_TI
CLR TI
SJMP MAIN_LOOP
END
```
### (ii) Serial Port to Transfer a Message

```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="BHAVAN";
unsigned char i;
TMOD=0X20; //TIMER 1, MODE 2
TH1=0XFA;
SCON=0X50;
TR1=1;
for(i-0;i<=12;i++)
{
SBUF=msg[i];
while(TI==0);
TI=0;
}
while(1);
}
```

### OUTPUT:
<img width="1401" height="758" alt="Screenshot 2025-10-07 204810" src="https://github.com/user-attachments/assets/7173f6a8-ae6d-4c48-bde9-e948ca26f2cd" />
<img width="1320" height="706" alt="Screenshot 2025-10-07 211334" src="https://github.com/user-attachments/assets/759894a8-0bf4-421d-9b92-1a1de8ce94bb" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
