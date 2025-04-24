# Coal-labs
-------**LAB 1***---------
Question 1:

Describe the function of each:
•	Accumulator Register (A, AX, EAX, RAX)
•	Base Register (B, BX, EBX, RBX)
•	Count Register (C, CX, ECX, RCX)
•	Data Register (D, DX, EDX, RDX)
Function of Each Register:
Accumulator Register (A, AX, EAX, RAX)
•	Used for arithmetic and logic operations.
•	Stores results of calculations.
•	Often used for multiplication and division.
Base Register (B, BX, EBX, RBX)
•	Used to store base addresses for memory access.
•	Can also hold data like other general-purpose registers.
Count Register (C, CX, ECX, RCX)
•	Used in loops and string operations.
•	Stores loop count in iterative processes.
Data Register (D, DX, EDX, RDX)
•	Used in multiplication and division (acts as an extension of AX).
•	Can be used to store I/O port addresses.
Question 2:
Describe the role of index registers in source and destination operations. Provide an example using SI and DI in an assembly instruction
 Role of Index Registers (SI & DI):
Index registers help in handling memory addresses when copying data from one location to another.
Example
MOV SI, 1000h; Source index (points to source address)
MOV DI, 2000h; Destination index (points to destination address)

•	SI (Source Index): Holds the address of the data to be read.
•	DI (Destination Index): Holds the address where data is stored.
Question 3:
 Briefly describe the functions of these bits:
•	Overflow Flag (OF)
•	Zero Flag (ZF)
•	Carry Flag (CF)
Function of Flags:
Overflow Flag (OF)
•	Becomes 1 if a signed operation results in a value too big or too small to fit in the register.
Zero Flag (ZF)
•	Becomes 1 if the result of an operation is zero.
Carry Flag (CF)
•	Becomes 1 if an addition or subtraction generates a carry/borrow beyond the register size.
Question 4:
Write a simple program using MOV, ADD, and SUB instructions:
•	Move values to registers
•	Perform addition and subtraction
•	Store and display results

 Simple Assembly Program:
MOV AX, 5      ; Move 5 into AX
MOV BX, 3      ; Move 3 into BX
ADD AX, BX     ; AX = AX + BX (5 + 3 = 8)
SUB AX, 2      ; AX = AX - 2 (8 - 2 = 6)
•	MOV: Stores values in registers.
•	ADD: Adds two numbers.
•	SUB: Subtracts a number from another.
The final value in AX will be 6.

------***LAB 2***----------
Task 1:
Write an assembly program to print a single character on screen.
Source code:
; display single character
org 100h
.data
.code
main proc
    mov dl,'S'
    mov ah,2h
    INT 21H
    main endp
    end main
Task 2:
Write a program to print your name on screen with characters.
Source Code:
;to display single character
org 100h
.data
.code
main proc   
    mov dl,'s'
     mov ah,2h 
    INT 21H  
     mov dl,'o'
      mov ah,2h 
      INT 21H
      mov dl,'b'
       mov ah,2h 
       INT 21H
       mov dl,'i' 
        mov ah,2h
        INT 21H
        mov dl,'a'
    mov ah,2h
    INT 21H
    main endp
end main
Task 3:
Write a program that input a character from user is in lowercase, the program will convert it to uppercase and will display it on console after conversion.
Source Code:
;to display single character
org 100h
.data
.code
main proc   
    
    mov dl,115
     mov ah,1h
     INT 21H
     mov dl,111
     mov ah,1h
     INT 21H
     mov dl,98
     mov ah,1h
     INT 21H
     mov dl,105
     mov ah,1h
     INT 21H 
     mov dl,97
     mov ah,1h
     INT 21H
      mov dl,115-32
     mov ah,2h
     INT 21H
     mov dl,111-32
     mov ah,2h
     INT 21H
     mov dl,98-32
     mov ah,2h
     INT 21H
     mov dl,105-32
     mov ah,2h
     INT 21H  
     mov dl,97-32
     mov ah,2h
     INT 21H
    main endp
end main

------***LAB 3***-------
TASK 1:
.model samll
.stack 100h
.data
.code
main proc
    mov dl,'6'
    mov ah,2 
    INT 21h  
    mov dl,'0'
    mov ah,2 
    INT 21h
    mov dl,'0'
    mov ah,2 
    INT 21h
    mov dl,'3'
    mov ah,2 
    INT 21h
    mov dl,'2'
    mov ah,2 
    INT 21h 
    mov ah,4ch
    INT 21h  
    main endp
end main
TASK 2:
.model samll
.stack 100h
.data
.code
main proc
mov ah,1h    
INT 21h
SUB al,30h
mov bl,al
mov ah, 1h
INT 21h
SUB al,30h
ADD bl,al
ADD bl,30h
mov dl,bl
mov ah, 2h
INT 21h
mov ah,4ch
main endp
end main

------***LAB 4***-------

TASK 1:

Take a two-digit number and display it in reverse order (e.g., 23 → 32).
Code:
org 100h
.model small
.data
.code
main proc
    MOV AH, 01h
INT 21h
SUB AL, 30h
MOV BL, AL
MOV AH, 01h
INT 21h
SUB AL, 30h
MOV BH, AL
MOV AL, BH
ADD AL, 30h
MOV DL, AL
MOV AH, 02h
INT 21h
MOV AL, BL
ADD AL, 30h
MOV DL, AL
MOV AH, 02h
INT 21h  
end mainp
endmain
TASK 2:
Write a program to input a number from user and display the square of number as output.
Code;
org 100h
.model small
.data
.code
main proc
   
    MOV AH, 1h
    INT 21h
    SUB AL, 30h     
    MOV BL, AL     
    MUL BL          
    ADD AL, 30h
    MOV DL, AL
    MOV AH, 02h
    INT 21h
    MOV AH, 4Ch
    INT 21h

main endp
end main
TASK 3:
Evaluate this expression: 3+5-6
Code:
org 100h
.model small
.data
.code
main proc
    mov bl, 3        
    mov bh, 5       
    add bl, bh       
    mov dl, 6       
    sub bl, dl       
    add bl, 30h      
    mov dl, bl       
    mov ah, 2h      
    int 21h
    mov ah, 4Ch
    int 21h
main endp
end main
TASK4:  
Input two single-digit numbers, store them in registers, swap their values before displaying them.
Code:
MOV AH, 1    
INT 21H      
SUB AL, 30H  
MOV BL, AL   
MOV AH, 1    
INT 21H      
SUB AL, 30H   
MOV BH, AL    

XCHG BL, BH  
ADD BL, 30H  
MOV DL, BL
MOV AH, 2
INT 21H
MOV DL, ' '   
MOV AH, 2
INT 21H
ADD BH, 30H   
MOV DL, BH
MOV AH, 2
INT 21H
MOV AH, 4CH   
INT 21H   
end mainp
endmain
TASK 5:
Write a program to take an ASCII number as an input from user and display the actual number.
Code:
org 100h
.model small
.data
.code
main proc
    mov ah, 1h       
    int 21h           
    add al, 30h       
    mov dl, al       
    mov ah, 2h
    int 21h           
    mov ah, 4Ch
    int 21h
main endp
end main

-----***LAB 5***----
Task 1:
Write a program in assembly language to print your CV or Biodata.
Code:
.model small
.stack 100h

.data
    case db '$'

.code
main proc
    
    mov ax, @data
    mov ds, ax
    mov ah, 01h          
    int 21h              
    sub al, 20h           
    mov dl, al            
    mov ah, 02h           
    int 21h
    mov dl, ' '           
    mov ah, 02h          
    int 21h
    mov ah, 4Ch
    int 21h
       main endp
end main
Task 2:
Write a program that input a character from user and print that again on screen in the given format. The user entered x character.
Code:
.model small
.stack 100h
.data

    CV_data DB 'Name: Sobiya Pir Bakhsh', 0DH, 0AH
            DB 'Age: 20 Years', 0DH, 0AH
            DB 'Degree: BS Software Engineering', 0DH, 0AH  
            DB 'Skills: programming ,develop aichatbot systems', 0DH, 0AH
            DB 'Phone: +923008765833', 0DH, 0AH
            DB 'Address: SAWABI', 0DH, 0AH ,'$'
           
          

.code
main proc
    MOV AX, @data
    MOV DS, AX

    MOV DX, OFFSET CV_data  
    MOV AH, 09H; 
    INT 21H; 

    MOV AH, 4CH  
    INT 21H

main endp
end main

Task 3:
Write a program that input a character from user is in lowercase, the program will convert it to uppercase and will display it on console after conversion. Show messages stored in variable strings to the user. (4) Hint: - The ASCII codes for lowercase letters (a-z) are 97-122. In order to convert a lowercase letter to uppercase letter, just subtract 32 from its ASCII code.     
Code:
.MODEL SMALL
.STACK 100H
.DATA
    msg DB 'Enter a character: $'   
    first DB 13, 10 , '$'        
    output DB 'The user entered: $' 

.CODE
MAIN PROC
    MOV AX, @DATA
    MOV DS, AX
    MOV DX, OFFSET msg
    MOV AH, 09H
    INT 21H
    MOV AH, 01H
    INT 21H
    MOV BL, AL   
    MOV DX, OFFSET first
    MOV AH, 09H
    INT 21H
    MOV DX, OFFSET output
    MOV AH, 09H
    INT 21H
    MOV DL, BL
    MOV AH, 02H
    INT 21H
    MOV AH, 4CH
    INT 21H

MAIN ENDP
END MAIN    

----***LAB 6***----
Task no 1
Code ;
.model small 

.stack 100h 

.data 

.code 

  

main proc 

    mov ah, 01h 

    int 21h            

    sub al, '0'        

    mov bl, al       

    mul bl             ; AL * BL => AX = num^2 (square) 

       add al, '0'       

    mov dl, al         

    mov ah, 02h 

    int 21h 

 mov ah, 4Ch 

    int 21h 

main endp 

end main
Task no 2
Code ;
.model small 

.stack 100h 

.data 

.code 

main proc 

     

    mov ah, 01h 

    int 21h            

    sub al, '4'         

    mov bl, al         

  

    ; Input Height 

    mov ah, 01h 

    int 21h             

    sub al, '5'        

    mov dl, bl         

    mul al             

    mov bx, 2 

    div bx             

    add al, '0'        

    mov dl, al         

    mov ah, 02h 

    int 21h 

    mov ah, 4Ch 

    int 21h 

        main endp 

end main
Task no 3
Code ;
.model small 

.stack 100h 

.data 

.code 

main proc 

    mov ah, 01h 

    int 21h             

    sub al, '0'  

    mov bl, al          

    mov ah, 01h 

    int 21h             

    sub al, '0'        

    mul bl             

    add al, '0'        

    mov dl, al        

    mov ah, 02h 

    int 21h 

    mov ah, 4Ch 

    int 21h 

    main endp 

end main
Task no 4
Code ;
.model small
.stack 100h

.code
main proc
    ; Read number
    mov ah, 01h
    int 21h
    sub al, '0'
    mov bl, al

    ; Calculate cube
    mov al, bl
    mul bl
    mul bl

    ; Print result (handling numbers greater than 9)
    mov cx, ax
    mov ah, 02h
    mov dl, ch
    add dl, '0'
    int 21h
    mov dl, cl
    add dl, '0'
    int 21h

    ; Exit
 mov ah, 4ch
    int 21h
main endp
end main

-----***LAB 7***----
Task 1:
Code:
.model small
.stack 100h

.data

.code
main proc
    
    mov cx, 5      
    mov dx, 49      

label1:
mov ah,2
int 21h
add dx,2
loop label1
mov ah ,4ch
int 21h

main endp
end main 
Task 2:
Code:
.model small
.stack 100h

.data

.code
main proc
    
    mov cx, 5      
    mov dx, 56      

label1:
mov ah,2
int 21h
sub dx,2
loop label1
mov ah ,4ch
int 21h
main endp
end main
Task 3:
Code:
.model small
.stack 100h

.data
    msg db 'The sum is: $'   

.code
main proc
    mov ax, @data
    mov ds, ax

    
    mov ah, 9h
    mov dx, offset msg
    int 21h

   
    mov al, 1
    add al, 2
    add al, 3         

    
    add al, '0'       

    
    mov dl, al
    mov ah, 2h
    int 21h

   
    mov dl, 13
    mov ah, 2h
    int 21h
    mov dl, 10
    int 21h

    
    mov ah, 4Ch
    int 21h
main endp

end main 
Task 4:
Code:
.model small
.stack 100h

.data
    msg db 'Enter a character: $' 

.code
main proc
    mov ax, @data
    mov ds, ax

    mov ah, 9h
    mov dx, offset msg
    int 21h

    
    mov ah, 1h       
    int 21h
    mov bl, al       

    mov cx, 10

print_loop:
  mov dl, bl
 mov ah, 2h
    int 21h
mov dl, 13
    mov ah, 2h
    int 21h
    mov dl, 10
    int 21h

  loop print_loop  
    mov ah, 4Ch
    int 21h
main endp

end main
TASK 5
Source code

  .model small
.stack 100h

.data
.code
main proc
    mov ax, @data     
    mov ds, ax

    mov cl, '9'       

print_loop:
    mov dl, cl       
    mov ah, 02h      
    int 21h

    dec cl            ; Move to previous digit
    cmp cl, '0'-1     ; '
    jg print_loop     ; If not, keep printing

    
    mov dl, 13        
    mov ah, 02h
    int 21h
    mov dl, 10        ; Line Feed
    int 21h

ov ah, 4Ch
    int 21h
main endp

end main
Task 6:
.model small
.stack 100h

.data
    newline db 13, 10, '$'

.code
main:
    mov ax, @data
    mov ds, ax

    mov cl, 'a'         ; ASCII of 'a' = 97

print_loop:
    mov dl, cl          ; Load character into DL
    mov ah, 02h         ; Function to display character
    int 21h

    inc cl              ; Go to next character
    cmp cl, 'z' + 1     ; Check if passed 'z'
    jl print_loop       ; Loop while cl <= 'z'

    ; Print newline
    mov ah, 09h
    mov dx, offset newline
    int 21h

    ; Exit program
    mov ah, 4Ch
    int 21h

end main

----***Lab 8***-----
Task 1:
.model small
.stack 100h

.data
    prompt db "Enter a one-digit positive number (0-9): $"
    msg_even db 13, 10, "The number is even.", 13, 10, '$'
    msg_odd  db 13, 10, "The number is odd.", 13, 10, '$'

.code
main proc
    mov ax, @data
    mov ds, ax

   
    mov dx, offset prompt
    mov ah, 09h
    int 21h

    
    mov ah, 01h
    int 21h        
    sub al, '0'    
    
    
    mov bl, al

    
    and bl, 1
    cmp bl, 0
     je is_even

    
    mov dx, offset msg_odd
    call print_msg
    jmp exit

is_even:
    mov dx, offset msg_even
    call print_msg

exit:
    mov ah, 4Ch
    int 21h

print_msg:
    mov ah, 09h
    int 21h
    ret
        main endp
end main
Task 2:
.model small
.stack 100h

.data
    prompt db "Enter your marks (0-9): $"
    msg_low db 13, 10, "Need Hard Work", 13, 10, '$'
    msg_good db 13, 10, "Satisfactory", 13, 10, '$'

.code
main proc 
    mov ax, @data
    mov ds, ax

    
    mov dx, offset prompt
    mov ah, 09h
    int 21h

    
    mov ah, 01h
    int 21h        
    sub al, '0'    

   
    cmp al, 5
    jl needs_hard_work

    
    mov dx, offset msg_good
    call print_msg
    jmp exit

needs_hard_work:
    mov dx, offset msg_low
    call print_msg

exit:
mov ah, 4Ch
    int 21h

print_msg:
    mov ah, 09h
    int 21h
      
    main endp

end main
TASK 3:
.model small
.stack 100h

.data
    prompt db "Enter a single-digit number (0-9): $"
    msg_zero db 13, 10, "The number is zero.", 13, 10, '$'
    msg_positive db 13, 10, "The number is positive.", 13, 10, '$'

.code
main proc
    mov ax, @data
    mov ds, ax

    mov dx, offset prompt
    mov ah, 9h
    int 21h

   
    mov ah, 1h
    int 21h
    
   
    sub al, '0'       

    
    cmp al, 0
    je is_zero

    mov dx, offset msg_positive
    call print_msg
    jmp exit

is_zero:
    mov dx, offset msg_zero
call print_msg

exit:
    mov ah, 4Ch  
    int 21h


print_msg:
    mov ah, 9h
    int 21h
    ret
    main endp

end main
TASK 4:
.model small
.stack 100h

.data
    msg_gt db "A is greater than B", 13, 10, '$'
    msg_lt db "A is less than B", 13, 10, '$'
    msg_eq db "A is equal to B", 13, 10, '$'

.code
main:
    mov ax, @data
    mov ds, ax

    ; Set values for A and B
    mov al, 30       ; A = 30
    mov bl, 25       ; B = 25

    ; Compare A and B
    cmp al, bl       ; Compare A with B
    ja a_greater     ; Jump if A > B (unsigned)
    jb a_less        ; Jump if A < B (unsigned)
    je a_equal       ; Jump if A == B

a_greater:
    mov dx, offset msg_gt
    call print_msg
    jmp end_program

a_less:
    mov dx, offset msg_lt
    call print_msg
    jmp end_program

a_equal:
    mov dx, offset msg_eq
call print_msg

end_program:
    mov ah, 4Ch      ; DOS exit function
    int 21h

; Procedure to print message at DX using int 21h
print_msg:
    mov ah, 09h      ; DOS print string
    int 21h
    ret

end main

---***Lab 9***----
Task 1:
.model small
.stack 100h

.data
    arr db 'H', 'e', 'l', 'l', 'o'   
    msg db 13,10, 'Character Array: $' 
    newline db 13,10, '$'             

.code
Main proc
    mov ax, @data
    mov ds, ax

    mov dx, offset msg          
    mov ah, 09h
    int 21h                     ; Display the message

    mov si, 0                   ; SI = 0 (index for array)

print_loop:
    mov al, arr[si]             
    mov dl, al                  
    mov ah, 02h
    int 21h                     ; Display the character in DL

    inc si                      ; Increment the index
    cmp si, 5                   ; Check if we have displayed all 5 characters
    jl print_loop               ; If not, continue looping

    ; Print newline after array
    mov dx, offset newline
    mov ah, 09h
    int 21h

    ; Exit program
    mov ah, 4ch
    int 21h

end main
TASK 2:
CODE:
.model small
.stack 100h

.data
    arr db 5 dup('#')  
    msg db 13,10, 'Array of "#" characters: $' 

.code
Main proc
    mov ax, @data
    mov ds, ax

    ; Display the message before printing the array
    mov dx, offset msg
    mov ah, 09h
    int 21h

    mov si, 0                   

print_loop:
    mov al, arr[si]             ; Load current character from array into AL
    mov dl, al                 
    mov ah, 02h
    int 21h                     ; Display the character in DL

    inc si                      ; Increment the index
    cmp si, 5                  
    jl print_loop              

    ; Print newline after array
    mov dx, offset newline
    mov ah, 09h
    int 21h

    ; Exit program
    mov ah, 4ch
    int 21h

newline db 13,10, '$'          ; Newline for formatting

end main
Task 3:
Code:
.model small
.stack 100h

.data
    arr db 5 dup(?)          
    msg db 13,10, 'Enter 5 characters: $'   
    msg2 db 13,10, 'Entered characters: $'  
    newline db 13,10, '$'     

.code
main:
    mov ax, @data
    mov ds, ax

    
    mov dx, offset msg
    mov ah, 09h
    int 21h

    mov si, 0                 

input_loop:
    
    mov ah, 01h               
    int 21h                   

    mov arr[si], al           

    inc si                   
    cmp si, 5                 
    jl input_loop             

   
    mov dx, offset msg2
    mov ah, 09h
    int 21h

    mov si, 0                 

display_loop:
    mov al, arr[si]           
    mov dl, al                
    mov ah, 02h
    int 21h                   

    inc si                    
    cmp si, 5                 
    jl display_loop          

    
    mov dx, offset newline
    mov ah, 09h
    int 21h

    
    mov ah, 4ch
    int 21h

end main
Task 4:
Code:
.model small
.stack 100h

.data
    arr db '10', '20', '30', '40', '50'      

.code
main:

    mov ax, @data
    mov ds, ax

    
    mov si, offset arr
    mov cx,15          

print:
mov dx,[si]
mov ah,2
int 21h
inc si
loop print
mov ah,4ch
int 21h
end main

----***Lab 10***----
Task 1:
CODE:
.model small
.stack 100h

.data
    arr db 10 dup(?)                
    msg1 db 'Enter digit (0-9): $'
    msg2 db 13,10,'Reversed array: $'
    newline db 13,10,'$'

.code
main proc
    mov ax, @data
    mov ds, ax

    mov si, 0                      


input_loop:
    mov dx, offset msg1
    mov ah, 09h
    int 21h

    mov ah, 01h                    
    int 21h                         
    sub al, '0'                    

    mov arr[si], al               
    mov ah, 0
    push ax                       

    mov dx, offset newline         
    mov ah, 09h
    int 21h

    inc si
    cmp si, 10
    jl input_loop


mov si, 0

pop_loop:
    pop ax
    mov arr[si], al                

    inc si
    cmp si, 10
    jl pop_loop


mov dx, offset msg2
mov ah, 09h
int 21h

mov si, 0

display_loop:
    mov al, arr[si]
    add al, '0'                    
    mov dl, al
    mov ah, 02h
    int 21h                        

    mov dl, ' '                    
    mov ah, 02h
    int 21h

    inc si
    cmp si, 10
    jl display_loop


mov ah, 4ch
int 21h

main endp
end main
Task 2:
Code:
.model small
.stack 100h

.data
    arr db 1, 2, 3, 4, 5          
    msg db 13,10,'Reversed array: $'
    newline db 13,10,'$'

.code
Main proc
    mov ax, @data
    mov ds, ax

   
    mov si, 0
    mov cx, 5

push_loop:
    mov al, arr[si]
    mov ah, 0
    push ax
    inc si
    loop push_loop

   
    mov si, 0
    mov cx, 5

pop_loop:
    pop ax
    mov arr[si], al
    inc si
    loop pop_loop

   
    mov dx, offset msg
    mov ah, 09h
    int 21h

    mov si, 0
    mov cx, 5

display_loop:
    mov al, arr[si]
    add al, '0'          
    mov dl, al
    mov ah, 02h
    int 21h

    mov dl, ' '           
    mov ah, 02h
    int 21h

    inc si
    loop display_loop

    
    mov ah, 4ch
    int 21h

end main
Task 3:
Code:
.model small

.stack 100h   

.data

    prompt db 'Enter a number: $'   
    newline db 13, 10, '$'           
    arr db 10 dup(?)                 

.code

main:

    
    mov ax, @data
    mov ds, ax

    
    mov si, 0               
    mov cx, 10              

input_loop:
    
    mov ah, 09h
    mov dx, offset prompt   
    int 21h

   
    mov ah, 01h
    int 21h  
    sub al, '0'             
    mov [arr + si], al      

    inc si                  
    loop input_loop         

   
    mov si, 0               
    mov cx, 10              

push_loop:
    mov al, [arr + si]     
    push ax                
    inc si                  
    loop push_loop          

    
    mov cx, 10              

pop_and_display:
    pop ax                  
    mov dl, al             
    add dl, '0'             
    mov ah, 02h             
    int 21h                 

    
    mov ah, 09h
    mov dx, offset newline  
    int 21h

    loop pop_and_display    

  
    mov ah, 4Ch
    int 21h

end main
Task 4:
Code:
.model small
.stack 100h

.data
    inputPrompt db 'Enter a number (0-9): $'
    newLine db 13, 10, '$'
    evenMsg db 'Even numbers < 6:', 13, 10, '$'
    numberArray db 10 dup(?)

.code
main proc
    mov ax, @data
    mov ds, ax

    mov cx, 10        
    mov si, 0         

inputLoop:
    mov ah, 09h
    mov dx, offset inputPrompt
    int 21h           

    mov ah, 01h
    int 21h           
    sub al, '0'       
    mov [numberArray + si], al

    mov ah, 0
    mov bl, 2
    div bl           
    cmp ah, 0
    jne notEven

    mov al, [numberArray + si]
    xor ah, ah
    push ax

notEven:
    inc si
    loop inputLoop

    mov ah, 09h
    mov dx, offset evenMsg
    int 21h

    mov cx, 10        
checkStack:
    cmp sp, 100h
    je doneDisplay   

    pop ax
    cmp al, 6
    jae checkStack   

    add al, '0'       
    mov dl, al
    mov ah, 02h
    int 21h

    mov ah, 09h
    mov dx, offset newLine
    int 21h

    loop checkStack

doneDisplay:
    mov ah, 4Ch
    int 21h
main endp
end main




