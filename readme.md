# Setting up your bot
## Creating The Bot
- Login to Discord Developer Portal via https://discord.com/developers/applications using your discord account info
- Click on “New Application” on the top right
- In the pop-up window, enter an application name, click the box and hit “Enter”
- You should see the dashboard for the new application by now! On your left under “Setting”, go to “Bot” tab and create a bot. Here you can add an avatar, change name and add description for your bot. 
- scroll down and copy the token. This is like the password to your bot so save it carefully as we will need to use it later in coding to get access to the bot. If you want to get a new token, you can always generate a new one here as well.
- continue scrolling down to the “Privileged Gateway Intents” section and enable all three intents here. They allow your bot to read and respond to messages. 




## Set Up Your Own Server
> [!note]
> If you already habe a server that you want to invite your bot into,  move on to step 3 :

- On Mobile: Go to the “Servers” tab on the bottom and 
- On Mobile & Laptop: click on “+” button in the leftmost column -> select “Create My Own” -> “For me and my friends” -> “Create Server”



## Invite Your Bot Into the Server
- Go back to the Discord Developer Portal and go to the “OAuth2” tab under “Setting”
- Scroll down to “OAuth2 URL Generator” section and tick the box for “bot” and “applications.commands”
- Continue Scrolling down to “Bot Permissions”. Depending on what you would like the bots to do, you can give it different permissions. For this tutorial, you can tick the options as the following 
- Scroll to the bottom, copy the generated URL into a new browser window and hit “Enter”
- Choose the server that you want to invite the bot into from the drop-down menu and continue -> authenticate -> done!

# Setting Up Your Environment
> [!note]
> If you have a working code editor you can skip this part [LINK]


# Coding Your Bot
Before we start please decide between which Javascript and Pyton
> [!important] 
> We will only be accepting Javascript and Python for this competion


For JavasScript: [LINK]

For Python: [LINK]

## Javascript
> [!note]
> The codes in this step are mostly from https://discordjs.guide/ . Visual Studio code is used here and it assumes that Node.js as well as Discord Js have been installed. Feel free to check out the reference section below if you haven’t already installed them :)

### Loging Into Your Bot
- In VS code,create a new js file to code for your bot and for reference purpose, say this js file is called bot.js

- Create a json file under the same folder to store the token of your bot and for reference purpose, say this json file is called config.json


- In config.json, paste the following codes, substitute in your token and save it
```
{
	"token": "your-token-goes-here"
}
```

- In bot.js, type in the following and save it
- Press “Ctrl” + “~” to invoke the terminal -> navigate to the folder where the bot.js file is in-> type in “node bot.js” and run 
- After a few seconds, you should get a “Ready! Logged in as (your_bot_name)” message in the terminal that indicates you have successfully accessed your bot. And if you go to the Discord server where your bot is in, you should see its status as “online” now ^-^

### Writing A Basic Bot
- In bot.js, continue typing in the following code 



- “messageCreate” is an event defined for the Client class in Discord Js and it is the case when a message is sent into the Discord server. After typing in the codes above, save the bot.js file and run it again in the terminal


- Now when you type in “!Hello” in the Discord server, your bot should be able to greet you as “Hello (your_Discord_username)”  ^-^


## Python
Before we get into the good stuff, double check that you have python installed on your computer. After that, open up your command prompt (window + r and type in cmd), then the syntax pip install discord. If there are any problems with this, https://www.youtube.com/watch?v=xhGWpnyVK8c has a wonderful guide on how to fix.
For mac-OS, open the terminal application and type the same syntax. 

With that done, let’s open up VS Code (Visual Studio Code). Go to the open folder button, this is where we choose to keep our files for our discord bot. You can choose to make an entirely new folder, or just select an already existing one.

### Setting Up
- Create a main file called main.py in our folder by right clicking and creating a new file.

- Follow this syntax, the command_prefix can be anything you’d like, as it is just the syntax for commands for the bot when you are actually using it in discord.
- For example, here we are using a very common prefix !, which for example, !play could be a command that allows you to search and play a song.




### testing the bot

- The syntax is bot.run(“Our unique token that we got from discord before”).
- Run our python file, it should return two lines, logging in using a statistic token, and that the Shard ID None has connected to Gateway.
- If you’ve made it this far, goodjob! It's running successfully. 



### Inviting your bot:
- To invite your bot into a server, simply go to  OAuth2 > URL Generator on our discord developer webpage and tick the bot checkpoint under scopes.
- Tick the permissions required for your bot to function under  “Bot Permissions”. Now the resulting URL at the bottom can be used to add your bot to a server.

> [!tip]
> If you are having trouble refer to this website: https://discordpy.readthedocs.io/en/stable/discord.html

Now, you are able to add your own code and functions to your personal bot, have fun! 

# Extra Resource
- Comand: https://discordpy.readthedocs.io/en/stable/ext/commands/commands.html
- https://www.youtube.com/watch?v=93DrbetB6oM
- 
