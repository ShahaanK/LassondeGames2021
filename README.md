# Lassonde Games 2021 — Pharmacy Refill System

A small Python project showcasing a **pharmacy ↔ client** refill workflow with simple menus, key generation, and a basic refill API/email flow. Files include separate menus for **clients** and **pharmacies**, a **key generator**, and helpers for **refill API** calls and **refill email** sending. This was created during the Lassonde Games 2021 as a submission.

## ✨ Features
- **Client Menu** (`client_menu.py`): place refill requests, view status, and interact through a simple CLI.
- **Pharmacy Menu** (`pharmacy_menu.py`): review incoming requests, approve/deny, and manage queue via CLI.
- **Key Generation** (`keyGenerator.py`): create keys/tokens used by the menus or API helpers.
- **Refill Helpers**:
  - `refill_api.py`: utilities for sending/receiving refill requests programmatically (e.g., HTTP calls).
  - `refill_email.py`: utility functions for sending confirmation/notification emails.
- **Packaging/Artifacts**: `dist/` (build output, if used), `red_scp/` (supporting scripts/resources).

## 🧱 Project Structure
```
LassondeGames2021/
├─ client_menu.py        # Client-facing CLI
├─ pharmacy_menu.py      # Pharmacy staff CLI
├─ keyGenerator.py       # Key/token creation
├─ refill_api.py         # API utilities for refills
├─ refill_email.py       # Email notifications for refills
├─ dist/                 # Built artifacts (optional)
├─ red_scp/              # Supporting scripts/resources
└─ .gitignore
```

## 🚀 Quick Start

### 1) Prerequisites
- **Python 3.8+** recommended
- An SMTP account (if you plan to send emails from `refill_email.py`)
- Any API keys/URLs required by `refill_api.py` (if used)

### 2) Create and activate a virtual environment
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
```

### 3) Install dependencies
If a `requirements.txt` exists:
```bash
pip install -r requirements.txt
```
If not, install needed libs per your environment. Many parts rely on Python’s standard library; if `refill_api.py` uses HTTP, you may need:
```bash
pip install requests
```

### 4) Configure environment
Create a `.env` (or export environment variables) for any secrets you use, for example:
```
SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USER=your_user
SMTP_PASS=your_pass
API_BASE_URL=https://api.example.com
API_KEY=your_api_key
```

### 5) Run
**Client menu:**
```bash
python client_menu.py
```

**Pharmacy menu:**
```bash
python pharmacy_menu.py
```

## ⚙️ Configuration Notes
- **Keys/Tokens:** Run `keyGenerator.py` first if your menus expect a generated key file or token.
- **Email:** Update sender, recipients, and SMTP details inside `refill_email.py` (or read them from environment variables).
- **API:** Point `refill_api.py` to your test/stub API URL for local development.

## 🧪 Testing
- Add unit tests under `tests/`. Example:
  ```
  tests/
    test_client_menu.py
    test_pharmacy_menu.py
    test_refill_api.py
    test_refill_email.py
  ```
- Suggested tooling:
  ```bash
  pip install pytest
  pytest -q
  ```

## 👥 Credits
- Team members listed in the repository: **Ali Raeisdanaei**, **Shahaan Khan**

