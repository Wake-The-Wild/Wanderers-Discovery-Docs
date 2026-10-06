# Resource packs

Server discovery JSON belongs in datapacks. Client assets belong in resource
packs or mod `assets/` resources. A matching resource pack is necessary only when
your discovery uses assets not already installed by a mod.

## Banner textures

Use the resource-pack format supported by your target Minecraft version; it
differs from the datapack format. The [companion example](../examples/README.md)
includes a concrete `pack.mcmeta`. Its format values are recorded in the
[compatibility reference](compatibility.md); update them for another target version.

Put an original texture at `assets/examplemod/textures/gui/moon_banner.png` and
reference `examplemod:textures/gui/moon_banner.png` from `banner_texture`.
Every discovery banner must be **256×44**, with the fixed centered panel and
frame geometry in the [layout contract](discovery-banner-layout.md). There are no
per-texture offsets or alternate render sizes.

Use nearest-neighbor editing and alpha values only **0 or 255** for the base PNG.
Soft glow is generated separately at runtime from frame/decorative colors; it
does not require a `banner_glow.png`. The dark text panel remains excluded from
the generated glow mask. Ordinary banners use continuous themed glow; camp
effects are selected by built-in discovery identity, not by a resource-pack field.

A wrong-size image logs a warning and disables its generated glow mask.
It does **not** guarantee a corrected-size replacement for the base texture.
Follow the fixed contract yourself; missing textures can show Minecraft's missing
asset behavior. Reload resource packs normally after replacing assets.

## Sounds

Define an event in `assets/examplemod/sounds.json`:

```json
{
  "discovery.moon_temple": {
    "sounds": ["examplemod:discovery/moon_temple"]
  }
}
```

Supply `assets/examplemod/sounds/discovery/moon_temple.ogg` as Ogg Vorbis, then
reference `examplemod:discovery.moon_temple` in WD's sound spec. Keep event/file
names consistent. Match `duration_ticks` to the intended presentation; WD performs
no automatic audio-peak analysis or loudness normalization for custom files.
Set volume/pitch explicitly and listen at WD's default 50% setting.

For a cohesive original pack, use short fades and comparable integrated loudness
across motifs. That preparation is an authoring step, not an extra runtime API.
Installed WD events can be referenced without copying their OGG files.

## Translations

Put translation keys in `assets/examplemod/lang/en_us.json` or another language
file and reference them through `name.translate`/`heading.translate`. Always
provide readable fallbacks for clients without the resource pack. WD ships only
English; there is no bundled Czech translation.

Use your own art/audio. WD documentation/examples are MIT, but WD texture and
audio files are not granted by that license. See [licensing](licensing.md).
