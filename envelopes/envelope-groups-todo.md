# Envelope Groups

Envelope groups are groups of 3 envelopes that affect either POSITION or OFFSET property types (aka, only properties that have an X, Y and Z value).

Each envelope can only be assigned one envelope group.

An example of an Envelope Group:

```kotlin
EnvelopeGroup(
    LinearEnvelope( // Envelope used for X component
        Envelope.PropertyType.POS_X,
        (-4.0).envelope,
        2.0.envelope,
        RepeatLoop(100)
    ),
    LinearEnvelope( // Envelope used for Y component
        Envelope.PropertyType.POS_Y,
        (-4.0).envelope,
        2.0.envelope,
        RepeatLoop(100)
    ),
    LinearEnvelope( // Envelope used for Z component
        Envelope.PropertyType.POS_Z,
        (-4.0).envelope,
        2.0.envelope,
        RepeatLoop(100)
    )
)
```

_This will create a line from (-4, -4, -4) to (2, 2, 2)_

Upon initialization of the envelope group, the `envelopeGroup` property of each envelope will be set to it. It cannot be changed.

Envelope groups are useful because you can apply a rotation to it (more on that later):

```kotlin
EnvelopeGroup(
    LinearEnvelope(
        Envelope.PropertyType.POS_X,
        (-4.0).envelope,
        2.0.envelope,
        RepeatLoop(100)
    ),
    LinearEnvelope(
        Envelope.PropertyType.POS_Y,
        (-4.0).envelope,
        2.0.envelope,
        RepeatLoop(100)
    ),
    LinearEnvelope(
        Envelope.PropertyType.POS_Z,
        (-4.0).envelope,
        2.0.envelope,
        RepeatLoop(100)
    ),
    rotationOptions = listOf(
        RotationOptions(
        EnvelopeTriple(0.0.envelope, 0.0.envelope, 0.0.envelope), // Point of reference for the rotation - center of circle
        90.0.envelope, // Will rotate 90 degrees
        RotationType.Z_AXIS // Will rotate around Z Axis
        )
    )
)
```

And because you can use envelope wrappers with them, which makes it much easier to animate lines, circles and other shapes. Envelope group wrappers are super handy, because there's a lot of boilerplate in the examples provided above.

To add an envelope group to the particle, you must call the `.add()` extension method on it.
