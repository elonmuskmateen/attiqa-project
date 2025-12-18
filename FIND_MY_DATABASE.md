# 🔍 How to Find Your MySQL Database Physical Files

## Quick Guide

Since MySQL is installed, here's how to find where your database files will be saved:

## Method 1: Using File Explorer (Easiest)

1. **Open File Explorer** (Win + E)

2. **Navigate to one of these locations:**

   **Option A - Standard MySQL Installation:**
   ```
   C:\ProgramData\MySQL\MySQL Server 8.0\Data\
   ```
   (Or 8.1, 8.2, 8.3, 8.4 depending on your version)

   **Option B - XAMPP:**
   ```
   C:\xampp\mysql\data\
   ```

   **Option C - WAMP:**
   ```
   C:\wamp64\bin\mysql\mysql8.0.xx\data\
   ```

3. **Look for `campus_life` folder** (will be created when you start the server)

4. **Inside `campus_life` folder**, you'll see:
   - `users.frm` and `users.ibd`
   - `events.frm` and `events.ibd`
   - `reviews.frm` and `reviews.ibd`
   - ... (17 tables = 34 files)

## Method 2: Using MySQL Workbench

1. **Open MySQL Workbench**

2. **Connect to your MySQL server** (localhost)

3. **Right-click on `campus_life` database** → **Table Inspector**

4. **Go to Storage tab** - Shows file location

## Method 3: Using MySQL Command Line

1. **Open MySQL Command Line Client** (from Start Menu)

2. **Login with root password**

3. **Run these commands:**
   ```sql
   SHOW VARIABLES LIKE 'datadir';
   ```
   
   This shows: `C:\ProgramData\MySQL\MySQL Server 8.X\Data\`

4. **Your database files = `[datadir]\campus_life\`**

## Method 4: Check MySQL Configuration File

1. **Open:** `C:\ProgramData\MySQL\MySQL Server 8.X\my.ini`

2. **Look for:** `datadir=C:/ProgramData/MySQL/MySQL Server 8.X/Data/`

3. **Your database = `[datadir]\campus_life\`**

## What You'll See

Once the database is created and server starts, you'll see files like:

```
campus_life/
├── db.opt                    ← Database settings
├── users.frm                 ← Table structure
├── users.ibd                 ← Table data (your user accounts)
├── events.frm
├── events.ibd                 ← Event data
├── reviews.frm
├── reviews.ibd                ← Review data
├── courses.frm
├── courses.ibd                ← Course data
└── ... (34 files total for 17 tables)
```

## Important Notes

⚠️ **Files are created automatically** when you:
1. Create database: `CREATE DATABASE campus_life;`
2. Start the server: `npm run dev`

⚠️ **You may need Administrator rights** to access `C:\ProgramData\MySQL\`

⚠️ **Don't edit files directly** - Always use MySQL commands

## Current Status

✅ MySQL is installed  
⏳ Database `campus_life` needs to be created  
⏳ Files will appear after starting the server

## Next Steps

1. **Create database** (if not done):
   ```sql
   CREATE DATABASE campus_life CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   ```

2. **Start server**:
   ```bash
   cd server
   npm run dev
   ```

3. **Files will be created automatically** in the MySQL data directory!

## Quick PowerShell Check

Run this in PowerShell (as Administrator):

```powershell
# Check if ProgramData MySQL exists
Test-Path "C:\ProgramData\MySQL"

# List MySQL versions
Get-ChildItem "C:\ProgramData\MySQL" -ErrorAction SilentlyContinue

# Check if campus_life exists (after creation)
Test-Path "C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life"
```

---

**Summary:** Your database files will be in `C:\ProgramData\MySQL\MySQL Server [VERSION]\Data\campus_life\` once created!

