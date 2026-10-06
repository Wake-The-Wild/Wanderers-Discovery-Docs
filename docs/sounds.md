# Installed sound events and timing

All event IDs below use namespace `wanderers_discovery`. Paths refer to installed
resources; reuse an event ID without copying the OGG. Timing is in ticks.

| Event path | OGG resource | Duration | Peak parameter |
| --- | --- | --- | --- |
| `discovery.poi.abandoned_camp` | `wanderers_discovery:discovery/abandoned_camp` | 140 | 41 |
| `discovery.poi.ancient_city` | `wanderers_discovery:discovery/ancient_city` | 140 | 55 |
| `discovery.poi.ancient_ruins` | `wanderers_discovery:discovery/ancient_ruins` | 140 | 47 |
| `discovery.poi.bastion_remnant` | `wanderers_discovery:discovery/bastion_remnant` | 100 | 13 |
| `discovery.poi.buried_treasure` | `wanderers_discovery:discovery/buried_treasure` | 140 | 39 |
| `discovery.poi.desert_pyramid` | `wanderers_discovery:discovery/desert_pyramid` | 140 | 33 |
| `discovery.poi.desert_well` | `wanderers_discovery:discovery/desert_well` | 100 | 13 |
| `discovery.poi.end_city` | `wanderers_discovery:discovery/end_city` | 140 | 59 |
| `discovery.poi.generic` | `wanderers_discovery:discovery/generic` | 140 | 47 |
| `discovery.poi.igloo` | `wanderers_discovery:discovery/igloo` | 140 | 59 |
| `discovery.poi.illager` | `wanderers_discovery:discovery/illager` | 140 | 48 |
| `discovery.poi.mineshaft` | `wanderers_discovery:discovery/mineshaft` | 140 | 28 |
| `discovery.poi.nautical_ruins` | `wanderers_discovery:discovery/nautical_ruins` | 140 | 64 |
| `discovery.poi.nether_fossil` | `wanderers_discovery:discovery/nether_fossil` | 100 | 11 |
| `discovery.poi.nether_ruins` | `wanderers_discovery:discovery/nether_ruins` | 140 | 25 |
| `discovery.poi.ocean_monument` | `wanderers_discovery:discovery/ocean_monument` | 140 | 45 |
| `discovery.poi.ocean_ruins` | `wanderers_discovery:discovery/ocean_ruins` | 100 | 25 |
| `discovery.poi.ruined_portal` | `wanderers_discovery:discovery/ruined_portal` | 140 | 40 |
| `discovery.poi.stronghold` | `wanderers_discovery:discovery/stronghold` | 140 | 29 |
| `discovery.poi.swamp_hut` | `wanderers_discovery:discovery/swamp_hut` | 140 | 34 |
| `discovery.poi.trail_ruins` | `wanderers_discovery:discovery/trail_ruins` | 100 | 5 |
| `discovery.poi.trial_chambers` | `wanderers_discovery:discovery/trial_chambers` | 140 | 41 |
| `discovery.poi.village_day_1` | `wanderers_discovery:discovery/village_day_1` | 140 | 32 |
| `discovery.poi.village_day_2` | `wanderers_discovery:discovery/village_day_2` | 140 | 14 |
| `discovery.poi.village_desert_day` | `wanderers_discovery:discovery/village_desert_day` | 100 | 42 |
| `discovery.poi.village_desert_night` | `wanderers_discovery:discovery/village_desert_night` | 100 | 26 |
| `discovery.poi.village_night_1` | `wanderers_discovery:discovery/village_night_1` | 140 | 18 |
| `discovery.poi.village_night_2` | `wanderers_discovery:discovery/village_night_2` | 140 | 57 |
| `discovery.poi.village_savanna_day` | `wanderers_discovery:discovery/village_savanna_day` | 100 | 49 |
| `discovery.poi.village_savanna_night` | `wanderers_discovery:discovery/village_savanna_night` | 100 | 21 |
| `discovery.poi.village_snowy_day` | `wanderers_discovery:discovery/village_snowy_day` | 100 | 7 |
| `discovery.poi.village_snowy_night` | `wanderers_discovery:discovery/village_snowy_night` | 100 | 20 |
| `discovery.poi.village_taiga_day` | `wanderers_discovery:discovery/village_taiga_day` | 100 | 52 |
| `discovery.poi.village_taiga_night` | `wanderers_discovery:discovery/village_taiga_night` | 100 | 46 |
| `discovery.poi.woodland_mansion` | `wanderers_discovery:discovery/woodland_mansion` | 100 | 24 |

Builtin preset volume is 0.24 and pitch is 1.0, multiplied by the player's
volume setting (default 50%) and Minecraft sound controls. Peak timing drives
the camp hit only; ordinary glow peaks at half the banner lifetime.
The runtime performs no automatic audio analysis, fade processing or loudness
normalization for replacement files.

Village day/night selection uses the recognized village style. Ancient Grove
compatibility chooses the day branch even during the night. Other custom
discovery sound variants are selected deterministically by location identity.

See [sound schema](discovery-schema.md) and [asset licensing](licensing.md).
