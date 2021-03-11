# Nameless

Nameless is a Rust crate prototyping Option C, for native code:

[https://github.com/sunfishcode/nameless](https://github.com/sunfishcode/nameless)

[https://crates.io/crates/nameless](https://crates.io/crates/nameless)

Nameless today works for native code by doing everything itself. But
once we hook it up to Typed Main in WASI, it'll be a very thin API.

```rust
/// # Arguments
///
/// * `pattern` - The regex to search for
/// * `inputs` - Input sources
#[kommand::main]
fn main(
    pattern: Regex,
    output: LazyOutput<OutputTextStream>,
    inputs: Vec<InputTextStream>,
) -> anyhow::Result<()> {
    let mut output = output.materialize(Type::text())?;

    let print_inputs = inputs.len() > 1;

    for input in inputs {
        let pseudonym = input.pseudonym();
        for line in BufReader::new(input).lines() {
            let line = line?;
            if pattern.is_match(&line) {
                if print_inputs {
                    output.write_pseudonym(&pseudonym)?;
                    write!(output, ":")?;
                }
                writeln!(output, "{}", line)?;
            }
        }
    }

    Ok(())
}
```
