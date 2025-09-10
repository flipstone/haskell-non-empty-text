Non Empty Text
==============

Typesafe thin wrapper around `Data.Text` to make impossible to be empty (to
always hold at least on character)

Roadmap
-------

### Done

  * Typesafe wrapper around Text
  * `Data.Text` ↔ `Data.NonEmptyText` back and forth conversion.
  * Basic functions: `(un)cons`, `head`, `tail`, `last`, `length`
  * Text equivalent of `null` -> `isSingleton`.

### To do

  * `Item` class instance
  * Transformations (`intercalate`, `reverse`)
  * Case conversions
  * Justification
  * Folds (especially, total `fold1` functions)
  * Scans
  * Substrings

_For now all of this can be done by calling `toText`, however the `Text` type
doesn't ensure that all of this functions return `NonEmptyText`._

_Another solution is to use `fromText . <function> . toText`, but this forces
the programmer to handle the `Nothing` case, which is for many of these functions
unnecessary._


FAQ
---

### Why not text1?

[`text1`](https://hackage.haskell.org/package/text1) basically does the same
thing than this package, and even more. It's also a great package.

However text1 has a lot of dependencies, and use [an alternative
homebrewed prelude](https://hackage.haskell.org/package/papa).

`non-empty-text` is aiming towards a minimal, thin wrapper. The goal is to do
the same thing as the [`text`](https://hackage.haskell.org/package/text), with
only `text` and `base` as dependencies, no extension.
