# Envelope

Envelopes are the main way of creating and customizing particle animations.\
An Envelope is essentially an interpolation of a value over time.\
An Envelope can control one property of the particle at a time. Some examples are: POS\_X, POS\_Y, POS\_Z, COUNT. _(for a full list, see `Envelope.PropertyType`)_

All Envelopes have expressions, which are strings that are then evaluated with exp4j for PartigonParticle objects.&#x20;

Envelopes have a `disabled` property, which when set to true, will be ignored and not affect the particle animation.

Envelopes also have an `isAbsolute` property. It is false by default, but if set to true, will be absolute, instead of being relative to the original property value, which is optionally provided in the PartigonParticle constructor.

Envelopes can be nested inside of each other, resulting in unique effects that are otherwise not possible.

Most particle animations can be created using one of the already provided Envelope implementations. To see how to use them, see \[].

For instructions on implementing your own Envelope, see \[].
