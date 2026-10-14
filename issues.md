# Static Code Analysis — Issue Identification and Resolution

| Issue | Type | Line(s) | Description | Fix Approach |
|---|---|---|---|---|
| Unsafe `eval()` | Security | 12 | Bandit B307; medium severity. Evaluates a formula as Python code. | Replace with safe arithmetic that doesn't execute arbitrary code. |
| Mutable default argument | Bug | 14 | Pylint W0102; the `logs=[]` list can be shared between calls. | Use `None` and create a new list inside the function. |
| Bare `except` | Error handling | 37 | Pylint W0702, Flake8 E722, Bandit B110. Can hide unexpected failures. | Catch specific exceptions and handle them appropriately. |
| Unused imports | Code quality | 2–3 | Pylint W0611 and Flake8 F401 report unused `math` and `sys`. | Remove unused imports. |
| File handling | Code quality | 29, 36 | Files aren't managed with `with`, and encoding isn't specified. | Use `with open(..., encoding="utf-8")`. |
| Boolean comparison | Style | 43 | Flake8 E712 and Pylint C0121. Compares a Boolean explicitly to `True`. | Use `if results[r]["eligible"]:` |
| Function naming | Style | 40 | Pylint C0103; `printShortlist` doesn't follow `snake_case`. | Rename it to `print_shortlist()`. |
| Missing docstrings | Code quality | Multiple | Pylint reports missing module and function docstrings. | Add concise explanatory docstrings. |