# MINI-PROJECT-1-SUDOKU-SOLVER-WITH-GROVER-S-ALGORITHM
To solve the 4x4 Sudoku puzzle using Grover's algorithm, we need to implement a quantum circuit that can find a valid solution with high probability. The solution involves encoding the Sudoku grid into qubits, creating an oracle to mark valid solutions, and applying a diffuser to amplify these solutions. Here's a step-by-step explanation and implementation:

    Problem Encoding:

        Represent each cell in the 4x4 Sudoku grid with 2 qubits (since each cell can hold values 1-4).

        Initialize fixed cells to their given values and apply Hadamard gates to variable cells to put them in superposition.

    Oracle Design:

        The oracle marks valid Sudoku solutions by flipping the phase of states that satisfy all Sudoku constraints (rows, columns, and 2x2 boxes must each contain distinct values 1-4).

        For each constraint (row, column, box), use flag qubits to track which values appear. Flip a constraint-violated qubit if any value is missing or duplicated.

        Flip an all_valid qubit if any constraint is violated. Apply a Z-gate to all_valid to mark valid states.

    Diffuser Implementation:

        The diffuser amplifies the amplitude of marked states by applying Hadamard gates, a multi-controlled Z gate (for the |0⟩ state), and Hadamard gates again.
    Grover Iterations:

        Perform the optimal number of Grover iterations (≈ √N, where N is the number of possible states for variable cells) to maximize the probability of measuring a valid solution.
    Measurement:

        Measure the grid qubits to obtain the solution.
