# Git Notify

Notify your team of important announcements via specialized Git commit messages.

This is an API-compatible version of [Jani Eväkallio's NodeJS-based `git-notify`][jevakallio] using only Bash and GNU coreutils.

[jevakallio]: https://github.com/jevakallio/git-notify

## Usage

Git Notify works through the use of [Git hooks][hooks]. Specifically, you will want to install `post-merge`, `post-rewrite`, and `post-checkout` hooks to check for announcements during each merge, rebase, and checkout. Currently, this is a manual process.

[hooks]: https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks

A basic `post-checkout` hook looks like the following:

``` shell
#!/bin/bash

git notify checkout "$1" "$2"
```

And a basic `post-merge` hook looks like this:

``` shell
#!/bin/bash

git notify merge
```

Lastly, a simple `post-rewrite` might look like:

``` shell
#!/bin/bash

git notify rewrite
```

