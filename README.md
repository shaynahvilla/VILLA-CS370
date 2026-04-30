# JLox Functions Implementation - CS370 Assignment

## Overview
This implementation adds function support to the JLox interpreter as required for section 10.6 (Local Functions and Closures). The implementation includes:

1. **Function declarations** in `Stmt.java` and `Parser.java`
2. **Function calls** in `Expr.java` and `Parser.java`
3. **Return statements** in `Stmt.java` and `Parser.java`
4. **Function expressions** for anonymous functions
5. **Closures** - functions capture their lexical environment
6. **Function execution** in `Interpreter.java`

## Files Modified

### Core Implementation
- `Stmt.java` - Added `Function` and `Return` statement classes, updated Visitor interface
- `Expr.java` - Added `Call` and `Function` expression classes, updated Visitor interface
- `Parser.java` - Added `function()`, `returnStatement()`, `call()`, `finishCall()` methods
- `Interpreter.java` - Added `LoxFunction` class, `visitFunctionStmt()`, `visitReturnStmt()`, `visitCallExpr()`, `visitFunctionExpr()` methods
- `AstPrinter.java` - Added `visitCallExpr()` and `visitFunctionExpr()` methods

### Test Programs
- `test_functions.lox` - Demonstrates function declarations, calls, and closures
- `fibonacci_VILLA.lox` - Fibonacci sequence using functions and loops
- `risk_assessment.lox` - Original if statement demonstration program

## Risk Assessment Program Output

```
Ineligible
High Risk  
High Risk
Low Risk
Low Risk
```

### Test Cases:
1. **Age 17, non-smoker, no medical condition** = Ineligible (under 18)
2. **Age 65, non-smoker, no medical condition** = High Risk (over 60)
3. **Age 45, smoker, has medical condition** = High Risk (smoker AND medical condition)
4. **Age 45, smoker, no medical condition** = Low Risk (only one risk factor)
5. **Age 30, non-smoker, no medical condition** = Low Risk (no risk factors)

## Criteria Implementation

The program correctly implements the required criteria:

- **Ineligible**: Anyone under 18
- **High Risk**: Anyone over 60 OR anyone who is a Smoker AND has a Medical Condition  
- **Low Risk**: Everyone else

## Compilation and Execution

```bash
# Compile the Java files
javac com\craftinginterpreters\lox\*.java

# Run the risk assessment program
java com.craftinginterpreters.lox.Lox ..\risk_assessment.lox

# Run the demo program
java com.craftinginterpreters.lox.Lox ..\demo.lox
```

## Demo Program Output

```
x is greater than 5
y is not greater than 5
Young person or student
Grade: B
```

The implementation successfully demonstrates:
- Basic if statements
- If-else statements
- Logical operators (and, or)
- Nested if-else if chains
- Complex boolean expressions
