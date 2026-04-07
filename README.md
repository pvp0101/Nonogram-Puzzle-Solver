# Nonogram Solver

This repository contains a C++ implementation of a terminal-based Nonogram solver. The program uses a state-propagation algorithm to solve puzzles by generating and validating all possible line arrangements based on the given clues.

## Project Background

The project was born out of a passion for Nonogram puzzles. After spending considerable time solving them manually, my friend and I collaborated on identifying the core logical rules that govern the game. We realized that a structured, step-by-step approach could be automated. [cite\_start]This C++ implementation is the result of that process, translating a manual puzzle-solving strategy into a functional terminal application[cite: 61, 63].

## Key Features

  * **State-Propagation Algorithm:** The solver utilizes a state-propagation approach, a type of backtracking-free logic-based solution, to fill the puzzle grid iteratively.
  * [cite\_start]**Object-Oriented Design:** The code is structured using a `NonogramSolver` class and a nested `State` struct, which cleanly encapsulates the puzzle's state, including the grid, clues, and change-detection flags[cite: 63].
  * **Arrangement Generation:** A core component of the solver is a recursive function that generates all possible valid arrangements of black squares for a given row or column based on its clues and the current state of the line.
  * **Common Element Identification:** The program's logic identifies and fills in squares that are consistent across all valid arrangements for a given line, which is the primary mechanism for solving the puzzle.
  * **Extensive Validation:** The solver includes functions to check if a puzzle is fully solved and if all clues have been satisfied, ensuring the final output is correct.

## Technical Details & Implementation Nitpicks

  * **State Representation:** The puzzle grid is represented as a `std::vector<std::vector<int>>` where a cell can be a `-1` (cross), `0` (blank), or `1` (black). The `State` struct holds all the necessary information, including the grid and the row and column clues, making it easy to manage.
  * **Arrangement Generation Logic:** The `generateArrangementsRecursive` function is the heart of the solver's logic. It intelligently prunes invalid arrangements by considering the minimum space needed for remaining clues, preventing brute-force generation and improving performance.
  * **Row/Column Sum Calculation:** The `rowColSum` helper function is a simple but critical optimization. It calculates the minimum length a line must be to accommodate all of its clues, which is used to determine the number of mandatory 'crosses' in a line without any arrangement generation.
  * **Change Detection:** A `booleanChange` flag within the `State` struct is used to detect if any progress was made during an iteration of the main solving loop. If a full pass over all rows and columns results in no changes, the algorithm halts, preventing an infinite loop.
  * **User-Friendly Output:** The `printState` method displays the puzzle's current state in a clear, human-readable format using 'X', '?', and '\#' characters for crosses, unknown, and black squares, respectively.

## Technologies Used

  * [cite\_start]**C++:** The entire project is implemented in C++[cite: 62].
  * [cite\_start]**Object-Oriented Programming (OOP):** The code is designed around classes and structs to model the problem domain effectively[cite: 62, 63].
  * **Backtracking:** The core logic, while iterative, relies on principles of backtracking in its recursive `generateArrangements` function, which systematically explores and validates possible line arrangements.

## Getting Started

### Prerequisites

You will need a C++ compiler (e.g., g++, clang) to compile and run the code.

### Installation and Compilation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/nonogram-solver.git
    cd nonogram-solver
    ```
2.  **Compile the source code:**
    ```bash
    g++ -o nonogram_solver Nonogram_Solver.cpp -std=c++17
    ```

### Usage

1.  **Run the compiled executable:**
    ```bash
    ./nonogram_solver
    ```
2.  The program will attempt to solve the hardcoded 10x10 example puzzle and print the solution if found.

## License

You are free to use this, just credit my LinkedIn in the repository. 

## Contact

If you have any questions or feedback, feel free to reach out:

  * [cite\_start]**Name:** Abhinay Ragam 
  * [cite\_start]**Email:** [abhinayragam@gmail.com](mailto:abhinayragam@gmail.com) 
  * **LinkedIn:** []

-----
