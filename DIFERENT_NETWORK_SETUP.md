# 🌐 Using App on Different Network - Setup Guide

When your phone and computer are on **different networks**, you need to make your backend accessible over the internet.

---

## 🎯 Solution Options

### Option 1: Use ngrok (Easiest - Recommended) ⭐

**ngrok** creates a secure tunnel to your local backend, making it accessible from anywhere.

#### Step 1: Install ngrok

**Mac:**
```bash
brew install ngrok
```

**Or download from:** https://ngrok.com/download

#### Step 2: Start Your Backend

```bash
cd backend
python app.py
```
Keep this running.

#### Step 3: Start ngrok Tunnel

Open a **new terminal** and run:
```bash
ngrok http 5000
```

You'll see something like:
```
Forwarding  https://abc123.ngrok.io -> http://localhost:5000
```

**Copy the HTTPS URL** (e.g., `https://abc123.ngrok.io`)

#### Step 4: Update App Backend URL

**For Android App:**
1. Open: `android-client/app/src/main/java/com/example/phishing/MainActivity.kt`
2. Change:
   ```kotlin
   private val BACKEND_URL = "https://abc123.ngrok.io/predict"
   ```
   (Use YOUR ngrok URL)

3. Rebuild APK and install

**For Web Version:**
1. Open: `web/index.html`
2. Change:
   ```javascript
   const BACKEND_URL = 'https://abc123.ngrok.io/predict';
   ```
   (Use YOUR ngrok URL)

#### Step 5: Use App from Anywhere!

- Phone can be on any network
- Works from anywhere in the world
- Secure HTTPS connection

**Note:** Free ngrok URLs change each time you restart. For permanent URL, sign up for ngrok account.

---

### Option 2: Deploy Backend to Cloud (Permanent Solution)

Deploy your backend to a cloud service so it's always accessible.

#### Option A: Heroku (Free Tier Available)

1. **Install Heroku CLI:**
   ```bash
   brew install heroku/brew/heroku
   ```

2. **Create Heroku App:**
   ```bash
   cd backend
   heroku create your-app-name
   ```

3. **Create Procfile:**
   ```bash
   echo "web: python app.py" > Procfile
   ```

4. **Deploy:**
   ```bash
   git add .
   git commit -m "Deploy to Heroku"
   git push heroku main
   ```

5. **Get URL:**
   - Your backend will be at: `https://your-app-name.herokuapp.com`
   - Update app to use: `https://your-app-name.herokuapp.com/predict`

#### Option B: Railway (Free Tier)

1. Go to: https://railway.app
2. Sign up with GitHub
3. New Project → Deploy from GitHub
4. Select your repository
5. Set root directory to `backend`
6. Deploy automatically
7. Get your URL and update app

#### Option C: Render (Free Tier)

1. Go to: https://render.com
2. Sign up
3. New Web Service
4. Connect GitHub repository
5. Set:
   - Root Directory: `backend`
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `python app.py`
6. Deploy
7. Get your URL

---

### Option 3: Use Same Network (Simplest)

**If possible, connect both to same WiFi:**

1. Connect phone to same WiFi as computer
2. Use computer's local IP (as in previous guide)
3. Works without internet!

---

## 🚀 Recommended: ngrok (Quick Setup)

### Complete ngrok Setup

1. **Install ngrok:**
   ```bash
   # Mac
   brew install ngrok
   
   # Or download from ngrok.com
   ```

2. **Sign up for free account** (optional but recommended):
   - Go to: https://dashboard.ngrok.com/signup
   - Get your authtoken
   - Run: `ngrok config add-authtoken YOUR_TOKEN`

3. **Start backend:**
   ```bash
   cd backend
   python app.py
   ```

4. **Start ngrok:**
   ```bash
   ngrok http 5000
   ```

5. **Copy the forwarding URL:**
   - Look for: `Forwarding https://xxxx.ngrok.io -> http://localhost:5000`
   - Copy the `https://xxxx.ngrok.io` part

6. **Update your app:**
   - Android: Update `BACKEND_URL` in `MainActivity.kt`
   - Web: Update `BACKEND_URL` in `index.html`
   - Use: `https://xxxx.ngrok.io/predict`

7. **Rebuild and use!**

---

## 📱 Update Android App

1. Open: `android-client/app/src/main/java/com/example/phishing/MainActivity.kt`

2. Change:
   ```kotlin
   private val BACKEND_URL = "https://YOUR_NGROK_URL.ngrok.io/predict"
   ```

3. Rebuild APK:
   ```bash
   cd android-client
   ./gradlew assembleDebug
   ```

4. Install on phone

---

## 🌐 Update Web Version

1. Open: `web/index.html`

2. Find and change:
   ```javascript
   const BACKEND_URL = 'https://YOUR_NGROK_URL.ngrok.io/predict';
   ```

3. Access from any device, any network!

---

## ⚠️ Important Notes

### ngrok Free Limitations:
- URL changes each restart
- Limited connections per minute
- For permanent URL, upgrade to paid plan

### Security:
- ngrok provides HTTPS automatically
- Backend is accessible to anyone with the URL
- Don't share ngrok URL publicly

### For Production:
- Use cloud deployment (Heroku, Railway, Render)
- Get permanent URL
- Better performance
- More reliable

---

## 🔒 Security Considerations

When using ngrok or cloud deployment:

1. **Add rate limiting** to prevent abuse
2. **Add authentication** if needed
3. **Monitor usage** and logs
4. **Use HTTPS** (ngrok provides this automatically)

---

## 📋 Quick Comparison

| Solution | Setup Time | Cost | Permanent URL | Best For |
|----------|------------|------|---------------|----------|
| **ngrok** | 2 minutes | Free | No (changes) | Testing, quick setup |
| **Heroku** | 10 minutes | Free tier | Yes | Production, permanent |
| **Railway** | 5 minutes | Free tier | Yes | Production, easy deploy |
| **Render** | 5 minutes | Free tier | Yes | Production, simple |
| **Same Network** | 1 minute | Free | N/A | Local testing only |

---

## 🎯 My Recommendation

**For Quick Testing:**
- Use **ngrok** - fastest setup, works immediately

**For Permanent Solution:**
- Deploy to **Railway** or **Render** - free, permanent URL, easy setup

---

## ✅ Step-by-Step: ngrok (Fastest)

1. Install ngrok: `brew install ngrok`
2. Start backend: `cd backend && python app.py`
3. Start ngrok: `ngrok http 5000` (in new terminal)
4. Copy HTTPS URL from ngrok
5. Update app: Change `BACKEND_URL` to ngrok URL
6. Rebuild app
7. Use from anywhere! 🎉

---

**Need help with any step? Just ask!** 😊

