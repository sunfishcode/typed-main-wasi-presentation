# Option A: Out of the box

For porting an existing application with no changes, things work like they do
in WASI today:
 - Everything is strings
 - User needs to use `--dir` preopens

This uses Typed Main, but with a fixed signature.
 - List-of-strings for the args
 - List-of-(handle,string) for the preopens
