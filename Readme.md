# 🕵️ Lead Qualifier Agent — Google ADK

> A production-ready B2B lead qualification agent built with Google Agent Development Kit (ADK) and Gemini. Paste a company name → agent researches it via Google Search → returns a scored qualify/disqualify verdict with product recommendations.

---

## 🚀 Demo

**Input:**

```
Research and qualify this lead: Bahria Town Pakistan
```

**Output:**

```
COMPANY: Bahria Town Pakistan
SCORE: 10/10
VERDICT: ✅ QUALIFY
REASON: Bahria Town is a massive real estate developer building smart cities with
extensive residential, commercial, healthcare, and educational infrastructure.
Requires comprehensive networking, surveillance, and access control systems.
SUGGESTED PRODUCT: Ubiquiti UniFi (networking), ZKTeco (access control), Hikvision (surveillance)
```

---

## 🛠️ Tech Stack

- **Framework:** Google ADK 2.6.1
- **Model:** Gemini 2.0 Flash
- **Tools:** Built-in `google_search`
- **UI:** ADK Dev UI (`adk web`)
- **Eval:** ADK local eval runner

---

## 📁 Project Structure

```
adk-production-agent/
├── agent/
│   ├── agent.py          # Root agent definition
│   ├── __init__.py
│   ├── evalset.json      # Eval test cases
│   ├── eval_config.json  # Eval scoring criteria
│   └── .env              # API keys (not committed)
├── venv/
└── README.md
```

---

## ⚙️ Setup

### 1. Clone & create virtual environment

```bash
git clone https://github.com/yourusername/adk-production-agent.git
cd adk-production-agent
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Mac/Linux
```

### 2. Install dependencies

```bash
pip install google-adk
```

### 3. Set up environment variables

Create `agent/.env`:

```env
GOOGLE_API_KEY=your_gemini_api_key_here
```

Get your key at: [aistudio.google.com](https://aistudio.google.com)

### 4. Run the agent

```bash
adk web
```

Open: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 🧪 Eval

```bash
cd agent
adk eval . evalset.json
```

Eval cases:
| ID | Input | Expected |
|----|-------|----------|
| `qualify_it_company` | Systems Limited Pakistan | QUALIFY |
| `disqualify_bakery` | Sweet Bites bakery Lahore | DISQUALIFY |
| `qualify_bahria` | Bahria Town Pakistan | QUALIFY |

---

## 💡 Use Case

Built for **Microtech Inc.** — a B2B hardware distributor dealing in:

- Ubiquiti UniFi
- Cisco / Huawei
- ZKTeco Access Control
- Hikvision / Imou Surveillance

Sales reps paste a company name and instantly get a scored lead verdict before cold calling.

---

## 📄 License

MIT

---

Built during **Google ADK Live Class** — Building Production-Ready AI Agents with Google ADK 🎓
