# Combined Meshes

If you want to use certain assets from vanilla moons, you may encounter a problem where objects appear to be ‘frozen.’ This is most likely due to the fact that they use `Combined Meshes`.

<img width="777" height="254" alt="image" src="https://github.com/user-attachments/assets/cb620ea2-a5bd-4c1f-bc87-b920ee1c0037" />

In your `Project` panel, navigate to `Assets` folder, and create new folder named `Editor`.

Download this .zip file and extract `MeshSplitting.cs` into `Editor`.

[https://gist.github.com/nomnomab/858a85af102fa21fe0d51012dabc094e](https://gist.github.com/nomnomab/858a85af102fa21fe0d51012dabc094e)

**Once added, a reload of your project may be required.**

According to Nomnom: "Only the "split all in scenes" might be wary due to the settings usage, but the normal single-object splits should be fine."

### Usage

To use, find an object in a vanilla Scene that is a `Combined Mesh` and right click the "`Mesh Filter`" component label and then "`Split Combined Meshes`" from the pop-up.

<img width="767" height="478" alt="image" src="https://github.com/user-attachments/assets/a6012216-5028-4058-b344-4935271e7827" />

**Note: Not all `Combined Meshes` will split well. I recommend trying to find the original Mesh if possible (`Assets/Lethal Company/Game/Meshes` folder).**

**Sometimes if the object uses a `Mesh Collider`, the source mesh will be listed as mesh. If you are good in software like Blender, you can export the `Combined Mesh` into it and cut away what you don't want, then re-import it into `Unity`.**

**Credits to @sniper1.1 ([Sniper1-1](https://github.com/Sniper1-1) for this guide in [Lethal Company Modding](https://discord.gg/raXqCP6NZw) Discord)**
