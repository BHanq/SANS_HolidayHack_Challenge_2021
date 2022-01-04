# Goal

Understand assembly, last challenge is about reading from a file and writing to stdout 

# Solution 

call openlabel

filename:
db '/var/northpolesecrets.txt',0

openlabel:
mov rax, 2
pop rdi
mov rsi, 0
mov rdx, 0 
syscall

readlabel:
mov rdi, rax
mov rax, 0 
mov rsi, rsp
mov rdx, 1000
syscall

writelabel:
mov rsi, rsp
mov rax,1
mov rdi, 1
mov rdx, 1000
syscall

exitlabel:
mov rax, 60
mov rdi, 0
syscall


