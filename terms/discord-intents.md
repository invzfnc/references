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