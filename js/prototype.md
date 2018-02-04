### Prototype

---

Javascript is an object-based language based on prototypes.

Objects in Javascript have an internal property, denoted in the specification as `[[Prototype]]` which is simply a reference to another object. 

The top-end of every normal `[[Prototype]]` chain is the built-in `Object.prototype`. This object includes a variety of common utilities used all over JS, because all normal (built-in, not host-specific extension) objects in JS 'descend from'(have at the top of their [[Prototype]] chain) the `Object.prototype` object.


