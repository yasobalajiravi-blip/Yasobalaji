# MONIK GROUP — Customer Insurance Management System

React + Vite frontend for the MONIK GROUP CIS Portal v2.0

## 🚀 Quick Start

```bash
# 1. Install dependencies
npm install

# 2. Start dev server
npm run dev

# 3. Open in browser
http://localhost:3000
```

## 📁 Project Structure

```
monik-insurance/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.jsx              # Entry point
    ├── App.jsx               # Root component + routing
    ├── index.css             # Global design system
    ├── context/
    │   └── AppContext.jsx    # Global state (auth, claims, toasts)
    ├── data/
    │   └── mockData.js       # All mock data + helpers
    ├── components/
    │   ├── UI.jsx            # Reusable UI components
    │   └── Layout.jsx        # Sidebar + Topbar
    └── pages/
        ├── Login.jsx
        ├── Dashboard.jsx
        └── Pages.jsx         # All feature pages
```

## 🔐 Demo Login

Use any username/password — select a role from the dropdown:

| Role             | Access                                    |
|------------------|-------------------------------------------|
| Administrator    | Full access to all modules                |
| HO Officer       | Claims, Benefits, Call Center, Reports    |
| Branch Officer   | Document Register, Enquiry                |
| Call Center Agent| Call Center only                          |
| Auditor          | Audit, Reports                            |
| Finance Officer  | Cash, Payment Update, Reports             |

## 📋 Modules

1. **Document Register** — Register new insurance claims (loan lookup → auto-fill)
2. **Document Received** — Mark received documents at HO
3. **Claim Processing** — Approve / Pending / Reject claims
4. **Handover** — Mark claims as handed over
5. **Benefits — Cash** — Select claims, generate Payment Request (A4 printable)
6. **Benefits — Packs** — Scholarship & GCE O/L pack tracking
7. **Facility & Loans** — Laptop loan ledger management
8. **Payment Update** — Mark batch payments as Paid/Pending/Failed
9. **Call Center** — 6-section verification checklist
10. **Audit** — Compliance audit with risk levels
11. **Pending & Reject** — Central issue tracking
12. **Claim Enquiry** — Search by NIC / Loan / Claim Code
13. **Reports** — Payment master, branch/type summary, audit log
14. **Admin** — Users, company/branch config, data upload, day end

## 🛠 VS Code Recommended Extensions

- **ESLint** (`dbaeumer.vscode-eslint`)
- **Prettier** (`esbenp.prettier-vscode`)
- **ES7+ React Snippets** (`dsznajder.es7-react-js-snippets`)
- **Vite** (`antfu.vite`)

## 🔗 Tech Stack

- **React 18** — UI framework
- **Vite 5** — Build tool & dev server
- **React Router DOM 6** — (installed, ready to use for URL routing)
- **Lucide React** — Icons (installed, ready to use)
- **CSS Variables** — Design system, no CSS framework needed

## 🗄 Connecting to Supabase

Replace mock data in `src/data/mockData.js` with Supabase calls:

```js
import { createClient } from '@supabase/supabase-js'

const supabase = createClient(
  import.meta.env.VITE_SUPABASE_URL,
  import.meta.env.VITE_SUPABASE_ANON_KEY
)

// Example: fetch claims
const { data, error } = await supabase
  .from('claim_master')
  .select('*')
  .eq('company_id', 'MON')
```

Create a `.env` file:
```
VITE_SUPABASE_URL=https://xxxx.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
```

## 📦 Build for Production

```bash
npm run build
# Output goes to /dist folder
```
