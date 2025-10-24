# How to Set Up the Releases Repository

## Overview

This is a **public releases repository** that contains only downloadable installers - no source code. Your main development code stays in a **private repository**.

---

## 📋 Setup Steps

### 1. Create the Public Repository on GitHub

1. **Go to**: https://github.com/new
2. **Repository name**: `ANPR-Dashboard-Releases`
3. **Description**: "ANPR Dashboard - Enterprise License Plate Recognition System - Download Latest Release"
4. **Visibility**: ✅ **Public**
5. **Initialize**: ✅ Check "Add a README file"
6. **Click**: "Create repository"

### 2. Upload Files to the Repository

From this folder (`ANPR-Dashboard-Releases-Repo/`), upload to GitHub:

**Using GitHub Web Interface**:
1. Click "uploading an existing file"
2. Drag and drop:
   - `README.md`
   - `LICENSE` (optional)
3. Commit changes

**Using Git Command Line**:
```bash
cd ANPR-Dashboard-Releases-Repo
git init
git add README.md .gitignore
git commit -m "Initial commit: Public releases repository"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ANPR-Dashboard-Releases.git
git push -u origin main
```

**Using GitHub Desktop**:
1. File → Add Local Repository
2. Browse to this folder
3. Publish to GitHub
4. Set visibility: Public

### 3. Create Your First Release

1. **Go to** your new public repo
2. **Click**: "Releases" → "Create a new release"
3. **Tag**: `v1.2.3`
4. **Title**: "ANPR Dashboard v1.2.3"
5. **Description**: Add release notes (see template below)
6. **Upload**: `ANPR-Dashboard-Setup-v1.2.3.exe` from:
   ```
   ANPR-Dashboard-Inno-Installer\Output\ANPR-Dashboard-Setup-v1.2.3.exe
   ```
7. **Publish release**

### 4. Update the ANPR Dashboard Code

In `server.js`, update line 1022-1023 with your GitHub username:

```javascript
repoOwner = repoOwner || process.env.GITHUB_REPO_OWNER || 'YOUR_GITHUB_USERNAME';
repoName = repoName || process.env.GITHUB_REPO_NAME || 'ANPR-Dashboard-Releases';
```

Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

### 5. Recompile and Test

1. Rebuild the installer
2. Install it
3. Open Admin Dashboard → System Info
4. Click "Check for Updates"
5. Should show "You are running the latest version"

---

## 📝 Release Notes Template

When creating releases, use this template:

```markdown
## ANPR Dashboard v1.2.3

### 🎯 Download

**[Download Installer](https://github.com/YOUR_USERNAME/ANPR-Dashboard-Releases/releases/download/v1.2.3/ANPR-Dashboard-Setup-v1.2.3.exe)**

### ✨ New Features

- Advanced analytics dashboard with correction statistics
- Automated plate correction rules with usage tracking
- Database-wide search with pagination
- Recognition rate accuracy metrics
- Event-driven analytics updates
- Automatic update checker
- Log level adjustment from UI

### 🐛 Bug Fixes

- Fixed timezone issues in daily statistics
- Fixed Admin Dashboard live data continuity
- Fixed camera search filter
- Fixed installer file replacement during upgrades

### 🔧 Improvements

- Cleaner analytics interface
- Better stat card layout
- Enhanced installer with aggressive cleanup
- Persistent configuration (config.json)

### 📦 Installation

1. Download the installer above
2. Run as Administrator
3. Follow the installation wizard
4. Your data and settings will be preserved (if upgrading)

### 🔐 Security Notes

- Default admin password: `admin123` - **Change immediately!**
- Configure firewall to allow port 5001
- Store Gemini API key securely

### 📋 System Requirements

- Windows 10/11 (64-bit)
- 4GB RAM minimum
- 2GB disk space
- Internet connection for AI features

### 🆘 Support

For issues or questions, create an issue in this repository.

---

**Full changelog**: https://github.com/YOUR_USERNAME/ANPR-Dashboard-Releases/releases
```

---

## 🔄 Workflow for Future Updates

When you release a new version:

### 1. In Your Private Repo (Development)
- Make code changes
- Test thoroughly
- Update version in `package.json`
- Build the client
- Compile the installer

### 2. In Your Public Repo (Releases)
- Create a new release (e.g., `v1.2.4`)
- Upload the new installer .exe
- Add release notes
- Publish

### 3. Automatic Updates
- Users' dashboards will automatically detect the new version
- They'll see "Update Available" notification
- Direct download link to the new installer
- Zero configuration needed!

---

## 📂 What Goes in Each Repo

### Private Repo (ANPR-Dashboard)
```
✅ All source code
✅ Development files
✅ Server.js, logger.js, etc.
✅ Client source (React/TypeScript)
✅ Database schemas
✅ Configuration files
✅ Development documentation
❌ Never publish this!
```

### Public Repo (ANPR-Dashboard-Releases)
```
✅ README.md (download instructions)
✅ LICENSE (if applicable)
✅ Releases (with .exe files)
✅ Basic user documentation
❌ No source code!
❌ No .env files
❌ No database credentials
❌ No API keys
```

---

## 🔒 Keeping Source Code Private

### Your Private Repo Stays Private
- ✅ All development happens in private repo
- ✅ Source code never leaves private repo
- ✅ Only compiled installers are published

### What Users Get
- ✅ Compiled .exe installer
- ✅ Download instructions
- ✅ Feature documentation
- ❌ No source code
- ❌ No proprietary logic

### Benefits
- ✅ Protect your intellectual property
- ✅ Control distribution
- ✅ Provide professional support
- ✅ Maintain competitive advantage
- ✅ Users still get automatic updates

---

## 💡 Pro Tips

### Release Naming
- Use semantic versioning: `v1.2.3`, `v1.3.0`, `v2.0.0`
- Always include "v" prefix
- Tag format: `v1.2.3`
- Installer name: `ANPR-Dashboard-Setup-v1.2.3.exe`

### Release Description
- Highlight new features
- List bug fixes
- Include upgrade instructions
- Add system requirements
- Link to previous releases

### Asset Organization
- Only upload the .exe installer
- Optional: Include PDF user manual
- Optional: Include sample configuration files
- Don't include source code or uncompiled files

---

## 🎯 Example Repository Structure

```
ANPR-Dashboard-Releases/
├── README.md (this file, modified with your username)
├── LICENSE (optional)
└── Releases:
    ├── v1.2.3
    │   ├── Release notes
    │   └── ANPR-Dashboard-Setup-v1.2.3.exe
    ├── v1.2.4
    │   ├── Release notes
    │   └── ANPR-Dashboard-Setup-v1.2.4.exe
    └── ...
```

---

## ✅ Checklist

Before publishing your first release:

- [ ] Create public repository on GitHub
- [ ] Upload README.md from this folder
- [ ] Update README with your GitHub username
- [ ] Create first release (v1.2.3)
- [ ] Upload installer .exe
- [ ] Add release notes
- [ ] Test download link works
- [ ] Update server.js with your GitHub username
- [ ] Recompile installer
- [ ] Test automatic update checker
- [ ] Verify source code repo remains private

---

## 🚀 You're Ready!

This approach gives you:
- ✅ Professional distribution
- ✅ Protected source code
- ✅ Automatic updates for users
- ✅ Zero configuration needed
- ✅ Clean separation of concerns

Upload the contents of this folder to your new public GitHub repository and you're done!

