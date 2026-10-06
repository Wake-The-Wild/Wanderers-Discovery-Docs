# Installation

Choose WD and WildTrack API releases for the same Minecraft version and Fabric
environment. Install the Fabric Loader, Fabric API and Java versions required by
those releases. Put the downloaded WD, WildTrack API and Fabric API JARs in
`mods/` on the client and dedicated server. Check each release’s dependency
requirements; the [compatibility reference](compatibility.md) records the build
used for the examples in these guides.

WD's mod ID is `wanderers_discovery`; WildTrack API's mod ID is `wildtrack`.
WildTrack is a required dependency, not an optional integration or nested copy.
Fabric rejects startup when the dependency is absent or incompatible.

Mod Menu is optional; its Configure action opens WD's wooden settings screen.
Without it, use the client command `/wdconfig` in-game. Natural Ambience and map
mods are optional compatibility consumers; WD works without them.

Place server datapacks in `<world>/datapacks` and enable them normally. Client
resource packs belong in `resourcepacks/` and must be enabled on every client
that needs custom assets. A datapack alone cannot supply HUD textures or audio.

Back up worlds before replacing mod versions. WD remembers discoveries in server
world data. Removing a client configuration file does not reset discovery history.
