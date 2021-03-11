# Command-line usage

Command-line parsing for Typed Main programs happens in the Wasm engine.

## Example: an `f32` argument

The user might type `"6.283185`"

In some locales, the user might type `"6,283185"`.

Or "0x1.921fb5p+2"`.

Parsing in the Wasm engine means that all programs have a consistent
interface.

## Example: a handle argument

Many programs read files, but they don't literally need *files*.

An "input stream", that supports `read` would often be enough.

Programs written this way:
 - Do one thing and do it well (waves to Unix)
 - Don't depend on a particular filesystem view
 - Don't depend on filesystem privileges
 - Don't depend on a filesystem at all!

## Bonus:

- No implied string comparisons! No:
  - Non-Unicode filenames
  - Unicode normalization
  - Case sensitivity
  - Windows special-case path parsing
  - Filename length limits
  - ...
