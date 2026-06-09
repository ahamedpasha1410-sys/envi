# Task 3: Python Environment Setup using UV

## Objective

This project demonstrates how to:

* Create a Git branch for UV setup
* Create and manage a Python virtual environment using UV
* Install dependencies using UV
* Run Python scripts inside the UV environment
* Commit and push the project to GitHub

---

##  1. Create and Switch to Branch

```bash
git checkout main
git checkout -b venv-with-uv
```

---

##  2. Install UV

### Windows CMD

```cmd
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Verify installation:

```cmd
uv --version
```

Example output:

```text
uv 0.11.19
```

---

##  3. Create a UV Project

```cmd
uv init uv-project
cd uv-project
```

This creates:

```text
uv-project/
├── main.py
├── pyproject.toml
└── README.md
```

---

##  4. Create a Virtual Environment

```cmd
uv venv
```

This creates:

```text
.venv/
```

Activate the environment:

```cmd
.venv\Scripts\activate
```

---

##  5. Add a Dependency

Install the `requests` library:

```cmd
uv add requests
```

This updates:

* pyproject.toml
* uv.lock

---

##  6. Create Example Program

Create a file named `example3.py`:

```python
import requests

response = requests.get("https://api.github.com")

print("Status Code:", response.status_code)
print("UV setup working!")
```

---

##  7. Run the Program

```cmd
uv run python example3.py
```

Expected Output:

```text
Status Code: 200
UV setup working!
```

---

##  Project Structure

```text
uv-project/
│
├── .python-version
├── .venv/
├── example3.py
├── main.py
├── pyproject.toml
├── README.md
└── uv.lock
```

---

##  How UV Works

* UV creates isolated virtual environments.
* Dependencies are stored in `pyproject.toml`.
* Exact package versions are stored in `uv.lock`.
* UV provides fast package installation and dependency resolution.
* UV can be used as a modern replacement for pip and venv.

---

##  Files to Ignore

Do not commit virtual environment files.

Example `.gitignore`:

```gitignore
venv/
.venv/
__pycache__/
*.pyc
```

---

##  Commit and Push to GitHub

Stage files:

```cmd
git add .
```

Commit:

```cmd
git commit -m "Add uv environment setup"
```

Push branch:

```cmd
git push origin venv-with-uv
```

---

##  Outcome

After completing this task:

✔ UV is installed and configured

✔ Virtual environment is created

✔ Dependencies are managed using UV

✔ Python application runs successfully

✔ Project is pushed to GitHub

---

##  Key Files

| File            | Purpose                                |
| --------------- | -------------------------------------- |
| pyproject.toml  | Project configuration and dependencies |
| uv.lock         | Locked dependency versions             |
| example3.py     | Sample Python program                  |
| README.md       | Project documentation                  |
| .python-version | Python version used by UV              |

```
```
