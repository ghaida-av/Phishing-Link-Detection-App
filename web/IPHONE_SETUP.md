# 📱 iPhone Setup Guide - Step by Step

Complete guide to use the Phishing Detector on any iPhone.

---

## 🚀 Quick Setup (5 Minutes)

### Step 1: Find Your Computer's IP Address

**On Mac:**
1. Open **Terminal**
2. Type: `ifconfig | grep "inet " | grep -v 127.0.0.1`
3. Look for something like: `inet 192.168.1.100`
4. **Copy that IP address** (e.g., `192.168.1.100`)

**On Windows:**
1. Open **Command Prompt** (cmd)
2. Type: `ipconfig`
3. Look for "IPv4 Address" under your WiFi adapter
4. **Copy that IP address**

---

### Step 2: Update Backend URL in index.html

1. Open the file: `web/index.html`
2. Find this line (around line 400):
   ```javascript
   const BACKEND_URL = 'http://localhost:5000/predict';
   ```
3. Replace `localhost` with your IP address:
   ```javascript
   const BACKEND_URL = 'http://192.168.1.100:5000/predict';
   ```
   (Use YOUR actual IP address from Step 1)

4. **Save the file**

---

### Step 3: Start Backend Server

1. Open **Terminal**
2. Navigate to backend folder:
   ```bash
   cd /Users/ghaidaa/Phishing-Link-Detection-App/backend
   ```
3. Start the server:
   ```bash
   python app.py
   ```
4. You should see: `Running on http://0.0.0.0:5000`
5. **Keep this terminal open** (don't close it)

---

### Step 4: Start Web Server

1. Open a **NEW Terminal window** (keep backend running)
2. Navigate to web folder:
   ```bash
   cd /Users/ghaidaa/Phishing-Link-Detection-App/web
   ```
3. Start web server:
   ```bash
   python3 -m http.server 8000
   ```
4. You should see: `Serving HTTP on 0.0.0.0 port 8000`
5. **Keep this terminal open too**

---

### Step 5: Connect iPhone to Same WiFi

1. On your iPhone, go to **Settings** → **Wi-Fi**
2. Make sure you're connected to the **same WiFi network** as your computer
3. Check the WiFi name matches

---

### Step 6: Open on iPhone

1. On iPhone, open **Safari** (not Chrome)
2. In the address bar, type:
   ```
   http://YOUR_IP_ADDRESS:8000
   ```
   Example: `http://192.168.1.100:8000`
3. Press **Go**
4. The app should load!

---

### Step 7: Add to Home Screen (Optional but Recommended)

1. In Safari, tap the **Share button** (square with arrow up)
2. Scroll down and tap **"Add to Home Screen"**
3. Tap **"Add"** (top right)
4. Now you have an app icon on your home screen!
5. Tap it anytime to open the app

---

## ✅ Test It

1. Enter a URL: `https://www.google.com`
2. Tap **"Check URL"**
3. Wait a few seconds
4. You should see the result!

---

## 🆘 Troubleshooting

### "Can't connect" or "Network error"

**Check these:**
1. ✅ Backend server is running (Step 3)
2. ✅ Web server is running (Step 4)
3. ✅ iPhone and computer on same WiFi
4. ✅ IP address is correct in `index.html`
5. ✅ Firewall isn't blocking ports 5000 and 8000

**Fix firewall (Mac):**
1. System Settings → Network → Firewall
2. Make sure it's not blocking connections

**Fix firewall (Windows):**
1. Windows Defender Firewall
2. Allow Python through firewall

---

### "Backend URL is wrong"

**Double-check:**
1. Open `web/index.html`
2. Find `BACKEND_URL`
3. Make sure it has your computer's IP (not localhost)
4. Format: `http://192.168.1.100:5000/predict`

---

### "Page won't load on iPhone"

**Try:**
1. Make sure you're using **Safari** (not Chrome)
2. Check the URL is correct: `http://IP:8000`
3. Try refreshing the page
4. Make sure both servers are running

---

### "App looks weird on iPhone"

**This is normal!** The app is optimized for iPhone:
- Full screen on iPhone
- Rounded corners on iPad/desktop
- Touch-friendly buttons
- Safe area support (iPhone X and newer)

---

## 📋 Checklist

Before using on iPhone:
- [ ] Found computer's IP address
- [ ] Updated BACKEND_URL in index.html
- [ ] Backend server running (port 5000)
- [ ] Web server running (port 8000)
- [ ] iPhone on same WiFi network
- [ ] Opened in Safari (not Chrome)
- [ ] Added to Home Screen (optional)

---

## 🎯 Quick Reference

**Backend URL format:**
```
http://YOUR_IP:5000/predict
```

**Web app URL format:**
```
http://YOUR_IP:8000
```

**Example:**
- IP: `192.168.1.100`
- Backend: `http://192.168.1.100:5000/predict`
- Web app: `http://192.168.1.100:8000`

---

## 💡 Pro Tips

1. **Bookmark the URL** in Safari for quick access
2. **Add to Home Screen** for app-like experience
3. **Keep servers running** while using the app
4. **Check IP address** if you change WiFi networks

---

## 🎉 That's It!

Your Phishing Detector now works perfectly on iPhone! 🚀

**Need help?** Check the troubleshooting section above.
