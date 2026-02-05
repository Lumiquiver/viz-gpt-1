# Discord LLM Bot (OpenRouter + Python)

A Discord bot that connects to a custom LLM via the OpenRouter API and maintains short-term conversation memory per channel.

This bot:
- Responds when mentioned
- Supports a `!chat` command
- Stores recent conversation history
- Uses OpenRouter chat completion API
- Can be deployed on Render for 24/7 uptime

---

## Features

- Channel-based memory
- Mention-to-chat interaction
- Manual chat command
- Memory reset command
- Handles Discord 2000-character message limit
- Async Discord bot using `discord.py`

---

## Project Structure

```

project/
├── bot.py
├── requirements.txt
└── README.md

```

---

## Environment Variables

You must set these variables:

```

DISCORD_TOKEN=your_discord_bot_token
LLM_API_KEY=your_openrouter_api_key

````

---

## Local Setup

### 1. Install Python
Python 3.9+ recommended.

---

### 2. Install dependencies

```bash
pip install -r requirements.txt
````

---

### 3. Run the bot

```bash
python bot.py
```

If successful, you should see:

```
Bot active:
```

---

## Discord Setup

Enable **Message Content Intent**:

Discord Developer Portal → Bot →
Enable:

```
MESSAGE CONTENT INTENT
```

Invite bot using OAuth2 URL generator with permissions:

* Read Messages
* Send Messages
* View Channels

---

## Commands

### Mention the bot

```
@BotName hello
```

---

### Chat command

```
!chat Hello there
```

---

### Clear memory

```
!clear
```

This resets conversation history for the current channel.

---

## Deploying to Render (Free 24/7)

Create a **Background Worker** on Render.

Settings:

Build Command:

```
pip install -r requirements.txt
```

Start Command:

```
python bot.py
```

Environment variables:

```
DISCORD_TOKEN=your_token
LLM_API_KEY=your_key
```

Deploy and check logs for:

```
Bot active:
```

---

## Notes

* Discord message limit is 2000 characters.
* Memory is stored per channel.
* Conversation history is limited to the last 10 messages.
* Never commit API keys or tokens to GitHub.

