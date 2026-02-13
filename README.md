# FACTORIAL-OF-A-NUMBER
# FACTORIAL OF A NUMBER USING 8051 (Keil)

## AIM
To write and execute an Assembly language program to perform the factorial of a number using 8051 Keil.

---

## APPARATUS REQUIRED
- Personal computer with Keil software

---

## ALGORITHM
1. **Start**
2. **Input**: Read the number `n`.
3. **Initialize**:
   - Set factorial to `1`.
   - Set `i` to `1`.
4. **Loop**: While `i` is less than or equal to `n`:
   - Multiply factorial by `i`.
   - Increment `i` by `1`.
5. **Output**: Store or print the value of factorial.
6. **End**

---

## FLOWCHART
<img width="506" height="525" alt="image" src="https://github.com/user-attachments/assets/f3b47187-6f0f-490c-8704-f2973cb2b276" />


---

## PROGRAM
```asm
ORG 0000H

        MOV     DPTR, #4500H     ; Point DPTR to input address
        MOVX    A, @DPTR        ; Read number from external memory
        MOV     R0, A           ; Store number in R0

        INC     DPTR            ; Point to output location
        ACALL   FACTORIAL      ; Call factorial subroutine

        MOVX    @DPTR, A        ; Store result in external memory

THIN:   SJMP    THIN            ; Infinite loop
FACTORIAL:
        DEC     R0

        CJNE    R0, #01H, PRODUCT
        SJMP    THICK

PRODUCT:
        MOV     B, R0
        MUL     AB              ; A = A × B
        ACALL   FACTORIAL

THICK:
        RET

END
```
OUTPUT

![WhatsApp Image 2026-02-13 at 11 30 27 AM](https://github.com/user-attachments/assets/e8d3a219-690e-41dd-a7ee-f5223c257b96)


---
MANUAL CALCULATIONS

![WhatsApp Image 2026-02-13 at 9 59 51 PM](https://github.com/user-attachments/assets/e833f892-cf6c-4039-baf9-f8b1b1f33c05)

---

RESULT

Thus, the factorial of a number was calculated and executed successfully using 8051 Keil.

---


