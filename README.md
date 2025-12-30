# Orzel Loot Filter  

   * [1. Overview](#1-overview)
   * [2. Design Goals](#2-design-goals)
   * [3. Might corrupt](#3-might-corrupt)
   * [4. Moneybags and Golddigger mode](#4-moneybags-and-golddigger-mode)
   * [5. Filter levels](#5-filter-levels)
   * [6. Editor](#6-editor)
   * [4. Colors & Visuals](#4-colors-visuals)
   * [7. Installation](#7-installation)
   * [8. Known Limitations](#8-known-limitations)
   * [9. Credits](#9-credits)

<h3>!!! -------------------------------------------------------------------------------------------------------------------- !!!</h3>

$${\color{red}Currently \space this \space loot \space filter \space is \space still \space work \space in \space progress, \space but \space every \space unchecked \space item \space is \space selected \space as \space God \space to \space not \space hide \space anything \space by \space mistake}$$

If you wanna help develop this loot filter you can use this GitHub page and [create new issue](https://github.com/orzel403/OrzelLootFilter/issues) to discuss

<h3>-------------------------------------------------------------------------------------------------------------------------</h3>

<br>
//TODO Donation link
<br>

## Overview

Orzel’s Loot Filter is designed to reduce cognitive overload without hiding useful information. Instead of treating loot as a binary show / don’t show problem, the filter classifies items by **value potential**.

Items are divided into meaningful tiers called item's level (**Low**, **Mid**, **God**), corruption candidates are explicitly highlighted called **Might corrupt**, crafting bases are surfaced intentionally and endgame content such as maps is made easier to identify and pick up. The goal is not to decide for the player, but to make good decisions faster.

The filter is published with customization in mind. It is optional since default value will fit most of the players. If you willing to modify this loot filter read more about [Orzel's Loot Filter Editor](#editor)

<br>

## Design Goals

The filter was built around a few core principles:

- Divide loot by **item's level**, (not item's ingame rarity alone):
  - Low: worth less than 1 wss, good when building new char with no backup gear
  - Mid: worth more than 1 wss
  - God: worth high runes or just high demand
- **Might corrupt** system (Shows which item is worth corrupting and which ones are most valuable)
- Allows unfilter items for **Crafters** to quickly collect needed bases
- Adds **Moneybags** and **Golddigger** mode to easy and fast (if needed) gold collection
- Support **newer players** with contextual hints (e.g. rune values, wss converter etc)
- Don't hide anything (including gold) while in the city. That's often issue with other loot filters
- Keep the screen readable in high-density situations
- Allow users to control how aggressive the filtering is

In short: fewer pauses, fewer mistakes, faster killing, better flow, better drop.

<br>

## Might corrupt
//TODO

<br>

## Moneybags and Golddigger mode
The $${\color{limegreen}Moneybags}$$ system highlights items that provide an excellent **gold-to-inventory-space ratio**, allowing players to quickly identify loot that is worth picking up purely for selling.

Instead of treating all vendor trash equally, the filter evaluates items by their **physical size** and **vendor price**, then visually marks the most efficient gold sources.

<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/de203d67-f401-43d9-9ca5-81967cc62f0e" />

Items are grouped by inventory footprint:

- **2×1** items shown as $${\color{limegreen}SSS}$$<br>
  _Examples: wands, small orbs, throwing weapons, small daggers or belts (1x2)_

- **3×1 items** shown as $${\color{limegreen}SS}$$<br>
  ! Visible only in Golddigger mode !<br>
  _Examples: short staves, maces, assassin weapons, quivers_

- **2×2 items** shown as $${\color{limegreen}S}$$<br>
  ! Visible only in Golddigger mode !<br>
  _Examples: helmets, gloves, boots, paladin shields_

Additionally to regular moneybags $$$ other smaller bags are visible only in Golddigger mode which also shows gold stacks and mark those on map as well. Bigger stacks are marked with bigger dot so you can easily see gold clusters.

<br>

## Maps selection
All maps are colored the same <img width="10" height="10" alt="image" src="https://github.com/user-attachments/assets/631eb7a9-d6cd-49c2-955a-aaae4f2b77c6" /> sage color. 

<img width="940" height="469" alt="image" src="https://github.com/user-attachments/assets/ed527059-60c8-4129-96dd-ae399da66fe2" />

Additional to their name they have prefix which is map's tier. Also color of that prefix shows map ingame rarity: white = normal, blue = magic and yellow = rare.<br>
Additional to all of the above you might wanna set your own map likeness. To do it you need to modify 'MAPLIKED', 'MAPMEDIUM' and 'MAPHATE' aliases in filter file or preferably use [Editor](#editor) instead. It will allows to show map suffixes to fit your likings.


| Possible prefix (tier)                             | Possible suffix                                |
|----------------------------------------------------|------------------------------------------------|
| [ $${\color{gray}T1}$$ ]                           | $${\color{red}¼}$$ - maps you don't like       |
| [ $${\color{blue}° \space T2 \space °}$$ ]         | $${\color{blue}½}$$ - maps other maps          |
| [ $${\color{goldenrod}°° \space T3 \space °°}$$ ]  | $${\color{limegreen}¾}$$ - maps you like       |

<br>

## Crafters
//TODO

<br>

## Editor

You are encouraged to treat this filter as a framework, not a black box. That's why I created Editor, so you can easly manipulate filter so it could always be the most perfect fit for you.

<br>

## Filter levels

There are a few loot filter's levels that allows you to modify what is display under Alt key. I recommend bind some hotkeys in **Configure hotkeys** menu option. I would also recommend set some keys to your favourite levels to quick change. <br>
My bindings are:

| Key              | Description                                    |
|------------------|------------------------------------------------|
| **<**            | decrease filter level                          |
| **>**            | increase filter level                          |
| **[**            | level 7 for finding crafting materials         |
| **\]**           | level 9 for regular map runs                   |
| **=**            | level 12 (God mode) for running quick maps     |
| **Backspace**    | to turn off filter completly (quick check up)  |
| **Num -**        | to reload (eg. after using [Editor](#editor))  |

Note that whatever description you see ingame when changing levels is exactly what you will see/not see!

Note! Hidden items have additional 1 level gap. While being hidden (not completly) item is displayed as rotated exclamation mark **¡**, when unhidden are mark with regular **!**.
Unhidden (visible even on upper level filters) by default are [rare]: amulets, rings, gloves, belt, boots (all-class items). <br>
To modify what stays unhidden you need to modify 'UNHIDE' alias in filter file or preferably use [Editor](#editor) instead.
<img width="1135" height="541" alt="image" src="https://github.com/user-attachments/assets/9497c887-72d2-4725-822a-f514a3676a76" />



| Level  | Name                                     | Description                                                                          |
|--------|------------------------------------------|--------------------------------------------------------------------------------------|
| 0      | Default (by game)                        | -                                                                                    |
| 1      | No Scrolls                               | No tp and id scrolls                                                                 |
| 2      | No Whites                                | No white items except sk+sox+ed)                                                     |
| 3      | No Blues                                 | No magic items (except rings, amu)                                                   |
| 4      | No Yellows ¡                             | Hides rare items (except amu, ring, jewls items)                                     |
| 5      | No Low Unique/Set ¡                      | Hides items with level Low (+completly hides yellows)                                |
| 6      | No Potions                               | No HP, MP and rev, shows only R+ (+completly hides low items)                        |
| 7      | No Flawless Gems, No Small Charms        | No flawless gems and small charms                                                    |
| 8      | No Perf Gems, No Low Runes               | No gems at all and no low runes (El-Ort)                                             |
| 9      | No Mid Unique/Set ¡                      | Hides items with level Mid                                                           |
| 10     | No Mid Runes, No Jewels, No Grand Charms | No jewels, no charms at all and no mid runes (Thul-Lem) (+completly hides mid items) |
| 11     | Golddigger                               | Read more about Golddigger mode                                                      |
| 12     | God mode (minimalistic)                  | Shows only items with level God and R+ potions                                       |

To check above list but in more specific view check TODO

The rules scale with progression, so the filter evolves naturally as the character moves from leveling into endgame farming but that was mainly imported from Wolfie's base loot filter.

<br>

## Colors & Visuals

Colors in Orzel’s Loot Filter are semantic, not only decorative. Gear's names are modified mostly when item is unidentified, after that i goes to regular description to not irritate the eye. To understand it better please read notes below.

There are a few colors in main palette:
| Color                                                                                                                              | Item groups                                   |
|------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/bdad79ac-8e22-405f-bd6d-ab5205bef309" />   | Runes, Keys                                   |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/f4b47f63-e3ab-4ff7-9923-e045072ec18e" />   | Materials, Might corrupts                     |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/0644dbfb-98fe-4af1-970a-5305b112efc1" />   | Gems (with addition of corresponding color    |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/631eb7a9-d6cd-49c2-955a-aaae4f2b77c6" />   | Maps                                          |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/631eb7a9-d6cd-49c2-955a-aaae4f2b77c6" />   | Jewels                                        |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/dc86fbf9-9bcc-4ccb-a120-502ed1f471d9" />   | Charms                                        |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/79fb4841-8b98-4ecb-a70a-5b365a0c3f36" />   | Catalyst shards, Rev potions                  |

| Color                                                                                                                              | Items rarity                                  |
|------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/e8789a47-2aec-4249-afae-3ca1fccb16a7" />   | Unique                                        |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/2700a816-4732-46d7-8402-86acaab38b21" />   | Rare                                          |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/09f06701-9792-4231-932a-6423a4ab8b7a" />   | Magic                                         |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/bdad79ac-8e22-405f-bd6d-ab5205bef309" />   | Craft                                         |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/0644dbfb-98fe-4af1-970a-5305b112efc1" />   | Eth, Socket                                   |
| <img width="20" height="20" alt="image" src="https://github.com/user-attachments/assets/cae4a8dc-d2c8-403c-8a24-e673059bcd97" />   | Normal                                        |

Nothing is colored “because it looks nice”. If it stands out, it has a reason.

<br>

## Installation

- Download the loot filter file 
- Place it in your Project Diablo 2 loot filter directory (...Diablo II\ProjectD2\filters\local)
- Select the filter in-game from the loot filter menu  
- Adjust filter level editor if applicable:
  - To install editor download orzel.html file
  - Editor is standalone, runs locally in browser, doesnt need any server, nothing
  - Place editor html file to the same location as loot filter file
  - Run by any browser

No external tools required.

<br>

## Known Limitations

$${\color{red}Currently \space this \space loot \space filter \space is \space still \space work \space in \space progress, \space but \space every \space unchecked \space item \space is \space selected \space as \space God \space to \space not \space hide \space anything \space by \space mistake}$$

- Item value is contextual and meta-dependent; no filter can predict every market shift
- The filter reflects the author’s valuation logic, which may differ from niche playstyles
- Extreme build-specific needs may require manual adjustments

This is a filter, not an oracle.

<br>

## Credits

- Built for **Project Diablo 2 – Season 12**
- Based on [Wolfie's loot filter](https://github.com/WolfieeifloW/pd2filter/)
- Inspired by community knowledge, PD2 mechanics, and thousands of items left on the ground for science
