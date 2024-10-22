for https://signate.jp/competitions/580

## Code Formatter and Linter Setup

### Installing and Running Black

1. Install Black by running:
   ```
   pip install black
   ```

2. Create a configuration file named `pyproject.toml` in the root directory of the repository with the following content:
   ```
   [tool.black]
   line-length = 88
   target-version = ['py37']
   ```

3. Run Black on your code by executing:
   ```
   black .
   ```

### Integrating Black with Editors or IDEs

- **VS Code**: Install the "Python" extension and configure it to use Black for formatting.
- **PyCharm**: Go to `Preferences` > `Tools` > `External Tools` and add Black as an external tool.
- **Other Editors**: Refer to the Black documentation for integration instructions.

### Installing and Running flake8

1. Install flake8 by running:
   ```
   pip install flake8
   ```

2. Create a configuration file named `.flake8` in the root directory of the repository with the following content:
   ```
   [flake8]
   max-line-length = 88
   ignore = E203, E266, E501, W503
   select = B,C,E,F,W,T4,B9
   ```

3. Run flake8 on your code by executing:
   ```
   flake8 .
   ```

### Setting Up Pre-Commit Hook

1. Install pre-commit by running:
   ```
   pip install pre-commit
   ```

2. Create a configuration file named `.pre-commit-config.yaml` in the root directory of the repository with the following content:
   ```
   repos:
     - repo: https://github.com/psf/black
       rev: 21.9b0
       hooks:
         - id: black
     - repo: https://gitlab.com/pycqa/flake8
       rev: 3.9.2
       hooks:
         - id: flake8
   ```

3. Install the pre-commit hook by running:
   ```
   pre-commit install
   ```

4. Now, every time you make a commit, the pre-commit hook will run Black and flake8 to ensure code formatting and quality.
