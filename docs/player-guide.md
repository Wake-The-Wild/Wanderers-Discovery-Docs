# Discovery behavior

Entering a supported, newly discovered location queues its banner and contextual
sound. The server records the instance so returning to the same location does
not replay its discovery presentation. Different structures of the same type
remain separate discoveries unless the player enables first-type-only presentation.

Village names are generated deterministically from location identity and remain
stable after reconnecting. Village and abandoned-camp styles vary with their
registered structure variant. Discovering an overlapping location does not erase
another one: presentations are queued in stable priority order.

The text above the hotbar identifies the active location. It has a separate
setting from discovery banners. Turning banners off does not disable discovery
history, advancement awards or sounds; use sound volume to silence audio.

Advancements are awarded by the server. Manually integrated custom advancements
are granted after the presentation lifetime plus a short delay, with queue offsets
for overlapping discoveries. Client presentation settings do not change this.

## Visual effects

Ordinary location banners reveal from the center and have a themed glow that
fades in toward the middle of the presentation and out toward disappearance.
Abandoned camps use one drifting HUD firefly, a timed hit, glow and a brief scale
pulse. These are HUD effects, not Minecraft world particles.

All discovery textures use one fixed canvas/panel format and one shared rendering
layout. WD does not apply per-banner text-position or geometry exceptions.
The [asset contract](discovery-banner-layout.md) also applies to custom banners.

## History scope

Dedicated servers store discoveries per player UUID in that world. Integrated
singleplayer uses a shared owner for that world's discovery history. First-type
filtering reads the synchronized history for the current world/server; it is not
a global account achievement across all worlds.

Changing client settings does not reset or manufacture records. A location
discovered while its banner is hidden remains discovered. WD and WildTrack have
separate discovery stores; clearing one is not a supported way to reset the other.
