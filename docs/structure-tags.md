# Built-in category tags

Add a registered modded structure to a category to reuse that built-in type's
name/behavior, advancement, sounds and presentation rather than create a separate
custom discovery ID.

Path example: `data/wanderers_discovery/tags/worldgen/structure/discovery/village.json`.

```json
{
  "replace": false,
  "values": ["examplemod:moon_village"]
}
```

WD provides these 21 paths under `discovery/`:

`village`, `pillager_outpost`, `mineshaft`, `woodland_mansion`, `jungle_temple`,
`desert_pyramid`, `igloo`, `shipwreck`, `swamp_hut`, `stronghold`, `ocean_monument`,
`ocean_ruins`, `nether_fortress`, `nether_fossil`, `end_city`, `buried_treasure`,
`bastion_remnant`, `ruined_portal`, `ancient_city`, `trail_ruins`, `trial_chambers`.

Abandoned camps instead use **`minecraft:abandoned_camp`**, at
`data/minecraft/tags/worldgen/structure/abandoned_camp.json`. There is no WD
`discovery/abandoned_camp` tag. Desert wells are placed features matched with a
WD block pattern through WildTrack; there is no structure category tag for them.

Use `replace: false` to extend an installed tag. A full custom discovery definition
takes precedence over a built-in category match. Category membership does not
register or generate the structure, and a custom village ID does not automatically
define a new village-specific art/sound style beyond WD's recognized variants.
