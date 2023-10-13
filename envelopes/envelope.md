# Envelope

Envelopes are how you customize particle animations and animate properties.\
An Envelope is essentially an interpolation of a value over time.\
An Envelope can control one property of the particle at a time. Some examples are: POS\_X, POS\_Y, POS\_Z, COUNT. _(for a full list, see `Envelope.PropertyType`)_

All Envelopes have expressions, which are strings that are evaluated with [exp4j](https://github.com/fasseg/exp4j).

Envelopes can be nested inside of each other, resulting in unique effects that are otherwise not possible.

Most particle animations can be created using one of the already provided Envelope implementations. To see how to use them, see \[].

For instructions on implementing your own Envelope, see \[].
