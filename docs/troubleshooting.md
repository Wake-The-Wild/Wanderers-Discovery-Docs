# Troubleshooting

| Symptom | Check |
| --- | --- |
| Startup reports missing dependency | Install compatible WildTrack API and Fabric API releases for your Minecraft version on the required sides |
| No banner for a location | Banners setting, first-type-only setting, previously recorded instance and available structure coverage |
| Hotbar label appears but no banner | Separate label/banner settings, known instance or first-type filtering |
| Banner appears but no sound | WD volume, Minecraft sound settings, available event and valid OGG |
| Custom definition is ignored | Correct directory, at least one target, valid JSON, enabled pack and `/reload` warnings |
| Structure ID is never matched | Real registered structure ID/tag and normal start/piece system; a placed feature is different |
| Custom assets are missing | Resource pack enabled on that client; namespaces and texture/event paths match |
| Text or glow looks wrong | Exact 256Ă—44 canvas, centered 160Ă—16 panel, equal rails and binary alpha |
| Custom advancement is not granted | Advancement JSON exists, all criteria can be manually awarded, presentation delay and `uses_vanilla_advancement` |
| Expected repeat does not occur | Same-instance discovery is persistent and intentionally not replayed |
| Cave ambience does not change | The suppression flag requires a compatible ambience consumer |

Do not delete player files or world history as an initial fix. Back up the world
and report exact mod versions, structure/definition ID, resource-pack state and
the relevant log exception. A disconnect message such as â€śInvalid player dataâ€ť
needs the server exception; the message alone does not identify its cause.

`/wdconfig` opens settings. Preview sound uses the selected discovery volume.
