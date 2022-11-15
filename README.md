# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Program:
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

Developed by: mitta yashaswi

RegisterNumber:  212221230062

*/
## Using NAND:
module comblogic(a,b,c,d,f);

input a,b,c,d;

output F;

wire f1,f2,f3;

assign f1 = (~c&~b&~a);

assign f2 = (~d&~c&~a);

assign f3 = (c&~(~b)&~a);

assign F= f1&~f2&~f3;

endmodule

## Using NOR Gate:
module comblogic(a,b,c,d,f);

input a,b,c,d;

output F;

wire f1,f2,f3,f4;

assign f1 = c&(~b)&a;

assign f2 = d&(~c)&a;

assign f3 = c&(~b)&a;

assign f4 = ~(f1|f2|f3);

not(F,f4);

endmodule

## Output:
## RTL:
![image](https://user-images.githubusercontent.com/94619247/201988622-7905d48f-9db2-444f-aa44-3a8efc0668b0.png)

## Timing Diagram :
![image](https://user-images.githubusercontent.com/94619247/201988673-1a222b29-ccfc-42b8-833d-0d2f509797a6.png)

## Truth Table:
![image](https://user-images.githubusercontent.com/94619247/201988735-7e49c0eb-8244-43fc-b264-49bd0f0be91c.png)

## Program 2:
## RTL:
![image](https://user-images.githubusercontent.com/94619247/201988878-6d3a96b0-d8b8-40ae-b9c0-19aa670be8e6.png)

## Timing Diagram:
![image](https://user-images.githubusercontent.com/94619247/201988930-f1ccd46d-996c-46a2-856a-34dc68ac2e3c.png)

## Truth Table:
![image](https://user-images.githubusercontent.com/94619247/201989080-55980606-860d-4013-998c-744e4e77b71c.png)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
