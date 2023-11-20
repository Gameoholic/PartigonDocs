# LinearEnvelope

An Envelope used for interpolation between 2 values linearly.

`LineEnvelope` requires 2 Envelope values.\
The value will be interpolated over the length of the loop provided. See[ Loops](loops.md).

\
For example, the following will animate the X position of the particle relative to its `originLocation`, from 0 to 5, over 21 ticks. It will then repeat forever:

```
positionX = LinearEnvelope(0.envelope, 5.envelope, RepeatLoop(21))
```

_(0.25, 0.5, 0.75, 1.0, ...)_\
_Note that in this case we made it last 21 ticks instead of 20, for the jumps to be in 0.25's._

_You can pass any type of envelope, for example:_

```
positionX = LinearEnvelope( 
    LinearEnvelope(0, 5, RepeatLoop(101)),
    2.envelope,
   BounceLoop(20)
 )
```

All envelopes have secondary constructor with the `NONE` property type as the default, which is used for the nested envelope above.

You can get real creative with this! You can pass Envelopes as both parameters, and even create Envelopes nested inside of Envelopes nested inside of Envelopes nested inside of _(you get the point)_
