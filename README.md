# DiscordBot

A Discord bot that uses OpenAI to respond to prompts from users.

## Installing Requirements
In virtualenv type `pip install -r requirements.txt`

## Running the Bot
Your `.env` file needs to include `DISCORD_TOKEN` and `OPENAI_API_KEY`.  
Start the bot with `python dexbot.py`

## Linting
`flake8 *.py`

## Running Tests
`pytest tests.py`

## Running Tests with Coverage

```
coverage run -m pytest tests.py
coverage html
```
Coverage files can be found in `htmlcov` directory. Open `index.html` in the browser.
