# BasicEnvelope

BasicEnvelope is the simplest implementation of Envelope. You pass it an envelope expression string, where `frame_index` is the frame.\
You also need to provide a Loop, the property type to affect, and may pass  nested envelopes. If you pass any nested envelopes, you may use them in your expression by adding `@ENV_X@`, where X is the index of the nested envelope, starting from 0.

Basic envelopes should only be used if you want to animate a particle at a static location, or for extension by other envelope types.

For more commonly used envelope types, see LineEnvelope and CurveEnvelope.
