# 📁 Physical Database File Location

## MySQL Database Files Location

The physical files for your `campus_life` database are stored in MySQL's data directory.

### Windows - Default MySQL Installation

**Primary Location:**
```
C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life\
```

**Alternative Locations (depending on MySQL version):**
```
C:\ProgramData\MySQL\MySQL Server 8.1\Data\campus_life\
C:\ProgramData\MySQL\MySQL Server 8.2\Data\campus_life\
C:\ProgramData\MySQL\MySQL Server 5.7\Data\campus_life\
```

### Windows - XAMPP Installation

```
C:\xampp\mysql\data\campus_life\
```

### Windows - WAMP Installation

```
C:\wamp64\bin\mysql\mysql8.0.xx\data\campus_life\
```

### Mac (Homebrew)

```
/usr/local/var/mysql/campus_life/
```

### Linux

```
/var/lib/mysql/campus_life/
```

## How to Find Your Exact Location

### Method 1: MySQL Command Line

```sql
mysql -u root -p
SHOW VARIABLES LIKE 'datadir';
```

This will show you the exact data directory path.

### Method 2: MySQL Workbench

1. Open MySQL Workbench
2. Connect to your server
3. Go to: **Server** → **Status and System Variables**
4. Search for: `datadir`
5. The value shown is your data directory

### Method 3: Check MySQL Configuration File

**Windows:**
```
C:\ProgramData\MySQL\MySQL Server 8.0\my.ini
```

Look for `datadir=` in the file.

**Linux/Mac:**
```
/etc/mysql/my.cnf
/usr/local/etc/my.cnf
```

## Database Files Structure

Once the database is created, you'll see these files:

```
campus_life/
├── db.opt                    # Database options (charset, collation)
├── users.frm                 # Table structure for users
├── users.ibd                 # Table data for users (InnoDB)
├── events.frm                # Table structure for events
├── events.ibd                # Table data for events
├── reviews.frm               # Table structure for reviews
├── reviews.ibd               # Table data for reviews
├── courses.frm               # Table structure for courses
├── courses.ibd               # Table data for courses
└── ... (17 tables total)
```

### File Types Explained

- **`.frm` files** - Table structure/definition files
  - Contains column definitions, data types, indexes
  - MySQL reads these to understand table structure

- **`.ibd` files** - InnoDB data files
  - Contains actual table data (rows)
  - Includes indexes for fast queries
  - Binary format optimized for MySQL

- **`db.opt`** - Database options file
  - Stores default character set and collation

## Important Notes

### ⚠️ Do NOT Modify Files Directly

- **Never** edit `.frm` or `.ibd` files directly
- **Never** delete files manually
- Always use MySQL commands or tools

### ✅ Safe Operations

- **View files**: Safe (read-only)
- **Backup directory**: Safe (copy entire folder)
- **Use MySQL tools**: Always safe

## Finding Your Database Files Right Now

### Step 1: Check if MySQL is Running

```bash
# Windows
sc query MySQL80

# Or check Services
services.msc → Look for "MySQL80"
```

### Step 2: Find Data Directory

```sql
-- Connect to MySQL
mysql -u root -p

-- Run this command
SHOW VARIABLES LIKE 'datadir';
```

### Step 3: Navigate to Database Folder

After finding `datadir`, go to:
```
[datadir]\campus_life\
```

Example:
- If `datadir` = `C:\ProgramData\MySQL\MySQL Server 8.0\Data`
- Then database files = `C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life\`

## Backup Physical Files

### Option 1: Copy Entire Directory

```powershell
# Windows PowerShell
Copy-Item "C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life" -Destination "C:\Backups\campus_life_backup" -Recurse
```

### Option 2: Use MySQL Dump (Recommended)

```bash
mysqldump -u root -p campus_life > backup.sql
```

## File Permissions

**Windows:**
- Usually requires Administrator privileges to access `C:\ProgramData\MySQL\`
- Files are owned by MySQL service account

**Linux/Mac:**
- Files owned by `mysql` user
- Requires `sudo` to access

## Size Information

- **Empty database**: ~1-2 MB (just structure files)
- **With 100 users**: ~5-10 MB
- **With full data**: 50-500 MB (depends on usage)

## Quick Reference

| Installation Type | Default Location |
|-----------------|-----------------|
| MySQL Installer (Windows) | `C:\ProgramData\MySQL\MySQL Server X.X\Data\campus_life\` |
| XAMPP (Windows) | `C:\xampp\mysql\data\campus_life\` |
| WAMP (Windows) | `C:\wamp64\bin\mysql\mysqlX.X\data\campus_life\` |
| Homebrew (Mac) | `/usr/local/var/mysql/campus_life/` |
| Linux (Default) | `/var/lib/mysql/campus_life/` |

## Summary

**Your database files are physically located at:**
```
[MySQL Data Directory]\campus_life\
```

**To find exact location:**
1. Run: `SHOW VARIABLES LIKE 'datadir';` in MySQL
2. Navigate to: `[datadir]\campus_life\`
3. You'll see all `.frm` and `.ibd` files for your tables

**Remember:** The database must be created first (via SQL command) before these files will exist!

