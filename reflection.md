# Static Code Analysis — Reflection

## Q1. Why is static code analysis important?

Static code analysis helps identify programming errors, security vulnerabilities, and coding-standard violations without executing the program. It improves code quality, readability, maintainability, and security.

## Q2. What is the difference between Pylint, Flake8, and Bandit?

- **Pylint:** Checks code quality, naming conventions, programming errors, and other potential problems.
- **Flake8:** Checks Python style and formatting rules, along with selected programming errors.
- **Bandit:** Examines Python code for common security issues, such as unsafe use of `eval()`.

## Q3. What were the major problems found in the original scholarship screening program?

The original program contained unsafe use of `eval()`, a mutable default argument, broad exception handling, file-handling issues, unused imports, and insufficient validation of applicant information.

## Q4. How were the identified issues resolved?

The code was improved by replacing `eval()` with a dedicated merit-score function, using `None` for the optional logging argument, catching specific exceptions, opening files with context managers and explicit encoding, removing unused imports, and validating GPA, credits, and income.

## Q5. How did you verify the corrections?

I reran the program and all three static analysis tools. Pylint returned a score of 10.00/10, Flake8 reported no violations, and Bandit identified no issues. The execution test also confirmed that invalid applicant U003 was skipped.

## Q6. What did you learn from this lab?

I learned that static analysis tools help detect different categories of code problems. Using multiple tools provides broader coverage than relying on a single tool. I also learned that validating inputs, handling exceptions properly, and following coding standards can improve the reliability and security of a Python application.