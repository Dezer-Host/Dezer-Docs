# Automatic Update Script

---

You can automatically update your Dezer Panel and its dependencies using the provided update script.

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
> Always review the script and adjust any settings to match your environment before running it.

## What the Script Does

- Checks for and installs updates for the Dezer Panel
- Updates Docker containers and dependencies
- Applies database migrations if needed
- Ensures your installation is up to date

For more details, see the [Dezer-Host/script repository](https://github.com/Dezer-Host/script).

---

For manual update instructions, see [Manual Update](./manual.md).
