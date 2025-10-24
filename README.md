# ANPR Dashboard - Download

**Enterprise Automatic Number Plate Recognition System**  
Version 1.2.3 | For Axis P-3265LVE Cameras

---

## 📥 Download Latest Version

**[➡️ Download ANPR Dashboard v1.2.3](../../releases/latest)**

Go to the [Releases](../../releases) page to download the latest installer.

---

## ✨ Features

### 🚗 Real-Time License Plate Detection
- Live monitoring of multiple Axis P-3265LVE cameras
- Real-time WebSocket updates
- Dual dashboards: Operator (view-only) and Admin (full control)

### 🤖 AI-Enhanced Recognition
- Google Gemini AI integration for low-confidence plates
- Configurable confidence threshold
- Automatic AI processing to improve accuracy
- Cost-effective: ~$0.70/year for typical usage

### 📊 Advanced Analytics
- Real-time correction statistics
- Manual vs. automated correction tracking
- Recognition rate metrics
- Most corrected plates analysis
- Event-driven updates

### 🔧 Automated Plate Corrections
- Create reusable correction rules for common camera misreads
- Automatic application of rules to new plates
- Track usage and effectiveness
- Prevent camera updates from overriding corrections

### 🔐 Security & Authentication
- Admin authentication system
- Password management
- Role-based access control
- Secure session management

### 📝 Professional Features
- Rotating log files with compression
- Configurable log levels
- Allow/deny list management
- CSV import/export
- Database-wide search with pagination
- Automatic update checker

---

## 💻 System Requirements

- **Operating System**: Windows 10/11 (64-bit)
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 2GB available space
- **Network**: Internet connection for AI features and updates
- **Database**: PostgreSQL (included in installer)
- **Runtime**: Node.js (included in installer)

---

## 📦 Installation

### Quick Install (5 minutes)

1. **Download** the latest installer from [Releases](../../releases)
2. **Right-click** the installer → **Run as Administrator**
3. **Follow** the installation wizard:
   - PostgreSQL will be installed automatically
   - Node.js dependencies will be installed
   - Database will be created and configured
4. **Configure** your Gemini API key (optional but recommended)
5. **Launch** from Start Menu or Desktop shortcut

### Post-Installation Setup

1. **Get a Gemini API Key** (free tier available):
   - Visit: https://aistudio.google.com/
   - Create an API key
   - Add to Admin Dashboard → System Info

2. **Configure Cameras**:
   - Set camera POST URL to: `http://your-server-ip:5001/api/camera-data`
   - Configure License Plate Verifier application on cameras

3. **Access the Dashboard**:
   - Operator Dashboard: http://localhost:5001/operator
   - Admin Dashboard: http://localhost:5001/admin (password: `admin123`)

---

## 🎯 Quick Start

### For Operators
1. Open: http://localhost:5001/operator
2. View real-time plate detections
3. Monitor system status

### For Administrators
1. Open: http://localhost:5001/admin
2. Login with password (default: `admin123`)
3. Configure settings, manage lists, view analytics
4. **Change the default password immediately!**

---

## 📸 Camera Configuration

### Axis P-3265LVE Setup

1. **Install License Plate Verifier** application on camera
2. **Configure HTTP POST**:
   - URL: `http://your-server-ip:5001/api/camera-data`
   - Method: POST
   - Content-Type: multipart/form-data
3. **Configure event data** to include:
   - License plate number
   - Confidence score
   - Camera ID and name
   - List status
   - Image data

---

## 🔄 Automatic Updates

The ANPR Dashboard includes an automatic update checker:

- **Automatic Check**: On admin dashboard startup
- **Manual Check**: Click "Check for Updates" in System Info
- **Notification**: Visual alert when new version is available
- **Download**: Direct link to latest installer

No configuration needed - updates are detected automatically!

---

## 🆘 Support & Troubleshooting

### Common Issues

**Camera not connecting?**
- Verify camera IP and network connectivity
- Check firewall allows port 5001
- Ensure License Plate Verifier is configured

**AI processing not working?**
- Add Gemini API key in Admin Dashboard → System Info
- Verify API key at https://aistudio.google.com/

**Admin dashboard not loading?**
- Clear browser cache (Ctrl+Shift+Del)
- Hard refresh page (Ctrl+Shift+R)
- Try private/incognito window

### Log Files

Logs are located at:
```
C:\Program Files\ANPR Dashboard\anpr-dashboard.log
```

Check logs for detailed error messages and troubleshooting.

---

## 📋 Version History

### v1.2.3 (Current)
- Advanced analytics dashboard with correction statistics
- Automated plate correction rules with usage tracking
- Database-wide search with pagination
- Plate locking (prevents updates to corrected/listed plates)
- Event-driven analytics updates
- Admin Dashboard live data improvements
- Log level adjustment from UI
- Gemini confidence threshold control
- Automatic update checker
- Enhanced installer with verbose logging

### Previous Versions
See [Releases](../../releases) for complete version history.

---

## 🔒 Privacy & Security

- **Authentication**: Admin dashboard requires password
- **Data Security**: All data stored locally in PostgreSQL
- **Network Security**: Configure firewall rules appropriately
- **Compliance**: Consider local privacy laws regarding license plate data

---

## 💰 Pricing

**FREE** - This software is provided at no cost.

**Optional Costs**:
- Google Gemini AI: ~$0.70/year (free tier available)
- Hardware: Axis P-3265LVE cameras (separate purchase)

---

## ⚖️ License

**Proprietary Software** - All rights reserved.

This software is provided for use as-is. Redistribution, modification, or reverse engineering is prohibited without explicit permission.

---

## 📧 Contact

For enterprise support, custom features, or licensing inquiries:
- Create an issue in this repository
- Contact: [jabird60@me.com]

---

## 🎓 About

ANPR Dashboard is a professional-grade license plate recognition system designed for corporate and security applications. It integrates seamlessly with Axis P-3265LVE cameras and uses Google Gemini AI for enhanced accuracy.

**Built for**: Security teams, parking management, access control systems, and fleet monitoring.

---

**Download the latest version from [Releases](../../releases) and get started in minutes!** 🚀

