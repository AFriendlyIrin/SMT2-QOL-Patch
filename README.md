# SMT2-QOL-Patch
Improvements to the Aeon Genesis Shin Megami Tensei 2 fan translation. Unaffiliated with Aeon Genesis or the original translation team. A DiztinGUIsh disassembly file and an Atlus-compatible text dump of the original ROM have been provided if you would like to make your own changes, as well as Cartographer instructions if you wish to make your own text dumps.

Many thanks to the members of the Aeon Genesis Discord server, who were very patient and helpful with my technical questions.

## Installation
To use, apply the IPS patch to a Shin Megami Tensei 2 ROM. (For legal reasons, ROMs cannot be distributed, so please do not ask for one.) I have not tested it on an original Japanese ROM, so I would recommend applying the official translation patch first.

Patch with Lunar IPS: https://www.romhacking.net/utilities/240/

## List of Changes
* All demon races, spell names, and item names changed to official localizations where possible. Additionally, translated demon races left untranslated by official localizations (yes I know these are rough translations, but I had to stick to one word here):
  * "Jirae" to "Natural"
  * "Youma" to "Mystic"
  * "Jaki" to "Monster"
* Improvements to demon status screen:
  * Race is now printed above name instead of on the same line to prevent truncation.
  * HP/MP costs for skills and spells no longer displayed to allow more space for skill names.
  * Skill name length limit increased to 11 characters.
* String length limit on the equipment screen increased to 11 characters. Equipment slot images moved slightly to allow this.
  * KNOWN ISSUE: The cursor for the unequip screen is a bit too wide. I have no idea how sprites are drawn, so I can't fix this.
* Where possible, all skill and item names have been shortened to fit within a 10-character limit. Breathe in that SNES nostalgia of deciphering jumbles of consonants.
* Certain location headers changed:
  * "JAKYOU" to "FUSION"
  * "MESIA" to "CHURCH"
  * "GAIA" to "TEMPLE"
* "CLOSE" status changed to "SEAL".

## Areas of Improvement
I would like to change all instances of "Jakyou", "Mesian", and demon races in dialogue, but this will be difficult until the bank change bug in Atlas is fixed.

Additional improvements are possible, but involve complex graphical work that is far beyond my current level of competence. If you know how to do these, feel free to contribute or make a fork:
* A variable width font protocol would help the text length issue. I have no idea how to do this.
* Fix the unequip cursor.
* I would like to changed from "Shin Megami Tensei" to "Return of the Goddess" or "Revelations" because it annoys me that even the official localization refuses to translate it. This would require adding a full alphabet of italic tiles, as currently only the letters for "SHIN MEGAMI TENSEI" exist in the tile data.
