# JLox If Statements Implementation - CS370 Assignment

## Overview
This implementation adds if statement support to the JLox interpreter as required for section 9.2. The implementation includes:

1. **If statement parsing** in `Parser.java`
2. **If statement execution** in `Interpreter.java` 
3. **Logical operators** (and, or) support
4. **Risk assessment program** demonstrating the functionality

## Files Modified

### Core Implementation
- `Stmt.java` - Added `If` statement class and updated Visitor interface
- `Expr.java` - Added `Logical` expression class for and/or operators
- `Parser.java` - Added `ifStatement()`, `or()`, `and()` methods
- `Interpreter.java` - Added `visitIfStmt()` and `visitLogicalExpr()` methods
- `AstPrinter.java` - Added `visitLogicalExpr()` method

### Test Programs
- `risk_assessment.lox` - Main assignment program
- `demo.lox` - Simple demonstration of if statements

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
