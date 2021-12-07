# Software Walk-through Project
# SE 4560 - Software Testing & Quality Assurance

## Team Members & Roles
* Kshitij Saxena - Leader
* Luke Chenevey - Recorder
* Grant Ferrell - Team Member
* Tihitina Hade - Team Member
* Jaxsin Power - Team Member

## Faults


## Inconsistencies


## Requirements Violations


## Possible Improvements


## Source-code Walk-through Checklist

### Data Reference Errors
- [ ] Are any containers accessed outside their bounds?
- [ ] Are all references through a pointer variable currently allocated?

### Computation Errors
- [ ] Is there any use of integer division with floating point devision is required?
- [ ] Is there a possibility of overflow or underflow during computation?
- [ ] Is there a possibility of a divide by zero?
- [ ] Are the order of operations in computations assumed correctly?

### Comparison Errors
- [X] Are any = operator used when == is needed?
- [ ] Are comparison operators correct?
- [ ] Are boolean operators and the operands they are used on correct?
- [ ] Are comparisons to floating point numbers handled correctly?

### Control-Flow Errors
- [X] All loops/recursive will terminate?
- [ ] Are there any off-by-one errors?
- [X] Are no do-while-statements used?

### Function Errors
- [X] Are all arguments passed in the correct order?
- [ ] Are all by-value parameters never modified?

### I/O Errors
- [X] Are all inputs to the system validated?
- [X] Are all opened files are closed?
- [X] Are end-of-file conditions handled correctly?
- [ ] Are I/O error conditions handled correctly?

### Other Errors
- [ ] Are all constant literals assigned a constant variable?
- [ ] Are returned error codes/states checked and handled correctly?
- [ ] Are all exceptions caught and handled correctly?
- [X] Are there no uses of using namespace std;