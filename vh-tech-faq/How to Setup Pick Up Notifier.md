# How to Setup Pick Up Notifier

Update 8 added the Pick Up Notifier mod 
(<https://www.curseforge.com/minecraft/mc-mods/pick-up-notifier>). The default 
configuration will **only** show certain vault mod items **while in a vault**.

**Making It Work With Backpacks**

**_This has been fixed in update 9!_**

You will need to change the mod’s server configuration file to support showing items being picked up right into a Backpack using a Pickup Upgrade.

You can find the file in `saves/<name>/serverconfig/pickupnotifier/pickupnotifier-server.toml` (playing in singleplayer) or `<world name>/serverconfig/pickupnotifier/pickupnotifier-server.toml` (hosting a server). Change “backpack_compatibility” to `true` or replace it with the attached file.

https://cdn.discordapp.com/attachments/889845714207801344/1084536594335277119/pickupnotifier-server.toml

Stop the server / log out of your world before you change it. I also recommend copying it to `defaultconfigs/pickupnotifier/pickupnotifier-server.toml` so it automatically applies to newly generated worlds.

Do note that the information on the Curseforge page regarding config file 
location is, ironically, _outdated_.

**Adding/Removing Items**

Pick Up Notifier displays items based on client side config files. You can have a global one and one for each dimension (e.g. Overworld, Nether, End). Vault Dimensions are generated on the fly, so you will have to make a global configuration for your vault settings, and then dimension-specific ones if you want separate settings for outside of vaults. You can find the settings in `config/pickupnotifier/*.json`. I recommend naming them after the dimension they apply to; the mod ships with files for global (`all.json`) as well as Overworld, Nether and End (named accordingly).

The shipped files will be **overwritten** on **each pack update**. So either you figure something out how to restore them every time, or you need to make your changes in additional files. Priority is alphabetical, descending; if your files are first in the list, they will apply. So basically, create some `0000_<dimension>.json`s.

As to how the dimension configurations work, see 
<https://github.com/Fuzss/pickupnotifier#configuration>. You can edit them 
“live” while the game is running and do `/pickupnotifier reload` to apply any 
changes.

**Visual Setup (Position, Size, …)**

*If you have subtitles turned on, the default positioning of the item display will be __behind__ the subtitles.*

Client side configuration is found in `config/pickupnotifier/pickupnotifier-client.toml`. The file is commented fairly heavily, that should give you the pointers you need.

You can also use the Create config menu (goggles in the ESC menu) or Configured 
(<https://www.curseforge.com/minecraft/mc-mods/configured>) to access these 
settings from the game.
