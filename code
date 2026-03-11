[org 0x7C00]
[bits 16]

resetdisk:
    mov ah, 0x00 ; reset function
    mov dl, 0x00 ; drive
    int 0x13     ; disk int
    jc resetdisk

getmem:
    mov bx, 0x0000 ; segment
    mov es, bx
    mov bx, 0x8000 ; offset
    ; es:bx = 0x0000:8000

writedisk:
    mov ah, 0x03 ; write function
    mov al, 0x01 ; sectors
    mov ch, 0x00 ; cylinder
    mov cl, 0x03 ; sector
    mov dh, 0x00 ; head
    mov dl, 0x80 ; drive
    int 0x13     ; disk int

times 510 - ($ - $$) db 0x00
db 0x55, 0xAA

times 8096 db 0xfe
