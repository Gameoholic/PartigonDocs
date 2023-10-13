# PartigonParticle

The PartigonParticle class is used to represent and control particle animations.\
While you can instantiate an instance of it with the primary constructor, Partigon offers a DLS Builder Pattern, which you can use more conveniently.

PartigonParticle requires the following arguments for instantiation: `originLocation`, and `particleType`.\
`originLocation` is the location at which the particle animation will be centered around, and `particleType` is the Minecraft Particle to be used for it.

You may also pass the following optional parameters to it:

* `envelopes`: The Envelopes to be used on the particle animation to control its properties
* Envelope properties (position, offset, count, extra, etc.): Properties controlled by envelopes
* `rotationOptions`: Rotations to be applied on the entire particle, affects position and offset.
* `animationFrameAmount`: How many frames to animate on every particle update (usually every tick), can be used to animate entire shapes at once. Default is 1.
* `animationInterval`: How often to update & spawn the particle, can be used for pulsing animations. Default is 1.

PartigonParticle has an integer value `frameIndex`, indicating the index of the current frame of the animation. It's set to -1 when the animation hasn't started, and to 0 on the first frame of the animation.

To start the particle animation, invoke `PartigonParticle#start`. This will reset the animation, if it was playing before.

To stop it, invoke `PartigonParticle#stop`.

To pause the animation temporarily, invoke `PartigonParticle#pause`. This will stop the animation, but upon Invoking `PartigonParticle#resume` will resume from the same frame.

Note that classes in this library are **mutable**, meaning you cannot pass an Envelope to one particle, then modify it and apply it to another envelope, without affecting both. There are, however, ways to reuse envelopes & particles to avoid boilerplate.

