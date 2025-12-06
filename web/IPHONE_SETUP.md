# 📱 iPhone Setup Guide - Step by Step

Complete guide to use Phishing Detector on any iPhone or iPad.

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
3. Look for **IPv4 Address** under your WiFi adapter
4. **Copy that IP address**

---

### Step 2: Start Backend Server

**On your computer:**

1. Open **Terminal** (Mac) or **Command Prompt** (Windows)
2. Navigate to backend folder:
   ```bash
   cd /Users/ghaidaa/Phishing-Link-Detection-App/backend
   ```
3. Activate virtual environment (if you have one):
   ```bash
   source venv/bin/activate  # Mac/Linux
   # OR
   venv\Scripts\activate     # Windows
   ```
4. Start the server:
   ```bash
   python app.py
   ```
5. You should see: `Running on http://0.0.0.0:5000`
6. **Keep this terminal open!**

---

### Step 3: Start Web Server

**Open a NEW Terminal window:**

1. Navigate to web folder:
   ```bash
   cd /Users/ghaidaa/Phishing-Link-Detection-App/web
   ```
2. Start web server:
   ```bash
   python3 -m http.server 8000
   ```
3. You should see: `Serving HTTP on 0.0.0.0 port 8000`
4. **Keep this terminal open too!**

---

### Step 4: Configure on iPhone

1. **Make sure iPhone and computer are on the SAME WiFi network**
2. On iPhone, open **Safari**
3. Go to: `http://YOUR_IP_ADDRESS:8000`
   - Example: `http://192.168.1.100:8000`
   - Replace `YOUR_IP_ADDRESS` with the IP from Step 1

4. The app should load!

5. **Configure Backend URL:**
   - Tap **"⚙️ Configure Backend URL"**
   - Enter: `http://YOUR_IP_ADDRESS:5000/predict`
   - Example: `http://192.168.1.100:5000/predict`
   - Tap **"Save Backend URL"**

---

### Step 5: Test It!

1. Enter a URL (e.g., `https://www.google.com`)
2. Tap **"Check URL"**
3. Wait a few seconds
4. See the results! 🎉

---

## 📲 Add to Home Screen (Make It Like an App)

1. In Safari, tap the **Share** button (square with arrow up)
2. Scroll down and tap **"Add to Home Screen"**
3. Edit the name if you want (or keep "Phishing Detector")
4. Tap **"Add"** (top right)
5. **Done!** You now have an app icon on your home screen!

---

## ✅ Works On:

- ✅ iPhone (all models)
- ✅ iPad
- ✅ iPod Touch
- ✅ Any iOS device with Safari
- ✅ Works on iOS 12 and later

---

## 🆘 Troubleshooting

### "Can't connect" or "Network error"

**Check these:**

1. ✅ Backend server is running (`python app.py`)
2. ✅ Web server is running (`python3 -m http.server 8000`)
3. ✅ iPhone and computer are on **same WiFi**
4. ✅ IP address is correct
5. ✅ Backend URL is configured correctly
6. ✅ Firewall isn't blocking ports 5000 and 8000

**Fix Firewall (Mac):**
1. System Settings → Network → Firewall
2. Make sure it allows Python/terminal connections

**Fix Firewall (Windows):**
1. Windows Defender → Firewall
2. Allow Python through firewall

---

### "Backend URL not working"

1. Tap **"⚙️ Configure Backend URL"**
2. Make sure it's: `http://YOUR_IP:5000/predict`
3. **NOT** `localhost` (that won't work from iPhone)
4. **NOT** `127.0.0.1` (that won't work either)
5. Must be your computer's actual IP address

---

### "Page won't load"

1. Check web server is running
2. Try: `http://YOUR_IP:8000` in Safari
3. Make sure no typos in the URL
4. Try refreshing the page

---

### "Results not showing"

1. Check backend server terminal for errors
2. Make sure backend URL is correct
3. Try a simple URL first: `https://www.google.com`

---

## 💡 Pro Tips

1. **Bookmark the page** for quick access
2. **Add to Home Screen** for app-like experience
3. **Save backend URL** - it's saved automatically
4. **Keep servers running** while using the app

---

## 🔄 Daily Use

**Every time you want to use it:**

1. Start backend: `cd backend && python app.py`
2. Start web server: `cd web && python3 -m http.server 8000`
3. Open on iPhone: `http://YOUR_IP:8000`
4. Use the app!

**Tip:** Create shortcuts/aliases to make this faster!

---

## 📋 Quick Reference

- **Backend URL format**: `http://YOUR_IP:5000/predict`
- **Web URL format**: `http://YOUR_IP:8000`
- **Backend port**: 5000
- **Web port**: 8000
- **Required**: Same WiFi network

---

## 🎉 That's It!

Your Phishing Detector now works on any iPhone! 🚀

Need help? Check the troubleshooting section above!

