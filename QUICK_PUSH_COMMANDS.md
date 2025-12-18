# ⚡ Quick Push Commands

## If Git is Installed but Not Recognized

**Option 1: Restart Terminal**
- Close this terminal/PowerShell window
- Open a **NEW** terminal/PowerShell window
- Navigate to project: `cd C:\Users\Silicon\Downloads\campus-life-main`
- Try: `git --version`

**Option 2: Use Full Path**
If Git is installed but not in PATH, use full path:

```powershell
# Find Git first
& "C:\Program Files\Git\bin\git.exe" --version

# Then use it:
& "C:\Program Files\Git\bin\git.exe" init
& "C:\Program Files\Git\bin\git.exe" add .
& "C:\Program Files\Git\bin\git.exe" commit -m "Initial commit"
```

## Complete Push Commands

**After Git is working, run these commands:**

```bash
# 1. Initialize (if not done)
git init

# 2. Configure Git (first time only)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# 3. Add all files
git add .

# 4. Create commit
git commit -m "Initial commit: Campus Life Platform with MySQL backend"

# 5. Set branch to main
git branch -M main

# 6. Create repository on GitHub.com first, then:
git remote add origin https://github.com/YOUR_USERNAME/campus-life-platform.git

# 7. Push to GitHub
git push -u origin main
```

## Alternative: Use GitHub Desktop

If command line is difficult:

1. **Download GitHub Desktop**: https://desktop.github.com/
2. **Sign in** with your GitHub account
3. **File → Add Local Repository**
4. **Select**: `C:\Users\Silicon\Downloads\campus-life-main`
5. **Click "Publish repository"**
6. **Done!** ✅

## Check Git Installation

Run in PowerShell:
```powershell
# Check if Git is installed
where.exe git

# Or check common locations
Test-Path "C:\Program Files\Git\bin\git.exe"
Test-Path "C:\Program Files (x86)\Git\bin\git.exe"
```

If none found, install Git: https://git-scm.com/download/win

---

**After Git works, follow PUSH_TO_GITHUB.md for detailed steps!**

