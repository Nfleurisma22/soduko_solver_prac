This problem is originally from CodeWars: http://www.codewars.com/kata/did-i-finish-my-sudoku/train/javascript

Write a function done_or_not/DoneOrNot passing a board (list[list_lines]) as parameter. If the board is valid return 'Finished!', otherwise return 'Try again!'

Check tests.js to see a example of what will be passed
 -- These will not work without the testing enviornment, so they wont work

# Sudoku rules: (Goal of the algorithm)

Complete the Sudoku puzzle so that each and every row, column, and region contains the numbers one through nine only once.

## Rows:

http://www.sudokuessentials.com/images/Row.gif

There are 9 rows in a traditional Sudoku puzzle. Every row must contain the numbers 1, 2, 3, 4, 5, 6, 7, 8, and 9. There may not be any duplicate numbers in any row. In other words, there can not be any rows that are identical.

In the illustration the numbers 5, 3, 1, and 2 are the "givens". They can not be changed. The remaining numbers in black are the numbers that you fill in to complete the row.

## Columns:

http://www.sudokuessentials.com/images/Column.gif

There are 9 columns in a traditional Sudoku puzzle. Like the Sudoku rule for rows, every column must also contain the numbers 1, 2, 3, 4, 5, 6, 7, 8, and 9. Again, there may not be any duplicate numbers in any column. Each column will be unique as a result.

In the illustration the numbers 7, 2, and 6 are the "givens". They can not be changed. You fill in the remaining numbers as shown in black to complete the column.

## Regions

http://www.sudokuessentials.com/images/Region.gif

A region is a 3x3 box like the one shown to the left. There are 9 regions in a traditional Sudoku puzzle.

Like the Sudoku requirements for rows and columns, every region must also contain the numbers 1, 2, 3, 4, 5, 6, 7, 8, and 9. Duplicate numbers are not permitted in any region. Each region will differ from the other regions.

In the illustration the numbers 1, 2, and 8 are the "givens". They can not be changed. Fill in the remaining numbers as shown in black to complete the region.

## Valid board example:

http://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Sudoku-by-L2G-20050714_solution.svg/364px-Sudoku-by-L2G-20050714_solution.svg.png

# Suggestions
1. Start by creating the function to check a Row (one array)
2. Next youll need to deal with Columns (they share a index)
3. Finally tackle Regions 
