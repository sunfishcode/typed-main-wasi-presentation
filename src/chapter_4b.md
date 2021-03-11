# Typed Main uses in WASI

## wasi-clocks

Clocks should be capabilities, rather than ambient authorities.

## wasi-random

Entropy sources should be capabilities, rather than ambient authorities.

## New WASI proposals

 - Serial ports
 - Audio devices
 - Database connections
 - etc.

A big question for all capability systems is how a program obtains the
first capability. Typed Main is a way to do this.
