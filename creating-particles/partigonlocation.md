# PartigonLocation

`PartigonLocation` is an interface used for providing the location for particles to spawn at.

The 2 implementations currently included within Partigon are `ConstantLocation`, and `EntityLocation`.

## ConstantLocation

A static location that does not change.

## EntityLocation

Follows the provided entity, with an optional offset.

## Custom PartigonLocation

To make your own implementation, simply extend the interface and override the `getLocation()` method.

Implementations such as locations relative to an entity (for cloak animations, for example) are planned.
