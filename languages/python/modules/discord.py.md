#### Concept: Intents
A mechanism that allows developers to specify and receive more granular information about events happening on a Discord server.
Intents are used to control which events a bot can listen to and respond to.

**Privileged intents**
Need to enable them in bot's application settings on the Discord Developer Portal
- `GUILD_MEMBERS` - Information about members (User IDs, usernames, statuses)
- `GUILD_PRESENCES` - Receive presence updates for members (Activities and statuses)

**Unprivileged intents**
- `GUILD_MESSAGES` - Allow bots to receive message events (sent, edited, deleted)
- `DIRECT_MESSAGES` - Allow bots to receive direct message events, able to interact with users through direct messages

Declaring which intents to use when connecting to the Discord API:
```python
intents = discord.Intents.default()
intents.members = True  # Enable GUILD_MEMBERS intent
intents.presences = True  # Enable GUILD_PRESENCES intent

client = discord.Bot(intents=intents)
```

#### Logging
Log messages default to `stderr`
Setting up logging
```python
import logging

handler = logging.FileHandler(filename="log.txt", encoding="utf-8", mode="w")
# Assuming client refers to a discord.Client subclass
client.run(token, log_handler=handler)
```

Disabling logging
```python
client.run(token, log_handler=None)
```

Level = `logging.DEBUG`
This is recommended, especially at verbose levels such as `DEBUG`, as there are a lot of events logged and it would clog the `stderr` of program
```python
import logging

handler = logging.FileHandler(filename="discord.log", encoding="utf-8", mode="w")
client.run(token, log_handler=handler, log_level=logging.DEBUG)
```

[Docs - Logging](https://discordpy.readthedocs.io/en/stable/logging.html)