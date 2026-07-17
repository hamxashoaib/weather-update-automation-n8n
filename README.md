# Weather Update Automation

![n8n](https://img.shields.io/badge/n8n-workflow-orange)
![Open-Meteo](https://img.shields.io/badge/Open--Meteo-API-blue)
![Telegram](https://img.shields.io/badge/Telegram-Bot-2CA5E0)

An automated weather notification system built in n8n that checks current weather conditions on a schedule and sends real-time updates through a Telegram bot, with no manual input needed.

## How It Works

`Schedule Trigger → Get Weather Data (Open-Meteo API) → Format Message → Send Telegram Message`

1. A schedule trigger runs the workflow automatically at set intervals
2. The workflow calls the Open-Meteo API to fetch current weather conditions for a specific location
3. The raw API response is formatted into a clean, readable message, including a human-readable weather condition (converted from Open-Meteo's numeric weather codes) and the current hour's chance of rain
4. The formatted message is sent to a Telegram chat via a Telegram bot

## Tech Stack

- **n8n** → workflow automation and scheduling
- **Open-Meteo API** → free weather data API, no API key required
- **Telegram Bot API** → delivers the weather update as a chat message

## Screenshots

![Workflow Screenshot](Workflow%20Image/Screenshot.png)


## Sample Output

```
Weather Update - Lodhran
Temperature: 32.5°C (feels like 36.8°C)
Condition: Clear sky
Humidity: 61%
Wind: 15.5 km/h
Chance of Rain: 0%
```

## Setup

1. Import `weather-update-automation.json` into n8n
2. Update the `latitude` and `longitude` values in the Open-Meteo URL to your target location
3. Create a Telegram bot via [@BotFather](https://t.me/BotFather) and get your bot token
4. Get your Telegram Chat ID by messaging [@userinfobot](https://t.me/userinfobot)
5. Add your bot token as a credential on the **Send Telegram Message** node, and paste your Chat ID into the node's Chat ID field
6. Message your bot once on Telegram (required before it can send you messages)
7. Adjust the Schedule Trigger interval to how often you want updates (e.g., every 6 hours)
8. Run the workflow to test

## Notes

- Open-Meteo requires no API key, making this easy to run without any signup friction
- The weather code mapping (converting numeric codes like `0`, `61`, `95` into readable text like "Clear sky" or "Thunderstorm") is handled in the Format Message step using Open-Meteo's WMO weather code reference

## About Me

I'm **Hamza Shoaib**, a BS Artificial Intelligence student at The Islamia University of Bahawalpur, focused on AI agents, automation, and applied GenAI. I built this project as part of my ongoing freelance and portfolio work in AI-powered automation using n8n.

- LinkedIn: [linkedin.com/in/ch-hamza-shoaib](https://linkedin.com/in/ch-hamza-shoaib)
- GitHub: [github.com/hamxashoaib](https://github.com/hamxashoaib)


