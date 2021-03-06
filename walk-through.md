# Software Walk-through Project
# SE 4560 - Software Testing & Quality Assurance

## Team Members & Roles
* Kshitij Saxena - Leader - Good participation
* Luke Chenevey - Recorder - Good participation
* Grant Ferrell - Team Member - Good participation
* Tihitina Hade - Team Member - Good participation
* Jaxsin Power - Team Member - Good participation

## Faults
- Nand and Nor are defined identically, though they should have different functionality.
    - Lines 157-163 (Nand) and lines 171-177 (Nor) in srcSAXEventDispatchUtilities.hpp.
    - Could be misunderstanding the use of these methods in the software at a larger scope, but in our small scope of the dispatcher folder it seems incorrect.
- Underflow possible with an integer added to a character reference.
    - Possible overflow at line 145 in srcSAXEventDispatchUtilities.hpp.
- Constructor on lines 540-548 in srcSAXEventDispatcher.hpp causes faults, but error is unknown.
- Destructor on lines 549-556 in srcSAXEventDispatcher.hpp causes faults, but error is unknown.

## Inconsistencies
- srcSAXEventDispatcher.hpp, line 119
  - Missing space after closing parenthesis and before starting curly brace in some places.
- srcSAXEventDispatcher.hpp, line 973-977
    - If statements that could be written in one line are written in both one line and multiple lines with curly braces.
- Styling inconsistency in the code. Camel case is mostly used, but there are instances when it is not.
    - In srcSAXEventDispatcher.hpp on line 73 the boolean values are not camel case.
    - In srcSAXEventDispatcher.hpp on line 72 underscores are used for the values instead of camel case.
- Naming inconsistency for classes with some beginning with lower case and other beginning with upper case.
    - For example: in srcSAXEventDispatcher.hpp on line 67.

## Requirements Violations
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
- [Y] Are any containers accessed outside their bounds?
    - There are containers, but everything is within their proper bounds.
- [Y] Are all references through a pointer variable currently allocated?

### Computation Errors
- [Y] Is there any use of integer division with floating point devision is required?
    - No division present.
- [Y] Is there a possibility of overflow or underflow during computation?
    - An integer is added to a character reference which could cause underflow or overflow.
- [Y] Is there a possibility of a divide by zero?
    - No division present.
- [Y] Are the order of operations in computations assumed correctly?
    - No computations beside incrementing variables.

### Comparison Errors
- [Y] Are any = operator used when == is needed?
- [Y] Are comparison operators correct?
- [Y] Are boolean operators and the operands they are used on correct?
- [Y] Are comparisons to floating point numbers handled correctly?
  - No floating point numbers present.

### Control-Flow Errors
- [Y] All loops/recursive will terminate?
    - All loops/recursion terminates. The while loop in srcSAXSingleEventDispatcher.hpp could be problematic if setDispatched() function fails.
- [Y] Are there any off-by-one errors?
- [Y] Are no do-while-statements used?
  - "for(event : events)" contains an unknown operator, could produce unexpected errors.

### Function Errors
- [Y] Are all arguments passed in the correct order?
    - There are no arguments passed in the implementation file (srcSAXEventDispatcher.cpp).
- [Y] Are all by-value parameters never modified?

### I/O Errors
- [Y] Are all inputs to the system validated?
    - No input data sent to the system from the implementation file (srcSAXEventDispatcher.cpp). However, parameters for methods are not validated.
- [Y] Are all opened files are closed?
    - No files are opened in the project.
- [Y] Are end-of-file conditions handled correctly?
    - No files are opened in the project.
- [Y] Are I/O error conditions handled correctly?

### Other Errors
- [Y] Are all constant literals assigned a constant variable?
- [Y] Are returned error codes/states checked and handled correctly?
- [Y] Are all exceptions caught and handled correctly?
- [Y] Are there no uses of using namespace std?