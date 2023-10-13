# Examples

```kotlin
val framesPerTick = 5
val circlePoint1 = TrigonometricEnvelope(
    Envelope.PropertyType.NONE,
    1.5.envelope,
    0.0.envelope,
    TrigonometricEnvelope.TrigFunc.COS,
    RepeatLoop(50 * framesPerTick)
)
val circlePoint2 = TrigonometricEnvelope(
    Envelope.PropertyType.NONE,
    (-1.5).envelope,
    0.0.envelope,
    TrigonometricEnvelope.TrigFunc.COS,
    RepeatLoop(50 * framesPerTick)
)
val particle = partigonParticle(Location(Bukkit.getWorld("world"), 0.0, 100.0, 0.0), Particle.END_ROD) {
    envelopes = listOf(
        *circleEnvelopeGroup(
            EnvelopeGroup.EnvelopeGroupType.POSITION,
            EnvelopePair(circlePoint2, 0.0.envelope),
            EnvelopePair(0.0.envelope, circlePoint1),
            CircleEnvelopeWrapper.CircleDirection.RIGHT,
            RepeatLoop(framesPerTick),
        ).getEnvelopes().toTypedArray(),

        *circleEnvelopeGroup(
            EnvelopeGroup.EnvelopeGroupType.OFFSET,
            EnvelopePair(circlePoint2, 0.0.envelope),
            EnvelopePair(0.0.envelope, circlePoint1),
            CircleEnvelopeWrapper.CircleDirection.RIGHT,
            RepeatLoop(10 * framesPerTick),
        ).getEnvelopes().toTypedArray(),
    )
    animationFrameAmount = framesPerTick
    animationInterval = 1
    count = 0.envelope
    extra = 0.1.envelope
}
particle.start()

object: BukkitRunnable() {
    override fun run() {
        particle.stop()
        this.cancel()
    }
}.runTaskTimer(Partigon.plugin, 50L, 1L)
```
