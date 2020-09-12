# Side Effect Marker

Function have additional type that indicates its side-effect, nicknamed as steadiness. These are implicitly inferred.

- Steady
- Mildly unsteady
- Very unsteady

A function is steady if it doesn't mutate any value outside it nor causes changes to IO. Such function can still mutate any value create within its body.

A mildly unsteady function are those function that mutates its parameter.

A very unsteady function are those that mutates values from outside or causes changes to IO (or both).
