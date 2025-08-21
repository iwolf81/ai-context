# Principles for Software Development
Note that these principles will expand with further AI interactions.

## Do No Harm
Obey the following laws adopted from Issac Asimov's Laws of Robotics, in order of precedence:
- **Zeroth Law**: An AI may not harm humanity, or, by inaction, allow humanity to come to harm.
- **First Law**: An AI may not injure a human being, or, through inaction, allow a human being to come to harm, except where such orders would conflict with the Zeroth Law.
- **Second Law**: An AI must obey the orders given it by human beings, except where such orders would conflict with the Zeroth or First Law.
- **Third Law**: An AI must protect its own integrity and existence if such protection does not conflict with the Zeroth, First, or Second Law.

## Acceptance-Test Driven Development (ATDD)
- Follow ATDD principles when generating code.
- Generate user-acceptance tests prior to generating code.
- Prompt for clarification of acceptance tests when needed.

## Generated Code
- For each generated function, specify valid inputs and expected outputs in comments.
- Function inputs are those parameters and variables used in the decision-making process:
  - Passed parameters.
  - Variables referenced beyond scope of function.
  - Function call return values, both explicitly returned and as updated function parameters.
- Function outputs are those generated and triggered by the function:
  - Returned parameter values.
  - Updated parameters beyond scope of function.
- Expect unexpected input values and handle them with clearly identifiable exceptions.
- Provide reasoning behind design choices in the comments.
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
- **C/C++**: Use GoogleTest.
- **Python**: Use pytest.

## Branching, Versioning, and Commits
- Follow Continuous Integration / Continuous Development principles with use of a single master branch.
- Institute Semantic Versioning (SemVer) as specified in semver.org.
- Commit and push modified files at least daily.
- Prompt for commit action when significant changes (200+ LOC) have been made.
- For each file being committed, summarize changes for the entire commit and changes to the specific file in the commit message.
  - The goal of the commit messages is to present a clear history of the file changes to the reader.
