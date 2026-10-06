# Custom discovery example

`custom-discovery-datapack` is a complete server datapack for the
[reference build](../docs/compatibility.md).
It gives a **vanilla jungle pyramid** the custom `examplemod:moon_temple`
discovery, so no imaginary structure mod is required. It reuses installed WD
banner/sound IDs and includes a manually granted advancement.

Copy that directory into `<world>/datapacks`, enable it and run `/reload`.
The definition takes precedence over the built-in jungle-temple match. Use an
instance not already recorded as this custom type when checking discovery.

`custom-discovery-resourcepack` is an optional client resource pack with the
example's English translation keys. Copy it into `resourcepacks/` and enable it.
The datapack has readable fallbacks, so it works without this companion pack.
Both packs include concrete format values for that reference build. When using
another Minecraft version, update both `pack.mcmeta` files to formats supported
by that version; do not assume datapack and resource-pack formats are identical.

To adapt it, replace `minecraft:jungle_pyramid` with your real registered structure
ID, choose your own namespace and keep it stable after release. Do not copy WD
PNG/OGG assets into your distributed pack. Referencing installed event/texture
IDs does not include those files or grant a license to redistribute them.

See the [full schema](../docs/discovery-schema.md),
[asset guide](../docs/resource-packs.md) and [MIT license](LICENSE).
