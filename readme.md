Submissions are due 11:59PM this Sunday (5 May).
- [Submission Link](https://forms.gle/mgbHteNX18uX6D7N7)


# Setting up your bot
## Creating The Bot
- Login to Discord Developer Portal via https://discord.com/developers/applications using your discord account info
- Click on “New Application” on the top right
![myImage](https://github.com/HackMelbourne/minihack/blob/main/src/p1.jpg)
- In the pop-up window, enter an application name, click the box and hit “Enter”
- You should see the dashboard for the new application by now! On your left under “Setting”, go to “Bot” tab and create a bot. Here you can add an avatar, change name and add description for your bot. 
- Scroll down and copy the token. This is like the password to your bot so save it carefully as we will need to use it later in coding to get access to the bot. If you want to get a new token, you can always generate a new one here as well.
- Continue scrolling down to the “Privileged Gateway Intents” section and enable all three intents here. They allow your bot to read and respond to messages. 
![myImage](https://github.com/HackMelbourne/minihack/blob/main/src/p2.jpg)



## Set Up Your Own Server
> [!note]
> If you already have a server that you want to invite your bot into,  move on to step 3 :

- On Mobile: Go to the “Servers” tab on the bottom and 
- On Mobile & Laptop: click on “+” button in the leftmost column -> select “Create My Own” -> “For me and my friends” -> “Create Server”



## Invite Your Bot Into the Server
- Go back to the Discord Developer Portal and go to the “OAuth2” tab under “Setting”
- Scroll down to “OAuth2 URL Generator” section and tick the box for “bot” and “applications.commands”
- Continue Scrolling down to “Bot Permissions”. Depending on what you would like the bots to do, you can give it different permissions. For this tutorial, you can tick the options as the following 
- Scroll to the bottom, copy the generated URL into a new browser window and hit “Enter”
- Choose the server that you want to invite the bot into from the drop-down menu and continue -> authenticate -> done!
![myImage](https://github.com/HackMelbourne/minihack/blob/main/src/p3.jpg)


# Coding Your Bot
> [!important] 
> We will only be accepting Javascript and Python for this competion
## Javascript


### Loging Into Your Bot
> [!tip]
> How to write Javascript code in Visual Studio:
https://www.youtube.com/watch?v=ewTbdhe2RCs 
>
> How to install Discord Js:
>https://www.youtube.com/watch?v=Zqt7tYIpfMs&t=291s 

- In VS code,create a new js file to code for your bot and for reference purpose, say this js file is called bot.js
- Create a json file under the same folder to store the token of your bot and for reference purpose, say this json file is called config.json
- In config.json, paste the following codes, substitute in your token and save it
```
{
	"token": "your-token-goes-here"
}
```

- In bot.js, type in the following and save it
```
	const {client, Events, IntentBitField} = requre('discord.js');
	const { token } = require('./config.json');

	const client = new Client ({ omtemts: [
		IntentBitField.Flags.Guilds,
		IntentBitField.Flags.GuildMembers,
		IntentBitField.Flags.GuildMessages,
		IntentBitField.Flags.MessageContent,
	]});

	client.once(Events.ClientReady, readyClient => {
		console.log("Ready! Logged in as ${readyClient.user.tag}');
	})

	client.login(token);
```
- Press “Ctrl” + “~” to invoke the terminal -> navigate to the folder where the bot.js file is in-> type in “node bot.js” and run 
- After a few seconds, you should get a “Ready! Logged in as (your_bot_name)” message in the terminal that indicates you have successfully accessed your bot. And if you go to the Discord server where your bot is in, you should see its status as “online” now ^-^

### Writing A Basic Bot
- In bot.js, continue typing in the following code
```
	client.on('messageCreate', (msg) => {
		let msgContent = msg.content;

		if(msgContent.charAt(0) == "!"){
			let command = msgContent.substring(1);

			if(command == "Hello"){
				msg.reply('Hello $(msg.author.username)');
			}
		}
	});
```
- “messageCreate” is an event defined for the Client class in Discord Js and it is the case when a message is sent into the Discord server. After typing in the codes above, save the bot.js file and run it again in the terminal
- Now when you type in “!Hello” in the Discord server, your bot should be able to greet you as “Hello (your_Discord_username)”  ^-^

> [!note]
> The codes in this step are mostly from https://discordjs.guide/ . Visual Studio code is used here and it assumes that Node.js as well as Discord Js have been installed. Feel free to check out the reference section below if you haven’t already installed them :)

## Python
>[!tip]
> Double check that you have python installed on your computer. After that, open up your command prompt (window + r and type in cmd), then the syntax pip install discord.
>
>If there are any problems with this, https://www.youtube.com/watch?v=xhGWpnyVK8c has a wonderful guide on how to fix.
For mac-OS, open the terminal application and type the same syntax. 
> 
> How to install vscode for python: https://youtu.be/cUAK4x_7thA?si=R4xqjOugj_xXz2iO
### Setting Up
- Create a folder for your discord bot
- Open vscode -> files -> open folder
![myImage](https://github.com/HackMelbourne/minihack/blob/main/src/p4.jpg)
- Create a main file called main.py in our folder by right clicking and creating a new file.
- Follow this syntax, the command_prefix can be anything you’d like, as it is just the syntax for commands for the bot when you are actually using it in discord.
- For example, here we are using a very common prefix !, which for example, !play could be a command that allows you to search and play a song.




### testing the bot

- The syntax is bot.run(“Our unique token that we got from discord before”).
```
import discord
from discord.ext import commands

bot = commands.Bot(command_prefix = "!", intents=discord.Intents.all())

@bot.event
async def on_message(message):
    if message.author == bot.user:
        return
    content_lower = message.content.lower()
    if "deez" in content_lower or "nuts" in content_lower:
        await message.channel.send("DEEZ NUTS!!! \nGOT'EM!!\n")
bot.run("{BOT TOKEN GOES HERE}")
```
- Run our python file, it should return two lines, logging in using a statistic token, and that the Shard ID None has connected to Gateway.
- If you’ve made it this far, goodjob! It's running successfully. 



### Inviting your bot:
- To invite your bot into a server, simply go to  OAuth2 > URL Generator on our discord developer webpage and tick the bot checkpoint under scopes.
- Tick the permissions required for your bot to function under  “Bot Permissions”. Now the resulting URL at the bottom can be used to add your bot to a server.

> [!tip]
> If you are having trouble refer to this website: https://discordpy.readthedocs.io/en/stable/discord.html

Now, you are able to add your own code and functions to your personal bot, have fun! 

# Extra Resource
### Python
- Comand: https://discordpy.readthedocs.io/en/stable/ext/commands/commands.html
- our bot: https://discord.com/oauth2/authorize?client_id=1233026847776837663&permissions=8&scope=bot 
### JavaScript
- CodeAcademy tutorial on building a Discord bot with js
https://www.codecademy.com/article/build-a-discord-bot-with-node-js

- To code your bot to send gifs (may need to adjust the bot permissions)
https://www.youtube.com/watch?v=9P1rB2MY4ZA&list=PLRqwX-V7Uu6avBYxeBSwF48YhAnSn_sA4&index=5

- Detailed video tutorial on how to make a Discord bot with js (about 30 min)
https://www.youtube.com/watch?v=KZ3tIGHU314


- Additional content (Optional reading!):
:https://discordjs.guide/additional-info/changes-in-v14.html#before-you-start

