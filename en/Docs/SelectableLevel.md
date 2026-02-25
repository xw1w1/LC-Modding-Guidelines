# SelectableLevel
**`SelectableLevel`** is an **entity** representing a game level or moon variant that the player can select from the menu (`Moon Catalog`) before starting an expedition.
Simply, every moon in Lethal Company, modded or not, is a **`SelectableLevel`**.

APIs such as `LethalLevelLoader` or `DawnLib` allows you to register your own custom levels, and this object packs data for the new level, such as the name of the moon, cost, weather settings, spawn settings for scrap, entities, etc.

Thus, **`SelectableLevel`** acts as a node between the selection menu and the actual level content.

<img width="832" height="400" alt="image" src="https://github.com/user-attachments/assets/d102820c-6049-47f6-86bb-cd6a39f31417" />

## Selectable Level Settings.

| Field | Description |
| :-------- | :---- |
| `Planet Prefab` | Planet prefab, which is drawn on the outside of the ship and is usually not even visible. There are currently three types: `Moon 1` (Deserted), `Moon 2` (Leash forest), `Moon 3` (Snowy). <img width="237" height="93" alt="image" src="https://github.com/user-attachments/assets/a5367597-cbf9-470b-a759-cc8a9b4ccb67" /> |
| `Scene Name` | A fairly self-descriptive field name. You must enter the EXACT name of the scene where your "moon" will be placed. |
| `Level ID` | The ID under which your moon will be located. Usually, the APIs themselves assign this at runtime, so just leave it at `0`. |
| `Locked For Demo` | Determines whether your planet will be open for visiting in demo, _hovewer i ain't really seen any kind of demo for Lethal Company, so just left it unchecked_. |
| `Spawn Enemies And Scrap` | Determines whether enemies and scrap should spawn on this moon. |
| `Planet Name` | The name of your moon. Example: `12 Aerona`. |
| `Level Description` | The description of the planet. Exactly what appears on the main ship monitor when you are in orbit of this planet. There are no any strict limits about it's size, but you may look at it in game and see if it looks good. In other case, you can do as much as you want, just add [AutoScroll](https://thunderstore.io/c/lethal-company/p/mrov/AutoScroll/) as a dependency so that the text slowly scrolls when it’s on the main monitor if it’s too long instead of being cut off. |
| `Video Reel` | The video clip that appears on the main ship monitor when you are orbiting this planet. |
| `Risk Level` | The danger level of the planet. `A`, `B`, `C`, `D`, `S`, `S+`, `S++`, anything of your choice. In game, it is displayed as `Hazard Level` when you land on the planet. |
| `Time To Arrive` | The amount of time it will take for the ship to land. In the case of `Adamance`, it's 4 seconds. |
| `Day Speed Multiplier` | The speed multiplier at which the day passes on the planet. Standard is `1`, but if you want to slow down or speed up time on the planet, you can play around with it. |

## Weather Settings (Random Weathers).
<img width="839" height="528" alt="image" src="https://github.com/user-attachments/assets/ec6d8896-225b-44f1-b181-c21b4a24758b" />

**`Random Weathers`** - is an array of elements that will be used when choosing the weather. |

| Field | Description |
| :--------- | :---- |
| `Weather Type` | Weather type, can be `Rainy`, `Stormy`, `Foggy`, `Flooded`, `Eclipsed`, etc. |
| `Weather Variable` | Variable used to set some of the weather settings. You can refer to the image below.|
| `Weather Variable 2` | Variable used to set some of the weather settings. You can refer to the image below.|
| `Override Weather` | Whether the weather should be fixed to the one selected in `Override Weather Type`. |
| `Override Weather Type` | Weather type to override with. |
| `Current Weather` | Runtime variable responsible for the current weather on the moon. Don't touch |

<img width="741" height="410" alt="image" src="https://github.com/user-attachments/assets/3dac0009-d101-4dcc-9ce0-2115ea4beffe" />

## Level Values.
<img width="827" height="337" alt="image" src="https://github.com/user-attachments/assets/eb98a9e1-6a14-4d6e-8163-a76c1a7e88f0" />

- `Factory Size Multiplier` - a value that affects the size of the facility itself. 

   On `Titan`, this value is `2.2`, while on `Experimentation` it's `1`. Choose the one that's comfortable for you.

### Indoors sound library (Dungeon Flow Types).
<img width="932" height="399" alt="image" src="https://github.com/user-attachments/assets/9bf3cdbe-0818-423b-857c-f1c652fa6d6f" />

- **`LevelAudienceLibrary`** - a library of random audios that play on the interior.

| Field | Description |
| :--------- | :---- |
| `Rarity` | Determines how often this library can be heard on your map. |
| `Override Level Ambience` | `Level Ambience Library` ScriptableObject. You can also make your own. |

### Traps appearing inside the facility (Spawnable Map Objects).
<img width="836" height="606" alt="image" src="https://github.com/user-attachments/assets/d0fdd505-218b-4f1f-b973-63975da31315" />

- `Spawnable Map Objects` - these are mines, turrets, and other traps that may await you inside. 

Here you can customize them, remove one, or edit them, but often this element is left untouched.

### Decorations outside (Spawnable Outside Objects).
<img width="839" height="291" alt="image" src="https://github.com/user-attachments/assets/b9f21071-206c-4907-94e0-70f9c61aaa94" />

- `Spawnable Outside Objects` - these are additional decorative elements that appear outside and are distributed across the map.

They include leafless trees, a pile of rocks, a giant pumpkin, etc.

## Scrap Settings.

### Scrap appearing inside the facility (Spawnable Scrap).
<img width="849" height="218" alt="image" src="https://github.com/user-attachments/assets/38f2e746-39c0-48d4-a2be-226965e3a7b3" />

- **`Spawnable Scrap`** is an array of items that can appear inside the facility and that players can collect.

| Field | Description |
| :--------- | :---- |
| `Spawnable Item` | An `Item` type to spawn. |
| `Rarity` | Determines how often this item can be encountered on your map. |

### Scrap value settings
<img width="837" height="87" alt="image" src="https://github.com/user-attachments/assets/0b3dc798-dfa7-4b9c-8873-23f3de65fb98" />

| Field | Description |
| :--------- | :---- |
| `Min Scrap` | The minimum number of items that can appear inside the facility. |
| `Max Scrap` | The maximum number of items that can appear inside the facility. |
| `Min Scrap Value` | The minimum total value of all items inside the facility. |
| `Max Scrap Value` | The maximum total value of all items inside the facility. |

   **Don't try to overly increase or decrease min/max scrap value, try to make it somewhat stable. If your planet is not a lategame option, don't make max scrap value exceed 1000 or more, although, this depends on the overall difficulty of your planet and your intentions.**

# Enemies Settings (Level enemy values).
<img width="828" height="90" alt="image" src="https://github.com/user-attachments/assets/e7dd1be3-fe46-401a-a0d4-65d153e4544a" />

| Field | Description |
| :--------- | :---- |
| `Max Enemy Power Count` | The maximum power count of entities that can exist simultaneously inside the facility. |
| `Max Outside Enemy Power Count` | The maximum power count of hostile entities that can exist simultaneously outside. |
| `Max Daytime Enemy Power Count` | The maximum power count of daytime entities that can exist simultaneously outside. |

   The idea is that “`Blob`” can be power of `1`, and “`Coil Head`” - `3`, that allows each type of enemies to contribute simulganeously according to it's impact.

   You can find out what weight each entity have by referring to the wiki: https://lethal.miraheze.org/wiki/Entities#Entity_list.

## Enemies spawn chances.

**`Enemies`** - a list of creatures that will appear inside the facility.

https://lethal.miraheze.org/wiki/Entities

<img width="839" height="446" alt="image" src="https://github.com/user-attachments/assets/fc11729c-1645-4304-8ebb-d46e944993f1" />

| Field | Description |
| :--------- | :---- |
| `Rarity` | The chance of a specific entity appearing during a spawn cycle. |
| `EnemyType` | Precisely those enemies that we may encounter in the game. |

<img width="1205" height="227" alt="image" src="https://github.com/user-attachments/assets/456cb9f4-1709-479f-bf4d-2424f9be89f5" />

   **Keep in mind that some of the creatures in this list may appear outside, and their presence inside the facility may look very strange and wrong, although the game allows it.**

### Outside enemies
<img width="833" height="220" alt="image" src="https://github.com/user-attachments/assets/dcb40ea9-74dc-4c43-a25e-81391fbbb3ba" />

- **`Outside Enemies`** - a list of creatures that will appear outside, such as forest giants, robots (RadMechs), etc.

   **For some entities that should be inside, placing them outside can cause serious lag, but I support experiments and good options could include `SandSpider` or `MaskedPlayerEnemy`.**

### Daytime emenies
<img width="944" height="293" alt="image" src="https://github.com/user-attachments/assets/a5c3d274-cc1a-42e3-958b-86163c780ec6" />

- **`Daytime Enemies`** - the ones you will see at first when you arrive on the `March` or `Vow`, these are usually harmless swarms of flies.

   `RedLocustBees` are the `Circuit Bees` ones that spawns with a Bee Hives on the moon.

   https://lethal-company.fandom.com/wiki/Circuit_Bee

### Miscellaneous
Imagine that at a certain moment (spawn cycle), the game selects a random number between `X` and `Y`. If this number `Z` is less than or equal to the number `W` (on the graph line), then the entity will spawn.

<img width="950" height="71" alt="image" src="https://github.com/user-attachments/assets/fecb2d3d-1e10-48c1-9f2c-e246b549426f" />

| Field | Description |
| :--------- | :---- |
| **`Enemy Spawn Chance Throughout Day`** | A graph responsible for the spawn chance of indoors enemies, such as Coil head, ghost girl, spider, nutcracker etc. throughout the day. |
| **`Outside Enemy Spawn Chance Through Day`** | A graph responsible for the spawn chance of outdoors enemies throughout the day. |
| **`Daytime Enemy Spawn Chance Through Day`** | A graph responsible for the spawn chance of outdoors entities throughout the day. |
| **`Spawn Probability Range`** | Affects the range in which the final total number of enemies that can appear during the current spawn cycle will be generated. |
| **`Daytime Enemies Probability Range`** | Affectsffects the range in which the final total number of daytime enemies will be generated — those creatures that appear during daylight hours — and may appear during the current spawn cycle. |

This means that in single spawn cycle:

The total spawn will be randomly selected within a range around the base probability (±`SpawnProbabilityRange`),

While daytime enemies will have a wider variation (±`DaytimeEnemiesProbabilityRange`).

Both of these settings affect the variability of random enemy spawns, not their absolute weights/percentages.

## Other level settings.
<img width="834" height="48" alt="image" src="https://github.com/user-attachments/assets/eadd3dd9-b289-4243-85cf-4b29188009ea" />

| Field | Description |
| :--------- | :---- |
| `Level Includes Snow Footprints` | Whether snow footprints should be left on this planet. |
| `Level Icon String` | Name for the visual icon level that will be used for display in Discord RPC. * |

## How to add snow footprints to your moon: 

https://github.com/xw1w1/LC-Modding-Guidelines/edit/main/en/Docs/Moons/SnowFootprints.md

# * - I'm not entirely sure about this statement.
