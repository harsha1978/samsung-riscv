
# Samsung RISC-V Program  

**RISC-V Talent Development Program**, powered by **Samsung Semiconductor India Research (SSIR)** in collaboration with **VLSI System Design (VSD)**.  

## Basic Details  
Name: Harsha G 
College: Vidyavardhaka College of Engineering  
Email: harshaachar55@gmail.com  

## Task 1: RISC-V Toolchain Installation 
- Installation of RISC-V toolchain using the VDI link provided.
- The program demonstrates basic operations in C and their equivalent implementation in RISC-V assembly language.
    
## Task 2: Spike simulation and compiling c prigramming using RISC-V GCC
Spike (RISC-V Instruction Set Architecture Simulator) Spike is an emulator for the RISC-V ISA, often used to simulate and test RISC-V programs. It mimics the behavior of a RISC-V processor, allowing programs to run in a virtualized and controlled environment for development and debugging purposes.
-d Option (Debug Mode) The -d option in Spike activates debug mode. This mode facilitates detailed program execution by enabling step-by-step inspection of the processor's state, including registers and memory, to help diagnose and resolve issues.
Proxy Kernel (pk) The proxy kernel (pk) functions as a lightweight operating system within the RISC-V simulation. It manages system calls and supports the execution of programs in the simulated environment provided by Spike.
RISC-V Assembly Commands addi sp, sp, -16 (Add Immediate): This command subtracts 16 from the current value of the stack pointer (sp), effectively adjusting the stack pointer downwards. lui a0, 0x21 (Load Upper Immediate): This instruction loads the immediate value 0x31, shifted left by 12 bits, into the upper part of register a2.
![task 2 11 - Copy](https://github.com/user-attachments/assets/5720d23d-d326-42ec-8d21-1b737dc09ae1)
![task 2 11](https://github.com/user-attachments/assets/df38dd18-8c0a-491a-a16a-9e4c66cffe90)
Program for printing numbers till n
![task 2 77](https://github.com/user-attachments/assets/d53c9fb3-fb96-4874-871b-0544633ed5ca)
compiling the program
![task 2 55](https://github.com/user-attachments/assets/0c5b51f4-1996-4322-aff5-32927529f101)
![task 2 44](https://github.com/user-attachments/assets/8b70e449-7aaa-431f-bd48-99b8bc54ff8a)

using -Ofast
![task 2 22](https://github.com/user-attachments/assets/cf96fcb9-36d7-4b04-bb65-b966444f9762)






## Task 3: Understanding RISC-V and Its Instruction Formats
# RISC-V Instruction Analysis
what is RISK-V
RISC-V is an open-source Instruction Set Architecture (ISA) rooted in RISC principles, designed to optimize processors for specific applications.
As the fifth generation of RISC-based ISAs, RISC-V offers a flexible, free alternative to proprietary processor technologies.
With its open and license-free nature, RISC-V empowers developers to create customized processors without the burden of licensing fees.
RISC-V’s open-source model fosters innovation and broadens the hardware development ecosystem, making it a compelling choice for modern processor design.

# RISC-V Instruction Formats

This document outlines the six primary instruction formats in the RISC-V architecture: R-format, I-format, S-format, B-format, U-format, and J-format. Each format serves a specific purpose and is structured to handle particular types of operations efficiently.

## 1. R-format (Register-Register Operations)
- **Purpose**: Used for instructions that perform arithmetic and logical operations between two registers.
- **Fields**:
  | **Field**   | **Bits** | **Description**          |
  |-------------|----------|--------------------------|
  | `opcode`    | 7        | Specifies the operation  |
  | `rd`        | 5        | Destination register     |
  | `funct3`    | 3        | Operation subtype        |
  | `rs1`       | 5        | Source register 1        |
  | `rs2`       | 5        | Source register 2        |
  | `funct7`    | 7        | Further specifies the operation |

## 2. I-format (Immediate Operations)
- **Purpose**: Used for operations involving immediate values, such as arithmetic with constants or load instructions.
- **Fields**:
  | **Field**   | **Bits** | **Description**          |
  |-------------|----------|--------------------------|
  | `opcode`    | 7        | Specifies the operation  |
  | `rd`        | 5        | Destination register     |
  | `funct3`    | 3        | Operation subtype        |
  | `rs1`       | 5        | Source register          |
  | `imm`       | 12       | Immediate value          |

## 3. S-format (Store Operations)
- **Purpose**: Used for storing data from a register to memory.
- **Fields**:
  | **Field**   | **Bits** | **Description**          |
  |-------------|----------|--------------------------|
  | `opcode`    | 7        | Specifies the operation  |
  | `imm[4:0]`  | 5        | Immediate value (low bits) |
  | `funct3`    | 3        | Operation subtype        |
  | `rs1`       | 5        | Base address register    |
  | `rs2`       | 5        | Source register          |
  | `imm[11:5]` | 7        | Immediate value (high bits) |

## 4. B-format (Branch Operations)
- **Purpose**: Used for conditional branch instructions, enabling flow control in the program.
- **Fields**:
  | **Field**   | **Bits** | **Description**          |
  |-------------|----------|--------------------------|
  | `opcode`    | 7        | Specifies the operation  |
  | `imm[11]`   | 1        | Immediate value (bit 11) |
  | `imm[4:1]`  | 4        | Immediate value (bits 4:1) |
  | `funct3`    | 3        | Condition subtype        |
  | `rs1`       | 5        | Source register 1        |
  | `rs2`       | 5        | Source register 2        |
  | `imm[10:5]` | 6        | Immediate value (bits 10:5) |
  | `imm[12]`   | 1        | Immediate value (bit 12) |

## 5. U-format (Upper Immediate Operations)
- **Purpose**: Used for instructions that load a 20-bit immediate value into the upper bits of a register.
- **Fields**:
  | **Field**   | **Bits** | **Description**          |
  |-------------|----------|--------------------------|
  | `opcode`    | 7        | Specifies the operation  |
  | `rd`        | 5        | Destination register     |
  | `imm`       | 20       | Immediate value          |

## 6. J-format (Jump Operations)
- **Purpose**: Used for jump instructions, allowing for control flow changes over a large range.
- **Fields**:
  | **Field**   | **Bits** | **Description**          |
  |-------------|----------|--------------------------|
  | `opcode`    | 7        | Specifies the operation  |
  | `rd`        | 5        | Destination register     |
  | `imm[19:12]`| 8        | Immediate value (bits 19:12) |
  | `imm[11]`   | 1        | Immediate value (bit 11) |
  | `imm[10:1]` | 10       | Immediate value (bits 10:1) |
  | `imm[20]`   | 1        | Immediate value (bit 20) |

### Summary
Each format in the RISC-V ISA is designed to optimize specific types of operations while maintaining simplicity and efficiency in decoding. Understanding these formats is essential for working with RISC-V assembly and machine code.


This document provides a detailed breakdown of 15 unique RISC-V instructions extracted from an object file. Each instruction is described in terms of its format, opcode, machine code, and binary representation.
![task 3](https://github.com/user-attachments/assets/23e9c52c-30f9-4c56-938a-f9d13f00ccfd)

| **Instruction** | **Format** | **Opcode** | **Machine Code** | **Binary Representation** |
|------------------|------------|------------|-------------------|--------------------------|
| `lui`           | U-type     | 0110111    | 00021537          | 00000000001000010101000011010011 |
| `addi`          | I-type     | 0010011    | ff010113          | 11111111000000010000000100010011 |
| `li`            | Pseudo     | 0010011    | 00600613          | 00000000011000000000011000010011 |
| `sd`            | S-type     | 0100011    | 00113423          | 00000001000100010011010000100011 |
| `jal`           | J-type     | 1101111    | 340000ef          | 00110100000000000000000011101111 |
| `ld`            | I-type     | 0000011    | 00813083          | 00001000000000010011000010000011 |
| `ret`           | I-type     | 1100111    | 00008067          | 00000000000000001000000001100111 |
| `auipc`         | U-type     | 0010111    | ffff0797          | 11111111111111110000011110010111 |
| `beqz`          | B-type     | 1100011    | 00078863          | 00000000000001111000100001100011 |
| `sub`           | R-type     | 0110011    | 40a60633          | 01000000101001100000011000110011 |
| `jalr`          | I-type     | 1100111    | 1d4000ef          | 00011101010000000000000011101111 |
| `lw`            | I-type     | 0000011    | 00012503          | 00000000000000010010010100000011 |
| `j`             | J-type     | 1101111    | 0c00006f          | 00001100000000000000000001101111 |
| `memset`        | Pseudo     | NA         | 10460613          | 00010000010001100000011000010011 |
| `exit`          | Pseudo     | NA         | 08c0006f          | 00001000110000000000000001101111 |

### Explanation of the Columns:

1. **Instruction**: The name of the RISC-V instruction.
2. **Format**: The instruction format type (U-type, I-type, S-type, etc.).
3. **Opcode**: The opcode of the instruction, which specifies the operation.
4. **Machine Code**: The 32-bit hexadecimal representation of the instruction as it appears in the object file.
5. **Binary Representation**: The equivalent binary representation of the machine code.

This table is helpful for understanding the structure of RISC-V instructions and how they translate into machine-readable formats.

## Task 4: Function simulation of RISC-V core

This guide provides steps to perform a functional simulation of the given RISC-V Core Verilog netlist and testbench, along with details about the differences between Standard RISC-V ISA and Hardcoded ISA.

## Steps to Perform Functional Simulation

### 1. Install Required Tools

In Ubuntu, open the terminal and enter the following commands to install **iverilog** and **GTKWave**:

```bash
$ sudo apt-get update
$ sudo apt-get install iverilog gtkwave
```

### 2. Clone the Repository

To clone the repository and download the netlist files for simulation, use these commands in your terminal:

```bash
$ git clone https://github.com/vinayrayapati/iiitb_rv32i
$ cd iiitb_rv32i
```

### 3. Create Files

Create two files:
- **Verilog file**
- **Testbench file**

### 4. Add Code to Files

Copy the code from the reference GitHub repository and paste it into your Verilog file and testbench file:
- **Verilog file**: `iiitb_rv32i.v`
- **Testbench file**: `iiitb_rv32i_tb.v`

### 5. Run and Simulate the Verilog Code

Use the following commands to compile and simulate the Verilog code:

```bash
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
$ ./iiitb_rv32i
```

### 6. View the Simulation Waveform

To see the simulation waveform in GTKWave, enter the following command:

```bash
$ gtkwave iiitb_rv32i.vcd
```

---

## Differences Between Standard RISC-V ISA and Hardcoded ISA

| Operation            | Standard RISC-V ISA | Hardcoded ISA |
|----------------------|---------------------|---------------|
| **ADD R6, R2, R1**  | `32'h00110333`      | `32'h02208300` |
| **SUB R7, R1, R2**  | `32'h402083b3`      | `32'h02209380` |
| **AND R8, R1, R3**  | `32'h0030f433`      | `32'h0230a400` |
| **OR R9, R2, R5**   | `32'h005164b3`      | `32'h02513480` |
| **XOR R10, R1, R4** | `32'h0040c533`      | `32'h0240c500` |
| **SLT R1, R2, R4**  | `32'h0045a0b3`      | `32'h02415580` |
| **ADDI R12, R4, 5** | `32'h004120b3`      | `32'h00520600` |
| **BEQ R0, R0, 15**  | `32'h00000f63`      | `32'h00f00002` |
| **SW R3, R1, 2**    | `32'h0030a123`      | `32'h00209181` |
| **LW R13, R1, 2**   | `32'h0020a683`      | `32'h00208681` |
| **SRL R16, R14, R2**| `32'h0030a123`      | `32'h00271803` |
| **SLL R15, R1, R2** | `32'h002097b3`      | `32'h00208783` |

---

## Analyzing the Output Waveform

The following instructions and their corresponding operations can be analyzed in the simulation waveform:

1. **Instruction 1: ADD R6, R2, R1**
   ![add](https://github.com/user-attachments/assets/aa0c0afc-25c8-4c29-b83c-5e185e095266)


2. **Instruction 2: AND R8, R1, R3**
   ![and](https://github.com/user-attachments/assets/6f14b1bc-d90d-454d-9b20-9c0547b65f02)


3. **Instruction 3: OR R9, R2, R5**
   ![OR](https://github.com/user-attachments/assets/2c8874ef-f96f-4ba8-ad21-a747474680d3)


4. **Instruction 4: XOR R10, R1, R4**
   ![XOR](https://github.com/user-attachments/assets/54fb9836-e334-4241-9074-3588bd05e8d0)


5. **Instruction 5: SLT R1, R2, R4**
  ![SLT](https://github.com/user-attachments/assets/9e0b2bad-a955-4134-bf92-f5cdf7e544a7)
`

6. **Instruction 6: ADDI R12, R4, 5**
   ![addi](https://github.com/user-attachments/assets/dcefb714-63ce-463e-8421-8c68c530f29e)


7. **Instruction 7: BEQ R0, R0, 15**
   ![BEQ](https://github.com/user-attachments/assets/dc461c33-c9ab-4c97-b0b2-24f30ece0edd)


8. **Instruction 8: BNE R0, R1, 20**
   ![BEN](https://github.com/user-attachments/assets/0e2c1477-78e7-404c-b414-38a847297b8e)


9. **Instruction 9: SLL R15, R1, R2**
    ![SLL](https://github.com/user-attachments/assets/d7105589-a852-4e2c-9214-b46d5190bf13)


10. **Instruction 10: SUB R7, R1, R2**
    ![SUB](https://github.com/user-attachments/assets/32d06791-14d2-4a14-9f69-40cedd71cd63)
    


