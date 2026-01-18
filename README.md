# MarkBot for Discord

A Markov chain bot using markov-strings.

## Variant: random message sending
Check `/config/config.json`

Adjust the parameters as desired, e.g.:
```json
"randomReplyChance": 0.25,
"randomReplyMentionChance": 0.50
```

## Usage

1. Configure what channels you want the bot to listen/learn from:
    * User: `/listen modify`
    * Bot: ![Select which channels your would like the bot to actively listen to](img/listen.png)
1. Train the bot in a lengthy text channel:
    * User: `/train`
    * Bot: ![Parsing past messages from 5 channel(s).](img/train.png)
1. Ask the bot to say something:
    * User: `/mark`
    * Bot: ![worms are not baby snakes, by the way](img/respond.png)

### Training from a file

Using the `json` option in the `/train` command, you can import a list of messages.
An example JSON file can be seen [here](img/example-training.json).

## Setup

This bot stores your Discord server's entire message history, so a public instance to invite to your server is not available due to obvious data privacy concerns. Instead, you can host it yourself.

1. Create a [Discord bot application](https://discordapp.com/developers/applications/)
1. Under the "Bot" section, enable the "Message Content Intent", and copy the token for later.
1. Setup and configure the bot using one of the below methods:

### Any Operating System

1. Install [Node.js 16 or newer](https://nodejs.org/en/download/).
1. Download this repository using git in a terminal window

    ```cmd
    git clone https://github.com/microcoded/markov-discord.git
    ```
1. Open a command prompt in the `markov-discord` folder.

    ```sh
    # NPM install non-development packages
    npm ci
    # Build the Typescript
    npm run build
    # Initialize the config
    npm start
    ```

1. The program will create a `config/config.json` in the project folder. Open it and add your bot token. You may change any other values to your liking as well. Details for each configuration item (from the orignal bot) can be found here: <https://claabs.github.io/markov-discord/classes/AppConfig.html>
1. Run the bot:

    ```sh
    npm start
    ```

    And use the invite link printed to the logs.
