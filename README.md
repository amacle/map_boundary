# map_boundary
A HTML application that keeps a known "player" shape completely inside of any arbitrarily-shaped "map" using SVG.

Here, the "player" shape is a circle that follows the mouse cursor, and the "map" is a closed SVG path. When the cursor moves outside of where the player can completely fit inside of the map, we want the player shape to follow the cursor by moving along the inner edge of the map in such a way that it's still completely contained within the map boundary.

An effective way to achieve this is to generate an inset [parallel curve](https://en.wikipedia.org/wiki/Parallel_curve) one player-radius away from the original map path. If the mouse cursor is inside of the offset shape, the player shape can follow the cursor normally. If the mouse cursor is outside of the offset shape, we instead have the player shape snap to the nearest point on the offset map's edge relative to the mouse cursor.

[Interactive demo](https://jsfiddle.net/Tropicarnage/og90s6Le/)

(Note that the demo presently doesn't work in Firefox, as the needed SVGGeometryElement hit-testing functions have yet to be implemented into the browser.)
