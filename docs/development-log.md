# Development Log

This document records the development progress of the Image Recognition App, including the work completed, problems encountered, solutions implemented, and knowledge gained throughout the project.

---

## 2 October 2026 — Initial Environment Setup

### What I Did

- Created the `Image-Recognition-App` GitHub repository.
- Added a Python `.gitignore` file to prevent unnecessary Python-generated files from being tracked by Git.
- Published the repository to GitHub.
- Installed Python 3.14.8.
- Created a Python virtual environment using Python's built-in `venv` module.
- Activated the virtual environment through the VS Code PowerShell terminal.
- Verified the Python version being used inside the virtual environment.

### Commands Used

Checked that Python was installed correctly:

```powershell
python --version
```

Created the virtual environment:

```powershell
python -m venv .venv
```

Initially attempted to activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

### Problem Encountered

When attempting to activate the virtual environment, PowerShell returned a `PSSecurityException` because script execution was disabled on the system.

This prevented the `Activate.ps1` script created by the Python virtual environment from running.

### Solution

Instead of permanently changing the system-wide PowerShell security settings, I changed the execution policy only for the current PowerShell process:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

I then activated the virtual environment:

```powershell
.venv\Scripts\Activate.ps1
```

The terminal displayed `(.venv)`, confirming that the virtual environment was active.

I verified the Python version again:

```powershell
python --version
```

Output:

```text
Python 3.14.8
```

### What I Learned

During this stage of the project, I learned how Python virtual environments can be used to isolate project dependencies from the main Python installation.

I also learned that PowerShell has execution policies that control whether PowerShell scripts are permitted to run. Using the `Process` scope allowed me to temporarily change the policy for the current terminal session without permanently changing the system-wide execution policy.

I also gained experience troubleshooting a development environment rather than assuming that an installation or setup problem was caused by the Python project itself.

### Next Steps

- Research suitable Python libraries for image recognition and computer vision.
- Check compatibility between Python 3.14 and the machine-learning libraries being considered.
- Decide on the initial architecture of the application.
- Set up the initial Python source-code structure.
- Begin implementing basic image loading and processing functionality.