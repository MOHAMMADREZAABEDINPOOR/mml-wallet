<div align="center">

# 💳 MML Wallet ⚡📊
### High-Performance Asynchronous Telegram Wallet Bot with Cloud Keep-Alive & Visual Web Database Console

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)
[![Python: 3.10+](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![aiosqlite](https://img.shields.io/badge/Database-aiosqlite_Async-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://github.com/omnilib/aiosqlite)
[![Flask](https://img.shields.io/badge/Web_Console-Flask-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Read in Persian](https://img.shields.io/badge/مطالعه_به_فارسی-Persian_README-008080?style=for-the-badge)](#-توضیحات-فوقالعاده-جامع-فارسی-persian-documentation)

<p align="center">
  A multi-user financial digital ledger and cryptocurrency wallet bot for Telegram. Powered by Python 3.10+ <code>asyncio</code> and <code>aiosqlite</code>, featuring dual-layer cloud keep-alive heartbeats tailored for free PaaS tiers (Render, Railway, Heroku), and an administrative Flask database management console.
</p>

[Project Overview](#-project-overview--architecture) •
[Directory Structure](#-directory--file-structure) •
[Keep-Alive Engine](#-cloud-keep-alive-engine) •
[Web Database Viewer](#-visual-web-database-viewer-db_viewerpy) •
[Installation Guide](#-installation--quick-start) •
[توضیحات فارسی](#-توضیحات-فوقالعاده-جامع-فارسی-persian-documentation) •
[License](#-license)

</div>

---

## 🎯 Project Overview & Architecture

Deploying 24/7 financial bots on free cloud PaaS tiers (Render, Railway, Heroku) often leads to containers being suspended due to inactivity, disrupting automated transactions.

**MML Wallet** solves this with an integrated resilience layer:
- **Asynchronous Double-Entry Ledger**: Handles concurrent transfers and deposits safely via SQLite WAL mode and `aiosqlite`.
- **Active Keep-Alive Scheduler**: Cycles event loops and fires periodic external pings to prevent cloud dynos from idling.
- **Standalone Web DB Viewer (`db_viewer.py`)**: Provides a zero-dependency Flask administrative web console to inspect user balances, audit trails, and transaction tables directly in your browser.

---

## 📂 Directory & File Structure

```
mml wallet/
│
├── main.py                          # 2500+ lines of robust async Telegram bot logic & ledger handlers
├── db_viewer.py                     # Standalone Flask administrative web database management console
├── env.example                      # Template environment variable configuration file
├── requirements.txt                 # Python dependencies (python-telegram-bot, aiosqlite, flask, requests)
├── README.md                        # Master comprehensive bilingual documentation
├── README_KEEPALIVE.md              # Technical specifications for the internal/external ping engine
│
└── data/ (Auto-created)
    ├── bot.db                       # Primary SQLite relational database file
    ├── bot.db-wal                   # Write-Ahead Log ensuring non-blocking concurrent reads/writes
    └── bot.db-shm                   # Shared memory index for WAL operations
```

---

## 💓 Cloud Keep-Alive Engine

```
┌────────────────────────────────────────────────────────┐
│                   MML Wallet Core                      │
└──────────────────────────┬─────────────────────────────┘
                           │
             ┌─────────────┴─────────────┐
             ▼                           ▼
┌──────────────────────────┐ ┌──────────────────────────┐
│   Internal Heartbeat     │ │    External HTTP Ping    │
│  - Interval: 10 minutes  │ │  - Interval: 5 minutes   │
│  - Clears GC & memory    │ │  - Pings public URL      │
│  - Prevents async freeze │ │  - Satisfies cloud dyno  │
└──────────────────────────┘ └──────────────────────────┘
```

---

## 🖥️ Visual Web Database Viewer (`db_viewer.py`)

Run `python db_viewer.py` alongside the bot to launch a browser-accessible inspection dashboard at `http://localhost:5001`:
- Real-time tabular view of users, balances, and pending transfers.
- Search and filter records without installing external SQLite GUI software.

---

## ⚙️ Configuration & Environment Variables

| Variable | Type | Default | Description |
| :--- | :---: | :---: | :--- |
| `BOT_TOKEN` | `string` | `""` | Telegram Bot Token obtained from [@BotFather](https://t.me/BotFather). |
| `ADMIN_CHAT_ID` | `int` | `0` | Numeric Telegram ID of the administrator. |
| `DATABASE_URL` | `string` | `bot.db` | Path to local SQLite database file. |
| `ENABLE_KEEP_ALIVE` | `bool`| `true` | Toggles the internal heartbeat and external ping engine. |
| `PING_URL` | `string` | `""` | Public endpoint URL to ping periodically. |

---

## 🚀 Installation & Quick Start

```bash
git clone https://github.com/MOHAMMADREZAABEDINPOOR/mml-wallet.git
cd mml-wallet

python -m venv venv
# Windows:
.\venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt

# Setup environment
cp env.example .env
# Edit .env with your BOT_TOKEN

# Run bot
python main.py

# In separate terminal, run web database console:
python db_viewer.py
```

---

## 🇮🇷 توضیحات فوق‌العاده جامع فارسی (Persian Documentation)

### ۱. معرفی پروژه ربات کیف پول MML Wallet
پروژه **MML Wallet** یک ربات پیشرفته تلگرام برای مدیریت امور مالی، کیف پول دیجیتال و تراکنش‌های همتا به همتا (P2P) است که با پایتون ناهمگام (**Asyncio**) و پایگاه‌داده **aiosqlite** مهندسی شده است. یکی از بزرگترین چالش‌های اجرای ربات روی هاست‌های ابری رایگان (مثل Render و Railway)، خاموش شدن یا خوابیدن (Sleep) سرور پس از چند دقیقه بی‌کاری است. این پروژه با سیستم هوشمند Keep-Alive این مشکل را برای همیشه برطرف کرده است.

---

### ۲. تشریح ساختار فایل‌های پروژه
- **`main.py`**: بیش از ۲۵۰۰ سطر کد استاندارد شامل هندلرهای ثبت‌نام، واریز، برداشت، انتقال موجودی بین کاربران و سیستم ریت‌لیمیت.
- **`db_viewer.py`**: پنل وب اختصاصی بر پایه فلسک برای مشاهده و مدیریت زنده جداول دیتابیس در مرورگر وب بدون نیاز به نرم‌افزارهای جانبی.
- **`bot.db`**: پایگاه‌داده سبک و فوق‌العاده سریع SQLite در حالت WAL برای ثبت امن تراکنش‌ها.

---

## 📜 License

Distributed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

---

<div align="center">
  <sub>Engineered by <a href="https://github.com/MOHAMMADREZAABEDINPOOR">MOHAMMADREZA ABEDINPOOR</a>. Leave a ⭐ to support open financial tools!</sub>
</div>
