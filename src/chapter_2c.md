# Types

MVP types: `i32`, `i64`, `f32`, `f64`

WASI is about interfaces, so we also look forward to
[Interface Types](https://github.com/WebAssembly/interface-types/blob/master/proposals/interface-types/Explainer.md#lifting-and-lowering-instructions):

 - signed and unsigned integers
 - `bool`
 - lists
 - variants
 - records
 - strings, aka lists of characters
 - handles

## Handles

The way we represent handles in wasm will likely evolve over time.
 - Integer indices into tables
 - `externref`
 - [Typed imports](https://github.com/WebAssembly/proposal-type-imports)

At the witx level, we can just use the `handle` type.
