# 📨 APOSTLE Mailer — Easy Installation Guide

Welcome to **APOSTLE Mailer**, a tool for sending advanced email campaigns with Node.js.  
Follow these simple steps to install and run it.

---

## ✅ What You Need

Before starting, make sure you have:
- A computer with **Ubuntu / macOS / Windows**
- **Node.js v20.19.5**
- **npm v10.8.2**

Check if you already have them by typing in your terminal:
```bash
node -v
npm -v
```

If the versions don’t match, follow the steps below.

---

## 📦 Step 1: Extract the ZIP File

If you downloaded a ZIP file of the project, extract it first.  
Then open your terminal and go inside the extracted folder:

```bash
cd APOSTLE
```

Your folder should contain files like `apostle.js` and `package.json`.

---

## ⚙️ Step 2: Install Node.js and npm

### 🐧 For Ubuntu / Linux
```bash
sudo apt update
sudo apt install -y curl
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
sudo npm install -g npm@10.8.2
```

### 🍎 For macOS
```bash
brew install node@20
npm install -g npm@10.8.2
```

### 🪟 For Windows
1. Go to [https://nodejs.org/en/download/prebuilt-installer](https://nodejs.org/en/download/prebuilt-installer)
2. Download **Node.js v20.19.5** and install it.
3. After that, open PowerShell and type:
   ```bash
   node -v
   npm -v
   ```

---

## 🧰 Step 3: Install Project Dependencies

Once you’re in the `APOSTLE` folder, run:

```bash
npm install
```

This will automatically install everything needed to run the mailer.

If you get any error, try:
```bash
npm cache clean --force
npm install
```

---

## 🚀 Step 4: Start the Mailer

After installation finishes, start the program with:

```bash
node apostle.js
```

You’ll see something like this:
```
🚀 APOSTLE Mailer started!
📧 Ready to send campaigns!
```

If you want it to restart automatically when editing files, install **nodemon**:
```bash
npm install -g nodemon
nodemon apostle.js
```

---

## 💡 Common Issues

| Problem | Fix |
|----------|-----|
| Modules missing | Run `npm install` again |
| Permission error | Try `sudo node apostle.js` (Linux/macOS) |
| Port already used | Change the port in `.env` or config file |
| Puppeteer Chrome error | Run `npx puppeteer browsers install chrome` |

---

## ❤️ Credits

Made by **PRIV8 / APOSTLE Team**  
Enjoy building and sending smarter campaigns!

