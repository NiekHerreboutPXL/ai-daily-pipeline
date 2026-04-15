# ai-daily-pipeline

Automated AI news pipeline for @ClaudeUpdatesBot on Telegram.

## Flow
1. **Claude routine** (scheduled remote agent) doet AI-nieuwsresearch
2. Agent schrijft bericht naar `messages/latest.json` en pusht naar deze repo
3. **GitHub webhook** triggert n8n workflow
4. **n8n** leest het bericht en stuurt naar Telegram

## Structuur
```
messages/
  latest.json    ← meest recente bericht (overschreven per run)
  archive/       ← optioneel: historische berichten
```

## Schedule
- 08:00 + 20:00 Europe/Brussels (dagelijks)
