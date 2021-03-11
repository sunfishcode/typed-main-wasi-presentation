# Option B: Provide a witx description

In this option, the Developer writes a witx file to describe their application.

This option involves no changes to the program itself.

The main program will still take strings and use preopens, but it can
be wrapped in a wasm interface generated form witx.

### Example:

```wasm
;; Typed main example: a simple grep

(module $grep
  ;;; Main entrypoint for grep.
  (@interface func (export "main")
    ;;; The string to search for.
    (param $pattern string)

    ;;; The output to write to.
    (param $output $output_byte_stream)

    ;;; The inputs to search for it in.
    (param $inputs (list $input_byte_stream))

    ;;; The result: Just indicate if any I/O failed.
    (result $error (expected unit (error $input_byte_stream_error)))
  )
)
```
