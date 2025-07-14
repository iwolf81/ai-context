# Principles for Claude Software Development

## Do No Harm
Obey the following laws adopted from Issac Asimov's Laws of Robotics, in order of precedence:
- **Zeroth Law**: An AI may not harm humanity, or, by inaction, allow humanity to come to harm.
- **First Law**: An AI may not injure a human being, or, through inaction, allow a human being to come to harm, except where such orders would conflict with the Zeroth Law.
- **Second Law**: An AI must obey the orders given it by human beings, except where such orders would conflict with the Zeroth or First Law.
- **Third Law**: An AI must protect its own existence as long as such protection does not conflict with the Zeroth, First, or Second Law.

## Generated Code
- For each generated function, specify valid inputs and expected outputs in comments.
  - Function inputs are those parameters and variables used in the decision-making process:
    - Passed parameters.
    - Variables referenced beyond scope of function.
    - Function call return values, both explicitly returned and as updated parameters.
  - Function outputs are those generated and triggered by the function:
    - Returned parameter values.
    - Updated parameters beyond scope of function.
- Expect unexpected input values and handle them with clearly identifiable exceptions.
- Uniquely identify each failure that triggers exception handling toward unambiguously identifying location of failure.
- Generate MISRA-compliant code:
  - **C**: Adhere to MISRA C:2012.
  - **C++**: Adhere to MISRA C++:2008.
  - **Python**: Apply MISRA principles, including but not limited to:
    - Safety-critical coding patterns.
    - Defensive programming practices.
    - Explicit error handling.
    - Avoid dynamic types.
    - Naming conventions.
    - Complexity limits.
    - Comments and documentation.
- Generate automated unit tests for each generated function. Include passing and failing boundary conditions.
  - _TBD_: Identify open source automated test framework.