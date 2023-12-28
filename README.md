# Developed By : Naveen Kumar.T
# Reference No: 23002899

# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

# Procedure:
1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow.

5.End the verilog program using keyword endmodule


## HALF SUBTRACTOR:
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

# Program:
                    module HS(a,b,borrow,diff);
                    input a,b;
                    output borrow,diff;
                    assign borrow=~a&b;
                    assign diff=a^b;
                    endmodule

# RTL Realization:

![291255631-24c991b9-2505-4e57-b23a-bc8d29030589](https://github.com/820NaveenKumar208/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154746066/cdafd3dd-70d4-40b9-85e0-d03eebc546e5)

# Truth Table:

![291255700-bbe4f57d-e237-4d64-8829-d5f1d8eb7259](https://github.com/820NaveenKumar208/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154746066/1c998053-653b-4bef-85b6-c4ee5bf21886)

# Timing Diagram:

![291255810-452cb7d7-303b-4e75-8c5e-9c6d9a074c99](https://github.com/820NaveenKumar208/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154746066/ffa23a65-986b-49e3-a150-3aea2a5e9ce0)

# FULL SUBTRACTOR:
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

# Program:
                 `module FS(a,b,bin,borrow,diff);
                 input a,b,bin;
                 output diff,borrow;
                 assign diff=(a^b)^bin;
                 assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
                 endmodule`


# RTL Realization:
  

![291256368-8a12efe3-c86e-4800-a68f-c70a7befe09e](https://github.com/820NaveenKumar208/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154746066/d57a60a5-f11e-4620-8046-7b999c14e144)

# Truth Table:

![291256384-531e58ee-f0b6-4146-b10e-5116dcf5f12f](https://github.com/820NaveenKumar208/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154746066/a6ec5886-1cc9-4fe5-a483-bf346b147520)





## Timing Diagram :

![291256418-37e4998a-532a-4fd5-9411-3c5447e13330](https://github.com/820NaveenKumar208/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/154746066/87c6bc74-4392-4f12-8444-3bc6205623c9)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
