# Supported locations and advancements

The base mod has 23 discovery types. Each uses one exploration advancement;
village/camp variants share their type and advancement.

| Type ID | Display name | Advancement title |
| --- | --- | --- |
| `village` | Village | Settled Paths |
| `pillager_outpost` | Pillager Outpost | Hostile Horizon |
| `mineshaft` | Abandoned Mineshaft | Echoes Below |
| `woodland_mansion` | Woodland Mansion | House in the Dark |
| `jungle_temple` | Jungle Temple | Vines over Stone |
| `desert_pyramid` | Desert Pyramid | Buried Dynasty |
| `igloo` | Igloo | Warmth beneath Snow |
| `shipwreck` | Shipwreck | Claimed by the Tide |
| `swamp_hut` | Swamp Hut | A Crooked Hearth |
| `stronghold` | Stronghold | The Path Below |
| `ocean_monument` | Ocean Monument | Temple of the Deep |
| `ocean_ruins` | Ocean Ruins | Drowned Memory |
| `nether_fortress` | Nether Fortress | Citadel of Flame |
| `nether_fossil` | Nether Fossil | Bones in Fire |
| `end_city` | End City | Beyond the Void |
| `buried_treasure` | Buried Treasure | X Marks the Spot |
| `bastion_remnant` | Bastion Remnant | Gilded Ruin |
| `ruined_portal` | Ruined Portal | A Broken Crossing |
| `ancient_city` | Ancient City | Silence Has a Name |
| `trail_ruins` | Trail Ruins | Brush with History |
| `trial_chambers` | Trial Chambers | The Trial Awaits |
| `abandoned_camp` | Abandoned Camp | Embers Gone Cold |
| `desert_well` | Desert Well | A Drink in the Dust |

Advancement IDs are `wanderers_discovery:exploration/<type>` and use the
`wanderers_discovery:exploration/root` parent. They are one base exploration
tree, not separate Overworld/Nether/End tabs or a variant completion set.

Village art has Plains, Desert, Savanna, Taiga and Snowy variants. Plains has
two day and two night sound variants; each other style has one for each period.
Abandoned camp artwork has the following 18 variant names:

- `abandoned_camp_bamboo_jungle`
- `abandoned_camp`
- `abandoned_camp_birch_forest`
- `abandoned_camp_cherry_grove`
- `abandoned_camp_dappled_forest`
- `abandoned_camp_flower_forest`
- `abandoned_camp_forest`
- `abandoned_camp_meadow`
- `abandoned_camp_old_growth_birch_forest`
- `abandoned_camp_old_growth_pine_taiga`
- `abandoned_camp_old_growth_spruce_taiga`
- `abandoned_camp_pale_garden`
- `abandoned_camp_savanna`
- `abandoned_camp_snowy_taiga`
- `abandoned_camp_sparse_jungle`
- `abandoned_camp_swamp`
- `abandoned_camp_taiga`
- `abandoned_camp_windswept_forest`
- `abandoned_camp_wooded_badlands`

The resource set contains 47 discovery PNGs, including default/shared textures.
Every one uses the fixed 256×44 layout. Texture/style variants do not create
separate first-type-only discovery categories. Custom resource packs must follow
the same [layout](discovery-banner-layout.md).
