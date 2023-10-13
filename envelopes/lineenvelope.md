# LineEnvelope

An Envelope used for interpolation between 2 values linearly.

LineEnvelope requires 2 values, they may be of type `Int`, `Double` or `Envelope`.

The value will be interpolated over the length of the loop provided. See Loops.\
For example, the following will animate the X position of the particle relative to its location, from 0 to 5, over 20 ticks. It will then repeat forever:

```
LineEnvelope(Envelope.PropertyType.POS_X, 0, 5, RepeatLoop(21))
```

_(0.25, 0.5, 0.75, 1.0, ...)_\
_Note that in this case we made it last 21 loops for the jumps to be in 0.25's, because the first index of the animation is 0 and not 1, and counts in the loop duration!_

_You may also pass an Envelope as one of the values:_

```
LineEnvelope(Envelope.PropertyType.POS_X, 
    LineEnvelope(Envelope.PropertyType.NONE,
        0, 
        5, 
        RepeatLoop(101)
    ),
    2,
   BounceLoop(20))
```

Since nested Envelopes don't affect a property, you should use `PropertyType.NONE` for them.

You can get real creative with this! You can pass Envelopes as both parameters, and even create Envelopes nested inside of Envelopes nested inside of Envelopes nested inside of

For examples see Examples.\
