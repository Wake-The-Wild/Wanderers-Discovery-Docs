# Release compatibility

The installation and integration guides are maintained in one documentation tree.
Choose downloads for your Minecraft version and check the selected release’s
dependency declarations. This page records the concrete build used to verify the
included examples; it does not claim compatibility with other Minecraft versions.

| Requirement | Reference build |
| --- | --- |
| Minecraft | 26.3 |
| Mod loader | Fabric |
| Fabric Loader | 0.19.5 or newer |
| Java | 25 or newer |
| Fabric API used for development | 0.160.6+26.3 |
| WildTrack API | 0.1.0 |
| WD minimum WildTrack API dependency | 0.1.0 |

Fabric API and both mod downloads must match the target Minecraft version.
Newer version numbers alone do not establish compatibility. Consult the selected
release’s requirements when they differ from this reference.

## Example pack formats

The supplied WD datapack uses **121.0** and its resource pack uses **97.1**.
These are Minecraft-specific values, not WD schema versions. Adapt `pack.mcmeta`
to the supported formats of your target Minecraft version. The fixed **256 × 44 px**
banner layout is a WD asset contract and is separate from Minecraft pack formats.


When requirements or content formats change, update this page and the affected
examples together. Git preserves the documentation for previous releases.
