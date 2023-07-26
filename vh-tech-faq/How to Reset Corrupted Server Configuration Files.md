# How to Reset Corrupted Server Configuration Files

*If your crash report mentions `mekanism` or `mekanism generators` server config files, see <#1092894660952858635> … because mek.*

**For Clients (Singleplayer)**

1. Open your instance folder. On Curseforge, click the menu button (3 dots), then click “Open Folder”.
2. Go to `saves/<your world name>`.
3. Delete the `serverconfig` subfolder.

**For Servers**

1. Stop the server.
2. Open your server folder.
3. Go into the `world` folder. If you changed `level-name` in `server.properties` to something else, go into that respective folder.
4. Delete the `serverconfig` subfolder.

**If that does not solve it**, delete the `defaultconfigs` folder from your 
instance/server main folder, replace it with a fresh one from the pack zip or 
a new instance, then repeat the steps above.
