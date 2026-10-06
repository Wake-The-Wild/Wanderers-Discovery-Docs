# WildTrack API and custom structures

WD depends on **WildTrack API** (`wildtrack`) for generic structure observation,
spatial query execution and bounded available-block searches. WD owns its
discovery definitions, presentation, names, advancement grants and saved history.
There is no separate WD structure-scanning engine to configure.

## Where custom content belongs

| Content | Owner |
| --- | --- |
| Register and generate a Minecraft structure | The supplying structure mod/datapack |
| Observe registered starts/pieces and query their geometry | WildTrack API |
| Choose a discovery name, category, banner, sound and advancement | WD datapack |
| Supply new client PNG/OGG/translation assets | Resource pack or supplying mod |
| Recognize an unrelated block feature or private location system | Deliberate consumer/API integration |

Registered modded Minecraft structures normally use WildTrack's existing structure
adapter; they do not need a new API provider merely because they are modded.
Add a [WD definition](datapacks.md) or [built-in category tag](structure-tags.md).

WD currently queries the built-in structure provider. Arbitrary locations published
through a private WildTrack provider do not automatically become WD discoveries.
Placed features are not structure starts. The desert-well recognition rule is WD's
consumer-owned block pattern, executed by WildTrack's generic bounded search.

## API reference

WildTrack's structure bridge guide describes available-source coverage, structure
metadata and geometry requirements. Its provider guide covers custom observations
and their integration limits.

The [WildTrack API documentation](https://github.com/Wake-The-Wild/WildTrack-API-Docs)
is maintained separately. The relevant pages are:

- `docs/integrations/wanderers-discovery.md` — WD structure bridge.
- `docs/api/locations.md` — source coverage, metadata and geometry.
- `docs/api/providers.md` — custom provider contracts.
- `docs/reference/README.md` — public Java type and member reference.
