# DEBUGGING

## order of execution 

the order in which scripts are run are important to acknowledge when debugging. 

e.g. 

![order of execution](images/order%20of%20execution.png)
 
 The Javascript interpreter processes one line of code at a time. When a statement needs data from another function, it **stacks** (or piles) the new function on top of the current task. 

 - When  a statement has to call some other code in order to do its job, the new task goes to the top of the pile of things to do. 
 - Once the new task has been performed, the interpreter can go back to the task in hand. 
 - each time a new item is added to the stack, it creates a new execution context. 

 ## hoisting 


**Understanding that these two phases happen helps with understanding a concept called hoisting. You may have seen that you can:**

- Call functions before they have been declared

(if they were created using function declarations - not function expressions)

- Assign a value to a variable that has not yet been declared

This is because any variables and functions within each execution context are created before they are executed.

The preparation phase is often described as taking all of the variables and functions and hoisting them to the top of the execution context. Or you can think of them as having been prepared.

Each execution context also creates its own variab1es object.This object contains detailsof all of the variables, functions, and parameters for that execution context.

## Common Problems 

## Handling Errors 