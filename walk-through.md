# Software Walk-through Project
# SE 4560 - Software Testing & Quality Assurance

## Team Members & Roles
* Kshitij Saxena - Leader
* Luke Chenevey - Recorder
* Grant Ferrell - Team Member
* Tihitina Hade - Team Member
* Jaxsin Power - Team Member

## Faults
- Nand and Nor are defined identically, though they should have different functionality.
    - Lines 157-163 (Nand) and lines 171-177 (Nor) in srcSAXEventDispatchUtilities.hpp.
    - Could be misunderstanding the use of these methods in the software at a larger scope, but in our small scope of the dispatcher folder it seems incorrect.
- Overflow or underflow possible with an integer added to a character reference.
    - Possible overflow at line 145 in srcSAXEventDispatchUtilities.hpp.
- Constructor on lines 540-548 in srcSAXEventDispatcher.hpp causes faults, but error is unknown.
- Destructor on lines 549-556 in srcSAXEventDispatcher.hpp causes faults, but error is unknown.

## Inconsistencies
- srcSAXEventDispatcher.hpp, line 119
  - Missing space after closing parenthesis and before starting curly brace in some places.
- srcSAXEventDispatcher.hpp, line 938-955
    - Use of ternary operator instead of if/else as used in other areas of the code.
- srcSAXEventDispatcher.hpp, line 973-977
    - If statements that could be written in one line are written in both one line and multiple lines with curly braces.
- Styling inconsistency in the code. Camel case is mostly used, but there are instances when it is not.
    - In srcSAXEventDispatcher.hpp on line 73 the boolean values are not camel case.
    - In srcSAXEventDispatcher.hpp on line 72 underscores are used for the values instead of camel case.

## Requirements Violations
- srcSAXEventDispatcher.hpp, line 22
    - Too much overhead from include statements.
- srcSAXEventDispatcher.hpp, example line 980
    - Methods not documented properly, hard to tell what they do. Violated the "Easy to use framework to execute components" requirement.

## Possible Improvements
- srcSAXEventDispatchUtilities.hpp, line 250
    - Add some more error handling instead of throwing a "something went wrong".
- Fixing style inconsistencies such as adding between parenthesis and curly braces.
- Convert identical if/else statements into a function for reuse (DRY principle).
    - For example: lines 964 and 973.
- Delete unneccesary comments.
    - In srcSAXEventDispatcher.hpp on line 312.
- Add comments to the software to explain what exactly is going on.
    - Comments are used for some more complex functions, but their use is not frequent.
- More error handling should be implemented, there is not much here.
- Remove comments of deprecated code.
    - For example: in srcSAXEventDispatcher.hpp on lines 849-857.

## Source-code Walk-through Checklist

### Data Reference Errors
- [X] Are any containers accessed outside their bounds?
    - There are containers, but everything is within their proper bounds.
- [X] Are all references through a pointer variable currently allocated?

### Computation Errors
- [X] Is there any use of integer division with floating point devision is required?
    - No division present.
- [X] Is there a possibility of overflow or underflow during computation?
    - An integer is added to a character reference which could cause underflow or overflow.
- [X] Is there a possibility of a divide by zero?
    - No division present.
- [X] Are the order of operations in computations assumed correctly?
    - No computations beside incrementing variables.

### Comparison Errors
- [X] Are any = operator used when == is needed?
- [X] Are comparison operators correct?
- [X] Are boolean operators and the operands they are used on correct?
- [X] Are comparisons to floating point numbers handled correctly?
    - No floating point numbers present.

### Control-Flow Errors
- [X] All loops/recursive will terminate?
    - All loops/recursion terminates. The while loop in srcSAXSingleEventDispatcher.hpp could be problematic if setDispatched() function fails.
- [X] Are there any off-by-one errors?
- [X] Are no do-while-statements used?
- "for(event : events)" contains an unknown operator, could produce unexpected errors.

### Function Errors
- [X] Are all arguments passed in the correct order?
    - There are no arguments passed in the implementation file (srcSAXEventDispatcher.cpp).
- [X] Are all by-value parameters never modified?

### I/O Errors
- [X] Are all inputs to the system validated?
    - No input data sent to the system from the implementation file (srcSAXEventDispatcher.cpp). However, parameters for methods are not validated.
- [X] Are all opened files are closed?
    - No files are opened in the project.
- [X] Are end-of-file conditions handled correctly?
    - No files are opened in the project.
- [X] Are I/O error conditions handled correctly?

### Other Errors
- [X] Are all constant literals assigned a constant variable?
- [X] Are returned error codes/states checked and handled correctly?
- [X] Are all exceptions caught and handled correctly?
- [X] Are there no uses of using namespace std?