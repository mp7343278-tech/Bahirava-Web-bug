# 🔥 BAHIRAVA VIP PAIR BAN BOT

**Telegram + WhatsApp Hybrid Bot with Pairing Code & 24-Hour Ban System**

---

## 📋 Features

✅ **Telegram Integration** - Full bot control via Telegram
✅ **WhatsApp Pairing Code** - No QR scan needed, just a code!
✅ **24-Hour Ban System** - Ban numbers automatically
✅ **Auto-Unban** - Unbans after 24 hours
✅ **Ban List** - View all banned numbers
✅ **Report System** - Report issues to owner
✅ **Persistent Storage** - Ban list saved permanently

---

## 🚀 Installation

### 1. Install Dependencies
```bash
npm install telegraf whatsapp-web.js qrcode-terminal dotenv puppeteer
```

Or use the package.json:
```bash
npm install -f hybrid-bot-package.json
```

### 2. Configure Environment
```bash
cp .env.hybrid-bot .env
```

Edit `.env`:
```env
TELEGRAM_BOT_TOKEN=YOUR_BOT_TOKEN
OWNER_ID=YOUR_TELEGRAM_ID
```

### 3. Start the Bot
```bash
node bahirava-hybrid-bot.js
```

---

## 🎮 Commands

### Telegram Commands

| Command | Description |
|---------|-------------|
| `/start` | Start the bot |
| `/pair 94771234567` | Generate pairing code |
| `/confirm` | Confirm WhatsApp linking |
| `/menu` | Open main menu |
| `/help` | Get help |

### WhatsApp Commands

| Command | Usage | Description |
|---------|-------|-------------|
| `.menu` | `.menu` | Show all commands |
| `.ban NUMBER` | `.ban 94771234567` | Ban for 24 hours |
| `.banlist` | `.banlist` | View all banned numbers |
| `.bantime NUMBER` | `.bantime 94771234567` | Check remaining ban time |
| `.report TEXT` | `.report Bug found` | Report issue |
| `.myinfo` | `.myinfo` | Your information |
| `.help` | `.help` | Get this menu |

---

## 📱 How to Use

### Step 1: Get Pairing Code

**Telegram:**
```
/pair 94771234567
```

Bot will generate an 8-digit **Pairing Code**

### Step 2: Link WhatsApp

1. Open WhatsApp on your phone
2. Go to **Settings → Linked Devices**
3. Select **Link a Device**
4. Enter the **Pairing Code** from Telegram

### Step 3: Bot is Active!

Once linked, type in WhatsApp:
```
.menu
```

You'll see the menu!

---

## 🚫 Ban System

### Ban a Number (24 Hours)

**WhatsApp:**
```
.ban 94771234567
```

**Response:**
```
✅ 94771234567 BANNED!

⏱️ Duration: 24 hours
🔐 Status: Active
📅 Expires: In 24:00:00
```

### Check Ban List

```
.banlist
```

Shows all currently banned numbers and remaining time.

### Check Ban Time

```
.bantime 94771234567
```

Shows exact remaining ban time in hours, minutes, seconds.

---

## 🔑 Key Features Explained

### 1. **Pairing Code System**
- No QR code needed
- Get 8-digit code via Telegram
- Link via WhatsApp Settings
- Valid for 5 minutes

### 2. **24-Hour Ban**
```
.ban 94771234567
```
- Number is automatically banned
- Can't use WhatsApp features
- Auto-unbans after 24 hours
- Persistent storage

### 3. **Auto-Unban**
- System checks every minute
- Automatically removes expired bans
- No manual intervention needed

### 4. **Report System**
```
.report Your issue here
```
- Reports sent to owner via Telegram
- Tracked and managed

### 5. **Ban Persistence**
- Bans stored in `bot_data/banlist.json`
- Survives bot restarts
- Automatic cleanup

---

## 📂 File Structure

```
.
├── bahirava-hybrid-bot.js        # Main bot file
├── hybrid-bot-package.json       # Dependencies
├── .env.hybrid-bot               # Configuration
├── bot_data/
│   ├── banlist.json             # Banned numbers
│   └── pairings.json            # User pairings
└── README.md                     # This file
```

---

## ⚙️ Configuration

### .env File

```env
# Telegram Bot Token (get from @BotFather)
TELEGRAM_BOT_TOKEN=123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11

# Your Telegram ID (get from @userinfobot)
OWNER_ID=123456789
```

---

## 🔐 Security Notes

⚠️ **Warning:** This bot has powerful features. Use responsibly!

- Keep your Telegram Token secret
- Only ban numbers you actually want to ban
- 24-hour bans are automatic
- Owner can manage all users

---

## 🐛 Troubleshooting

### Bot Not Starting?
```bash
# Check if ports are available
# Check .env file is correctly configured
npm install -f
node bahirava-hybrid-bot.js
```

### Pairing Code Not Working?
- Code expires after 5 minutes
- Get a new code with `/pair` command again

### Ban Not Working?
```
.ban 94771234567
```
- Must include country code
- Number must be valid

### WhatsApp Not Connecting?
```bash
# Delete session and restart
rm -rf .wwebjs_auth
node bahirava-hybrid-bot.js
```

---

## 📊 Data Storage

### banlist.json
```json
{
  "94771234567": {
    "bannedAt": 1704067200000,
    "expiresAt": 1704153600000,
    "hours": 24
  }
}
```

### pairings.json
```json
{
  "123456789": {
    "number": "94771234567",
    "linkedAt": 1704067200000
  }
}
```

---

## 🚀 Deployment

### Heroku
```bash
heroku create bahirava-ban-bot
git push heroku main
```

### Railway
```bash
railway link
railway up
```

### VPS/Server
```bash
npm install -g pm2
pm2 start bahirava-hybrid-bot.js
pm2 save
pm2 startup
```

---

## 📞 Support

Report issues via `.report` command in WhatsApp

---

## 📜 License

MIT License - Use responsibly!

---

**Made with ❤️ by BAHIRAVA**
