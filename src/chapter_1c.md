# What problems does parsing cause?

*Commmand-line parsing* is inconsistent and error-prone.

Is `-ab` the same as `-a` `-b`?

Is `-a` `-b` the same as `-b` `-a`?

Also, *security* and *virtualization*:

 - Child process needs same filesystem view as parent
 - Child process needs permissions of parent
 - Child process hard-codes how to turn strings into streams

We can sandbox child processes, but we often don't.
