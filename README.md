1. Create and Switch to Branch
git checkout main
git checkout -b venv-with-poetry
2. Install Poetry (if not installed)
pip install poetry

OR recommended:

curl -sSL https://install.python-poetry.org | python3 -
3. Initialize Poetry Project
poetry init

During setup:

Set project name: envi
Accept default values OR press Enter for all prompts
4. Configure Project (IMPORTANT FIX)

If Poetry shows packaging error, add this in pyproject.toml:

package-mode = false
5. Add Dependency

We use requests library:

poetry add requests

This will:

Create/update pyproject.toml
Generate poetry.lock
6. Install Dependencies
poetry install

If needed:

poetry lock
poetry install
7. Create Python File (example1.py)
import requests

response = requests.get("https://api.github.com")

print("Status Code:", response.status_code)
print("Success!")
8. Run Project
Run using Poetry environment:

poetry run python example1.py
9. Project Structure
envi/
│
├── example1.py
├── pyproject.toml
├── poetry.lock
├── README.md

Do NOT include:
venv/
.venv/
pycache/
10. How Poetry Works
Poetry automatically creates virtual environment
Manages dependencies in pyproject.toml
Locks versions in poetry.lock
Ensures reproducible environment across systems
11. Important Rules
Never use pip install inside Poetry project

Always use:

poetry add <package>

Always run scripts using:

poetry run python file.py
12. Commit & Push to GitHub
Add files:
git add .
Commit changes:
git commit -m "Add Poetry environment setup"
Push branch:
git push origin venv-with-poetry
