# Project and build

The project contains common discovery/content code, client HUD/settings code,
network payloads and server/client resources. `api` contains the supported client
helpers and datapack entry points; internal implementation classes are not a
promise of compatibility.

| Area | Purpose |
| --- | --- |
| `discovery` | Server discovery matching, records, names and presentation specifications |
| `client` | Shared banner renderer, effects, glow and wooden settings controls |
| `client/config` | Client-local options and file persistence |
| `api` | Custom definitions, category tags, marker and ambience integration |
| `network/payload` | WD history and active-state synchronization |
| `sound` | Discovery sound registration |
| `assets/wanderers_discovery` | English text, textures and audio |
| `data/wanderers_discovery` | Built-in tags and advancements |

Build with the included Gradle wrapper and the Java version required by the
project’s target Minecraft version:

```text
gradlew.bat clean build
```

The default sibling API dependency path is configured in `build.gradle`.
Override it with `-PwildtrackJar=<path>` when using another API build or checkout
layout. Use a JAR compatible with the project’s Minecraft target. Fabric/Loom dependencies
must already be cached for `--offline` builds.

The runtime JAR belongs in `mods`; sources and the clean project archive are
development artifacts. WildTrack remains a separate required mod, not embedded
WD code. 

Documentation changes do not require modifying discovery logic. Keep the banner
format and persisted definition IDs stable, document new schema fields explicitly,
and update sound/advancement inventories when content changes.
