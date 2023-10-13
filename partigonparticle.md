# PartigonParticle

The PartigonParticle class is used to represent and control particle animations.\
While you can instantiate an instance of it with the primary constructor, Partigon offers a DLS Builder Pattern, which you can use more conveniently.

PartigonParticle requires the following arguments for instantiation: `location`, and `particleType`.\
location is the location at which the particle animation will be centered around, and particleType is the Minecraft Particle to be used for it.

You may also pass the following optional parameters to it:

* envelopes: The Envelopes to be used on the particle animation
* count: The amount of particles that will be spawned each frame
* offset: The Minecraft offset of the particle (a Vector)

PartigonParticle has an integer value `frameIndex`, indicating the index of the current frame of the animation. It's set to -1 when the animation hasn't started, and to 0 on the first frame of the animation.

To start the particle animation, invoke `PartigonParticle#start`. This will reset the animation, if it was playing before.

To stop it, invoke `PartigonParticle#stop`.

To pause the animation temporarily, invoke `PartigonParticle#pause`. This will stop the animation, but upon Invoking `PartigonParticle#resume` will resume from the same frame.

