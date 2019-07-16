# gitscripts - *some custom git commands*

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

<sup>Right now, I only have one such script, `git-pull-all`, in this repository. I'll
likely add others later. But I don't plan to add `git-push-all`, because I
suspect a substantial fraction of `git push-all` usages would be mistakes, and
more importantly because I have rarely wanted to do that personally.</sup>

See `BUGS.md` for information about known bugs.
