Protect The Bandit
=========================================
A Warcraft 3 Map built with WurstScript
---------------------------------------

How to Build
------------
This map is built with WurstScript, which is an awesome scripting language that transpiles to JASS. Wurst is also used for generating many of the units in the map at compile time. The map file in the top level directory is known as the _terrain map_ and, in a proper wurst project, is only used for terrain. In this project, about half of the heroes, units, spells, and preplaced objects are defined in the terrain map, which is weird.

To get started, you should clone this repository, and then go download the wurst installer over here
https://wurstlang.org
Once you've got that, you can use the installer app to add wurst to the repo. This will bundle the wurst standard lib into the project (this is all within files ignored by git, so you don't get them by default).
You will also need to install VisualStudioCode and get the appropriate wurst extensions for it.

At that point, you can either open up the map in the world editor to change the terrain or define objects if you prefer to do it that way, or jump straight into the code.

How To Make Changes
-------------------
###Add a Hero
First, define the new hero either in the Object editor in the world editor, or define it in the wurst CustomUnits file, following the other examples.
If you go with the scripting route in CustomUnits, you'll probably also need to define spells in the CustomAbilities file

Now, assuming your hero has some scripted spells or other traits, make a new file called YourHero.wurst. See other hero files for examples on how to organize this.

Once your hero is ready, you can add them as a purchasable unit to the tavern, which has the ID COOL_TAVERN and is found within the CustomUnits.wurst file. Add your hero to the sold heroes section.

If you wish to test your hero, I suggest just spawning one for Player(0) in the init() section of any of the files. You can then also set the level so you can test out their progression, etc

### Add a bad guy or wave
Define the unit in either the object editor or the CustomUnits file like you do for a hero. Define any abilities in the CustomAbilities file and add them to the unit. If there are scripted abilities, I generally put all of their scripts into the MonsterAbilities.wurst package. 
Finally, Look in the Waves.wurst package. You'll see the definition for all the waves there. Either insert a new wave somewhere with your bad guy, or add your guy to an existing wave

### Add a Unit Trainer
Adding a unit trainer is much like adding a bad guy, except instead of adding it to a wave, you make it purchasable at one of the shops defined in CustomUnits.wurst
I suggest looking at the definition of an existing merc trainer in the CustomUnits file to get an idea of the fields that should be set (such as stock start delay, etc).

### Add a Tower
I haven't gotten around to making a builder defined in CustomUnits, so currently all towers are defined in the Object editor. You can simply copy one of the existing ones, make the changes you want, and add it to the stuff built by the builder. Or you can define a new builder.


