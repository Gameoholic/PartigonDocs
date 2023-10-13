# Examples

The following creates a simple flame particle at the player's location, that doesn't move or change anything.

```
        partigonParticle(player.location, Particle.FLAME) {

        }
```

The following creates a flame particle animation, which goes up and down over 40 ticks, then repeats.

```
partigonParticle(player.location, Particle.FLAME) {
    envelopes = listOf(
        LineEnvelope(
            Envelope.PropertyType.POS_Y, 0, 2, BounceLoop(40)
        )
    )
}.start()
```

