# Text Expansion for CSM

Provides a text expansion configuration simplifying some of the more complex CLI
commands necessary for administering a CSM environment. Examples of this
include:

1. Connecting to a node's console
1. Determining available firmware versions for a node
1. Getting VCS credential and cloning a vcs repo.
1. Finding an unused node.

and many, many more. Consult the [matchers configuration](./match/base.yml) for
the comprehensive list.

## Dependency on Espanso

Espanso is an opensource, desktop application available for Linux, Windows, and
Mac. It enables text expansion by keyword or, even better, by a searchable
pop-up dialog.

For Mac OS or a Linux environment with homebrew, `brew install espanso` works
well. Consult the [espanso install docs](https://espanso.org/install/) for
current info.
