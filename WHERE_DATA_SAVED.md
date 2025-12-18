# 📊 Where Your Data Will Be Saved

## Overview

All data for the Campus Life Platform is stored in a **MySQL relational database** on your local computer.

## Database Information

- **Database Name**: `campus_life`
- **Database Type**: MySQL (Relational Database Management System)
- **Server Location**: `localhost:3306`
- **Storage Engine**: InnoDB (default)

## Physical File Location

### Windows (MySQL Server Installation)
```
C:\ProgramData\MySQL\MySQL Server 8.0\Data\campus_life\
```

### Windows (XAMPP Installation)
```
C:\xampp\mysql\data\campus_life\
```

### Mac (Homebrew)
```
/usr/local/var/mysql/campus_life/
```

### Linux
```
/var/lib/mysql/campus_life/
```

## What Gets Saved

When you start the server, it automatically creates **17 tables** that store all your data:

### User Data
- **users** table → Stores all user accounts (students, teachers, admins)
  - Usernames, emails, encrypted passwords
  - User roles, profiles, settings

### Event Data
- **events** → Event proposals and details
- **event_votes** → Individual votes on events
- **event_feedback** → Comments and feedback on events

### Review Data
- **reviews** → Teacher reviews and ratings
- **review_helpful** → Helpfulness votes on reviews

### Course Data
- **courses** → Course information and metadata
- **course_ratings** → Student ratings for courses

### Election Data
- **elections** → Election information
- **election_candidates** → Candidate registrations
- **election_votes** → Individual votes cast

### Q&A Data
- **questions** → Questions posted
- **answers** → Answers provided
- **answer_helpful** → Helpfulness votes

### Feedback Data
- **feedback** → Campus services feedback
- **feedback_upvotes** → Upvotes on feedback

### Notification Data
- **notifications** → User notifications

## File Structure

Each table consists of:
- **Table Structure** (`.frm` files) - Defines columns and data types
- **Table Data** (`.ibd` files) - Contains actual data rows
- **Index Files** - For fast searching and queries

Example:
```
campus_life/
├── users.frm          (table structure)
├── users.ibd          (user data)
├── events.frm
├── events.ibd
├── reviews.frm
├── reviews.ibd
└── ... (17 tables total)
```

## How to View Your Data

### Option 1: MySQL Workbench (Recommended GUI)
1. Download: https://dev.mysql.com/downloads/workbench/
2. Connect to `localhost:3306`
3. Select `campus_life` database
4. Browse tables and view data

### Option 2: Command Line
```bash
mysql -u root -p
USE campus_life;
SHOW TABLES;
SELECT * FROM users;
```

### Option 3: phpMyAdmin (Web Interface)
1. Install XAMPP
2. Access: http://localhost/phpmyadmin
3. Select `campus_life` database
4. Browse tables

## Data Persistence

✅ **Data persists** between server restarts  
✅ **Data persists** even if you close the application  
✅ **Data is safe** until you delete the database or MySQL files  
✅ **Automatic backups** can be configured

## Backup Your Data

### Create Backup
```bash
mysqldump -u root -p campus_life > backup_$(date +%Y%m%d).sql
```

### Restore Backup
```bash
mysql -u root -p campus_life < backup_20240101.sql
```

## Current Setup Status

⚠️ **MySQL needs to be installed** before the server can save data.

### To Complete Setup:

1. **Install MySQL**
   - Download: https://dev.mysql.com/downloads/installer/
   - Or use XAMPP: https://www.apachefriends.org/

2. **Create Database**
   ```sql
   CREATE DATABASE campus_life CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   ```

3. **Update `.env` file** in `server/` directory:
   ```env
   DB_PASSWORD=your-mysql-password
   ```

4. **Start Server**
   ```bash
   cd server
   npm run dev
   ```

5. **Tables will be created automatically** on first run!

## Security Notes

- ✅ Passwords are **encrypted** (bcrypt hashing)
- ✅ Database requires authentication
- ✅ Data files are protected by file system permissions
- ⚠️ Keep your MySQL root password secure!

## Data Size

- **Empty database**: ~1-2 MB
- **With 1000 users**: ~5-10 MB
- **With full data**: Depends on usage, typically 50-500 MB

## Summary

**Your data is saved in:**
- **Database**: MySQL `campus_life` database
- **Location**: MySQL data directory on your computer
- **Format**: Binary MySQL files (optimized for performance)
- **Access**: Via MySQL tools or API endpoints

Once MySQL is installed and the server starts, all data operations (create, read, update, delete) will automatically save to these MySQL tables!

