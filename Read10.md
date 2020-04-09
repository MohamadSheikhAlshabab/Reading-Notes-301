# Read-10:
----------

## Call stack:

- A __call stack__ is a mechanism for an interpreter to keep track of its place in a script that calls multiple functions.

 - When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
 - Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
 - When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
 - If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error. 
 
 -----------------
## Understanding the JavaScript call stack:

- The JavaScript engine, is a single-threaded interpreter comprising of a heap and a single call stack.
- The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom.
- It means the call stack is synchronous.
- In Asynchronous JavaScript, we have a callback function, an event loop, and a task queue.
- The callback function is acted upon by the call stack during execution after the call back function has been pushed to the stack by the event loop.
- __LIFO__: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

 - ### What causes a stack overflow?
   - A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point.
   - The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.
- __In summary__:

1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.


--------------

## JavaScript error messages && debugging:

 - __Types of error messages__:
  1. Reference errors:
  2. Syntax errors
  3. Range errors
  4. Type errors
 
- __Debugging__:
 - To debug your JS code, the easiest and maybe the most common way its to simply console.log() the variables you want to check or, by using chrome developer tools, open your page with your JS code (press cmd+o in macOS or Ctrl+o in Windows) and choose your file to debug,
 click the line you wanna debug and refresh your page again (F5).
 
- __Call stack__:
- __Handling errors__:
- __Tools to avoid runtime errors__:
  - quokka to evaluate your code as you typeز
  - eslint to make sure your style guide is consistency
  - TypeScript
 
 - __Conclusion__:
 - Being able to read error messages and practising debugging is one of your biggest weapons has a developer.

_________________

