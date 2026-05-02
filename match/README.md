# PBS Pro Espanso Expansions

## Job Submission

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qsub` | PBS - submit a job | Submit a batch job with queue, account, resources |
| `:PBS_qsub_interactive` | PBS - submit interactive job | Submit an interactive session |
| `:PBS_qsub_mixed` | PBS - submit mixed resource job | Submit job with mixed hardware/software nodes |

## Examining Queues

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qstat` | PBS - show queue status | Show queue status |
| `:PBS_qstat_jobs` | PBS - list all jobs | List all jobs in the system |
| `:PBS_qstat_user` | PBS - list jobs for specific user | Filter jobs by username |
| `:PBS_qstat_account` | PBS - list jobs for specific account | Filter jobs by account |
| `:PBS_qstat_full` | PBS - show full job details | Show detailed info for a specific job |
| `:PBS_qstat_json` | PBS - list jobs in JSON format | Output jobs in JSON format |

## Listing Nodes

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_pbsnodes` | PBS - list all nodes | List all nodes |
| `:PBS_pbsnodes_verbose` | PBS - list nodes with verbose output | List nodes with full details |
| `:PBS_pbsnodes_state` | PBS - filter nodes by state | Search for a specific node |
| `:PBS_pbsnodes_json` | PBS - list nodes in JSON format | Output nodes in JSON format |
| `:PBS_pbsnodes_busy` | PBS - list busy nodes | Show nodes in busy state |
| `:PBS_pbsnodes_free` | PBS - list free nodes | Show nodes in free state |
| `:PBS_pbsnodes_offline` | PBS - list offline nodes | Show nodes in offline state |

## Reserving Nodes

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_hold` | PBS - hold a job | Hold a job (reserve resources) |
| `:PBS_release` | PBS - release a held job | Release a held job |
| `:PBS_reserve_node` | PBS - reserve a node with a dummy job | Reserve a specific node |
| `:PBS_delete_reservation` | PBS - delete reservation job | Delete a reservation |
| `:PBS_qrerank` | PBS - rerank queue | Force queue reranking |

## Node Comments

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_comment_node` | PBS - add comment to a node | Add a comment to a node via qmgr |
| `:PBS_comment_node_delete` | PBS - delete comment from a node | Remove a comment from a node |
| `:PBS_comment_job` | PBS - add comment to a job | Add a comment to a running job |
| `:PBS_comment_server` | PBS - add comment to server | Add a comment to the PBS server |

## Job Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qdel` | PBS - delete a job | Delete a specific job |
| `:PBS_qdel_user` | PBS - delete all jobs for a user | Delete all jobs owned by a user |
| `:PBS_qsig` | PBS - send signal to job | Send a signal (e.g., SIGUSR1) to a job |
| `:PBS_qmove` | PBS - move job to different queue | Move a job to another queue |

## Queue Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qterm` | PBS - terminate a queue | Terminate (pause) a queue |
| `:PBS_qstart` | PBS - start a queue | Start (resume) a queue |
| `:PBS_qmgr_list` | PBS - list queue configuration | List all queue configurations |
