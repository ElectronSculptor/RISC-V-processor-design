
# RISC-V Processor Design in Logisim-Evolution

This project is a simple implementation of a RISC-V processor using the Logisim-Evolution software. The design was developed as part of the coursework for the "Architecture des Processeurs" module. It consists of three main stages, each corresponding to different design tasks and functionalities, which were progressively implemented during the lab sessions.

## Authors
- Ismail EL BATTAHI
- Gevorg ISHKHANYAN

## Project Overview

This project focuses on designing a RISC-V processor, starting from basic operations and moving towards implementing more complex instructions and functionalities. The project was broken into three parts:

### 1. **Basic Processor Architecture (TD1)**

In the first stage, the focus was on setting up the basic building blocks of the processor. The tasks included:
- Designing a register bank with 32-bit wide registers compliant with the RISC-V specification.
- Implementing basic register operations such as reading and writing to registers.
- Verifying the behavior through simulations, including adding values to registers and observing changes in the clock cycles.

#### Key Features:
- Register bank with 4 registers (expandable).
- Basic ALU (Arithmetic Logic Unit) operations.
- Functionality of the register bank to support additions using a simple ALU (addition function).

### 2. **Datapath and Control Path Implementation (TD2)**

The second stage focused on building the datapath and control path, enabling the processor to handle different types of instructions, specifically register-to-register instructions. We implemented:
- Support for instruction execution through the control path.
- The ability to handle immediate values.
- Execution of simple arithmetic instructions, such as addition and bitwise OR.

#### Key Features:
- Implemented a control path that decodes instructions and selects appropriate signals.
- Modified datapath to support immediate values for instructions like `ADDI`.
- Support for branch instructions and other logic operations (e.g., OR).

### 3. **Branch Instructions and Memory Integration (TD3)**

In the final stage, we added support for branch instructions and integrated memory handling into the processor. The design included:
- Implementing branch instructions (`BEQ` - Branch if Equal).
- Adding memory instruction handling, including instruction fetching and branching based on conditions.
- Modification of the immediate value generator to support branch instruction execution.
  
#### Key Features:
- Support for branch instructions (using the `BEQ` instruction).
- Integration of the program counter (PC) with branch logic.
- Memory-based instruction fetching and execution.

### Simulations and Testing

Throughout the project, each component and feature was verified using Logisim-Evolution’s simulation tools:
- **TD1:** Simulations confirmed correct behavior of the register bank during addition operations.
- **TD2:** The control and datapath correctly handled register-to-register instructions, as observed during simulation.
- **TD3:** Branch instructions were tested with loops, ensuring the correct increment and condition handling for program counter updates.

### Example Assembly Program

Below is a sample assembly program that was used to verify the branch instruction functionality (`BEQ`) in the third stage:

```assembly
# Initialize registers
ADDI R1, R0, 0     # Initialize R1 to 0 (loop counter)
ADDI R2, R0, 10    # Initialize R2 to 10 (number of iterations)

# Loop
While: 
BNE R1, R2, Exit   # If R1 != R2, exit loop
ADDI R1, R1, 1     # Increment R1
J While            # Jump back to While

Exit:
```

### How to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/<your-github-username>/<your-repository-name>.git
    ```
2. Open the `.circ` files in Logisim-Evolution.
3. Run the simulation in Logisim-Evolution to verify the processor's behavior for various instructions.

### Tools Used

- **Logisim-Evolution:** A digital logic simulator for designing and testing logic circuits.
- **RISC-V Instruction Set Architecture:** A standard open-source instruction set architecture.

### Future Improvements

- Add support for more complex instructions (e.g., multiplication, division).
- Optimize the control path to handle more instruction types.
- Integrate a more complex memory management unit.

---

This project is a great starting point for further exploration of RISC-V architecture and processor design. Feel free to clone, modify, and experiment with the design.

