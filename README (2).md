# 🌸 Bloom & Petals AI Assistant

An AI-powered chatbot built with **Google Gemini 2.0 Flash** and **Gradio**, designed to help customers of **Bloom & Petals Flower Shop** inquire about floral arrangements, event designs, and deliveries — and to automatically record leads and feedback.

---

## 🚀 Features

- 💬 Conversational AI assistant powered by Google Gemini  
- 🧠 Function calling for:
  - Recording **customer leads** (name, email, inquiry)
  - Recording **customer feedback** or unanswered questions
- 📊 Interactive Gradio interface with real-time data view  
- 💾 Persistent storage of leads and feedback in JSON format  
- 🧾 Optional export to Excel / JSON  
- 🔐 Secure API-key management using `.env` file

---

## 🧰 Tech Stack

- **Python 3.10+**
- [google-generativeai](https://pypi.org/project/google-generativeai/)
- [gradio](https://gradio.app)
- [python-dotenv](https://pypi.org/project/python-dotenv/)
- **Pandas** (optional, for Excel export)

---

## ⚙️ Setup Instructions

1. **Clone the repo**
   ```bash
   git clone https://github.com/yourusername/bloom-petals-ai-assistant.git
   cd bloom-petals-ai-assistant
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate   # or venv\Scripts\activate on Windows
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Create a `.env` file** in the project root:
   ```
   GOOGLE_API_KEY=your_real_key_here
   ```

5. **Run the app**
   ```bash
   python business_agent_fixed.py
   ```

6. The Gradio interface will launch — open the provided local or public link.

---

## 🗂️ Data Files

| File | Purpose |
|------|----------|
| `customer_leads.json` | Stores recorded leads (name, email, message) |
| `customer_feedback.json` | Stores customer feedback or unanswered questions |
| `.env` | Holds the Google API key (not pushed to GitHub) |

---

## 🔐 Security Notes
- Do **not** share or commit `.env` to GitHub.  
- API key is loaded via `python-dotenv`.  
- `.gitignore` ensures secrets and local data are excluded from version control.

---

## 📊 Export Data
You can export leads and feedback to Excel:
```python
import pandas as pd, json
leads = pd.DataFrame(json.load(open("customer_leads.json")))
feedback = pd.DataFrame(json.load(open("customer_feedback.json")))
with pd.ExcelWriter("bloom_petals_data.xlsx") as w:
    leads.to_excel(w, "Customer Leads", index=False)
    feedback.to_excel(w, "Customer Feedback", index=False)
```

---

## 💖 Credits
Developed with ❤️ by [Your Name]  
Powered by Google Gemini and Gradio.
