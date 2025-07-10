# Grover-Based Quantum 4x4 Sudoku Solver (Qiskit)

This project implements a Grover's algorithm-based solver for 4x4 Sudoku puzzles using [Qiskit](https://qiskit.org/). It encodes the puzzle as a quantum oracle and uses amplitude amplification to find valid solutions, with no classical measurements or bits in the circuit. Post-processing is handled using a statevector simulation to extract the most probable solution.

---

## Features

-  **Solves 4x4 Sudoku** with quantum Grover search
-  **Purely quantum circuit**: no classical bits or measurements
-  **Reusable gates**: oracle and diffuser are defined with `.to_gate()` for modularity and circuit readability
-  **Post-processing** uses statevector to extract the peak probability assignment (valid solution)

---

## Requirements

- Python 3.7+
- Qiskit

Install via pip:

```bash
pip install qiskit


**Usage**

Run the main script directly:
python quantum_sudoku_solver.py

Example hard-coded Sudoku grid in the script:
grid_example = [
    [1, 0, 3, 4],
    [3, 4, 1, 2],
    [2, 1, 4, 3],
    [4, 3, 2, 0]
]

**Output will show:**

    Binary solution for variable cells

    Reconstructed full grid
