### Hi there 👋

ORG 0000H
UP1:MOV DPTR, #0100H
MOV R5,#11
UP: CLR A
MOVC A,@A+DPTR
MOV P2,A
ACALL DELAY
INC DPTR
DJNZ R5,UP
SJMP UP1

DELAY:MOV R2,#255
M1:MOV R3,#255
M: DJNZ R3,M
DJNZ R2,M1
RET

ORG 0100H
DB 00,25,50,75,100,125,150,175,200,225,250
END
