# Content Container
A **ContentContainer** is a **ScriptableObject** (a **Unity**'s asset used to store data) that defines which **AssetBundles** your mod will register.

Your **ContentContainer** should list and organize your mod's content (any Items, Enemies, Moons, MapObjects etc.) across different **AssetBundles**.

This setup enables having **AssetBundles** that function as self-contained modules that don't depend on other **AssetBundles**, and allows them to be turned off individually.

# What This Means

This modular setup lets you divide your mod into parts without needing to upload multiple separate mods.

DawnLib automatically generates configuration files that allow players to **enable** or **disable** specific **AssetBundles**, letting them load only the content they want, similiar to selecting a collection of small mods to download.

You can inclide as much content as you like in a single **AssetBundle**.

<img width="555" height="304" alt="image" src="https://github.com/user-attachments/assets/d46a3496-c3bf-4a46-828e-2cb4ac427a0a" />

### In short:
A single **ContentContainer** doesn't need to represent only one thing.

It organizes your mod's content and lets you divide your mod into separate parts without needing to upload multiple mods.

It can hold a mix of Enemies, Items or anything else your mod adds.

## Options Explained.
| Option | Description |
| :----: | :---------- |
| **AssetBundleName** | Select one of your existing **`AssetBundles`**. This bundle contains your `ContentDefinition` objects, which define what gets registered. |
| **Config Name** | Sets the config category name for the bundle. Example: If named `AirControlUnit`, the configs appear under `ModName/AirControlUnit` Options. |
| **Genrate NamespacedKeys** | Useful if you’re using the **DawnLib SourceGenerator** for code-based mods. Not required, but it helps other developers write compatibility code. |
| **Debug Vanilla NamespacedKey** | Used internally by DawnLib developers to generate vanilla keys for debugging after updates. You can ignore this.

### You can learn more about:
- **`DawnLib ContentContainer`** in `B.2 Registering via Unity Editor` section under `DawnLib`'s Wiki: https://thunderstore.io/c/lethal-company/p/TeamXiaolan/DawnLib/wiki/4099-b2-registering-via-unity-editor/
- `Unity's AssetBundles`:
  - [Introducing to AssetBundles](https://docs.unity3d.com/6000.3/Documentation/Manual/AssetBundlesIntro.html)
  - [Preparing AssetBundles](https://docs.unity3d.com/6000.3/Documentation/Manual/AssetBundles-Preparing.html)
  - [Assigning specific items to AssetBundles](https://docs.unity3d.com/6000.3/Documentation/Manual/assetbundles-assign-assets.html)
  - [AssetBundles dependencies handling](https://docs.unity3d.com/6000.3/Documentation/Manual/AssetBundles-Dependencies.html)
