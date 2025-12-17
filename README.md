# HarmonyXPack

![Build](https://github.com/ModioMori/HarmonyXPack/actions/workflows/build.yml/badge.svg)

A ready-to-use dependency, packing in the latest HarmonyX (and consequently MonoMod/Cecil) for other Gladio Mori mods to rely upon.
[Find it on mod.io here.](https://mod.io/g/gladio-mori/m/harmonyxpack)

## Usage

To use this pack, you'll still need to include HarmonyX in your NuGet package references, but you can keep it at compile-time only. The game will load this mod and load the HarmonyX assembly for you.

Importantly, **you must** add this mod as a dependency to your `gm.modcfg` file and as a dependency on mod.io. If you are trying to use HarmonyX with a local (not published to mod.io) mod, you must build and package this yourself. This is because the game loads local mods before mod.io mods, so your load order will be wrong if you don't do this.

For an example group of package references in your `.csproj`:

```xml
<ItemGroup>
 <PackageReference Include="Microsoft.NETFramework.ReferenceAssemblies" Version="1.0.3" PrivateAssets="all" />
 <PackageReference Include="HarmonyX" Version="2.16.0" IncludeAssets="compile" />
 <PackageReference Include="UnityEngine.Modules" Version="6000.0.59" IncludeAssets="compile" />
</ItemGroup>
```

For an example `gm.modcfg`:

```json
{
  "modioDependencies": [5585734]
}
```
