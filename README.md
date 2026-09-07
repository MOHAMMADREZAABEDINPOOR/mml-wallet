<div align="center">

<!-- ============================================================================== -->
<!-- DYNAMIC ANIMATED CAPSULE HEADER                                                -->
<!-- ============================================================================== -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=1,12,24,30&height=220&section=header&text=MML%20Wallet&fontSize=42&fontAlignY=35&desc=%F0%9F%9B%91%20Archived%20Async%20Telegram%20Ledger%20%26%20Keep-Alive%20Engine&descFontSize=16&descAlignY=62" alt="MML Wallet Banner" width="100%" />

<!-- ============================================================================== -->
<!-- ANIMATED TYPING SVG TELEMETRY                                                 -->
<!-- ============================================================================== -->
<a href="https://github.com/MOHAMMADREZAABEDINPOOR/mml-wallet">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=2800&pause=1000&color=00D2FF&center=true&vCenter=true&width=780&lines=Project+Status%3A+Inactive+%2F+Archived+Ledger;High-Performance+Async+Telegram+Financial+Ledger+(Python+3.10%2B);Zero-Downtime+Cloud+PaaS+Keep-Alive+Engine+(Internal%2BExternal);Visual+Administrative+Flask+Web+Database+Console+(Port+5001);SQLite3+Double-Entry+Accounting+with+Write-Ahead+Logging;Strict+Rate-Limiter+Mitigating+Telegram+API+FloodWait+Limits;Bilingual+Interactive+Inline+Keyboards+(English+%26+Persian)" alt="Typing SVG" />
</a>

<br/>

<!-- ============================================================================== -->
<!-- BADGES MATRIX                                                                  -->
<!-- ============================================================================== -->
[![Project Status: Inactive / Archived](https://img.shields.io/badge/Status-Inactive%20%7C%20Archived-critical?style=for-the-badge&logo=archive)](https://github.com/MOHAMMADREZAABEDINPOOR)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg?style=for-the-badge&logo=gnu)](https://www.gnu.org/licenses/agpl-3.0)
[![Python: 3.10+](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![aiosqlite](https://img.shields.io/badge/Database-aiosqlite_Async-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://github.com/omnilib/aiosqlite)
[![Flask](https://img.shields.io/badge/Web_Console-Flask-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Telegram Bot API](https://img.shields.io/badge/Telegram_Bot_API-v21+-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://core.telegram.org/bots/api)
[![Read in Persian](https://img.shields.io/badge/مطالعه_به_فارسی-Persian_README-008080?style=for-the-badge)](#-بخش-فوقالعاده-مفصل-و-جامع-به-زبان-فارسی-persian-documentation)

<p align="center">
  <b>MML Wallet</b> is an asynchronous financial cryptocurrency and digital asset wallet bot for Telegram. Engineered with Python 3.10+ <code>asyncio</code> and <code>aiosqlite</code>, MML Wallet features multi-user double-entry accounting, internal and external keep-alive heartbeats designed specifically for free-tier PaaS cloud hosts (Render, Railway, Heroku), and a standalone administrative Flask web database console.
</p>

<!-- ============================================================================== -->
<!-- QUICK NAVIGATION ANCHORS                                                       -->
<!-- ============================================================================== -->
[Project Overview](#-project-overview--architecture) •
[Directory Anatomy](#-exhaustive-directory--file-anatomy) •
[Keep-Alive Engine](#-cloud-paas-keep-alive-engine) •
[Visual Web Console](#-visual-web-database-console-db_viewerpy) •
[Installation Guide](#-installation--quick-start) •
[Configuration](#-configuration--environment-variables) •
[توضیحات فارسی](#-بخش-فوقالعاده-مفصل-و-جامع-به-زبان-فارسی-persian-documentation) •
[Roadmap](#-strategic-engineering-roadmap) •
[License](#-copyleft-license--legal-attribution)

</div>

---

> [!CAUTION]
> ### 🛑 Project Status: Inactive / Archived (پروژه غیرفعال و بایگانی‌شده)
> **Notice**: This repository is currently **inactive** and maintained as an open-source architectural reference for asynchronous financial ledgers. The live Telegram bot is offline and not operating.
>
> **توجه مهم**: این پروژه در حال حاضر **کاملاً غیرفعال (Inactive / Archived)** است و سرور یا ربات مالی فعالی در تلگرام بر روی آن بالا نیست. سورس‌کد صرفاً جهت نمایش معماری فنی و حسابداری دوطرفه نگهداری می‌گردد.

## ⚡ Project Overview & Architecture

> *"Financial transactions demand absolute consistency. Running asynchronous ledger bots on free cloud containers requires continuous heartbeat orchestration to guarantee zero sleeping containers and zero dropped transactions."*

### The Free PaaS Deployment Challenge
Deploying 24/7 Telegram bots on modern free cloud platforms (Render, Railway, Heroku) presents a major hurdle: **Inactivity Sleep Policies**. After 15 minutes of zero inbound HTTP traffic, containers are paused, rendering the Telegram polling loop unresponsive until manually restarted.

### The MML Wallet Solution
**MML Wallet** pairs an enterprise financial ledger with an active keep-alive architecture:
- 💼 **Double-Entry Asynchronous Ledger**: Over 2,500 lines of robust Python handling peer-to-peer transfers, deposits, withdrawals, and balance verification.
- 💓 **Dual Keep-Alive Engine**:
  - Internal event-loop heartbeat running every 10 minutes.
  - External synthetic HTTP ping running every 5 minutes to satisfy cloud host traffic monitors.
- 🖥️ **Browser Database Console (`db_viewer.py`)**: Built-in Flask management server allowing administrators to inspect users, balances, and audit logs without SQLite desktop tools.

---

## 📂 Exhaustive Directory & File Anatomy

```
d:/code/mml wallet/
│
├── main.py                          # Master application: 2,500+ lines of async bot logic, handlers & ledger engine
├── db_viewer.py                     # Standalone Flask administrative web database management console (port 5001)
├── env.example                      # Template environment variables manifest with documented defaults
├── requirements.txt                 # Dependencies (python-telegram-bot[rate-limiter], aiosqlite, flask, requests)
├── README.md                        # Master comprehensive bilingual documentation
├── README_KEEPALIVE.md              # Technical whitepaper on the internal/external ping engine
│
└── data/ (Auto-initialized at runtime)
    ├── bot.db                       # Primary SQLite database file
    ├── bot.db-wal                   # Write-Ahead Log ensuring non-blocking concurrent writes
    └── bot.db-shm                   # Shared memory index for WAL operations
```

---

## 💓 Cloud PaaS Keep-Alive Engine

```
┌─────────────────────────────────────────────────────────────────────────┐
│                           MML Wallet Bot Core                           │
└────────────────────────────────────┬────────────────────────────────────┘
                                     │
           ┌─────────────────────────┴─────────────────────────┐
           ▼                                                   ▼
┌─────────────────────────────────────┐     ┌─────────────────────────────────────┐
│       Internal Loop Heartbeat       │     │          External HTTP Ping         │
│                                     │     │                                     │
│ • Runs every 10 minutes             │     │ • Runs every 5 minutes              │
│ • Cycles asyncio event loop         │     │ • Dispatches GET to public endpoint │
│ • Executes garbage collection       │     │ • Satisfies cloud inactivity timers │
│ • Prevents thread freezing          │     │ • Guarantees 24/7 dyno uptime       │
└─────────────────────────────────────┘     └─────────────────────────────────────┘
```

---

## 🖥️ Visual Web Database Console (`db_viewer.py`)

Executing `python db_viewer.py` initiates a lightweight administrative management portal accessible at `http://localhost:5001`:
- **Real-Time Tables**: Inspect user balances, registered Telegram IDs, and complete transaction histories.
- **Search & Filter**: Find any user by numeric ID or username without installing SQLite browser software.
- **Zero Configuration**: Reads directly from `bot.db` in WAL mode without locking the running bot.

---

## ⚙️ Configuration & Environment Variables

| Variable | Type | Default Value | Description |
| :--- | :---: | :---: | :--- |
| `BOT_TOKEN` | `string` | `""` | Telegram Bot Token obtained from [@BotFather](https://t.me/BotFather). |
| `ADMIN_CHAT_ID` | `int` | `0` | Numeric Telegram ID of the master administrator. |
| `COLLECTION_WALLET` | `string` | `""` | Master treasury wallet address for incoming deposits. |
| `DATABASE_URL` | `string` | `bot.db` | Local filesystem path to the SQLite relational database. |
| `ENABLE_KEEP_ALIVE` | `bool` | `true` | Toggles the internal heartbeat and external HTTP ping scheduler. |
| `PING_URL` | `string` | `""` | Public URL of your deployed application (e.g. on Render or Railway). |
| `PING_INTERVAL` | `int` | `300` | Frequency in seconds between external HTTP pings (default: 5 min). |

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

# Setup environment configuration
cp env.example .env
# Edit .env and supply your BOT_TOKEN and ADMIN_CHAT_ID

# Run the Telegram bot daemon:
python main.py

# In a separate terminal, launch the web database console:
python db_viewer.py
```
Open `http://localhost:5001` in your browser to inspect database tables.

---

## 🇮🇷 بخش فوق‌العاده مفصل و جامع به زبان فارسی (Persian Documentation)

> ⚠️ **وضعیت پروژه: کاملاً غیرفعال (Inactive / Archived)**
> این پروژه و بات‌های مربوطه در حال حاضر غیرفعال بوده و عملیاتی نیستند؛ سورس‌کد کامل پروژه صرفاً برای اهداف آموزشی، پژوهشی و استفاده به عنوان مرجع متن‌باز در دسترس قرار دارد.

### ۱. مقدمه و چرایی ساخت ربات کیف پول MML Wallet
پروژه **MML Wallet** یک سامانه پیشرفته مدیریت امور مالی، کیف پول دیجیتال و دفترکل تراکنش‌های همتا به همتا (P2P) در پیام‌رسان تلگرام است که به زبان پایتون مدرن و با معماری کاملاً ناهمگام (**Asyncio**) و پایگاه‌داده **aiosqlite** مهندسی شده است.

یکی از بزرگترین مشکلات اجرای ربات‌های تلگرام بر روی هاست‌های ابری و رایگان (مانند Render، Railway یا Heroku)، خاموش شدن یا خوابیدن سرور (Server Sleep) پس از چند دقیقه بی‌کاری است که باعث عدم پاسخ‌دهی ربات به پیام‌های کاربران می‌شود. ربات MML Wallet با پیاده‌سازی سیستم هوشمند Keep-Alive (پینگ مداوم داخلی و خارجی) این مشکل را به طور کامل حل کرده و به صورت ۲۴ ساعته و بدون وقفه فعال می‌ماند.

---

### ۲. تشریح ساختار فایل‌های پروژه
- **`main.py`**: بیش از ۲۵۰۰ سطر کد پایتون بهینه شامل مدیریت ثبت‌نام کاربران، سیستم شارژ حساب، انتقال وجه، اعتبارسنجی موجودی و سیستم ضد اسپم Rate-Limiter.
- **`db_viewer.py`**: پنل وب اختصاصی بر پایه میکرو فریم‌ورک Flask که دیتابیس را روی پورت ۵۰۰۱ به صورت گرافیکی نمایش می‌دهد تا مدیر بدون نیاز به نرم‌افزارهای جانبی بتواند موجودی‌ها را کنترل کند.
- **`bot.db`**: پایگاه‌داده SQLite در حالت مدرن WAL (Write-Ahead Logging) که امکان خواندن و نوشتن همزمان تراکنش‌ها بدون قفل شدن دیتابیس را تضمین می‌کند.

---

## 🗺️ Strategic Engineering Roadmap

- [x] **v1.0**: Core async ledger, deposit/transfer handlers, SQLite WAL persistence.
- [x] **v1.5**: Dual keep-alive ping engine, standalone Flask web database console.
- [ ] **v2.0**: Direct cryptocurrency blockchain payment gateway (TRON USDT TRC-20 & TON Network).
- [ ] **v2.5**: Automated Telegram Invoice API integration with multi-currency conversion.
- [ ] **v3.0**: Decentralized escrow smart contracts for secure peer-to-peer transactions.

---

## 📜 Copyleft License & Legal Attribution

Distributed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.  
Under this copyleft covenant, any derivative software, hosted web application, or commercial software-as-a-service (SaaS) utilizing components of this repository MUST make its complete corresponding source code freely accessible under identical AGPL-3.0 terms.

---

<div align="center">

<!-- ============================================================================== -->
<!-- ANIMATED CAPSULE FOOTER                                                        -->
<!-- ============================================================================== -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=1,12,24,30&height=120&section=footer" alt="Footer" width="100%" />

<sub>Architected with dedication by <a href="https://github.com/MOHAMMADREZAABEDINPOOR"><b>MOHAMMADREZA ABEDINPOOR</b></a>. If MML Wallet powers your financial workflows, consider leaving a ⭐!</sub>

</div>
