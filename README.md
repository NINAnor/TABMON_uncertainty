# uncertainty

## Setup
Install `uv`: https://docs.astral.sh/uv/getting-started/installation/

```bash
git init
uv sync
git add .
git commit -m "Initial commit"
uv run pre-commit install # optional
```

## Setup Notebook
Run the following commands first to setup the notebook environment:
```bash
uv run ipython kernel install --user --env VIRTUAL_ENV $(pwd)/.venv --name=uncertainty
```
This register this project environment as a kernel `uncertainty`, kernels are isolated environments that you can use to run your code.
If the kernel is not available in the list of kernels, you can refresh the page and it should appear.

**If you are using a local jupyter notebook** run the following command:
```bash
uv run --with jupyter jupyter lab
```

### Run
To execute your software run:
```
uv run main.py
```

### Development
Just run `uv run main.py` and you are good to go!

### (Optional) pre-commit
pre-commit is a set of tools that help you ensure code quality. It runs every time you make a commit.
To install pre-commit hooks run:
```bash
uv run pre-commit install
```

### How to install a package
Run `uv add <package-name>` to install a package. For example:
```bash
uv add requests
```

#### Visual studio code
If you are using visual studio code install the recommended extensions


### Tools installed
- uv
- pre-commit (optional)

#### What is an environment variable? and why should I use them?
Environment variables are variables that are not populated in your code but rather in the environment
that you are running your code. This is extremely useful mainly for two reasons:
- security, you can share your code without sharing your passwords/credentials
- portability, you can avoid using hard-coded values like file-system paths or folder names

you can place your environment variables in a file called `.env`, the `main.py` will read from it. Remember to:
- NEVER commit your `.env`
- Keep a `.env.example` file updated with the variables that the software expects
