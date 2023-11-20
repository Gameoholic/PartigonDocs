# ConstantEnvelope

Used for holding a constant numeric value.

You can instantiate a `ConstantEnvelope` like this:

`ConstantEnvelope(propertyType: Envelope.PropertyType, value: Number)`

Or without a property, like this:

`ConstantEnvelope(value: Number)`

A nice extension property is defined for this, so to create a `ConstantEnvelope` with the value 3.5, you can just do: `3.5.envelope`.
