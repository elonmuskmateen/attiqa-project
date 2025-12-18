# 🚀 GitHub Setup Guide

## Step 1: Configure Git (if not already done)

If you haven't set your Git username and email, run:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Step 2: Create Initial Commit

The project is ready to commit. Run:

```bash
git add .
git commit -m "Initial commit: Campus Life Platform with MySQL backend"
```

## Step 3: Create GitHub Repository

1. **Go to GitHub**: https://github.com/new
2. **Repository name**: `campus-life-platform` (or your preferred name)
3. **Description**: "Campus Life Platform - University management system with MySQL backend"
4. **Visibility**: Choose Public or Private
5. **DO NOT** initialize with README, .gitignore, or license (we already have these)
6. **Click "Create repository"**

## Step 4: Connect Local Repository to GitHub

After creating the repository, GitHub will show you commands. Run:

```bash
git remote add origin https://github.com/YOUR_USERNAME/campus-life-platform.git
git branch -M main
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

## Step 5: Push Your Code

```bash
git push -u origin main
```

## Alternative: Using GitHub CLI (if installed)

```bash
gh repo create campus-life-platform --public --source=. --remote=origin --push
```

## What Will Be Uploaded

✅ **Included:**
- All source code (React frontend, Node.js backend)
- Database models and configurations
- Documentation files
- Package.json files
- Project structure

❌ **Excluded (via .gitignore):**
- `node_modules/` folders
- `.env` files (sensitive data)
- Build files
- Log files
- IDE settings
- Temporary files

## Important Notes

⚠️ **Before pushing:**
- Make sure `.env` files are NOT committed (they're in .gitignore)
- Check that no sensitive data is in the code
- Review what will be committed: `git status`

⚠️ **After pushing:**
- Add `.env.example` files to show required environment variables
- Update README.md with setup instructions
- Consider adding LICENSE file

## Environment Variables Template

Create `server/.env.example`:

```env
PORT=3001
NODE_ENV=development

# MySQL Database Configuration
DB_HOST=localhost
DB_PORT=3306
DB_NAME=campus_life
DB_USER=root
DB_PASSWORD=your-mysql-password

# JWT Secret
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
JWT_EXPIRE=7d

# CORS Configuration
FRONTEND_URL=http://localhost:3000
```

## Next Steps After Upload

1. ✅ Add a README.md with project description
2. ✅ Add setup instructions
3. ✅ Add screenshots/demo images
4. ✅ Add LICENSE file
5. ✅ Enable GitHub Pages (if needed)
6. ✅ Add GitHub Actions for CI/CD (optional)

## Troubleshooting

**"Permission denied" error:**
- Use SSH keys or Personal Access Token
- GitHub no longer accepts passwords

**"Repository not found":**
- Check repository name and username
- Verify you have access to the repository

**Large files:**
- If files are too large, use Git LFS
- Or exclude large files in .gitignore

---

**Ready to push!** Follow the steps above to upload your project to GitHub.

