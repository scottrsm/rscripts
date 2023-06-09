## Solve Sudoku


### Description

The solver is an executable R script called SolveSudoku located in the R subdirectory.

It solves Sudoku puzzles input as CSV files. Each file consists of 9 lines with each field
in a line matching the regex pattern:
    \[1-9\<X\>\]\(\[1-9\<X\>\]\){8}
    Here, \<X\> is one of "", ".", "NA".

The Solver first checks the puzzle for errors. If none are found it outputs a solution to stdout.

### Solution Strategy
No heuristics are used. Instead:

- Use R vectorization as much as possible. 
- Look for empty spaces that have 1 possible solution; fill in the blank; repeat -- no recursion.
- If we have exhausted the simple cases, order the blanks by the number of possibilities
  and then *recurse* starting with the blank with the smallest possibilities.

### Usage 
SolveSudoku [-h] [-v] [-o output_file_name] puzzle_file


### Options

- h -- Help Message.
- v -- Verbose mode: Shows the max level of sub-recursions during solution.
- o -- Place solution in an output file (comma separated).

### Args

- puzzle_file -- The name of a Sudoku Puzzle file.

### R Package Dependence
- Depends on the package(s): optparse. 

### Puzzles

Directory 'puzzles' contains of puzzles of varying difficulties as well as puzzles that are ill-formed which are used for testing.

