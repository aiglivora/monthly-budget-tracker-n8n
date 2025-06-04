# 💸 Monthly Budget Tracker (n8n + Google Sheets + Telegram)

A personal assistant connected to **Telegram** and **Google Sheets** via **n8n**, allowing you to record your money in/out and track your monthly budget in a simple and automated way.

---

## 🚀 Features

- **Record Transactions**: Log income (`/in`) and expenses (`/out`) via Telegram.
- **AI-Powered Parsing**: Automatic data extraction with an AI agent.
- **Google Sheets Integration**: Stores data in a structured Google Sheet.
- **Budget Tracking**: Calculates and displays your remaining monthly budget.
- **Personalized Feedback**: Receive real-time updates in Telegram.

---
## 🧠 How It Works

1. Send a transaction message to the Telegram bot (e.g., `/out groceries 53.20`).
2. n8n parses the message to extract **date**, **description**, and **amount**.
3. The transaction is appended to a Google Sheet.
4. For budget summaries, n8n reads the sheet, calculates totals, and sends the remaining balance via Telegram.

## 📱 Telegram Commands

| Command | Description | Example |
|---------|-------------|---------|
| `/in`   | Log incoming payment | `/in salary 2000` |
| `/out`  | Log an expense | `/out groceries 53.20` |
| `/sum`  | View remaining monthly budget | `/sum` |

---

## 📊 Google Sheet Format

| Date       | Description | Amount |
|------------|-------------|--------|
| 2025-06-02 | Netflix     | 12.99  |
| 2025-06-03 | Salary      | 2000.00|

---

## 🧠 Technical details

## 🛠 Technical Details

1. **Telegram Trigger**: Receives messages from the Telegram bot.
2. **Sender Verification**: Restricts access to authorized users.
3. **Command Routing**: Uses a `Switch` node to handle `/in`, `/out`, or `/sum`.
4. **Transaction Processing** (`/in` or `/out`):
   - Formats the message with the current date.
   - Uses a LangChain AI agent to extract details.
   - Appends data to Google Sheets.
5. **Budget Summary** (`/sum`):
   - Reads all transactions for the current month.
   - Calculates total income and expenses.
   - Returns the remaining balance via Telegram (e.g., `Month remaining: 1500 euros`).

---



## ⚙️ How to Use

1. Clone this repo.
2. Import the `monthly-budget-tracker.json` workflow into n8n.
3. Set up your **Telegram Bot API** credentials.
4. Connect your **Google Sheets** credentials.
5. Customize the sheet ID and income value.

---

## 📝 Future Improvements

- Addition of the `Category` column (AI-detected)
- Generation of monthly charts
- Automatic detection of recurring payments
- Weekly or monthly reports sent automatically

## 🔑 License

This project is licensed under the MIT License.
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🙋 About

Developed by @aiglivora as a no-code budgeting solution using n8n, Telegram, and Google Sheets. Contributions and feedback are welcome!

⭐ Star this repo if you find it useful! Feel free to open issues or submit pull requests for improvements.
