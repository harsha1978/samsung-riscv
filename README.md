
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
