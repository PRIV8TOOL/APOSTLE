# 📨 APOSTLE Mailer — Complete Guide

Welcome to the **APOSTLE Mailer**, a powerful yet beginner-friendly Node.js tool for managing and sending professional email campaigns.  
This guide helps you **install, configure, and use** APOSTLE from start to finish — even if you’ve never used Node.js before.

---

## ⚡ Quick Start

If you just want to get started right away:

1️⃣ **Extract** the ZIP file you downloaded  
2️⃣ **Open Terminal / CMD** and go inside the project folder  
3️⃣ **Install Node.js v20.19.5** and **npm v10.8.2**  
4️⃣ Run:
```bash
npm install
node apostle.js
```

That’s it! 🎉 You’re ready to start sending.

---

## 📚 Table of Contents
- [🧭 Introduction](#-introduction)
- [🪜 Installation Guide](#-installation-guide)
- [✉️ Example Email Template](#-example-email-template)
- [🧩 Placeholder Functions Reference](#-placeholder-functions-reference)
- [⚙️ Configuration Settings Reference](#-configuration-settings-reference)
- [❤️ Credits](#-%EF%B8%8F-credits)

---

## 🧭 Introduction

**APOSTLE Mailer** is designed for easy, flexible, and secure bulk email sending.  
It includes built-in placeholder support, templating, PDF/HTML/EML attachments, random data generation, and multi-threaded SMTP rotation.

Whether you’re sending newsletters or automated campaigns — APOSTLE helps you do it faster, safer, and smarter.

---

## 🪜 Installation Guide

### 1. Extract the ZIP File
After downloading the ZIP file, extract it and open a terminal inside the extracted folder:

```bash
cd APOSTLE
```

### 2. Install Node.js and npm

#### 🐧 For Ubuntu / Linux
```bash
sudo apt update
sudo apt install -y curl
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
sudo npm install -g npm@10.8.2
```

#### 🍎 For macOS
```bash
brew install node@20
npm install -g npm@10.8.2
```

#### 🪟 For Windows
1. Download Node.js v20.19.5 from: [https://nodejs.org/en/download/prebuilt-installer](https://nodejs.org/en/download/prebuilt-installer)
2. Install it, then open PowerShell and verify:
```bash
node -v
npm -v
```

### 3. Install Dependencies
Once inside the project folder, run:
```bash
npm install
```
If you see any errors, try:
```bash
npm cache clean --force
npm install
```

### 4. Start the Mailer
Run:
```bash
node apostle.js
```

---

## ✉️ Example Email Template

Here’s a simple HTML example that uses placeholders:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Welcome, [{name}]!</title>
</head>
<body style="font-family: Arial, sans-serif; color: #333;">
  <h2>Hello [{name}],</h2>
  <p>We're excited to have you at <b>[{company}]</b>!</p>
  <p>Your registered email is <b>[{email}]</b>.</p>
  <p>Click below to verify your account:</p>
  <a href="[{link}]" style="background:#0078D4; color:white; padding:10px 15px; border-radius:4px; text-decoration:none;">Verify Now</a>
  <br><br>
  <small>Sent on [{date}] at [{time}]</small>
</body>
</html>
```

💡 You can combine placeholders freely inside your email content, subject, or attachments.

---

## 🧩 Placeholder Functions Reference

Below are all placeholders supported in APOSTLE Mailer, grouped by category.

### 🧍 Recipient-Based Placeholders
| Placeholder | Description | Type |
|--------------|-------------|------|
| `[{email}]` | The full recipient email address. | Recipient |
| `[{email64}]` | Base64 encoded recipient email. | Recipient |
| `[{email64_urlencode}]` | URL-safe Base64 encoded email. | Recipient |
| `[{email_sec}]` | Partially masked email (e.g. jo*****@gm***.com). | Recipient |
| `[{user}]` | The part of the email before the @ sign. | Recipient |
| `[{domain}]` | The domain part of the email. | Recipient |
| `[{name}]` | Best guess full name (e.g. "john.doe" → "John Doe"). | Recipient |
| `[{company}]` | Best guess company name from domain. | Recipient |

### 📨 Sender & SMTP Placeholders
| Placeholder | Description | Type |
|--------------|-------------|------|
| `[{frommail}]` | The "From" email address used. | Sender |
| `[{fromname}]` | The "From Name" used. | Sender |
| `[{subject}]` | Subject line used for send. | Sender |
| `[{smtp_user}]` | SMTP username in use. | SMTP |
| `[{smtp_server}]` | SMTP server hostname. | SMTP |
| `[{smtpdomain}]` | Domain part of "From" email. | Sender |

### 🕓 Date & Time Placeholders
| Placeholder | Description | Type |
|--------------|-------------|------|
| `[{date}]` | Current full date (e.g. "Wednesday, October 9, 2025"). | Date/Time |
| `[{date_tomorrow}]` | Tomorrow’s date. | Date/Time |
| `[{time}]` | Current time (24-hour). | Date/Time |
| `[{year}]` | Current 4-digit year. | Date/Time |
| `[{microtime}]` | Unix timestamp in milliseconds. | Date/Time |

### 🎲 Random String Generators
| Placeholder | Description | Type |
|--------------|-------------|------|
| `[{randstring10}]` | Random letters (10 chars). | Random |
| `[{randstringnum20}]` | Random letters + numbers (20 chars). | Random |
| `[{number6}]` | Random numbers (6 digits). | Random |
| `[{symbls8}]` | Random symbols (8 chars). | Random |

### 🧠 Faker.js Data Generators
| Placeholder | Description | Type |
|--------------|-------------|------|
| `[{data_name}]` | Random full name. | Faker.js |
| `[{data_address}]` | Random street address. | Faker.js |
| `[{data_company}]` | Random company name. | Faker.js |
| `[{data_job}]` | Random job title. | Faker.js |
| `[{data_ipv4}]` | Random IPv4 address. | Faker.js |
| `[{data_uuid}]` | Random UUID. | Faker.js |
| `[{country}]` | Random country. | Faker.js |
| `[{data_phone_number}]` | Random phone number. | Faker.js |
| `[{data_domain_name}]` | Random domain name. | Faker.js |
| `[{data_company_email}]` | Random company email. | Faker.js |
| `[{data_image_url}]` | Random image URL. | Faker.js |
| `[{data_mac_address}]` | Random MAC address. | Faker.js |
| `[{data_md5}]` | Random MD5 hash. | Faker.js |
| `[{data_sha1}]` | Random SHA1 hash. | Faker.js |
| `[{data_sha256}]` | Random SHA256 hash. | Faker.js |

### ⚡ Special & Dynamic Placeholders
| Placeholder | Description | Type |
|--------------|-------------|------|
| `[{link}]` | Main link from config. | Dynamic |
| `[{ulogo}]` | Embeds company logo. | Dynamic |
| `[{qr}]` | Embeds QR code pointing to `[{link}]`. | Dynamic |

---

## ⚙️ Configuration Settings Reference

Below are the main config options supported by APOSTLE Mailer.

Each config variable is defined in your `.env` or config file.

| Category | Setting | Description | Placeholders? |
|-----------|----------|--------------|----------------|
| License & General | `TOKEN` | Your Apostle Mailer license key. | No |
| | `THREADS` | Number of concurrent email threads. | No |
| | `SMTP_TIMEOUT` | How long to wait for SMTP server response `(in ms)`. | No |
| | `TIMEZONE` | Timezone for date/time placeholders `(e.g., America/New_York)`. | No |
| Recipients & Content | `MAILLIST_FILE` | File containing recipient emails (one per line). | No |
| | `SUBJECT` | Subject line of the email `(supports placeholders)`. | Yes |
| | `FROM_NAME` | Sender name `(can use placeholders or multiple values)`. | Yes |
| | `LINK` | Main URL used in `[{link}]` and `[{qr}]`. | Yes |
| Attachments | `ATTACH_PDF_FILENAME` | Generates a PDF attachment. | Yes |
| | `ATTACH_SVG_FILENAME` | Generates an SVG attachment. | Yes |
| | `ATTACH_DOCX_FILENAME` | Generates a DOCX attachment. | Yes |
| | `ATTACH_RTF_FILENAME` | Generates an RTF attachment. | Yes |
| SMTP Settings | `SMTP_LIST_FILE` | Path to SMTP credentials file. | No |
| | `SMTP_ROTATION_MODE` | Rotation mode: `(ROTATE/QUEUE/RANDOM)`. | No |
| | `SMTP_QUEUE_LIMIT` | Number of emails per SMTP in queue mode. | No |
| | `SMTP_POOL_ENABLED` | Enables SMTP connection pooling. | No |
| Logo & QR | `USE_MICROSOFT_LOGO` | If true, uses Microsoft logo. | No |
| | `ULOGO_MODE` | Embedding mode `(cid/base64)`. | No |
| | `QR_MODE` | QR embedding mode. | No |
| Testing | `TEST_EMAIL` | Email to receive test messages. | No |
| | `TELEGRAM_BOT_TOKEN` | Token for Telegram tracking bot. | No |
| | `TELEGRAM_CHAT_ID` | Chat ID for Telegram notifications. | No |

---

## ❤️ Credits

Developed by **PRIV8 / APOSTLE Team** with passion and precision.  
For support or contributions, feel free to open an issue on the official GitHub repository.

> ✉️ *“Apostle Mailer — built for reliability, flexibility, and speed.”*  
