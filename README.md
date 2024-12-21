# FULL_ADDER_SUBTRACTOR
Date:18/10/2024
Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

Write the detailed procedure here

**Program:**
```
/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:Naneshvaran
RegisterNumber:24900972
*/
 
module full_add_sub(sum,cout,a,b,cin);
 output sum;
 output cout;
 input a;
 input b;
 input cin;
 wire W1,W2,W3;
 assign W1=a^b;
 assign W2=a&b;
 assign W3=W1&cin;
 assign sum=W1^cin;
 assign cout=W2|W3;
 endmodule

module Full_sub(a,b,bin,difference,borrow);
input a,b,bin;
output difference,borrow;
assign difference= ( (a ^ b)^bin);
assign borrow= ( ( ~a & b)| ( bin & (~(a ^ b ))));
endmodule

```

**RTL Schematic**
![output04fullas (de)](https://github.com/user-attachments/assets/a6543933-093d-46fa-a3c6-3776628100df)
![Screenshot 2024-12-21 222818](https://github.com/user-attachments/assets/a03ed6c2-a900-4fca-828e-fcf3c5843fc8)

**Output Timing Waveform**
![waveform(04)fullas](https://github.com/user-attachments/assets/bd882857-0b61-45d9-beb8-c55037c48a93)
![Screenshot 2024-12-21 222927](https://github.com/user-attachments/assets/56ab3c37-e531-4504-b415-21a2c8769db1)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



