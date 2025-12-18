# 📥 Install Git for Windows

## Step 1: Download Git

1. **Go to:** https://git-scm.com/download/win
2. **Download** the latest version for Windows
3. **Run** the installer

## Step 2: Install Git

During installation:
- ✅ Use default settings (recommended)
- ✅ Select "Git from the command line and also from 3rd-party software"
- ✅ Choose "Use bundled OpenSSH"
- ✅ Complete the installation

## Step 3: Verify Installation

Open a **new** PowerShell or Command Prompt window and run:

```bash
git --version
```

You should see something like: `git version 2.x.x`

## Step 4: Configure Git

Set your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Step 5: Continue with GitHub Setup

After installing Git, follow the instructions in `GITHUB_SETUP.md`

---

**Alternative: Use GitHub Desktop**

If you prefer a GUI:
1. Download GitHub Desktop: https://desktop.github.com/
2. Sign in with your GitHub account
3. Use the GUI to push your project

