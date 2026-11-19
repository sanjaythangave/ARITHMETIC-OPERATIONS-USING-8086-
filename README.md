# ARITHMETIC-OPERATIONS-USING-8086
## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI, 2000H        
    MOV AX, [SI]         
    MOV BX, [SI+02H]     
    MOV CL, 00H          
    ADD AX, BX           
    JNC L1               
    INC CL               
L1:
    MOV [SI+04H], AX     
    MOV [SI+06H], CL     
    MOV AH, 4CH          
    INT 21H
CODE ENDS
END START
END
```

#### Output Table

| INPUT MEMORY LOCATION | INPUT DATA | OUTPUT MEMORY LOCATION | OUTPUT DATA |
| -------------|---------- | -------------|----------- |
|        2000 | FF          |    2004| FE               |
|        2001 | FF          |    2005 |FF               |
|        2002 | FF          |    2006| 01               |
|        2003 | FF          |                         |


#### Manual Calculations

<img width="1196" height="940" alt="image" src="https://github.com/user-attachments/assets/832af7bf-f982-46e8-86d1-1a605b6fbd8d" />


---

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="628" height="265" alt="Screenshot 2026-10-10 142120" src="https://github.com/user-attachments/assets/b4589a79-731b-4629-8662-28a176056bad" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI, 2000H        
    MOV AX, [SI]         
    MOV BX, [SI+02H]     
    MOV CL, 00H          
    SUB AX, BX           
    JNC L1               
    INC CL               
L1:
    MOV [SI+04H], AX     
    MOV [SI+06H], CL     
    MOV AH, 4CH          
    INT 21H
CODE ENDS
END START
END
```


#### Output Table

| INPUT MEMORY LOCATION | INPUT DATA | OUTPUT MEMORY LOCATION | OUTPUT DATA |
| -------------|---------- | -------------|----------- |
|        2000 | 22          |    2004| 11               |
|        2001 | 22          |    2005 |11               |
|        2002 | 11          |    2006| 00               |
|        2003 | 11          |                         |

#### Manual Calculations

<img width="1280" height="674" alt="image" src="https://github.com/user-attachments/assets/6435610f-e5f3-4ca1-a049-d04d6d155594" />


---


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="648" height="262" alt="Screenshot 2026-10-12 084639" src="https://github.com/user-attachments/assets/50fb56c6-2312-448e-8385-689767f55e02" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI,2000H
    MOV DX,0000H
    MOV AX,[SI]
    MOV BX,[SI+02H]
    MUL BX
    MOV [SI+04H],AX
    MOV [SI+06H],DX
    MOV AH,4CH
    INT 21H
CODE ENDS
END START
```

#### Output Table


| INPUT MEMORY LOCATION | INPUT DATA | OUTPUT MEMORY LOCATION | OUTPUT DATA |
| -------------|---------- | -------------|----------- |
|        2000 | FF          |    2004| 01               |
|        2001 | 44          |    2005 |76               |
|        2002 | FF          |    2006| 98               |
|        2003 | 44          |    2007|12                     |


#### Manual Calculations

<img width="1280" height="590" alt="image" src="https://github.com/user-attachments/assets/22526981-c96f-4d2a-b848-4b2bdc5aca57" />


---

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="622" height="252" alt="Screenshot 2026-10-12 085727" src="https://github.com/user-attachments/assets/7c991ff1-f62c-442b-8a4f-94bbf4b12c25" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
START:
    MOV AX, CODE
    MOV DS, AX
    MOV SI,2000H
    MOV DX,0000H        
    MOV AX,[SI]         
    MOV BX,[SI+02H]     
    DIV BX              
    MOV [SI+04H],AX     
    MOV [SI+06H],DX     
    INT 3               
CODE ENDS
END START
END
```

#### Output Table

| INPUT MEMORY LOCATION | INPUT DATA | OUTPUT MEMORY LOCATION | OUTPUT DATA |
| -------------|---------- | -------------|----------- |
|        2000 | 44          |    2004| 02               |
|        2001 | 00          |    2005 |00              |
|        2002 | 22          |    2006| 00               |
|        2003 | 00          |    2007|00                     |

#### Manual Calculations

<img width="1280" height="590" alt="image" src="https://github.com/user-attachments/assets/ad7d0574-ed5e-4aba-b315-1da760880cd5" />


---
## OUTPUT FROM MASM SOFTWARE
<img width="647" height="371" alt="Screenshot 2026-10-12 090723" src="https://github.com/user-attachments/assets/9249de76-a7f9-438e-a79e-7492d8cdbe75" />




## RESULT
Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.


