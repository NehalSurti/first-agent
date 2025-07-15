# 💬 Josh — Terminal-Based AI Finance Agent

Josh is a CLI-based AI assistant for tracking personal finances, powered by Groq's blazing-fast Llama 3.3-70B model.

## 🧠 Agent Architecture

Josh uses tool-calling capabilities to interact with financial data:
- Income entries
- Expense records
- Balance checks
- Expense queries over time

### 🧩 Agent Loop (Terminal Edition)

1. User enters a message in the terminal
2. Node.js (via Bun) sends message history and tool definitions to Groq
3. Groq's LLM either:
   - Responds directly **(no tool required)**  
   - Or, triggers a tool call (e.g., `addExpense`)
4. If a tool is called:
   - The JS function is executed
   - Result is sent back to the LLM for final reasoning
5. Final assistant message is printed in the terminal

### ⚒️ Supported Tools

| Tool Name       | Description                                |
|-----------------|--------------------------------------------|
| `addIncome`     | Add income entry to memory                 |
| `addExpense`    | Add an expense entry                       |
| `getTotalExpense` | Get total spent in a given time period    |
| `getMoneyBalance` | Check current financial balance           |

---

## 🚀 Run It

Make sure you have a `.env` with your Groq key:

