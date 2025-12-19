# HarmonyXPack

![Build](https://github.com/ModioMori/HarmonyXPack/actions/workflows/build.yml/badge.svg)

A ready-to-use dependency, packing in the latest HarmonyX (and consequently MonoMod/Cecil) for other Gladio Mori mods to rely upon.
[Find it on mod.io here.](https://mod.io/g/gladio-mori/m/harmonyxpack)

## Usage

To use this pack, you'll need to add a reference to the nuget.org package `ModioMori.HarmonyXPack`. This package is solely a metapackage that keeps its runtime private, so HarmonyX will not be emitted when you build your mod. The runtime will be shipped by the HarmonyXPack game mod on mod.io, which requires a dependency added on mod.io.

Importantly, **you must** add this mod as a dependency to your `gm.modcfg` file and as a dependency on mod.io. If you are trying to use HarmonyX with a local (not published to mod.io) mod, you must build and package this yourself. This is because the game loads local mods before mod.io mods, so your load order will be wrong if you don't do this.

For an example group of package references in your `.csproj`:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NETFramework.ReferenceAssemblies" Version="1.0.3" PrivateAssets="all" />
  <PackageReference Include="ModioMori.HarmonyXPack" Version="2.16.0-p1" />
  <PackageReference Include="UnityEngine.Modules" Version="6000.0.59" IncludeAssets="compile" />
</ItemGroup>
```

For an example `gm.modcfg`:

```json
{
  "modioDependencies": [5585734]
}
```
