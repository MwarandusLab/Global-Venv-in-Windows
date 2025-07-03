## ✅ STEP 1: Create 4 Global Virtual Environments
Pick a directory to hold your venvs, e.g., `C:\venvs`
Open CMD or PowerShell as Admin and run:
```bash
mkdir C:\venvs
```
```bash
cd C:\venvs
```
# Create each venv (As many as you want)
```bash
python -m venv django
```
```bash
python -m venv flask
```
```bash
python -m venv facerecognition
```
```bash
python -m venv others
```
## ✅ STEP 2: Install Packages into Each
Activate each venv and install your desired packages:
For `django:`
```bash
C:\venvs\django\Scripts\activate
pip install django
deactivate
```
For `flask:`
```bash
C:\venvs\flask\Scripts\activate
pip install flask
deactivate
```
For `facerecognition:`
```bash
C:\venvs\facerecognition\Scripts\activate
pip install face_recognition
deactivate
```
For `others:`
```bash
C:\venvs\others\Scripts\activate
pip install <your-other-packages>
deactivate
```
## ✅ STEP 3: Create Global Aliases (activate commands)
We’ll define aliases or functions in both PowerShell and CMD.
### 🔹 A. For PowerShell (`activate` in PowerShell)
1.Open PowerShell and run:
```bash
notepad $PROFILE
```
2. Add these lines:
```bash
function activate {
    param(
        [string]$envName
    )

    $venvPath = "C:\venvs\$envName\Scripts\Activate.ps1"

    if (Test-Path $venvPath) {
        & $venvPath
    } else {
        Write-Host "Environment '$envName' not found at $venvPath"
    }
}
```
Now you can run the following command separate to activate each env of your choice:
```bash
activate django
activate flask
activate facerecognition
activate others
```
**Note:** If **$PROFILE** doesn’t exist, PowerShell will create it.

###🔹 B. For CMD (activate in CMD)
1. Create a batch file for each env. Open Notepad and paste this for Django:
```bash
@echo off
call C:\venvs\django\Scripts\activate.bat
```
Save inside the venv you had created as:
```bash
C:\venvs\activate_django.bat
```
Repeat for others:

2. Add C:\venvs to your System PATH (so activate_django works globally):
- Press `Win + S` → Search Environment Variables
- Edit **System Environment Variables**
- Under Path, add `C:\venvs`
3. Now in CMD, just run:
```bash
activate_django
activate_flask
activate_facerecognition
activate_others
```
