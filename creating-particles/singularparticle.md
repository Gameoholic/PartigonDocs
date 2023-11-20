# SingularParticle

The `SingularParticle` class is used to represent and control single particle animations.\
While you can instantiate it with the primary constructor, Partigon offers a DSL Builder Pattern, which you can use more conveniently.

The builder accepts the following parameters, all of which have a default value:

* `originLocation`: The[ location](partigonlocation.md) of the particle.
* `particleType`: The Minecraft Particle to spawn.
* property types (positionX, positionY, count, etc.)
* And more.

It also offers the following extension functions:

* `Envelope#add` - Adds this Envelope to the particle
* `EnvelopeGroup#add` - Adds this Envelope Group to the particle
* `RotationOptions#add` - Applies this Rotation Options on top of everything else before spawning the particle
* `RotationOptions#addToGroups` - Applies this Rotation Options to every Envelope Group

PartigonParticle has an integer value `frameIndex`, indicating the index of the current frame of the animation. It's set to -1 when the animation hasn't started, and to 0 on the first frame of the animation.

To start the particle animation, invoke `SingularParticle#start`. This will reset the animation, if it was playing before.

To stop it, invoke `SingularParticle#stop`.

To resume the particle animation from the same frame, invoke `SingularParticle#resume`.

Note that classes in this library are **mutable**, meaning you cannot pass an Envelope to one particle, then modify it and apply it to another envelope, without affecting both. There are, however, ways to reuse envelopes & particles to avoid boilerplate.



An example of a SingularParticle:

{% code overflow="wrap" %}
```kotlin
singularParticle {
    particleType = Particle.FLAME

    // Location of particle can be ConstantLocation, EntityLocation, or your own implementation!
    originLocation = ConstantLocation(Location(Bukkit.getWorld("world"), 0.0, 170.0, 0.0))
}
```
{% endcode %}

