# How to Remove Terralith and Accidentally Generated Terrain From a Sky Vaults Server

If you created a Sky Vaults server and didn’t follow <#1078348963423461457> properly, or if you update your Sky Vaults server and forget to remove Terralith again, you will find it generating terrain in newly explored chunks. Here is how to get rid of it.

You will need an NBT editor to fix the world settings, and a world editor for removing affected chunks:
– <https://github.com/jaquadro/NBTExplorer>
– <https://github.com/Querz/mcaselector>

Fixing your world settings:

1. Stop the server and **Create a backup of your server’s world**. It will be the `world` folder by default, or whatever you have set as `level-name` in `server.properties`.
2. Remove `Terralith_v<version>.jar` from your server’s `mods` folder.
3. Open `<worldname>/level.dat` in NBTExplorer.
4. Expand `Data` → `WorldGenSettings` → `dimensions` → `minecraft:overworld` → `generator`.
5. Delete `biome_source`.
6. Save the file and exit NBTExplorer.
7. Start the server. Once it is up, stop it again.
8. Repeat step 3 and 4.
9. Set the `type` to `the_vault:sky_vaults`. Change the `type` within `generator`, not a level higher.
10. Make sure that the entry `structure_overrides` exists. If it does not, create a new _list_ entry for it using the button in the toolbar and leave it empty.
11. Expand `Data` → `WorldGenSettings` → `dimensions` → `minecraft:the_nether` → `generator`. Do **not** delete the `biome_source` entry this time
12. Set `type` to `the_vault:sky_vaults`. Again, under `generator`.
13. Make sure that the entry `structure_overrides` exists. If it does not, create a new _string_ tag for it using the button in the toolbar and set it to `minecraft:nether_complexes`.
14. Save the file and exit NBTExplorer.
15. Make sure the `level-type` in `server.properties` is set to `the_vault:sky_vaults`.
16. Start the server. Once it’s up, stop it and double check that the settings you applied are still there. If not, you probably forgot to remove Terralith or to set the `level-type` in `server.properties`.

Removing chunks that have generated terrain:

1. Stop the server and **Create a backup of your server’s world**. It will be the `world` folder by default, or whatever you have set as `level-name` in `server.properties`.
2. Open your world folder in MCAselector.
3. Select the chunks you want to delete. Make sure you zoom in to target _chunks_ and not _regions_.
4. Click `Selection` → `Delete Selected Chunks` or press `ctrl + d` to delete the chunks.
5. Save the world and close MCASelector.
6. Start the server. The chunks should be gone, and generate fresh without terrain.

If your _Nether_ has generated with terrain, it’s probably easiest to remove it entirely instead of going through the steps above for it as well. So unless you have already built something in the Nether you want to keep, simply delete the `<worldname>/DIM-1` folder.
