# What is a call stack? 

A call stack is a stack of invoked functions. A data structure that uses the LIFO principle to temporarily store and manage invoked functions. 

# What is a ‘call’?

A function invocation

# How many ‘calls’ can happen at once?

infinite functions at once y'all. what whaaat. 

# What does LIFO mean?

Last in, First Out. The last function that gets pushed into the stack is the first to be popped out, when the function returns. 

# Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

```
Function filling() {
    veganHam();
}

Function bread() {
    filling();
}

Function Sandwhich() {
    bread();
}

sandwhich();
```

# What causes a Stack Overflow?

A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error. 

# What is a ‘reference error’?

A reference error is when you try to use a variable that is not yet declared you get this type of error: Uncaught ReferenceError: variable is not defined. 

# What is a ‘syntax error’?

Syntax errors occur when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse: Uncaught SyntaxError: unexpected token o in JSON at position 1

# What is a ‘range error’?

A range cannot have a negative length and this is when an error would appear for range: Uncaught RangeError: Invalid array length. 

# What is a ‘type error’?

Like the name indicates, these types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable: Uncaught TypeError: Cannot read property 'baz' of undefined. 

# What is a breakpoint?

A breakpoint is an intentional stopping or pausing place in a program, put in place for debugging purposes. It is also sometimes referred to as a pause. 

# What does the word ‘debugger’ do in your code?

The debugger keyword stops the execution of JavaScript, and calls (if available) the debugging function. This has the same function as setting a breakpoint in the debugger. if no debugging is available, the debugger statement has no effect. 