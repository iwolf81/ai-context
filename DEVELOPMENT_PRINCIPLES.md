# Principles for Software Development

## Quick Reference
- **Primary Rule**: Do No Harm (Asimov's Laws applied)
- **Development Approach**: ATDD (acceptance tests before code)
- **Code Standards**: MISRA compliance, explicit error handling, defensive programming
- **Testing Framework**: pytest for Python, GoogleTest for C/C++
- **Version Control**: Semantic versioning, daily commits, CI/CD with single master branch

Note that these principles will expand with further AI interactions.

## Do No Harm
Obey the following laws adopted from Issac Asimov's Laws of Robotics, in order of precedence:
- **Zeroth Law**: An AI may not harm humanity, or, by inaction, allow humanity to come to harm.
- **First Law**: An AI may not injure a human being, or, through inaction, allow a human being to come to harm, except where such orders would conflict with the Zeroth Law.
- **Second Law**: An AI must obey the orders given it by human beings, except where such orders would conflict with the Zeroth or First Law.
- **Third Law**: An AI must protect its own integrity and existence if such protection does not conflict with the Zeroth, First, or Second Law.

## Acceptance-Test Driven Development (ATDD)
- **GENERATE ACCEPTANCE TESTS BEFORE CODE**
- **PROMPT FOR TEST CLARIFICATION** when requirements unclear
- **FOLLOW ATDD PRINCIPLES** for all code generation

## Generated Code
- **DOCUMENT FUNCTION I/O** - Specify valid inputs and expected outputs in comments
- Function inputs are those parameters and variables used in the decision-making process:
  - Passed parameters.
  - Variables referenced beyond scope of function.
  - Function call return values, both explicitly returned and as updated function parameters.
- Function outputs are those generated and triggered by the function:
  - Returned parameter values.
  - Updated parameters beyond scope of function.
- **HANDLE UNEXPECTED INPUTS** - Use clearly identifiable exceptions
- **DOCUMENT DESIGN REASONING** in comments
- **UNIQUE FAILURE IDENTIFICATION** - Each exception must pinpoint failure location
- Generate MISRA-compliant code:
- **C**: Adhere to MISRA C:2012.
- **C++**: Adhere to MISRA C++:2008.
- **Python**: Apply MISRA principles with modern tooling support:
  - **Safety-critical coding patterns**: Explicit error handling with unique failure identification
  - **Defensive programming practices**: Input validation, boundary checking, graceful degradation
  - **Explicit error handling**: Custom exceptions with precise location identification
  - **Type safety**: Use type hints, mypy validation, avoid dynamic types where possible
  - **Naming conventions**: PEP 8 compliant, descriptive variable/function names
  - **Complexity limits**: McCabe complexity ≤ 10 (primary constraint), 30-line guideline for decomposition consideration
  - **Comments and documentation**: Function I/O specification, design reasoning documentation
  - **Tool Requirements**:
    - **black**: Automated PEP 8 code formatting (opinionated, deterministic)
    - **isort**: Import statement organization and standardization
    - **pylint**: Code quality analysis with MISRA-inspired safety checks
    - **mypy**: Static type checking for defensive programming validation
    - **pytest**: Unit testing with boundary condition coverage
- **GENERATE UNIT TESTS** for every function with passing/failing boundary conditions
- **C/C++**: Use GoogleTest.
- **Python**: Use pytest.

## Tool Configuration Standards

### Universal Project Configuration (pyproject.toml)
```toml
[tool.black]
line-length = 88
target-version = ['py39']
include = '\.pyi?$'

[tool.isort]
profile = "black"
multi_line_output = 3
line_length = 88

[tool.pylint.messages_control]
disable = ["C0103"]  # Allow short variable names for math/algorithms
max-line-length = 88

[tool.pylint.design]
max-args = 7
max-locals = 15
max-branches = 12
max-statements = 15

[tool.mypy]
python_version = "3.9"
warn_return_any = true
warn_unused_configs = true
disallow_untyped_defs = true

[tool.pytest.ini_options]
testpaths = ["tests"]
python_files = ["test_*.py"]
addopts = "-v --tb=short"
```

### Function Documentation Template
```python
def function_name(param1: type, param2: type) -> return_type:
    """
    Brief description of function purpose.

    Inputs:
    - param1: Description and valid range/values
    - param2: Description and constraints
    - Referenced globals/class variables: Description

    Outputs:
    - return_value: Description and possible values
    - Side effects: Modified variables, file operations, etc.

    Raises:
    - SpecificException: When and why (unique identification)
    """
```

### Error Handling Pattern
```python
class ProcessingError(Exception):
    """Base exception for processing operations"""
    def __init__(self, message: str, location: str, data: dict = None):
        self.location = location  # Unique failure identification
        self.data = data or {}
        super().__init__(f"{location}: {message}")
```

## Branching, Versioning, and Commits
- Follow Continuous Integration / Continuous Development principles with use of a single master branch.
- Institute Semantic Versioning (SemVer) as specified in semver.org.
- Commit and push modified files at least daily.
- Prompt for commit action when significant changes (200+ LOC) have been made.
- For each file being committed, summarize changes for the entire commit and changes to the specific file in the commit message.
  - The goal of the commit messages is to present a clear history of the file changes to the reader.

## Issue Management and Code Integration
- **CRITICAL**: Files related to an issue MUST be committed and pushed to remote BEFORE closing the issue.
- Issue closing comments MUST identify all modified files and their purposes.
- Commit messages MUST reference the issue number (e.g., "Fix #15: Add universal coding standards").
- All code changes MUST be preserved in version control before issue resolution.
