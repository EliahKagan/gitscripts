# gitscripts - some custom git commands

*Written in 2019 by Eliah Kagan \<degeneracypressure@gmail.com\>.*

*To the extent possible under law, the author(s) have dedicated all copyright
and related and neighboring rights to this software to the public domain
worldwide. This software is distributed without any warranty.*

*You should have received a copy of the CC0 Public Domain Dedication along with
this software. If not, see
<http://creativecommons.org/publicdomain/zero/1.0/>.*

This repository contains scripts that start with `git-` and conceptually
perform well-defined actions for git.

When installed to a directory listed in `$PATH`, a script (or other executable)
`git-X` defines a new git command `X`. Running `git X ...` calls `git-X ...`.

See `BUGS.md` for information about known bugs.

Here's a summary of the commands:

### `git-chmod`

This command changes executable permissions for files in the index. Use it like
`chmod`, but specify only `+x` or `-x` as the mode. Pass one or more paths
after the mode. For example:

```sh
git chmod +x foo
git chmod -x bar baz quux
```

`git-chmod` is a thin wrapper for `git update-index --chmod=`.

This is mostly useful on Windows (with Git for Windows), together with
`git-lsx` to inspect the permissions.

As for how the `--chmod` option to `git update-index` works, see [this
article](https://medium.com/@akash1233/change-file-permissions-when-working-with-git-repos-on-windows-ea22e34d5cee)
by [Dharmendra Singh](https://medium.com/@akash1233).

If `git` ever supports setting permissions on staged files other than with `+x`
and `-x`, and uses the same syntax, then other such arguments to `git-chmod`
will work, too.

### `git-lsx`

This command lists files in the Git index with their associated permissions,
emphasizing those marked executable (and, in a different style, symlinks) in a
manner similar to the effect of `ls --color=auto -F`.

This is mostly useful on Windows (with Git for Windows). On a Unix-like system,
your repositories are presumably on a filesystem that supports Unix-style
permissions, so you can usually just use `ls -l`. Occasionally you might still
want to inspect the index rather than your working tree, though.

### `git-pull-all`

This command pulls all branches from the *origin* remote. Currently it uses
*origin* even if it's not the upstream remote.

I don't plan to add `git-push-all`. I suspect a substantial fraction of
`git push-all` usages would be mistakes. More important, I have rarely wanted
to do that personally.
