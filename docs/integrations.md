# Client integrations

The public helpers are in `net.fabs.wanderersdiscovery.api` and must be used on
the client. For optional integration, check whether `wanderers_discovery` is
loaded before referencing its classes; isolate direct references in a compatibility
class, or use reflection. If required, declare WD as a Fabric dependency.

## Map markers

`DiscoveryClientApi.mapMarkers()` returns an immutable list of
`DiscoveryMapMarker` records. Fields are stable identity string, discovery type
ID, dimension ID, X/Y/Z, localized `Component` display name and item icon
`Identifier`. `horizontalDistanceSquared(x,z)` supports cheap map sorting.

```java
List<DiscoveryMapMarker> markers = DiscoveryClientApi.mapMarkers();
```

Register `DiscoveryMapEvents.MARKERS_CHANGED` to refresh your map after history
synchronization, new discoveries or connection reset. The callback receives the
current marker list. Treat `Component` values as read-only; collection immutability
does not grant deep mutation safety. Filter by dimension before drawing.

WD does not supply a map UI. Built-in types expose their intended item icons;
custom definitions use `map_icon`, defaulting to `minecraft:filled_map`.
Persisted built-in marker type IDs use short names while custom IDs are namespaced;
`currentDiscoveryId()` is namespaced. Do not compare these forms blindly.

## Current location and ambience

`DiscoveryClientApi.currentDiscoveryId()` returns the active type ID or `null`.
`DiscoveryClientApi.suppressesCaveAmbience()` exposes the active definition's
suppression flag. WD publishes the signal; a compatible ambience mod chooses
whether to stop its own cave loops/events. WD does not itself rewrite Minecraft
cave sounds or require Natural Ambience.

Client data clears on disconnect. Server observation, structure recognition and
generic discovered-location services are documented by [WildTrack API](wildtrack-api.md).
WD's map-history cache is not a full server world index and is not the same store
as WildTrack's player-visible discovery projection.
