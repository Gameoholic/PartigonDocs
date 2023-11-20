# Envelopes

Envelopes are how you customize particle animations and animate properties.\
An Envelope is essentially an interpolation of a value over time.\
An Envelope can control one property of the particle at a time. Some examples are: `POS_X`, `POS_Y`, `POS_Z`, `COUNT`. _(for a full list, see `Envelope.PropertyType`)_

In Partigon, almost everything is an Envelope. Even the parameters that you pass into Envelopes, are Envelopes themselves.

All Envelopes have expressions, which are strings that are evaluated with [exp4j](https://github.com/fasseg/exp4j).

Envelopes can be nested inside of each other, resulting in unique effects that are otherwise not possible. In these cases, the property type will be `PropertyType.NONE`.

Most particle animations can be created using one of the already provided Envelope implementations, or using [Envelope Wrappers](../envelope-wrappers-todo.md).

All Envelopes extend [BasicEnvelope](basicenvelope.md), but you can create your own implementation.

Envelopes have a `completion` parameter, which indicates how much of the envelope to animate. For example, setting it to `1.0` will animate it in its entirety, `0.5` only half, `-1.0` will play it in reverse, etc.



There are several ways to add Envelopes to particles, in order of preference:

1\) Constructor-parameter envelopes

```kotlin
positionY = LinearEnvelope(0.0.envelope, 4.0.envelope, RepeatLoop(40))
```

2\) Property type defined in envelope, add with add() extension function

```kotlin
LinearEnvelope(Envelope.PropertyType.POS_Y, 0.0.envelope, 4.0.envelope, RepeatLoop(40)).add()
```

3\) Pass list of envelopes

```kotlin
envelopes = listOf(
    LinearEnvelope(Envelope.PropertyType.POS_Y, 0.0.envelope, 4.0.envelope, RepeatLoop(40))
)
```
