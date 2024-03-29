# Bridge Tool

This mod adds a new "bridge tool" that makes placing stone (or glass, earth, or any material) while building a bridge in no-fly mode easy.

**Version 2.2**

The bridge tool has 3 modes that can be switched by left clicking with the tool.
And you can switch the WIDTH of the path built by holding down the SNEAK key and left clicking.
![bridge tool settings](https://i.imgur.com/S4b6UMH.png)
The inventory image changes with the mode indicates exactly how the bridge tool builds in that mode.  For width of 2 and 3 you will note either 2 or 3 little blue squares appear below the main image to let you know what the width is.

On a right click, the bridge tool will attempt to use whatever material is in the inventory slot directly to the right of the bridge tool to build in the direction indicated by the mode

In **mode 1** it will build **FORWARD** in a straight line:
![bridge tool mode 1](https://i.imgur.com/zkYmV6U.png)
This saves you a lot of time pressing the sneak button and leaning over the edge so you can click on the outward face of the node.  Please note that the bridge tool can build out in any of the 4 directions depending on what way you are facing when you right click.

In **mode 2** the bridge tool builds **DOWN** diagonally:
![bridge tool mode 2](https://i.imgur.com/WfqIQkI.png)
This is perhaps the most important function of the bridge tool because what seems like it should be simple, building down from a bridge you are standing on, is virtually impossible without this tool.

In **mode 3** the bridge tool builds **UP** diagonally:
![bridge tool mode 3](https://i.imgur.com/nz9mubc.png)
This is not hard to do without the tool, but using the tool saves you several steps.

And when you select a **width** of 2 or 3 by holding down the sneak button and left clicking the tool will build a path of that width:
![bridge tool width 2](https://i.imgur.com/sywdErd.png)
![bridge tool width 3](https://i.imgur.com/tKHQxbO.png)

If the bridge tool can not build where you asked it to, or if it runs out of material in the stack to the right of the tool, it will notify you of the problem via chat message.

The bridge tool is crafted using 3 steel ingots in a v shape, and one mese crystal:

```
steel ingot,                     ,steel ingot
           ,    steel ingot      ,
           ,mese crystal fragment,
```

![bridge tool crafting](https://i.imgur.com/BF9hdss.png)

The inventory image will switch from the tool itself to the mode image the first time you left click with the tool.

The bridge tool automatically orients **stairs** in the proper direction.  When building a 3 node wide stair, the tool will ensure that all stairs point the correct direction.  And when building forward, the tool will orient the stair downward.

And the bridge tool is now configured to wear out.  If you wish to implement this feature edit the init.lua and change the value of WEAR_PER_USE from 0 to whatever you wish.  (Max wear is 65535 and wear will be applied for each node of width of the path you are building)

**Video:**
Excalibur Zero created a video demonstrating this mod:
[https://www.youtube.com/watch?v=j2E9ojtyitc](https://www.youtube.com/watch?v=j2E9ojtyitc)

**Author:** Kilarin (Donald Hines)

**Credits:**
My son helped me with some ideas for this mod.  I got a lot of code examples from the screwdriver mod in minetest_game by RealBadAngel, Maciej Kasatkin.  I also copied and modified the screwdriver's mode number images for use in the bridge tool inventory images.
Topywo suggested adding wear, correcting down stair orientation, and using not_in_creative_inventory.  Sokomine suggested adding width so that you could build 2 or 3 wide.

**Dependencies:**
soft depends on default, but without default you have no recipe.

**Incompatibilities:**
Problems have been reported when using this mod with inventory tweak

**License:**
code MIT, textures CC BY-SA 3.0

**github source:** https://github.com/Kilarin/bridgetool

**github Download:** https://github.com/Kilarin/bridgetool/archive/master.zip

**ContentDB:** https://content.minetest.net/packages/Kilarin/bridgetool

**Minetest Forum:** https://forum.minetest.net/viewtopic.php?f=11&t=9126

**Changelog**

--Version 2.2
Added new global enable_chat_warn at top of init.lua that can be set to NO if you don't want bridgetool warning messages to appear in chat.
Removed dependency upon default.  Put the recipie inside an if checking for default so that in the unlikely case someone is running this without default, they still could.  they would just have to use /giveme or creative mode to get the tools
Corrected two undeclared globals to locals.
Renamed the git repository to bridgetool-master to be in line with other mods.

--Version 2.1
Corrected fact that 3 wide stairs would sometimes orient the 3rd stair the wrong way
Modified stair orientation when using mode 1(forward) so that the stair will face down (since the only reason you would use the "forward" option with this tool and a staircase is to begin a down stair.)

---Version 2.0
Added width of 2 or 3
corrected down stair orientation
added not_in_creative_inventory=1 to all of the "mode" versions of the tool
added wear option

---Version 1.0
Initial release


