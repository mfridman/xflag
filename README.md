# xflag

There's a bit more details in the [Allowing flags anywhere on the
CLI](https://mfridman.com/blog/2024/allowing-flags-anywhere-on-the-cli/) post.

To summarize, the stdlib `flag` package has an opinionated approach to parsing flags. It enforces
that flags must be defined before any positional arguments.

Unfortunately, nowadays, it's common for users to expect (read want) to be able to define flags
after positional arguments.

So, this package exposes a single function called `ParseToEnd` which takes a normal `flag.FlagSet`
and `os.Args[1:]` and attempts to parse all the flags, even if they're defined after the positional
arguments.

The code here is really intended to be copy/pasted instead of imported. It's more of a
proof-of-concept for how I _wish_ the stdlib `flag` package worked.

If it looks like a flag, parses like a flag, and quacks like a flag, then it probably is a flag.
