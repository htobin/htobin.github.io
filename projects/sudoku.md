---
layout: project
type: project
image: images/sudokuPic.jpg
title: Sudoku Solver
permalink: projects/sudokuSolver
# All dates must be YYYY-MM-DD format!
date: 2017-10-15
labels:
  - Java
summary: Sudoku Solver in my second semester of Computer Science
---

<div class="ui small rounded images">
  <img class="ui image" src="../images/sudokuPic.jpg">
</div>
<p>
 &emsp;
  This is a sample of some of the cirriculum we had last semester in ics 211. The point of the assignment was to create a recursive sudoku puzzle solver. This was under the assumption that all sudoku puzzles were solvable. We were given premade puzzles that were confirmed to be solvable. We were also given the checks for determining whether the row, columb, or 3 x 3 box had the number that was being determined.
 </p>
 <p>
 &emsp;
  My contribution to the assignment was to recursively implement an algorithm that uses the number verification functions that were given. The algorithm had to traverse the board, find the correct number, and then keep traversing the board as it went through the numbers. If the algorithm had exhausted all possibilities from 1 to 9 then it does what they call "backtracking" in which the algorithm is able to go back to the previous index and change the value of that index and it progresses through the puzzle until it reaches the last index of the entire puzzle. 
 </p> 
 <p>
&emsp;
  This project was an interesting way to see how recursion works. Recursion to me was such an alien idea until this project. I never really understood what recursion was, nor how it worked. I kind of understood that it involved some kind of method that called itself. I also understood it would continue to call itself, until the "base case" was fulfilled. With this assignment I learned about back tracking, and how recursion could allow you to do so. Since recursion was based on a stack data structure, allowing the stack to go back "down" the stack.
</p>  

<a href="https://github.com/htobin/ManiniProjects2">Check out my early projects!</a>




