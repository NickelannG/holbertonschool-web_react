## Task 0. Creating an interface for a student

Copy the following configuration files (provided above) into the task_0 directory: package.json, .eslintrc.js, tsconfig.json, webpack.config.js

Write your code in the js/main.ts file:
- Write an interface named Student that accepts the following elements:
  - firstName: string
  - lastName: string
  - age: number
  - location: string
- Create 2 students variables called student1 and student2 and store them into an array named studentsList
- Using Vanilla Javascript, render a table and for each elements in the array, append a new row to the table
- Each row should contain the first name of the student and the location

Requirements:
- When running, Webpack should return No type errors found.
- Every variable should use TypeScript when possible.