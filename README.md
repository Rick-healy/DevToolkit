# DevToolkit

A collection of development support tools and utilities designed to streamline and automate common development tasks.

## Folders

### Git

The Git folder contains scripts to automate Git workflow tasks:

- **initialize-local-git-create-remote.ps1**: PowerShell script that initializes a local Git repository, creates a README file, and sets up a remote GitHub repository. The script handles authentication with GitHub CLI, creates the remote repository under personal or organization accounts, and pushes initial changes.

- **initialize-local-git-create-remote.sh**: Bash script equivalent of the PowerShell version for Unix-like environments. Performs the same Git initialization and GitHub repository creation tasks.

These scripts help standardize the repository setup process and save time when starting new projects.

## Running Scripts Directly from Command Line

> **⚠️ SECURITY WARNING ⚠️**  
> Never execute scripts directly from remote sources without first reviewing their contents. Always understand what a script does before running it. Remote scripts can contain malicious code that could harm your system or compromise your data.

### Windows PowerShell

To run a script directly from PowerShell without downloading it first:

```powershell
# First, review the script contents
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/rick-healy/DevToolkit/main/Git/initialize-local-git-create-remote.ps1" -UseBasicParsing | Select-Object -ExpandProperty Content

# Once reviewed and understood, execute with:
Invoke-Expression (Invoke-WebRequest -Uri "https://raw.githubusercontent.com/rick-healy/DevToolkit/main/Git/initialize-local-git-create-remote.ps1" -UseBasicParsing).Content
```

### WSL / Bash

To run a script directly from Bash without downloading it first:

```bash
# First, review the script contents
curl -s https://raw.githubusercontent.com/rick-healy/DevToolkit/main/Git/initialize-local-git-create-remote.sh

# Once reviewed and understood, execute with:
curl -s https://raw.githubusercontent.com/rick-healy/DevToolkit/main/Git/initialize-local-git-create-remote.sh | bash
```

### Alternative with Safety Check

A safer approach is to download the script first, review it, and then execute:

```bash
# Windows PowerShell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/rick-healy/DevToolkit/main/Git/initialize-local-git-create-remote.ps1" -OutFile "initialize-local-git-create-remote.ps1"
# Review the file contents before executing
./initialize-local-git-create-remote.ps1

# WSL / Bash
curl -s https://raw.githubusercontent.com/rick-healy/DevToolkit/main/Git/initialize-local-git-create-remote.sh > initialize-local-git-create-remote.sh
# Review the file contents before executing
chmod +x initialize-local-git-create-remote.sh
./initialize-local-git-create-remote.sh
```

**Remember**: Scripts may require parameters or have specific requirements. Always check the script documentation before running.