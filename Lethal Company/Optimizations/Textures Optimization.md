# Textures Optimization

Working on textures can greatly help you in order to shrink your bundles size.

Open any texture used in your project (even if it is vanilla from the `LethalCompany/Game/Materials` folder).

<img width="778" height="712" alt="image" src="https://github.com/user-attachments/assets/f0e16337-8442-4791-b6a4-c1d63fcb8152" />

What you can see are three "maps" that we can retouch.

**‼️ `GPU Instancing` can be set for commonly used materials, basically means if you use it more than once in a scene. ‼️**

### Texture settings

Open any Texture and look at it's settings.

<img width="775" height="753" alt="image" src="https://github.com/user-attachments/assets/7b906141-787e-49cc-848d-6e6e789c40ab" />

| Field | Value |
| :---- | :---- |
| Read/Write | Better let it be enabled. |
| Max Size | To achieve a more "vanilla" look, set it to `512`. <br /> You can set the resolution lower for textures that are barely visible, but `512` is the standard. <br />If you feel that the quality has dropped too much, set it to `1024`, but don't go any higher than that please. |
| Compression | For a more "vanilla" look, use `Normal Quality`, but you can always go lower; it won't be very noticeable in the game. |
| Use Crunch Compression | Use Crunch Compression. |
| Copressor Quality | Normally you can set it to `50%`, but for some textures you can go down to `0%`, it depends on your choice. |

**For some Normal Maps** make sure they are actually Normals:

<img width="771" height="180" alt="image" src="https://github.com/user-attachments/assets/1fbf6b3c-5a9d-463d-9ac2-a495053f5161" />

**By performing this compression procedure for each "Map", you can significantly reduce the size of the `Material`, and thus all bundles themselves.**

Don't forget to check for overrides aswell (you don't need them).

<img width="759" height="152" alt="image" src="https://github.com/user-attachments/assets/a9013b5c-5123-472b-b6a3-6f7eb5e76481" />

**Credits to @s1ckboy ([s1ckboii]([https://github.com/Sniper1-1](https://github.com/s1ckboii)) for this guide in [Lethal Company Modding](https://discord.gg/raXqCP6NZw) Discord)**
