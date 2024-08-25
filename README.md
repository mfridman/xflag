# xflag

The `flag` package in Go's standard library takes an opinionated approach to parsing flags. It stops
parsing when it encounters a positional argument.

However, most users nowadays expect — and want — to define flags anywhere in the CLI.

For more details, check out my blog post:

[Allowing flags anywhere on the
CLI](https://mfridman.com/blog/2024/allowing-flags-anywhere-on-the-cli/)

This package introduces a single function, `ParseToEnd`, which takes a standard `flag.FlagSet` and
`os.Args[1:]`. It attempts to parse all flags, even when they're mixed with or placed after
positional arguments.

The code is meant to be copy-pasted rather than imported. It's essentially a proof-of-concept for
how I'd like the `flag` package to work.

If it looks like a flag, parses like a flag, and quacks like a flag, then it probably is a flag.
