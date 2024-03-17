# FiveM Discord Bot
Bot was originally made for a Danish roleplay server, written in javascript.

Everything beside prints is writtin in Danish and you'll have to translate it yourself.

# Miscellaneous Features
- <b> Displays online players as status </b>
   > Example: Online: 420/1000
- <b> Attachments only channel </b>
   > Prevents everything beside attachments (pictures, videos etc.) from being sent in a your choise of channels, ex. for ingame-pictures channel 

# Moderation Commands
- <b> /clear \<amount\> </b>
   > Clear a X amount of messages from a text channel

- <b> /lookup \<ingame-id\> </b>
   > Lookup player identifiers such as discord ID, rockstar license etc.

- <b> /supportaccess \<user\> \<channel-no\> </b>
   > Temporarily give a user access to screenshaere in a support channel (and join, but that's requried after a new discord update)
   > Removes permission after 5 minutes by default

- <b> /whitelistaccess </b>
   > Temporarily give a user access to screenshaere in a whitelist interview channel (and join, but that's requried after a new discord update)
   > Removes permission after 1.5 minutes by default

- <b> /tempplate \<type\> </b>
   > Returns message with application-tempplate for a user to fill out, ex. in a ticket.

- <b> /whitelist \<user\> </b>
   > Gives user whitelist role on discord.
   > Also has to be used in a specific because the return message isn't "ephemeral" and to log whitelists.

- <b> /unwhitelist \<user\> </b>
   > Removes user's whitelist role on discord.
   > Also has to be used in a specific because the return message isn't "ephemeral" and to log whitelists.

# Requirements
- [Node.js](https://nodejs.org/en/)

# How to install
1. Create your bot under discords developer portal and tick off everything under "Privileged Gateway Intents"

2. Go to OAuth2 > URL Generator
   - Tick off `applications.commands` and `bot` under "Scopes"
   - Give your bot `Administrator` under "Bot Permissions"
   - Invite your bot

3. Open the terminal and run the following command in your bots folder:
   - `npm install`

4. Create the following files:
   - `.env`
   - `config.json`

5. Fill out values in `.env` and `config.json` (example below)

6. Go under src/commands and change permissions of all the commands to your liking

7. Run `start.bat` or use `node src/index.js` in the terminal

# ENV file example
```
TOKEN = ''
GUILD_ID = ''
CLIENT_ID = ''
```

# Config file example
```json
{
    "general": {
        "cfxip": "3lamjz",
        "activity": "dnd",
        "discordLogo": "https://i.imgur.com/example.png",
        "RemoveSupportPermAfterMin": 5,
        "RemoveWhitelistPermAfterMin": 1.5
    },
    "roleIds": {
        "whitelistRole": "roleID"
    },
    "channelsIds": {
        "whitelistCommands": "channelID",
        "onlyAttachmentsChannels": [
            "channelID1",
            "channelID2",
            "channelID3"
        ],
        "supportChannels": {
            "1": "channelID1",
            "2": "channelID2",
            "3": "channelID3"
        },
        "whitelistChannels": {
            "1": "channelID1",
            "2": "channelID2",
            "3": "channelID3"
        }
    }
}
```
