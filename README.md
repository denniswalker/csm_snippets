# Text Expansion for CSM

Provides a text expansion configuration simplifying some of the more complex CLI
commands necessary for administering a CSM environment. Examples of this
include:

1. Connecting to a node's console
1. Determining available firmware versions for a node.
1. Getting VCS credential and cloning a vcs repo.
1. Finding an unused node.
1. Search through SMA logs.
1. View Prometheus alerts.
1. Get customizations.yaml.
1. Retrieve the Keycloak admin pass.
1. Boot all nodes that are off.
1. Check compute nodes view of DVS servers. (requires clush)
1. Convert xname into nid name.
1. Check an NCN's nowipe param value.
1. Get API auth token.
1. Get power state for node from PCS.
1. Get power state for node from CAPMC.
1. Set power state for node to on through PCS.
1. Show pending BOS sessions.
1. Get boot status through either SAT or BOS for a node.
1. List firmware for a model in FAS.
1. Find a free node via HSM.
1. Test a specific ansible change on a node using cfs.
1. Get all failed CFS logs.
1. Show last errors in those CFS logs.
1. Create a new image from CFS layer.
1. Get a CFS session name from BOS session.
1. Show logs for that CFS session.
1. Get Nexus credentials.

and many, many more. Consult the [matchers configuration](./match/base.yml) for
the comprehensive list.

## Dependency on Espanso

Espanso is an opensource, desktop application available for Linux, Windows, and
Mac. It enables text expansion by keyword or, even better, by a searchable
pop-up dialog.

For Mac OS or a Linux environment with homebrew, `brew install espanso` works
well. Consult the [espanso install docs](https://espanso.org/install/) for
current info.
