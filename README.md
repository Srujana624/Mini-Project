💰 Personal Finance Dashboard
A full-stack personal finance management application that tracks expenses, manages budgets, sends bill reminders, and provides an interactive chatbot assistant — built with Flask (backend) and React + TailwindCSS (frontend).

🚀 Features

Expense Tracking — Add and categorize expenses with date and description
Budget Management — Set per-category spending limits and get real-time alerts
Bill Reminders — Schedule upcoming bills and receive due-date notifications
SMS Parsing — Auto-categorize transactions from SMS text using rule-based keyword matching
Interactive Chatbot — Ask natural language questions about your spending
Monthly Reports — Aggregate spending data into category-wise summaries
Visual Charts — Pie chart breakdown of spending by category (Matplotlib)
Notification Engine — Unified alerts combining budget overflows and bill reminders


🗂️ Project Structure
finance-dashboard/
├── backend/
│   ├── app.py              # Flask REST API
│   ├── reminder.py         # APScheduler-based bill reminder
│   ├── sms_parser.py       # SMS categorization logic
│   ├── budget_alerts.py    # Real-time budget alert checker
│   ├── chatbot.py          # Rule-based finance chatbot
│   ├── storage.py          # JSON-based local data persistence
│   ├── visualizer.py       # Matplotlib expense pie chart
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── src/
│   │   └── components/
│   │       ├── Dashboard.js     # Overview: total spent, budget, categories
│   │       ├── Notifications.js # Bill reminders & budget alerts
│   │       └── Chatbot.js       # Finance assistant chat UI
│   └── index.html           # Basic HTML + JS frontend (no-build option)
└── README.md

🛠️ Tech Stack
LayerTechnologyBackendPython, Flask, Flask-CORSSchedulerAPSchedulerFrontendReact, TailwindCSSChartsMatplotlibStorageLocal JSON filesTestingSMS Simulator (built-in)

⚙️ Setup & Installation
Prerequisites

Python 3.8+
Node.js 16+ (for React frontend)

Backend
bash# Clone the repository
git clone https://github.com/your-username/finance-dashboard.git
cd finance-dashboard/backend

# Install dependencies
pip install -r requirements.txt

# Run the Flask server
python app.py
The API will be available at http://localhost:5000.
Frontend (React)
bashcd frontend
npm install
npm start
Frontend (No-Build HTML)
Simply open frontend/index.html in a browser — no build step needed.

📡 API Endpoints
MethodEndpointDescriptionPOST/add_expenseAdd a new expenseGET/get_summaryGet category-wise spending summaryPOST/set_budgetSet a budget limit for a categoryPOST/add_billSchedule a new billGET/get_billsGet bills due today or overdue
Example: Add Expense
bashcurl -X POST http://localhost:5000/add_expense \
  -H "Content-Type: application/json" \
  -d '{"amount": 250, "category": "food", "description": "Zomato order"}'

🤖 SMS Parsing
Transactions can be auto-categorized from raw SMS text:
pythonfrom sms_parser import categorize_sms

sms = "Your account was debited ₹250 at Zomato"
print(categorize_sms(sms))  # → 'food'
Supported categories: food, travel, groceries, bills, income, other

📊 Sample Chatbot Queries
"How much did I spend on food?"
"What is my highest spending category?"

📦 requirements.txt
Flask
flask-cors
apscheduler
requests
matplotlib

🔮 Future Enhancements

 User authentication (JWT)
 Database integration (PostgreSQL / SQLite)
 Bank SMS auto-import on Android
 Export reports as PDF/CSV
 Multi-currency support
 AI-powered spending insights
