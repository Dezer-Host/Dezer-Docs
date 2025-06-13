# Install/Update Script

---

This script helps automate the installation or update process for the Panel and its database.

## Usage

### On Linux/macOS

```sh
curl -fsSL https://raw.githubusercontent.com/Dezer-Host/script/main/script.sh -o /tmp/dx.sh && bash /tmp/dx.sh
```

### On Windows

> **Note:**  
> This script is designed for Linux/macOS environments.  
> For Windows, consider using WSL or running the script on a compatible server.

> **Important:**  
> Make sure to review the script and adjust any settings to match your environment before running it.

## What the Script Does

- Installs required dependencies (NodeJS, Docker Compose, etc.)
- Sets up the MySQL database and user
- Pulls and configures the Dezer Panel Docker containers
- Applies necessary updates and migrations
- Performs initial configuration and setup

For more details, see the [Dezer-Host/script repository](https://github.com/Dezer-Host/script).

---

For manual setup instructions, see [Database Setup](./database.md).
