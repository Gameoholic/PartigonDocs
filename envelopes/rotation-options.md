# Rotation Options

Envelope Groups allow rotations to be applied to them, individually.

Using the circle envelope wrappers, you can only create circles on the XZ plane. This is an example of a circle on the ZY plane:

```kotlin
circleEnvelopeGroup(
    EnvelopeGroup.EnvelopeGroupType.POSITION,
    EnvelopePair(0.0.envelope, 0.0.envelope),
    3.0.envelope,
    RepeatLoop(50),
    rotationOptions = listOf(
        RotationOptions(
            EnvelopeTriple(0.0.envelope, 0.0.envelope, 0.0.envelope), // Point of reference for the rotation - center of circle
            90.0.envelope, // Will rotate 90 degrees
            RotationType.Z_AXIS // Will rotate around Z Axis
        )
    )
).add()
```

As you can see, we just rotate it around (0, 0, 0) 90 degrees around the Z axis.

Rotations are the backbone to many cool animations. Try messing around with them.

If we don't need separate rotation options for different envelope groups, we can use the `addToGroups()` extension function to apply the rotation to all the groups. This method is nicer, so you should prefer it over adding them to each group separately.

{% code overflow="wrap" %}
```kotlin
circleEnvelopeGroup(
    EnvelopeGroup.EnvelopeGroupType.POSITION,
    EnvelopePair(0.0.envelope, 0.0.envelope),
    3.0.envelope,
    RepeatLoop(100)
).add()

circleEnvelopeGroup(
    EnvelopeGroup.EnvelopeGroupType.OFFSET,
    EnvelopePair(0.0.envelope, 0.0.envelope),
    3.0.envelope,
    RepeatLoop(100)
).add()

RotationOptions(
    EnvelopeTriple(0.0.envelope, 0.0.envelope, 0.0.envelope),
    LinearEnvelope(0.0.envelope, 360.0.envelope, RepeatLoop(100)),
    RotationType.Z_AXIS
).addToGroups()
```
{% endcode %}



Rotation Options can also be applied on top of all other envelopes, right before the particle spawns. \
To do it, use the `add()` extension function. This does not require any envelope group.
