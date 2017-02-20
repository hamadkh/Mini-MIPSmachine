# Mini-MIPSmachine

Design a simplified version of a MIPS machine and write Verilog programs that describe its structure and simulate its functioning.

Use gate-level modeling for all components unless otherwise specified. The machine should include the following components:

1. General purpose registers (register file): 4 registers, 16-bit long, numbered 0 - 3. Register $0 must contain 0 (read-only). Implemented by D flip-flops with gate-level modeling.
2. Other registers: 16-bit program counter, pipeline registers. Implemented by reg vectors in Verilog.
3. Istruction Memory. Word size: 16 bits, word addressed, size: 1024 bytes. Implemented by reg vectors in Verilog.
4. Data Memory. Word size: 16 bits, byte addressed, size: 1024 bytes. Implemented by reg vectors in Verilog.
5. Data Cache (optional): direct mapped, write-through, 16-bit block size, size: 8 blocks. Any kind of Verilog model accepted.
6. ALU: 16-bit data, 3-bit control. Functions: and, or, add, sub, slt.
7. Control unit: may be implemented by behavioral modeling.
8. Other components necessary to connect the main components: multiplexes and decoders implemented by gate-level modeling.

##Instruction set

##Instruction	Opcode
add	0000
sub	0001
and	0010
or	0011
addi	0100
lw	0101
sw	0110
slt	0111
beq	1000
bne	1001

##Instruction formats:

R-format (add, sub, and, or, slt)

op	rs	rt	rd	unused
4	2	2	2	6
I-format (addi, lw, sw, beq, bne)

op	rs	rt	address / value
4	2	2	8

##Restrictions:

1. Use structural (gate level) modeling for all components except for the program counter, memories, and pipeline registers.
2. Implement a pipelined datapath and control.

###Testing: 
To test the MIPS machine write a simple program that includes arithmetic (add, sub), data transfer (lw, sw) and branch (beq or bne) instructions. Use the addi instruction to introduce numeric constants in your program. For example, this may be a program that sums up 5 consecutive memory words by using a loop and stores the result in a register. Include in your report:

1. The assembly source of the test program with comments explaining the algortihm
2. The machine code (the contents of the memory)
3. Simulation results obtained by running the Verilog program. To monitor the execution of the test program for each instruction display the value at the write data input of the register file. For the branch instructions show results from both decisions (branch taken and branch not taken). Show the PC in the simulation output. For the pipelined processor show results with and without nop's that demonstarte the pipeline hazards.

@hamadkhawaja @cody @heathloader
