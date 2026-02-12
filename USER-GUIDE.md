# 📖 COMPLETE USER GUIDE
## Phone Backend Platform - Step-by-Step Setup

**Total Time: 30 minutes**  
**Difficulty: Beginner-friendly**  
**Cost: $0 (completely free)**

---

## 🎯 WHAT YOU'LL BUILD

By the end of this guide, you'll have:
- ✅ A live dashboard where you can create APIs
- ✅ A routing service that connects everything
- ✅ Your old Android phone working as a backend server
- ✅ A fully functional API you can use in any app

---

## 📋 PREREQUISITES

Before starting, make sure you have:

- [ ] GitHub account (sign up at github.com)
- [ ] Google account (for Firebase authentication)
- [ ] Old Android phone
- [ ] Computer with internet
- [ ] 30 minutes of time

---

## PART 1: DEPLOY THE DASHBOARD (10 minutes)

### Step 1.1: Create GitHub Repository

1. **Go to:** https://github.com/new

2. **Fill in:**
   - Repository name: `phone-backend`
   - Description: `Turn old phones into backend servers`
   - **Make it PUBLIC** (important!)
   - Click **"Create repository"**

### Step 1.2: Upload Dashboard

1. **On the empty repository page**, you'll see:
   ```
   …or create a new file on the command line
   ```

2. **Click:** "uploading an existing file" link

3. **Drag and drop** the `index.html` file from the `dashboard/` folder

4. **Scroll down** and click **"Commit changes"**

### Step 1.3: Enable GitHub Pages

1. **Click** the "Settings" tab (top of your repo)

2. **Scroll down** to "Pages" in the left sidebar

3. **Click** "Pages"

4. **Under "Source":**
   - Branch: **main**
   - Folder: **/ (root)**

5. **Click** "Save"

6. **Wait 1-2 minutes**, then **refresh the page**

7. **You'll see:**
   ```
   Your site is live at https://YOUR_USERNAME.github.io/phone-backend/
   ```

8. **Copy this URL** - you'll need it!

### Step 1.4: Add Domain to Firebase

1. **Go to:** https://console.firebase.google.com/project/harshitproto

2. **Click:** Authentication (left sidebar)

3. **Click:** Settings tab → Authorized domains

4. **Click:** "Add domain"

5. **Paste:** `YOUR_USERNAME.github.io` (just the domain, no https://)

6. **Click:** "Add"

### Step 1.5: Test Your Dashboard

1. **Visit:** `https://YOUR_USERNAME.github.io/phone-backend/`

2. **You should see:** Beautiful landing page

3. **Click:** "Get Started"

4. **Click:** "Sign in with Google"

5. **Choose your Google account**

6. **You should see:** Your dashboard with your name!

✅ **Dashboard is LIVE!**

---

## PART 2: DEPLOY ROUTING SERVICE (10 minutes)

### Step 2.1: Create Account on Railway

1. **Go to:** https://railway.app

2. **Click:** "Login" (top right)

3. **Click:** "Login with GitHub"

4. **Authorize Railway** to access your GitHub

### Step 2.2: Create Repository for Routing Service

1. **Go to:** https://github.com/new

2. **Fill in:**
   - Repository name: `phone-backend-routing`
   - **Make it PUBLIC**
   - Click **"Create repository"**

3. **Upload these files** from the `routing-service/` folder:
   - `package.json`
   - `server.js`
   - `README.md`

4. **Commit changes**

### Step 2.3: Deploy to Railway

1. **Go back to:** https://railway.app/dashboard

2. **Click:** "New Project"

3. **Click:** "Deploy from GitHub repo"

4. **Select:** `phone-backend-routing`

5. **Click:** "Deploy Now"

6. **Wait 2-3 minutes** for deployment

### Step 2.4: Get Your Routing URL

1. **Click on your deployment** (in Railway dashboard)

2. **Click:** "Settings" tab

3. **Scroll to:** "Domains"

4. **Click:** "Generate Domain"

5. **Copy the URL** (e.g., `phone-backend-routing.up.railway.app`)

### Step 2.5: Test Routing Service

Open your browser and visit:
```
https://YOUR-ROUTING-URL.railway.app/health
```

**You should see:**
```json
{
  "status": "ok",
  "connectedPhones": 0,
  "uptime": 12.34
}
```

✅ **Routing Service is LIVE!**

---

## PART 3: SETUP CLI ON GITHUB (5 minutes)

### Step 3.1: Create CLI Repository

1. **Go to:** https://github.com/new

2. **Fill in:**
   - Repository name: `phone-backend-cli`
   - **Make it PUBLIC** (important!)
   - Click **"Create repository"**

3. **Upload these files** from the `cli/` folder:
   - `package.json`
   - `bin/phone-backend.js`

4. **Commit changes**

### Step 3.2: Update CLI Code

1. **In your `phone-backend-cli` repository:**

2. **Click** on `bin/phone-backend.js`

3. **Click** the pencil icon (Edit)

4. **Find this line** (around line 42):
   ```javascript
   const ROUTING_URL = process.env.ROUTING_URL || 'http://localhost:3001';
   ```

5. **Change it to:**
   ```javascript
   const ROUTING_URL = 'https://YOUR-ROUTING-URL.railway.app';
   ```
   (Use YOUR actual Railway URL!)

6. **Scroll down** and click **"Commit changes"**

✅ **CLI is ready on GitHub!**

---

## PART 4: CONNECT YOUR PHONE (5 minutes)

### Step 4.1: Install Termux on Android

1. **Download F-Droid app:**
   - Go to: https://f-droid.org/
   - Download and install F-Droid

2. **Open F-Droid**

3. **Search:** "Termux"

4. **Install** Termux

5. **Open** Termux

**⚠️ IMPORTANT:** Don't use Google Play version - it's outdated!

### Step 4.2: Install Node.js

In Termux, type each command and press Enter:

```bash
pkg update
```
**Press:** `y` when asked

```bash
pkg install nodejs git
```
**Press:** `y` when asked

**This takes 2-3 minutes**

### Step 4.3: Install Phone Backend CLI

```bash
git clone https://github.com/YOUR_USERNAME/phone-backend-cli
```
(Replace YOUR_USERNAME with your GitHub username!)

```bash
cd phone-backend-cli
```

```bash
chmod +x bin/phone-backend.js
```

```bash
npm link
```

### Step 4.4: Test Installation

```bash
phone-backend help
```

**You should see:**
```
📱 Phone Backend CLI

Commands:
  login   ...
  start   ...
  ...
```

✅ **CLI is installed!**

---

## PART 5: CREATE YOUR FIRST API (2 minutes)

### Step 5.1: Create API in Dashboard

1. **Visit your dashboard:**
   ```
   https://YOUR_USERNAME.github.io/phone-backend/
   ```

2. **Sign in** (if not already)

3. **Click:** "+ Create New API"

4. **Fill in:**
   - API Name: `My First API`
   - Description: `Testing my phone backend`

5. **Click:** "Create API"

6. **You'll see your API** listed with:
   - API URL
   - Your username
   - Created date

7. **Copy your username** (shown in the API card)

✅ **API Created!**

---

## PART 6: CONNECT PHONE TO API (3 minutes)

### Step 6.1: Login from Phone

In Termux on your phone:

```bash
phone-backend login YOUR_USERNAME
```
(Use the username from your dashboard!)

**You should see:**
```
✅ Logged in as: YOUR_USERNAME
Run "phone-backend start" to begin serving
```

### Step 6.2: Start Server

```bash
phone-backend start
```

**You should see:**
```
🚀 Phone Backend Starting...
📱 Username: YOUR_USERNAME
✅ Connected to routing service
✅ Authentication successful

🔗 Your API URL: https://your-routing-url.railway.app/api/u/YOUR_USERNAME

📊 Status: Online ✅
Press Ctrl+C to stop
```

✅ **Phone is connected!**

---

## PART 7: TEST YOUR API (2 minutes)

### Step 7.1: Make a Test Request

**On your computer**, open a new browser tab and visit:

```
https://YOUR-ROUTING-URL.railway.app/api/u/YOUR_USERNAME/test
```

**You should see:**
```json
null
```
(This is correct - the path /test doesn't exist yet!)

### Step 7.2: Create Some Data

**Try creating a todo:**

Open browser console (F12) and run:

```javascript
fetch('https://YOUR-ROUTING-URL.railway.app/api/u/YOUR_USERNAME/todos', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ title: 'My first todo!', done: false })
})
.then(r => r.json())
.then(data => console.log(data))
```

**You should see:**
```json
{
  "id": "1234567890",
  "title": "My first todo!",
  "done": false
}
```

### Step 7.3: Get Your Data

**Now visit:**
```
https://YOUR-ROUTING-URL.railway.app/api/u/YOUR_USERNAME/todos
```

**You should see your todo!**

✅ **API is WORKING!**

---

## 🎉 SUCCESS! YOU DID IT!

You now have:
- ✅ A live dashboard
- ✅ A working routing service
- ✅ Your phone as a backend server
- ✅ A functional API
- ✅ Data stored on your phone!

---

## 📱 KEEPING YOUR PHONE RUNNING

### Option 1: Use tmux (Recommended)

```bash
# Install tmux
pkg install tmux

# Start new session
tmux new -s backend

# Start server
phone-backend start

# Detach: Press Ctrl+B, then press D
# Now you can close Termux!

# To reattach later:
tmux attach -t backend
```

### Option 2: Use Wake Lock

```bash
# Install wake lock
pkg install termux-wake-lock

# Acquire lock
termux-wake-lock

# Start server in background
phone-backend start &
```

### Option 3: Auto-start on Boot

```bash
# Install Termux:Boot from F-Droid

# Create startup script
mkdir -p ~/.termux/boot
nano ~/.termux/boot/start-backend.sh

# Add this:
#!/data/data/com.termux/files/usr/bin/bash
termux-wake-lock
cd ~/phone-backend-cli
phone-backend start

# Save: Ctrl+X, then Y, then Enter

# Make executable
chmod +x ~/.termux/boot/start-backend.sh
```

---

## 🎯 USING YOUR API

### In Any Website:

```javascript
// GET data
fetch('https://your-routing-url/api/u/username/todos')
  .then(r => r.json())
  .then(data => console.log(data))

// CREATE data
fetch('https://your-routing-url/api/u/username/todos', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ title: 'New todo' })
})

// UPDATE data
fetch('https://your-routing-url/api/u/username/todos/123', {
  method: 'PATCH',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ done: true })
})

// DELETE data
fetch('https://your-routing-url/api/u/username/todos/123', {
  method: 'DELETE'
})
```

### In React:

```jsx
function MyApp() {
  const [todos, setTodos] = useState([]);

  useEffect(() => {
    fetch('https://your-routing-url/api/u/username/todos')
      .then(r => r.json())
      .then(data => setTodos(data))
  }, []);

  return (
    <div>
      {Object.entries(todos).map(([id, todo]) => (
        <div key={id}>{todo.title}</div>
      ))}
    </div>
  );
}
```

---

## 🐛 TROUBLESHOOTING

### Dashboard Issues

**Problem:** Can't see dashboard  
**Fix:** Make sure GitHub Pages is enabled and wait 2 minutes

**Problem:** Can't sign in  
**Fix:** Add `YOUR_USERNAME.github.io` to Firebase Authorized Domains

### Routing Service Issues

**Problem:** Health check returns error  
**Fix:** Check Railway deployment logs

**Problem:** API returns 503  
**Fix:** Make sure phone is running `phone-backend start`

### Phone Issues

**Problem:** Command not found  
**Fix:** Run `npm link` again in the `phone-backend-cli` folder

**Problem:** Can't connect  
**Fix:** Check internet connection and routing URL in code

**Problem:** Phone disconnects  
**Fix:** Use tmux or wake lock

---

## 📊 NEXT STEPS

Now that everything works:

1. **Build a real app** using your API
2. **Add more data** to your phone backend
3. **Share with friends** and help them set up
4. **Learn and experiment** with different features
5. **Build your portfolio** with real backend experience

---

## 🎓 WHAT YOU LEARNED

- ✅ Deploying to GitHub Pages
- ✅ Using Railway for backend services
- ✅ Firebase authentication
- ✅ WebSocket connections
- ✅ RESTful API design
- ✅ CLI tool development
- ✅ Full-stack development

---

## 📞 NEED HELP?

If something doesn't work:

1. **Re-read the step** you're stuck on
2. **Check the troubleshooting section**
3. **Make sure all URLs are updated** with YOUR values
4. **Verify each component** works independently

---

## ✅ FINAL CHECKLIST

- [ ] Dashboard live on GitHub Pages
- [ ] Can sign in with Google
- [ ] Routing service deployed on Railway
- [ ] Health check works
- [ ] CLI repository on GitHub
- [ ] CLI installed in Termux
- [ ] Created API in dashboard
- [ ] Phone connected successfully
- [ ] Test API request works
- [ ] Can create/read data

**If all checked:** CONGRATULATIONS! 🎉

You have a fully functional phone backend platform!

---

**Happy Building! 🚀**
