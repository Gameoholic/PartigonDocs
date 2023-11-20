# BasicEnvelope

`BasicEnvelope` is the simplest implementation of the `Envelope` interface. It should only be used for extension by other envelopes or envelope wrappers.

You pass it an envelope [expression](https://github.com/fasseg/exp4j) string, where `frame_index` is the frame.\
You also need to provide a Loop, the property type to affect, its completion, and may pass nested envelopes. \
If you pass any nested envelopes, you may use them in your expression by adding `@ENV_X@`, where X is the index of the nested envelope, starting from 0.

For more commonly used envelope types, see [LinearEnvelope](linearenvelope.md) and [Envelope Wrappers](../envelope-wrappers-todo.md).

