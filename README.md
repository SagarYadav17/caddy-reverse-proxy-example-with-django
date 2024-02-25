# Caddy Reverse Proxy Example with Django

This repository demonstrates how to set up a Django project with Caddy as a reverse proxy, serving both WSGI and ASGI on different ports. This setup allows you to use the same initial URL endpoints for both WSGI and ASGI protocols.

## Setup

1. Clone the repository:
2. Create and activate Conda environment (for development only):

    ```bash
    conda env create -f ./backend/environment.yml
    conda activate caddy
    pip install -r ./backend/requirements.txt
    ```

3. Start the caddy container and servers

    ```bash
    docker compose -f ./backend/compose.yaml up -d --build
    ```
