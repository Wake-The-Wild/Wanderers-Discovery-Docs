# Settings

Open Mod Menu → Wanderer's Discovery → Configure, or use `/wdconfig`.
**Done** saves changes. **Cancel** or Escape discards pending changes.
**Reset to defaults** restores the pending defaults; press Done to save them.

| Setting | Default | Behavior |
| --- | --- | --- |
| Discovery banners | ON | Shows the banner and its visual effects |
| Text above hotbar | ON | Shows the active-location label |
| First discovery of each type only | OFF | Shows the banner and plays its presentation sound only for the first recorded location of a type |
| Discovery sound volume | 50% | Multiplies discovery playback volume; 0% silences it |
| Preview sound | Action | Plays a sample using the current pending volume |

First-type-only leaves the hotbar label, server history and advancements active.
All village variants share the village type; all camp variants share the camp
type. Custom discoveries are grouped by their namespaced definition ID.
The setting applies to history synchronized by the current world/server.

The local file is `config/wanderers_discovery.json`:

```json
{
  "banners": true,
  "locationLabel": true,
  "soundVolume": 0.5,
  "firstTypeOnly": false
}
```

Volume uses a fraction from 0 to 1. Missing fields fall back to defaults; malformed
settings fall back with a log warning. Saving uses a temporary file and replacement
to reduce partial-write risk. The file is client-local, not a server datapack or
a global cross-world discovery database.

Minecraft's normal sound settings also affect playback. WD's slider does not
normalize a custom sound file's loudness or change its pitch.
