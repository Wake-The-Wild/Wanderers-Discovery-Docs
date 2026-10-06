# Discovery definition schema

Path: `data/<namespace>/wanderers_discovery/poi_types/<path>.json`.
Persistent type ID: `<namespace>:<path>`. Definitions reload with `/reload`.

| Field | Type | Default / meaning |
| --- | --- | --- |
| `structures` | Array of strings | Structure IDs or `#structure_tag`; empty when omitted |
| `structure_tags` | Array of strings | Additional structure tag IDs, without `#` |
| `priority` | Integer | `2`; lower has higher selection priority |
| `detection` | String | `piece`; supported alternative `bounding_box` |
| `suppress_cave_ambience` | Boolean | `false`; publishes a compatibility signal |
| `name` | Object | Generated translation key and title-cased final path fallback |
| `heading` | Object | `hud.wanderers_discovery.location_discovered`, fallback `Location discovered` |
| `name_generator` | Identifier string | None; supported public generator `wanderers_discovery:village` |
| `map_icon` | Identifier string | `minecraft:filled_map` |
| `banner_texture` | Identifier string | `wanderers_discovery:textures/gui/discovery/default_banner.png` |
| `sound` | String or object | Generic preset when no usable sound is provided |
| `sounds` | Array of strings/objects | Variants; takes precedence over singular `sound` |
| `advancement` | Identifier string | None |
| `uses_vanilla_advancement` | Boolean | `false`; true leaves awarding to another system |

At least one structure or tag target is required. Use exactly the documented
spellings; unrecognized detection strings currently fall back to piece detection
rather than forming a new mode. Malformed definitions are warned and skipped.

## Text objects

`name` and `heading` accept `translate` and `fallback` strings. A present language
key is translated; otherwise fallback text is used. The generated default name
key is `poi.<namespace>.<path>` with path slashes replaced by dots. An explicit
name object can use just `fallback` to avoid requiring a translation.

## Sound objects

An object requires `event`, a sound-event identifier available to the client:

```json
{
  "event": "wanderers_discovery:discovery.poi.generic",
  "duration_ticks": 140,
  "glow_peak_tick": 47,
  "volume": 0.24,
  "pitch": 1.0
}
```

String shorthand and omitted object timing use `duration_ticks: 200`,
`glow_peak_tick: 70`, `volume: 0.24`, `pitch: 1.0`. If the sound field/variant list
does not produce a sound spec, the generic fallback instead uses **140/47** ticks.
Variant selection is deterministic from location identity.

Duration is clamped to at least 60 ticks; peak to `[0,duration]`; volume to `[0,4]`;
pitch to `[0.01,4]`. Supply finite values in those ranges. At normal server/client
tick rate, 20 ticks are approximately one second. Pitch changes audible duration
but WD does not analyze the file or recalculate timing automatically.

`duration_ticks` controls presentation lifetime and server award scheduling.
`glow_peak_tick` controls the hit moment for **camp presentations**; ordinary
presentations use continuous glow peaking halfway through their lifetime.
A custom definition has no public `camp_effect`, `impactTime`, glow color or
particle-style field. Do not invent those keys to enable camp effects.

## Complete example

```json
{
  "structures": ["examplemod:moon_temple", "#examplemod:moon_temples"],
  "priority": 1,
  "detection": "piece",
  "suppress_cave_ambience": true,
  "name": {"translate": "poi.examplemod.moon_temple", "fallback": "Moon Temple"},
  "heading": {"fallback": "Ancient shrine discovered"},
  "map_icon": "minecraft:amethyst_shard",
  "banner_texture": "wanderers_discovery:textures/gui/discovery/default_banner.png",
  "sound": {"event": "wanderers_discovery:discovery.poi.generic", "duration_ticks": 140, "glow_peak_tick": 47, "volume": 0.24, "pitch": 1.0},
  "advancement": "examplemod:exploration/moon_temple",
  "uses_vanilla_advancement": false
}
```

`name_generator: "wanderers_discovery:village"` chooses a stable generated village
name instead of the ordinary name. `map_icon` is consumed by compatible map mods;
WD does not add its own map screen. Ambience suppression is a signal only and
requires a compatible ambience consumer to have an audible effect.
