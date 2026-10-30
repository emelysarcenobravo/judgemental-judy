# Judgmental Judy

**Your judgmental AI budget advisor.**

Judgmental Judy is a generative AI-powered budgeting application that helps users track expenses, manage discretionary spending, and identify opportunities to cut back on excessive spending habits. Powered by Anthropic's Claude, Judy analyzes users' financial information and delivers personalized insights with a witty, sarcastic, and increasingly judgmental personality as their discretionary budget decreases.

## Features

- **Financial Dashboard:** View monthly income, necessary expenses, discretionary spending, and remaining available cash.
- **Expense Tracking:** Manually enter transactions and organize spending into categories such as food, shopping, entertainment, and subscriptions.
- **Discretionary Budgeting:** Calculate available discretionary income after accounting for monthly necessities and track how much remains.
- **Spending Analysis:** Identify potentially excessive spending, recurring purchases, and questionable financial habits.
- **AI Budget Advisor:** Receive personalized financial observations and recommendations from Judy, with increasingly judgmental commentary as discretionary funds decrease.
- **Interactive Chat:** Ask Judy questions about your finances, spending habits, and purchasing decisions through a conversational chatbot.
- **Sample Financial Profiles:** Explore the application using predefined financial scenarios without entering personal financial information.

## How Judy Works

The application uses traditional programming logic to process financial information, calculate budgets, and track spending. This structured financial data is then passed to Claude, which interprets spending patterns and generates personalized feedback.

Judy interacts with users in two ways:

- **Dashboard Commentary:** Judy automatically provides sarcastic observations about spending habits and reacts to changes in discretionary spending.
- **Conversational Chatbot:** Users can interact directly with Judy to ask questions, discuss financial decisions, and receive personalized advice.

Judy's judgmental personality escalates as users approach their discretionary spending limits, while maintaining a humorous and helpful approach to financial awareness.

## Tech Stack

- **Frontend:** React, Vite, Tailwind CSS, Recharts
- **Backend:** Python, Flask
- **Database:** SQLite
- **Generative AI:** Anthropic Claude API
- **Development:** VS Code, Git, GitHub, ESLint
- **Deployment:** Vercel (frontend), backend hosting TBD

## Getting Started

### Prerequisites

Install these before setting up the project:

- [Python 3.12+](https://www.python.org/downloads/) (on macOS: `brew install python@3.12`)
- [Node.js 20+](https://nodejs.org/) (includes npm)
- [Git](https://git-scm.com/)
- [VS Code](https://code.visualstudio.com/) (recommended)

### 1. Clone the repository

```bash
git clone https://github.com/emelysarcenobravo/judgmental-judy.git
cd judgmental-judy
```

### 2. Set up the backend (Flask)

```bash
cd backend
python3.12 -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Create a `backend/.env` file for your Claude API key (never commit this file):

```
ANTHROPIC_API_KEY=your-key-here
```

Start the server:

```bash
python app.py
```

Visit http://localhost:5001/api/health to confirm it's running.

Test Judy's chat endpoint (requires your API key in `backend/.env`):

```bash
curl -X POST http://localhost:5001/api/chat \
  -H "Content-Type: application/json" \
  -d '{"messages": [{"role": "user", "content": "I spent $80 on boba this week"}]}'
```

> Activate the virtual environment (`source venv/bin/activate`) every time you open a new terminal to work on the backend.

### 3. Set up the frontend (React + Vite + Tailwind)

In a new terminal:

```bash
cd frontend
npm install
npm run dev
```

Visit http://localhost:5173 to view the app.

### Useful commands

| Command | Where | What it does |
|---|---|---|
| `python app.py` | `backend/` | Start the Flask API |
| `npm run dev` | `frontend/` | Start the frontend dev server |
| `npm run lint` | `frontend/` | Check code for errors with ESLint |
| `npm run build` | `frontend/` | Create a production build (Vercel runs this on deploy) |

### Project structure

```
judgmental-judy/
├── backend/          # Flask API
│   ├── app.py
│   └── requirements.txt
├── frontend/         # React + Vite + Tailwind app
│   ├── src/
│   └── package.json
└── README.md
```

## Project Status

Currently in development as part of CSC 603/803 — Generative AI at San Francisco State University.

## Goal

Help users become more aware of their spending, make informed budgeting decisions, and build healthier financial habits—with a little judgment along the way.

*Your finances called. Judy has some questions.*
