<div align="center">

# 💳 PIMX_WALLET_BOT ⚡📊

### Asynchronous Telegram Financial Wallet Bot with Cloud Keep-Alive & Visual Web Database Viewer

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)
[![Python: 3.10+](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![aiosqlite](https://img.shields.io/badge/Database-aiosqlite_Async-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://github.com/omnilib/aiosqlite)
[![Flask](https://img.shields.io/badge/Web_Viewer-Flask-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Read in Persian](https://img.shields.io/badge/مطالعه_به_فارسی-Persian_README-008080?style=for-the-badge)](#-توضیحات-فارسی-persian-description)

<p align="center">
  A feature-packed Telegram digital wallet bot built on asyncio and aiosqlite. Features multi-user ledger management, internal and external keep-alive ping mechanisms tailored for free PaaS hosts (Render, Railway, Heroku), and a standalone Flask administrative database viewer.
</p>

[Key Features](#-key-features) •
[Keep-Alive Architecture](#-keep-alive-architecture) •
[Quick Start](#-quick-start) •
[توضیحات فارسی](#-توضیحات-فارسی-persian-description) •
[License](#-license)

</div>

---

## ⚡ Key Features

- 💼 **Asynchronous Ledger Accounting**: Complete user balance, deposit, transfer, and transaction history tracking backed by `aiosqlite`.
- 💓 **Cloud PaaS Keep-Alive Engine**:
  - Heartbeat scheduler prevents cloud containers from sleeping during periods of inactivity.
  - Optional external self-ping mechanism to satisfy cloud HTTP traffic requirements.
- 🖥️ **Visual Web Database Inspector (`db_viewer.py`)**: Lightweight web-based visual management console to inspect user tables, balances, and audit trails without external SQLite tools.
- 🛡️ **Graceful Concurrency & Rate Limiting**: Built with Telegram RateLimiter to prevent flood limits and API throttling.

---

## 💓 Keep-Alive Architecture

Designed specifically to run 24/7 on free-tier container platforms:
1. **Internal Heartbeat**: Runs every 10 minutes to cycle the asyncio event loop and clear garbage collection.
2. **External HTTP Ping**: Pings the application endpoint every 5 minutes to keep worker dynos active.

---

## 🚀 Quick Start

### 1. Prerequisites
- Python 3.10+
- Telegram Bot Token from [@BotFather](https://t.me/BotFather)

### 2. Installation
```bash
git clone https://github.com/MOHAMMADREZAABEDINPOOR/PIMX_WALLET_BOT.git
cd PIMX_WALLET_BOT

python -m venv venv
source venv/bin/activate  # Windows: .\venv\Scripts\activate
pip install -r requirements.txt

# Configure environment
cp env.example .env
# Edit .env and supply your BOT_TOKEN and ADMIN_IDS
```

### 3. Execution
```bash
# Run the Telegram Bot
python main.py

# In another terminal, run the Visual Database Viewer (Optional)
python db_viewer.py
```
Open `http://localhost:5001` to view the SQLite tables.

---

## 🇮🇷 توضیحات فارسی (Persian Description)

### معرفی ربات کیف پول PIMX_WALLET_BOT
ربات **PIMX_WALLET_BOT** یک سیستم کیف پول دیجیتال غیرهمزمان (Async) برای تلگرام است که با **Python** و پایگاه‌داده **aiosqlite** توسعه یافته و مجهز به سیستم زنده نگه‌دارنده (Keep-Alive) برای هاست‌های ابری رایگان است.

### امکانات ویژه:
1. **مدیریت تراکنش‌ها و موجودی:**
   * ثبت تراکنش‌ها، سوابق واریز، برداشت و انتقال وجه داخلی بین کاربران.
2. **سیستم Keep-Alive اختصاصی:**
   * جلوگیری از خاموش شدن و Sleep رفتن ربات در پلتفرم‌های ابری مانند Render و Railway.
3. **نمایشگر بصری دیتابیس تحت وب (`db_viewer.py`):**
   * پنل وب جمع‌وجور با فلسک برای مشاهده رکوردهای دیتابیس، موجودی کاربران و تراکنش‌ها در مرورگر.

---

## 📜 License & Copyleft

This project is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

> **Copyright (c) 2026 MOHAMMADREZA ABEDINPOOR.**  
> Distribution or hosting must provide complete source code under identical AGPL-3.0 terms.

---

<div align="center">
  <sub>Developed by <a href="https://github.com/MOHAMMADREZAABEDINPOOR">MOHAMMADREZA ABEDINPOOR</a>. Don't forget to ⭐!</sub>
</div>
