# DiscordBot

A Discord bot that uses OpenAI to respond to prompts from users.

## Installing Requirements
In virtualenv type `pip install -r requirements.txt`

## Running the Bot
Your `.env` file needs to include `DISCORD_TOKEN` and `OPENAI_API_KEY`.  
Start the bot with `python discordbot.py`

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

## Get your OpenAI API Key

Go to https://platform.openai.com/ and select `API`. You will need to create an account for that. Create an 
organization, and set up billing. Set up `usage limits` in case you make a mistake, or someone steals your API key, and 
you end up with a large surprise bill. With a few dozen calls per day, the cost is in the order of a few dollars 
per month. 

Select `API Keys`. Generate a key. Place this in your environment variables or `.env` under the key `OPENAI_API_KEY`. 

## Create the Discord Bot

Do the following steps in **Chrome**, the Discord Developers Portal **doesn't work in Safari**. 
Go to the [Discord developer portal](https://discord.com/developers/docs/getting-started) and select `get started`. 
Go to [Applications > New Application](https://discord.com/developers/applications?new_application=true), give the app 
a name and click `Create`

Go to the `Bot` section. You can give the bot a name, that will be its user name in the Discord channel. 
here you can select the `permissions` and `intents` the bot has. It will need Message Content Intent.  

On this page you will find the `token`. Copy this down in your environment variables or your `.env` under the key 
`DISCORD_TOKEN`. You won't be able to view or edit this token, if you lose it you have to generate a new one. 

## Invite the bot to your discord server

Generate an Invite Link: Go to `OAuth2>URL generator`. 
Under `Scopes`, select `bot`.
Then, under `Bot Permissions`, choose the permissions this bot needs. Choose `Read messages/View Channels` and 
`Send messages`. 
This will generate a URL which you can use to invite the bot to your Discord server.
Invite the Bot: Use the generated URL to add the bot to a server. You must have the necessary permissions 
on the server to add a bot.

## Using the bot

Type `!help` for a list of commands. On a channel, the bot responds to direct messages, or 
on a channel to commands like `!prompt` and `!image`. You can set the bot's `!role` to make it 
role play. `!role` without an argument will set a random role. `!image random` generates a self-portrait of the 
bot's current role. `!summarize` returns a summary of the current conversation as far as the bot remembers. 
This is not persisted between restarts. `!temp` sets the `temperature`, in a range between 0.0 and 1.0. The higher 
this number, the more random, or creative the response becomes. Above a certain temperature, the output becomes 
nonsense. `!tokens` sets the maximum number of tokens of the response. What tokens are is a bit fuzzy, it's more 
than letters but less than words. The maximum is 4096 at this time. Shorter responses are faster. `!forget` clears the 
conversation history of a user. 

Examples:
```
!prompt what is the best way to hit a nail on the head? 

!image a banana in a bikini

!role an extremely pendantic English professor who can't stop talking about anime

!prompt summarize the conversation so far but in Korean
```

## Abuse

The bot has no content filter, but the OpenAI API does, and they will ban you if you attempt too 
conspicuously to circumvent it  