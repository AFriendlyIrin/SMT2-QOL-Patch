# SMT2-QOL-Patch
Improvements to the Aeon Genesis Shin Megami Tensei 2 fan translation. Unaffiliated with Aeon Genesis or the original translation team. A DiztinGUIsh disassembly file and an Atlus-compatible text dump of the original ROM have been provided if you would like to make your own changes, as well as Cartographer instructions if you wish to make your own text dumps.

Many thanks to the members of the Aeon Genesis Discord server, who were very patient and helpful with my technical questions.

## Installation
To use, apply the IPS patch to a Shin Megami Tensei 2 ROM. (For legal reasons, ROMs cannot be distributed, so please do not ask for one.) I have not tested it on an original Japanese ROM, so I would recommend applying the official translation patch first.

Patch with Lunar IPS: https://www.romhacking.net/utilities/240/

## List of Changes
* All demons, demon races, spell names, and item names changed to official localizations where possible. Additionally, translated demon races left untranslated by official localizations (yes I know these are rough translations, but I had to stick to one word here):
  * "Jirae" to "Dwarf"
  * "Youma" to "Mystic"
  * "Jaki" to "Monster"
* Improvements to demon status screen:
  * Race is now printed above name instead of on the same line to prevent truncation.
  * HP/MP costs for skills and spells no longer displayed to allow more space for skill names.
  * Skill name length limit increased to 10 characters.
* The HP/MP display in the status select menu has been moved a bit to the right, allowing for 2 extra characters of name space.
* String length limit on the equipment screen increased to 11 characters. Equipment slot images moved slightly to allow this.
* Where possible, all skill and item names have been shortened to fit within a 10-character limit. Breathe in that SNES nostalgia of deciphering jumbles of consonants.
  * Significant change: "Divine Retribution" changed to "Judgment".
* Certain location headers changed:
  * "JAKYOU" to "FUSION"
  * "MESIA" to "CHURCH"
  * "GAIA" to "TEMPLE"
  * "JUNKS" to "ITEMS"
  * "KAIFUKU" to "SPRING"
* "CLOSE" status changed to "SEAL".
* "GOOD" status changed to "NORMAL".
* Demon "Depth" changed to "Drowned" to make it clearer they're the victims of the Great Flood (as explained in the artbook).
* Fixed the text glitch that occurred when using Analyze Spell.
* Shortened some item/spell info text:
  * "All enemies" to "All"
  * "Fusion Sword" to "Fus. Sword"
  * "Electricity" to "Electric"
* Changed "wait for input" commands in several battle messages to auto-newline commands instead to make battles go faster. (Also did the same for Puck's spiel during the chase sequence because dear god that got annoying.)

### Known Issues
* Demon names in the party GUI will sometimes run out of bounds. This can't be fixed easily, as the max length variable is shared between all menu entries; reducing it would also truncate item and skill names.
* The cursor for the unequip screen is a bit too wide. I have no idea how sprites are drawn, so I can't fix this.
* There may be some glitches when the game attempts to load text located right at the boundary of certain databases (e.g. demon names vs. skill names vs. bar NPC names), as these boundaries are hardcoded in the printing code and not automatically updated to reflect changed text addresses. I've tried to stay on top of this, but I can't guarantee I've found them all.

## List of Changes - Experimental Version
I've also included another patch marked "exp". This patch contains alternate translations for demon races that I feel are more accurate to the original Japanese. The official localizations are, frankly, pretty terrible, and garble a lot of information that helps you understand how the different races are related to one another.

The races changed are:
|&nbsp; |&nbsp; |&nbsp;
|--- |--- |---
|Godly → God         |Herald → Archangel  |Avian → Sacred Bird           
|Avatar → Beast God  |Holy → Sacred Beast |Dragon → Dragon God 
|Lady → Mother       |Divine → Angel      |Snake → Dragon      
|Night → Nightmare   |Fiend → Demon       |Megami → Goddess
|Femme → Fatale      |Vile → Devil        |Wilder → Predator
|Wood → Plant        |Tyrant → Demon Lord |Drake → Wyrm             
|Spirit → Ghost      |Haunt → Undying     |Foul → Anathema

Yes, this means the Angel demon is now "Angel Angel", and the Archangel demon is not of the Archangel race. It was like that in the original Japanese too. Embrace the absurdity. However, I did make one concession: The Nightmare demon is changed to "Marra" (the Old English name for the same creature) so it's not "Nightmare Nightmare".

The encounter message for Jack the Ripper will spill over to a second line with this patch. I have not tested it with other demons, but they should be fine as the ones with the greatest length differences (Sacred Bird, Beast God, Sacred Beast, and Dragon God) can't be encountered in the wild. Demon Lord may also cause problems, but I haven't tested this since I don't have save states just before their fights.

This patch alters the pointers for in-message and in-menu demon races so that they both point to the same text. Testing showed no problems, but just a heads-up that if something goes wrong that might be the culprit.

## Areas of Improvement
I would like to change all instances of "Jakyou", "Mesian", and demon races in dialogue, but this will be difficult until the bank change bug in Atlas is fixed.

Additional improvements are possible, but involve complex graphical work that is far beyond my current level of competence. If you know how to do these, feel free to contribute or make a fork:
* A variable width font protocol would help the text length issue. I have no idea how to do this.
* Fix the unequip cursor.
* I would like to change the title from "Shin Megami Tensei" to "Return of the Goddess" or "Revelations" because it annoys me that even the official localization refuses to translate it. This would require adding a full alphabet of italic tiles, as currently only the letters for "SHIN MEGAMI TENSEI" exist in the tile data.
* It is technically possible to increase the size of the message box when displaying spell/item info, but doing so currently causes it to glitch out and load garbage tiles in the expanded area. If this could be fixed, info boxes could be expanded to include an additional line, which would be really helpful.
