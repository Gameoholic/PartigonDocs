# Envelope Wrappers

Envelope wrappers are utility methods that make it easier to create shapes and animations.

The 3 current Envelope wrapper classes are: `CircleEnvelopeWrapper`, `CurveEnvelopeWrapper` and `LinearEnvelopeWrapper`.

Only the most commonly used ones will be explained here, but it's recommended to take a look at the classes, there's Javadoc for all of them.

### LinearEnvelopeWrapper#linearEnvelopeGroup

Envelope wrapper that creates a straight line between 2 points/offsets in 3D space.

<pre class="language-kotlin" data-overflow="wrap"><code class="lang-kotlin"><strong>linearEnvelopeGroup(
</strong>    EnvelopeGroup.EnvelopeGroupType.POSITION, // Can be either POSITION or OFFSET
    EnvelopeTriple((-4.0).envelope, (-4.0).envelope, (-4.0).envelope), // First position: (-4, -4, -4)
    EnvelopeTriple(2.0.envelope, 2.0.envelope, 2.0.envelope), // Second position (2, 2, 2)
    RepeatLoop(100)
).add()
</code></pre>

_Will create a line from (-4, -4, -4) to (4, 4, 4)_

### CurveEnvelopeWrapper#curveEnvelopeGroup

Envelope wrapper that creates a curve between 2 points/offsets in 3D space.

{% code overflow="wrap" %}
```kotlin
curveEnvelopeGroup(
    EnvelopeGroup.EnvelopeGroupType.POSITION,
    EnvelopeTriple(0.0.envelope, 0.0.envelope, 0.0.envelope),
    EnvelopeTriple(4.0.envelope, 4.0.envelope, 4.0.envelope),
    CurveEnvelopeWrapper.CurveOrientation.RIGHT_BELOW, // Tons of different ways to create curves, see Javadoc
    BounceLoop(200)
).add()
```
{% endcode %}

### CircleEnvelopeWrapper#circleEnvelopeGroup

Envelope wrapper that creates a circle around a point in the XZ plane.

{% code overflow="wrap" %}
```kotlin
circleEnvelopeGroup(
    EnvelopeGroup.EnvelopeGroupType.POSITION,
    EnvelopePair(0.0.envelope, 0.0.envelope), // Center of circle: (0, 0) in the XZ plane
    3.0.envelope, // Radius of circle: 3.0
    RepeatLoop(100)
).add()
```
{% endcode %}

There are individual method wrappers in those classes, as well as other envelope group wrappers. I recommend to take a look at the classes to find what you need.
