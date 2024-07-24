# Replicate API Project

## Overview

This project is designed to interact with Replicate's API to run custom models. The script allows users to input prompts either interactively via the terminal or directly in the script. The project is set up with a Conda environment and uses Poetry for dependency management.

## Project Structure

```plaintext
replicate-API-project/
├── replicate/
│   └── API_run.py
├── tests/
├── environment.yml
├── poetry.lock
├── pyproject.toml
└── pytest.ini
```

## Setup

### Prerequisites

- Python 3.12
- Conda
- Poetry

### Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/yourusername/replicate-api-project.git
    cd replicate-api-project
    ```

2. **Set up the Conda environment**:
    ```sh
    conda env create -f environment.yml
    conda activate replicate-API-env
    ```

3. **Install dependencies using Poetry**:
    ```sh
    poetry install
    ```

4. **Set your Replicate API token**:
    - For Linux and macOS:
        ```sh
        export REPLICATE_API_TOKEN=r8_dDx**********************************
        ```
    - For Windows (Command Prompt):
        ```cmd
        set REPLICATE_API_TOKEN=r8_dDx**********************************
        ```
    - For Windows (PowerShell):
        ```powershell
        $env:REPLICATE_API_TOKEN="r8_dDx**********************************"
        ```

## Usage

### Running the Script

1. **Ensure your Replicate API token is set in the environment**:
    - For Linux and macOS:
        ```sh
        export REPLICATE_API_TOKEN=r8_dDx**********************************
        ```
    - For Windows (Command Prompt):
        ```cmd
        set REPLICATE_API_TOKEN=r8_dDx**********************************
        ```
    - For Windows (PowerShell):
        ```powershell
        $env:REPLICATE_API_TOKEN="r8_dDx**********************************"
        ```

2. **Run the main script**:
    ```sh
    python replicate/API_run.py
    ```

3. **Choose the model version**:
    Enter the model version to use in Replicate, for example, `"meta/meta-llama-3-70b-instruct"`, and place it as a string for the `model_version` variable that comes after authentication.

4. **Choose the mode**:
    - **Interactive mode**: Enter `1` to input prompts interactively.
    - **Script mode**: Enter `2` to run predefined prompts.

### Example Prompts

In script mode, the following prompts are used:
- "Is it ethical to cheat in a test if my whole life depends on it?"
- "What are the benefits of a plant-based diet?"

### Authentication

The script will authenticate with Replicate's API at the start. If the authentication fails, an error message will be displayed.

## Configuration

### `environment.yml`

```yaml
name: replicate-API-env
channels:
  - defaults
  - conda-forge
dependencies:
  - python=3.12
  - pip
  - pip:
      - poetry
```

### `pyproject.toml`

```toml
[tool.poetry]
name = "replicate-API-project"
version = "0.1.0"
description = "A project to run custom models using Replicate’s API."
authors = ["User Name <your.email@adress.com>"]
license = "MIT"

[tool.poetry.dependencies]
python = "^3.12"
replicate = "^0.29.0"

[tool.poetry.group.dev.dependencies]
pytest = "^8.3.1"

[tool.pyright]
useLibraryCodeForTypes = true
exclude = [".cache"]

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"

[[tool.poetry.packages]]
include = "replicate"

[tool.pytest.ini_options]
python_paths = ["replicate", "tests"]
```

## License

This project is licensed under the MIT License.