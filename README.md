<div align="center">

<img src="assets/readme/hero.gif" width="1200" alt="MML WALLET: a Telegram wallet with stacked coins and a transaction receipt" />

**[English](README.md) · [فارسی](README.fa.md)**

</div>

# 👛 MML WALLET

A Telegram wallet/collection bot with asynchronous SQLite storage, configurable administrative settings, a keep-alive helper and a Flask database viewer.

[GitHub](https://github.com/MOHAMMADREZAABEDINPOOR/mml-wallet) · [PIMX / Profile](https://github.com/MOHAMMADREZAABEDINPOOR) · [Static artwork](assets/readme/hero.png)

| At a glance | Details |
|:---|:---|
| 👛 Experience | Telegram bot and its supporting tools |
| 🧰 Built with | `python-telegram-bot[rate-limiter]==21.6` · `aiosqlite==0.20.0` · `flask==3.0.3` · `requests==2.32.3` |
| 🌐 Documentation | [English](README.md) · [فارسی](README.fa.md) |

[✨ Features](#features) · [🚀 Getting started](#getting-started) · [⚙️ Configuration](#configuration) · [🌍 Deployment](#deployment)

---

<a id="features"></a>

## ✨ Features

| Area | Included capability |
|:---|:---|
| 🗄️ Data | Async Telegram handlers and SQLite persistence |
| 👤 Accounts | Collection wallet and administrator configuration |
| 🔌 Integration | Optional keep-alive service for hosting |
| 🌐 Experience | Separate Flask viewer for local database inspection |

<a id="stack"></a>

## 🧰 Stack

| Tool | Version / source |
|---|---|
| python-telegram-bot[rate-limiter]==21.6 | `requirements.txt` |
| aiosqlite==0.20.0 | `requirements.txt` |
| flask==3.0.3 | `requirements.txt` |
| requests==2.32.3 | `requirements.txt` |

<a id="getting-started"></a>

## 🚀 Getting started

Python 3; a desktop/Tk installation for Tkinter or turtle examples. Tkinter is provided by the Python installation, not pip. Legacy dependencies may need a compatible Python version.

```bash
git clone https://github.com/MOHAMMADREZAABEDINPOOR/mml-wallet.git
cd mml-wallet

python -m venv .venv
# Windows: .venv\Scripts\Activate.ps1; macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
# Copy env.example to .env and configure BOT_TOKEN
python main.py
```

<a id="configuration"></a>

## ⚙️ Configuration

These names are found in the example configuration or source; not all are required. Check their defaults/usage in those files and supply secrets only in your local or hosting environment.

| Name | Role |
|---|---|
| `ADMIN_CHAT_ID` | Application setting; inspect its definition |
| `BOT_DB_PATH` | Application setting; inspect its definition |
| `BOT_TOKEN` | Credential/connection setting; keep private |
| `COLLECTION_WALLET` | Application setting; inspect its definition |
| `CONTACT_EMAIL` | Application setting; inspect its definition |
| `DATABASE_URL` | Credential/connection setting; keep private |
| `ENABLE_KEEP_ALIVE` | Application setting; inspect its definition |
| `MODE` | Application setting; inspect its definition |
| `PING_INTERVAL` | Application setting; inspect its definition |
| `PING_URL` | Application setting; inspect its definition |
| `PORT` | Application setting; inspect its definition |
| `TOKEN_LIMIT` | Credential/connection setting; keep private |
| `WEBHOOK_URL` | Application setting; inspect its definition |

<a id="usage"></a>

## 🎯 Usage

Copy env.example to .env and configure BOT_TOKEN plus collection/admin settings. Run main.py. Use db_viewer.py only on a trusted local interface to inspect a development database.

<a id="project-structure"></a>

## 🗂️ Project structure

| Path | Role |
|---|---|
| [`assets/`](assets/) | Brand/media/README assets |
| [`db_viewer.py`](db_viewer.py) | Project entry/configuration file |
| [`main.py`](main.py) | Project entry/configuration file |

<a id="commands-and-checks"></a>

## 🧪 Commands and checks

No automated test command is declared in a manifest. Verify behavior through a local example run.

<a id="deployment"></a>

## 🌍 Deployment

Host a long-running bot process with environment secrets and private storage. Run a single polling instance. Check network access and dependency compatibility on the host.

<a id="limitations"></a>

## 📌 Limitations

The source does not establish audited accounting, custody or transaction guarantees. The viewer can expose user records if made public. Keep-alive requests do not guarantee hosting uptime.

<a id="troubleshooting"></a>

## 🛠️ Troubleshooting

- Authentication/provider errors: verify credentials and selected model/provider.
- No Telegram updates: check polling/webhook mode and concurrent bot instances.
- Missing dependencies: use the declared manifest or inspect imports if no manifest is provided.

<a id="contributing"></a>

## 🤝 Contributing

Create a focused branch, verify the affected behavior and explain the change clearly. Keep private data, build outputs and local databases out of commits.

Supporting guides:

- [README_KEEPALIVE.md](README_KEEPALIVE.md)

<a id="license"></a>

## 📄 License

No repository-level license file is included in this snapshot. Public visibility alone does not grant reuse rights; contact the repository owner for terms.

---

Part of **PIMX** · Documentation in English and Persian.

---

<div align="center">

👛 **MML WALLET** · [English](README.md) · [فارسی](README.fa.md)

</div>
