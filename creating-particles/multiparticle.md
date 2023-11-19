# MultiParticle

MultiParticle represents a particle animation with multiple instances of `SingularParticle`.

Starting, stopping or resuming it will do it for all the Singular Particles it contains.

While you can instantiate it with the primary constructor, Partigon offers a DLS Builder Pattern, which you can use more conveniently.

To add particles to it, you can either pass a list containing `SingularParticle`'s or use the `SingularParticle#add` extension function.



An example of a MultiParticle:

