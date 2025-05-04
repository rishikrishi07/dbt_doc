# dbt Documentation Setup Guide

This guide provides the steps to set up and generate dbt documentation from a cloned repository.

## Setup Steps

### 1. Clone the Repository
```bash
git clone https://github.com/rishikrishi07/dbt_doc.git
cd dbt_doc
```

### 2. Set Up Virtual Environment
```bash
# For Mac/Linux
python -m venv dbt_env
source dbt_env/bin/activate

# For Windows
python -m venv dbt_env
dbt_env\Scripts\activate
```

> **IMPORTANT**: The `dbt` command will only work when the virtual environment is activated. 
> If you see `command not found: dbt`, make sure you've activated the environment.

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Navigate to dbt Directory & Install Packages
```bash
cd dbt
dbt deps
```

### 5. Generate Documentation
```bash
dbt docs generate
```

### 6. Serve Documentation
```bash
dbt docs serve --port 8081
```

The documentation will be available at: http://localhost:8081

## One-line Command (Mac/Linux)
If you're already in the root directory, you can use this single command to activate the environment and serve the docs:
```bash
source dbt_env/bin/activate && cd dbt && dbt docs serve --port 8081
```

## Troubleshooting

- **Error: `command not found: dbt`**  
  Solution: You need to activate the virtual environment first with `source dbt_env/bin/activate`

- **Missing dependencies**  
  Solution: Make sure you've run `pip install -r requirements.txt` and `dbt deps` 