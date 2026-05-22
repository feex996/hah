# 🌅 AI Daily Briefing

 Every day at your scheduled time, it collects your tasks, news headlines, and weather — then generates a personalized, actionable briefing using AI.

## ✨ Features

- **Personalized Greeting** — Tailored to your name and location
- **Weather Summary** — Practical advice based on today's conditions
- **Top News Digest** — 3 curated headlines most relevant to your day
- **Smart Task Prioritization** — AI picks your 2 most important tasks
- **Daily Insight** — One motivational or strategic thought to start your day
- **Follow-up Q&A** — Ask the AI follow-up questions about your briefing
- **Auto Save** — Briefing saved to JSON for logging/review
- **Cron / Scheduler Ready** — Run automatically every morning

## 🚀 Quick Start

### 1. Clone the repo
```bash
git clone https://github.com/yourusername/ai-daily-briefing.git
cd ai-daily-briefing
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure environment
```bash
cp .env.example .env
# Edit .env with your API key, name, and city
```

### 4. Add your tasks

Edit `tasks.json`:
```json
[
  "Review project proposal",
  "Reply to client emails",
  "Team standup at 10am"
]
```

### 5. Run it
```bash
python scheduler.py
```

## ⏰ Automate with Cron

Run every morning at 7:00 AM automatically:
```bash
crontab -e
# Add this line:
0 7 * * * cd /path/to/ai-daily-briefing && python scheduler.py >> briefing.log 2>&1
```

## 📊 Sample Output

```
==================================================
🌅 DAILY BRIEFING — 2026-05-23 Saturday
==================================================

👋 Good morning! Today looks productive — let's make it count.

🌤  Weather: 22°C and partly cloudy in Shanghai, light jacket recommended.

📰 Top News:
   1. Global AI investment hits record $200B in Q1 2026
   2. New Python 3.14 release brings major performance improvements
   3. Remote work productivity study shows 23% efficiency gain

✅ Focus Tasks:
   • Send proposal to client by 3pm
   • Fix login bug on staging server

💡 Insight: Deep work before 11am — protect your morning from meetings.

⏱  Read time: 1 min
==================================================
```

## 🛠 Tech Stack

- **Python 3.10+**
- **Anthropic Claude API** (claude-opus-4-5)
- **APScheduler** — for production scheduling
- **Multi-turn conversation** — follow-up Q&A support

## 📁 Project Structure

```
ai-daily-briefing/
├── scheduler.py          # Main agent + scheduler logic
├── tasks.json            # Your daily task list
├── requirements.txt      # Python dependencies
├── .env.example          # Environment variable template
└── README.md
```

## 🔑 Environment Variables

| Variable | Description | Default |
|---|---|---|
| `ANTHROPIC_API_KEY` | Your Anthropic API key | required |
| `USER_NAME` | Your name for personalized greeting | `User` |
| `CITY` | Your city for weather context | `Shanghai` |

## 📄 License

MIT License — free to use and modify.
