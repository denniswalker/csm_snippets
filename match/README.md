# Espanso Expansions

## Table of Contents

- [PBS Pro](#pbs-pro)
  - [Job Submission](#job-submission)
  - [Examining Queues](#examining-queues)
  - [Listing Nodes](#listing-nodes)
  - [Reserving Nodes](#reserving-nodes)
  - [Node Comments](#node-comments)
  - [Job Management](#job-management)
  - [Queue Management](#queue-management)
- [Lustre](#lustre)
  - [File System Management](#file-system-management)
  - [Stripe Operations](#stripe-operations)
  - [File Operations](#file-operations)
  - [Network Operations](#network-operations)
  - [Network and Connectivity](#network-and-connectivity)
  - [MGS/MDS Operations](#mgsmds-operations)
  - [OSS Operations](#oss-operations)
  - [Health and Monitoring](#health-and-monitoring)
  - [Backup and Recovery](#backup-and-recovery)
  - [Performance](#performance)
  - [Miscellaneous](#miscellaneous)

---

## PBS Pro

### Job Submission

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qsub` | PBS - submit a job | Submit a batch job with queue, account, resources |
| `:PBS_qsub_interactive` | PBS - submit interactive job | Submit an interactive session |
| `:PBS_qsub_mixed` | PBS - submit mixed resource job | Submit job with mixed hardware/software nodes |

### Examining Queues

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qstat` | PBS - show queue status | Show queue status |
| `:PBS_qstat_jobs` | PBS - list all jobs | List all jobs in the system |
| `:PBS_qstat_user` | PBS - list jobs for specific user | Filter jobs by username |
| `:PBS_qstat_account` | PBS - list jobs for specific account | Filter jobs by account |
| `:PBS_qstat_full` | PBS - show full job details | Show detailed info for a specific job |
| `:PBS_qstat_json` | PBS - list jobs in JSON format | Output jobs in JSON format |

### Listing Nodes

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_pbsnodes` | PBS - list all nodes | List all nodes |
| `:PBS_pbsnodes_verbose` | PBS - list nodes with verbose output | List nodes with full details |
| `:PBS_pbsnodes_state` | PBS - filter nodes by state | Search for a specific node |
| `:PBS_pbsnodes_json` | PBS - list nodes in JSON format | Output nodes in JSON format |
| `:PBS_pbsnodes_busy` | PBS - list busy nodes | Show nodes in busy state |
| `:PBS_pbsnodes_free` | PBS - list free nodes | Show nodes in free state |
| `:PBS_pbsnodes_offline` | PBS - list offline nodes | Show nodes in offline state |

### Reserving Nodes

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_hold` | PBS - hold a job | Hold a job (reserve resources) |
| `:PBS_release` | PBS - release a held job | Release a held job |
| `:PBS_reserve_node` | PBS - reserve a node with a dummy job | Reserve a specific node |
| `:PBS_delete_reservation` | PBS - delete reservation job | Delete a reservation |
| `:PBS_qrerank` | PBS - rerank queue | Force queue reranking |

### Node Comments

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_comment_node` | PBS - add comment to a node | Add a comment to a node via qmgr |
| `:PBS_comment_node_delete` | PBS - delete comment from a node | Remove a comment from a node |
| `:PBS_comment_job` | PBS - add comment to a job | Add a comment to a running job |
| `:PBS_comment_server` | PBS - add comment to server | Add a comment to the PBS server |

### Job Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qdel` | PBS - delete a job | Delete a specific job |
| `:PBS_qdel_user` | PBS - delete all jobs for a user | Delete all jobs owned by a user |
| `:PBS_qsig` | PBS - send signal to job | Send a signal (e.g., SIGUSR1) to a job |
| `:PBS_qmove` | PBS - move job to different queue | Move a job to another queue |

### Queue Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:PBS_qterm` | PBS - terminate a queue | Terminate (pause) a queue |
| `:PBS_qstart` | PBS - start a queue | Start (resume) a queue |
| `:PBS_qmgr_list` | PBS - list queue configuration | List all queue configurations |

## Lustre

### File System Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_df` | Lustre - show filesystem usage | Show Lustre filesystem disk usage |
| `:Lustre_lfs_df_human` | Lustre - show filesystem usage (human readable) | Show disk usage with human-readable sizes |
| `:Lustre_lfs_df_stripe` | Lustre - show stripe usage per OST | Show usage broken down by OST |
| `:Lre_lfs_mdf` | Lustre - show MDT usage | Show MDT disk usage |

### Stripe Operations

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_stripe` | Lustre - show stripe information | Show stripe layout for a file/directory |
| `:Lustre_lfs_setstripe` | Lustre - set stripe parameters | Set stripe count, size, and index |
| `:Lustre_lfs_setstripe_random` | Lustre - set random striping | Set random OST selection |
| `:Lustre_lfs_setstripe_single` | Lustre - set single stripe | Force single-stripe layout |
| `:Lustre_lfs_getstripe` | Lustre - get stripe information | Display stripe details |
| `:Lustre_lfs_mkdir` | Lustre - create directory with striping | Create directory with pre-set stripe params |

### File Operations

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_cpdcp` | Lustre - copy file with cp | Copy file using Lustre-aware cp |
| `:Lustre_lfs_mkdir_template` | Lustre - create directory with template | Create directory using a template file |
| `:Lustre_lfs_find_ost` | Lustre - find files on specific OST | Find files stored on a specific OST |
| `:Lustre_lfs_find_size` | Lustre - find files by size range | Find files within a size range |
| `:Lustre_lfs_rrd` | Lustre - run remote debug | Run command remotely on OST |

### Network Operations

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_faila` | Lustre - set failover parameters | Configure automatic failover |
| `:Lustre_lfs_failost` | Lustre - fail an OST | Manually fail an OST for testing |
| `:Lustre_lfs_hsm` | Lustre - HSM archive operation | Archive files to HSM |
| `:Lustre_lfs_hsm_release` | Lustre - HSM release operation | Release files from HSM archive |

### Network and Connectivity

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lctl` | Lustre - lctl common query | Query a Lustre kernel parameter |
| `:Lustre_lctl_set` | Lustre - lctl set parameter | Set a Lustre kernel parameter |
| `:Lustre_lctl_nid` | Lustre - show NID information | List network interface identifiers |
| `:Lustre_lctl_debug` | Lustre - enable debug logging | Enable debug messages |
| `:Lustre_lctl_nidcheck` | Lustre - check NID connectivity | Verify NID connectivity |

### MGS/MDS Operations

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_mds` | Lustre - show MDS information | Display MDS details |
| `:Lustre_lfs_mgs` | Lustre - show MGS information | Display MGS details |
| `:Lustre_lfs_mgss` | Lustre - list MGS targets | List all MGS targets |

### OSS Operations

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_ost` | Lustre - show OST information | Display OST details |
| `:Lustre_lfs_ost_list` | Lustre - list all OSTs | List all OSTs in filesystem |
| `:Lustre_lfs_ost_fail` | Lustre - fail an OST | Manually fail an OST |

### Health and Monitoring

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_health` | Lustre - run health check | Run filesystem health check |
| `:Lustre_lfs_health_detail` | Lustre - run detailed health check | Run verbose health check |
| `:Lustre_lfs_health_export` | Lustre - export health data to JSON | Export health data as JSON |
| `:Lustre_lfs_mds_health` | Lustre - check MDS health | Check MDS health status |
| `:Lustre_lfs_ost_health` | Lustre - check OST health | Check OST health status |

### Backup and Recovery

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_scrub` | Lustre - run scrub operation | Start metadata scrub |
| `:Lustre_lfs_scrub_status` | Lustre - check scrub status | Check scrub progress |
| `:Lustre_lfs_scrab_canceled` | Lustre - cancel scrub | Cancel running scrub |
| `:Lustre_lfs_mksnap` | Lustre - create snapshot | Create a filesystem snapshot |
| `:Lustre_lfs_rmsnap` | Lustre - remove snapshot | Delete a snapshot |
| `:Lustre_lfs_listsnap` | Lustre - list snapshots | List all snapshots |

### Performance

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_lfs_iostat` | Lustre - show I/O statistics | Display I/O stats for filesystem |
| `:Lustre_lfs_io` | Lustre - show I/O patterns | Show I/O patterns over time |
| `:Lustre_lfs_bw` | Lustre - bandwidth test | Run bandwidth benchmark |

### Miscellaneous

| Trigger | Label | Description |
|---------|-------|-------------|
| `:Lustre_mount` | Lustre - mount filesystem | Mount a Lustre filesystem |
| `:Lustre_umount` | Lustre - unmount filesystem | Unmount a Lustre filesystem |
| `:Lustre_lfs_gdl` | Lustre - list GIDs | List GID mappings |
| `:Lustre_lfs_gdl_add` | Lustre - add GID mapping | Add GID to user mapping |
| `:Lustre_lfs_gdl_remove` | Lustre - remove GID mapping | Remove GID mapping |
