# paulie glot's discord bible translation toolkit

use this toolkit to make collaborative Bible translations and a Discord verse browser bot!

## setting up the bot and running it

you supply the discord server, the bot account, and a device to run the bot from. currently only one discord server is supported at a time.

you will need to write an environment file for the bot. this will not be difficult.

the environment file should be called .env, and should be located in the project's root directory.

the environment file should define three variables: DISCORD_TOKEN, DISCORD_GUILD, and GUILD_ID.

the value of DISCORD_TOKEN should be set to the bot's token. you can find this in the Bot section of your bot's page in the Discord Developer Portal.

the value of DISCORD_GUILD should be a string containing your Discord server's name.

the value of GUILD_ID is the ID of your Discord server. get this by right-clicking on the server's name at the top of the channel menu and selecting "Copy Server ID". if you don't see this option available, go to the Advanced section of your Discord User Settings and turn on Developer Mode.

the bot should have all it needs to function now. navigate to the project root directory in your terminal and run bot.py. you should get a couple of status messages, then a ready indicator.

you should now see your bot listed as "online" in your server's user list. users in your server can now interact with the bot. woohoo!

note that since the bot fetches verses from its local copy of the chapter files, you will need to periodically restart the bot to update the local copy after changes are made.

## using the buildbook script

buildbook.sh has two purposes: to set up the chapter files and folders for each book and section, and also to compile all their contents into the fulltext file full.md.

all the sections, books, and chapter files are set up in this repo, but in case you end up losing some for whatever reason you can always run buildbook.sh again and it will set them up for you.

buildbook.sh generates chapter files based on the contents of the file chapters.txt in the project root directory. give it a look, you should be able to figure out how to modify it to fit your needs. it also uses this file to compile the chapter files into full.md.

note that buildbook.sh cannot rename files and folders - you will have to rename them manually and edit chapters.txt to reflect this.

you should run buildbook.sh periodically to keep the fulltext file up-to-date. as a useful morale boost, it will also inform you of how many verses have been completed, presuming that they have been formatted correctly.

## adding new verses

each verse should take up one line of text and one line only. they should be preceded by their verse number within the chapter, a colon, and a space.

new verses should be added to the chapter files of their respective chapters. do NOT add them in full.md, as they will be regenerated away the next time buildbook.sh is run.