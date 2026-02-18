# AI Experts Assignment (Python)

This repository contains the solution for the AI Software Engineer assignment. It demonstrates:

- Setting up a small Python project to run reliably (locally + Docker)
- Pinning dependencies for reproducible installs
- Writing focused tests to reproduce a bug
- Implementing a minimal, reviewable fix

---

## Project Structure
-app/ # Application code
-tests/ # Test suite
-Dockerfile # Docker build instructions
-requirements.txt # Pinned dependencies
-EXPLANATION.md # Explanation of bug fix
-README.md # This file



---

## Running Tests

### Locally

1. Create and activate a virtual environment:

```bash
python -m venv venv
# Windows
.\venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

2. Install dependencies:
pip install -r requirements.txt

3. Run the tests:
pytest -v


### Using Docker
1 . Build the Docker image:
docker build -t ai-assignment .

2. Run tests inside Docker:
docker run ai-assignment
