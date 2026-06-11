# 🏦 VAULT — Banking Management System

A fully functional **Banking Management System** that runs entirely in the browser. No server, no backend, no installation — just open `index.html`.

**[→ Live Demo](https://your-username.github.io/vault-banking)** *(replace with your GitHub Pages URL)*

---

## Features

| Feature | Details |
|---|---|
| **Open Account** | Name, email, phone, account type (Savings/Checking), initial deposit, 4-digit PIN |
| **Deposit** | PIN-authenticated deposit with live balance preview |
| **Withdraw** | Insufficient-funds guard, live account preview |
| **Transfer** | Account-to-account with real-time ledger update on both sides |
| **Transaction History** | Full ledger, filterable by account number |
| **Dashboard** | Stats overview + recent 8 transactions |
| **Account Registry** | All accounts at a glance with detail modal |
| **Export / Import** | JSON backup and restore |
| **Data Persistence** | localStorage — survives browser restarts |

---

## Quick Start

### Option A — Open locally
```bash
# Just double-click index.html, or:
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

### Option B — GitHub Pages (free hosting)

1. Fork or push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under *Source*, select **Deploy from a branch → main → / (root)**.
4. Click **Save**. Your site will be live at:
   ```
   https://your-username.github.io/vault-banking/
   ```

---

## Project Structure

```
vault-banking/
├── index.html    ← Entire application (HTML + CSS + JS, self-contained)
└── README.md
```

No build step. No npm. No dependencies.

---

## How It Works

All data is stored in `localStorage` under two keys:

| Key | Contents |
|---|---|
| `vault_accounts` | Array of Account objects |
| `vault_transactions` | Array of Transaction objects |

### Data Model

```js
// Account
{
  number:   100000001,         // Auto-generated
  name:     "Alice Johnson",
  email:    "alice@example.com",
  phone:    "+1 555 0100",
  type:     "Savings",         // or "Checking"
  pinHash:  "...",             // Hashed 4-digit PIN
  balance:  1500.00,
  active:   true,
  opened:   "2026-06-11T...",
  txnCount: 4
}

// Transaction
{
  id:           1718100000123,
  account:      100000001,
  type:         "Deposit",     // Deposit | Withdraw | Transfer In | Transfer Out | Open
  amount:       500.00,
  balanceAfter: 1500.00,
  counterpart:  null,          // Other account number, for transfers
  date:         "2026-06-11T..."
}
```

---

## Security Notes

> This is an **educational/demo** application. For real-world banking:

- PIN is hashed client-side with a simple hash — use a proper algorithm (bcrypt, Argon2) server-side.
- localStorage is not encrypted — never store real credentials.
- Add HTTPS (GitHub Pages provides this automatically).
- For production, move data to a secure backend with proper authentication.

---

## License

MIT — see [LICENSE](LICENSE) for details.
