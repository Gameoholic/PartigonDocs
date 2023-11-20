# Loops

Loops are what's used for controlling envelopes, and how long they last.\
The following are Loops included within Partigon, however, you can also make your own implementations.

All loops require the duration as an Integer parameter.

_As always, the method and class descriptions provide more information._

## RepeatLoop

When loop ends, restarts the animation on the first frame (frame 0).

## ReverseLoop

When loop reaches end, reverses the animation, playing it in the same way but in reverse. It then repeats.

## BounceLoop

When loop reaches end, will reverse in the same way as ReverseLoop, but will not repeat the first and last frame, resulting in a clean "bounce" animation.

## ContinueLoop

Nothing changes when loop ends, the animation continues.

## Custom Loops

To implement your own Loop, extend the Loop interface, and override the `duration` and `envelopeDuration` fields, and the `applyLoop` method.

I'd recommend taking a look at the existing Loop classes to see how to implement your own.
