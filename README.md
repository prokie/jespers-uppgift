# Hjälp Jesper

## Prerequisites
- Docker
- Python 3.11 

## Setup

1. Clone the repository:
    ```sh
    git clone https://github.com/prokie/jespers-uppgift.git
    cd jespers-uppgift
    ```

2. Open the project in Visual Studio Code:
    ```sh
    code .
    ```

3. Reopen the project in the dev container:
    - Press `F1` and select `Remote-Containers: Reopen in Container`.

4. Install dependencies using `uv sync`:
    ```sh
    uv sync --all-extras --compile-bytecode
    ```

