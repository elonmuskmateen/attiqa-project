# 📍 Your MySQL Database Physical Location

## Current Status

✅ **MySQL is installed**  
📍 **Location**: Found at `C:\Program Files\MySQL`

## Database Files Location

### Where Your Data Will Be Saved

Once you create the `campus_life` database and start the server, your database files will be located at:

**Most Likely Location:**
```
C:\ProgramData\MySQL\MySQL Server 8.X\Data\campus_life\
```

(Replace `8.X` with your MySQL version number: 8.0, 8.1, 8.2, 8.3, or 8.4)

## How to Find Your Exact Location

### Method 1: Check ProgramData Directory

1. Open File Explorer
2. Navigate to: `C:\ProgramData\MySQL\`
3. Look for folder: `MySQL Server 8.X` (where X is your version)
4. Go into: `MySQL Server 8.X\Data\`
5. Your database will be: `campus_life\`

### Method 2: Use MySQL Workbench

1. Open MySQL Workbench
2. Connect to your MySQL server
3. Go to: **Server** → **Status and System Variables**
4. Search for: `datadir`
5. The value shown is your data directory
6. Your database files = `[datadir]\campus_life\`

### Method 3: Check MySQL Configuration

1. Open: `C:\ProgramData\MySQL\MySQL Server 8.X\my.ini`
2. Look for: `datadir=C:/ProgramData/MySQL/MySQL Server 8.X/Data/`
3. Your database = `[datadir]\campus_life\`

## Database Files Structure

When the database is created, you'll see:

```
campus_life/
├── db.opt                    (Database options)
├── users.frm                 (Users table structure)
├── users.ibd                 (Users table data)
├── events.frm                (Events table structure)
├── events.ibd                (Events table data)
├── reviews.frm               (Reviews table structure)
├── reviews.ibd               (Reviews table data)
├── courses.frm               (Courses table structure)
├── courses.ibd               (Courses table data)
└── ... (17 tables = 34 files total)
```

## Next Steps

### 1. Create the Database

Open MySQL Command Line Client or MySQL Workbench and run:

```sql
CREATE DATABASE campus_life CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

### 2. Update .env File

Edit `server/.env` and add your MySQL root password:

```env
DB_PASSWORD=your-mysql-root-password
```

### 3. Start the Server

```bash
cd server
npm run dev
```

### 4. Files Will Be Created Automatically

Once the server starts, it will automatically create all 17 tables and the physical files will appear in:

```
C:\ProgramData\MySQL\MySQL Server 8.X\Data\campus_life\
```

## View Your Database Files

### Using File Explorer

1. Press `Win + R`
2. Type: `C:\ProgramData\MySQL\`
3. Navigate to your MySQL version folder
4. Go to `Data\campus_life\`
5. You'll see all `.frm` and `.ibd` files

**Note:** You may need Administrator privileges to access `C:\ProgramData\MySQL\`

### Using MySQL Workbench

1. Open MySQL Workbench
2. Connect to localhost
3. Expand `campus_life` database
4. Right-click on any table → **Table Inspector** → **Storage** tab
5. Shows file location

## Quick Access Commands

### PowerShell (Run as Administrator)

```powershell
# List MySQL versions
Get-ChildItem "C:\ProgramData\MySQL" -Directory

# Check if campus_life exists
Test-Path "C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life"

# View database files (if exists)
Get-ChildItem "C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life" -File
```

## Summary

**Your database physical files location:**
```
C:\ProgramData\MySQL\MySQL Server [VERSION]\Data\campus_life\
```

**To find exact version:**
- Check `C:\ProgramData\MySQL\` folder
- Look for `MySQL Server 8.X` folder
- Your database will be in `Data\campus_life\`

**Files are created automatically** when you start the server after creating the database!

