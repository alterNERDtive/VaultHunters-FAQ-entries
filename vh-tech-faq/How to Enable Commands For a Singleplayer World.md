# How to Enable Commands For a Singleplayer World

There are two ways you can enable “cheats” (which would be better called “commands”, and are in the level file …). One is temporary, one is permanent.

**Temporary:**

Hit `Escape`, click “Open to LAN” and enable commands in the prompt that follows. Do keep in mind that your client will effectively turn into a server, so e.g. you cannot pause the game until you relog.

**Permanently:**

Grab <https://github.com/jaquadro/NBTExplorer/releases>. Run it, and navigate to your instance folder, then open `saves/<your world folder/level.dat`.

Under `Data`, change `allowCommands` to `1` (see screenshot). Save the file, 
close NBTExplorer, and start Minecraft. You should now be able to use commands 
in the world you have edited.
