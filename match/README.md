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
- [HPCM](#hpcm)
  - [Node Management](#node-management-1)
  - [Image Management](#image-management)
  - [Group Management](#group-management)
  - [Service Management](#service-management)
  - [Health and Events](#health-and-events)
  - [Software Management](#software-management)
- [MPI](#mpi)
  - [Job Launching - mpirun](#job-launching---mpirun)
  - [Job Launching - mpiexec](#job-launching---mpiexec)
  - [Process Mapping and Binding](#process-mapping-and-binding)
  - [Environment](#environment)
  - [Compilation](#compilation)
  - [Info and Diagnostics](#info-and-diagnostics)
  - [Intel MPI](#intel-mpi)
  - [Debugging](#debugging)
  - [Tuning](#tuning)
- [NVIDIA GPU](#nvidia-gpu)
  - [nvidia-smi Basic Status](#nvidia-smi-basic-status)
  - [nvidia-smi Custom Queries](#nvidia-smi-custom-queries)
  - [nvidia-smi Device Monitoring](#nvidia-smi-device-monitoring)
  - [nvidia-smi Power and Clocks](#nvidia-smi-power-and-clocks)
  - [nvidia-smi ECC](#nvidia-smi-ecc)
  - [nvidia-smi MIG](#nvidia-smi-mig)
  - [nvidia-smi NVLink](#nvidia-smi-nvlink)
  - [nvidia-smi Reset and Drain](#nvidia-smi-reset-and-drain)
  - [DCGM Discovery](#dcgm-discovery)
  - [DCGM Groups](#dcgm-groups)
  - [DCGM Diagnostics](#dcgm-diagnostics)
  - [DCGM Health](#dcgm-health)
  - [DCGM Job Statistics](#dcgm-job-statistics)
  - [DCGM Field Groups and Monitoring](#dcgm-field-groups-and-monitoring)
  - [DCGM Host Engine](#dcgm-host-engine)
  - [CUDA Compilation](#cuda-compilation)
  - [Miscellaneous](#miscellaneous-1)

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

## HPCM

### Node Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:HPCM_node_list` | HPCM - list all nodes | List all nodes in the cluster |
| `:HPCM_node_show` | HPCM - show node details | Show detailed info for a node |
| `:HPCM_node_status` | HPCM - show node status | Show current status of a node |
| `:HPCM_node_power_on` | HPCM - power on node | Power on a node |
| `:HPCM_node_power_off` | HPCM - power off node | Power off a node |
| `:HPCM_node_power_reset` | HPCM - power reset node | Hard reset a node |
| `:HPCM_node_reboot` | HPCM - reboot node | Gracefully reboot a node |
| `:HPCM_node_console` | HPCM - open serial console to node | Open serial console to a node |
| `:HPCM_node_ssh` | HPCM - SSH into node | SSH into a node |
| `:HPCM_node_ping` | HPCM - ping node | Ping a node |
| `:HPCM_node_add` | HPCM - add a node | Add a new node to the cluster |
| `:HPCM_node_remove` | HPCM - remove a node | Remove a node from the cluster |

### Image Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:HPCM_image_list` | HPCM - list images | List all available images |
| `:HPCM_image_show` | HPCM - show image details | Show details for an image |
| `:HPCM_image_create` | HPCM - create image | Create a new image |
| `:HPCM_image_clone` | HPCM - clone image | Clone an existing image |
| `:HPCM_image_assign` | HPCM - assign image to node | Assign an image to a node |
| `:HPCM_image_delete` | HPCM - delete image | Delete an image |

### Group Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:HPCM_group_list` | HPCM - list node groups | List all node groups |
| `:HPCM_group_show` | HPCM - show group details | Show details for a group |
| `:HPCM_group_create` | HPCM - create group | Create a new node group |
| `:HPCM_group_delete` | HPCM - delete group | Delete a node group |
| `:HPCM_group_add_node` | HPCM - add node to group | Add a node to a group |
| `:HPCM_group_remove_node` | HPCM - remove node from group | Remove a node from a group |

### Service Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:HPCM_service_list` | HPCM - list services | List all managed services |
| `:HPCM_service_status` | HPCM - show service status | Show status of a service |
| `:HPCM_service_start` | HPCM - start service | Start a service |
| `:HPCM_service_stop` | HPCM - stop service | Stop a service |
| `:HPCM_service_restart` | HPCM - restart service | Restart a service |

### Health and Events

| Trigger | Label | Description |
|---------|-------|-------------|
| `:HPCM_health` | HPCM - cluster health overview | Show overall cluster health |
| `:HPCM_event_list` | HPCM - list events | List recent cluster events |
| `:HPCM_alert_list` | HPCM - list active alerts | List active cluster alerts |

### Software Management

| Trigger | Label | Description |
|---------|-------|-------------|
| `:HPCM_software_list` | HPCM - list installed software | List all installed software packages |
| `:HPCM_software_install` | HPCM - install software package | Install a software package |
| `:HPCM_software_remove` | HPCM - remove software package | Remove a software package |

## MPI

### Job Launching - mpirun

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_mpirun` | MPI - run MPI program | Basic mpirun launch |
| `:MPI_mpirun_hostfile` | MPI - run with hostfile | Launch with explicit hostfile |
| `:MPI_mpirun_ppn` | MPI - run with processes per node | Launch with ppn specified |
| `:MPI_mpirun_hosts` | MPI - run with explicit host list | Launch with inline host list |
| `:MPI_mpirun_pbs` | MPI - run using PBS nodefile | Launch using $PBS_NODEFILE |

### Job Launching - mpiexec

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_mpiexec` | MPI - mpiexec run program | Basic mpiexec launch |
| `:MPI_mpiexec_ppn` | MPI - mpiexec with processes per node | Launch with ppn specified |
| `:MPI_mpiexec_hostfile` | MPI - mpiexec with hostfile | Launch with explicit hostfile |
| `:MPI_mpiexec_pbs` | MPI - mpiexec using PBS nodefile | Launch using $PBS_NODEFILE |

### Process Mapping and Binding

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_map_by_node` | MPI - map processes by node | Round-robin mapping across nodes |
| `:MPI_map_by_socket` | MPI - map processes by socket | Map across sockets |
| `:MPI_map_by_core` | MPI - map processes by core | Map across cores |
| `:MPI_bind_to_core` | MPI - bind processes to cores | Pin each rank to a core |
| `:MPI_bind_to_socket` | MPI - bind processes to sockets | Pin each rank to a socket |
| `:MPI_bind_to_none` | MPI - disable process binding | Run without affinity binding |

### Environment

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_export_env` | MPI - export environment variable to ranks | Forward env var to all ranks |
| `:MPI_export_env_value` | MPI - export env variable with value to ranks | Set and forward env var to all ranks |

### Compilation

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_mpicc` | MPI - compile C program | Compile C source with MPI wrappers |
| `:MPI_mpicxx` | MPI - compile C++ program | Compile C++ source with MPI wrappers |
| `:MPI_mpif90` | MPI - compile Fortran 90 program | Compile Fortran 90 source with MPI wrappers |
| `:MPI_mpif77` | MPI - compile Fortran 77 program | Compile Fortran 77 source with MPI wrappers |

### Info and Diagnostics

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_ompi_info` | MPI - show Open MPI build info | Show Open MPI configuration |
| `:MPI_ompi_info_all` | MPI - show all Open MPI parameters | List all MCA parameters |
| `:MPI_ompi_info_param` | MPI - show specific Open MPI parameter | Query a specific MCA parameter |
| `:MPI_ompi_version` | MPI - show Open MPI version | Print Open MPI version string |
| `:MPI_mpichversion` | MPI - show MPICH version | Print MPICH version info |
| `:MPI_mpiname` | MPI - show MPI implementation name | Print MPI implementation details |

### Intel MPI

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_impi_hydra` | MPI - Intel MPI run with Hydra launcher | Launch using Intel Hydra bootstrap |
| `:MPI_impi_rankfile` | MPI - Intel MPI run with rankfile | Launch with explicit rank placement file |

### Debugging

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_mpirun_verbose` | MPI - run with verbose output | Launch with verbose MPI output |
| `:MPI_mpirun_display_map` | MPI - display process map before launching | Show process placement map |
| `:MPI_mpirun_display_devel_map` | MPI - display detailed process map | Show detailed developer process map |
| `:MPI_mpirun_report_bindings` | MPI - report process bindings | Print CPU binding for each rank |

### Tuning

| Trigger | Label | Description |
|---------|-------|-------------|
| `:MPI_mca_param` | MPI - set MCA parameter at launch | Pass arbitrary MCA parameter |
| `:MPI_mca_btl` | MPI - set BTL (byte transfer layer) | Select byte transfer layer(s) |
| `:MPI_mca_pml` | MPI - set PML (point-to-point messaging layer) | Select point-to-point messaging layer |

## NVIDIA GPU

### nvidia-smi Basic Status

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi` | nvidia-smi - show GPU status summary | Show GPU status overview |
| `:NV_smi_watch` | nvidia-smi - continuous monitoring | Poll GPU stats at an interval |
| `:NV_smi_list` | nvidia-smi - list GPUs | List all detected GPUs |
| `:NV_smi_topo` | nvidia-smi - show GPU topology matrix | Show inter-GPU and CPU topology |
| `:NV_smi_topo_p2p` | nvidia-smi - show P2P access matrix | Show peer-to-peer access capabilities |

### nvidia-smi Custom Queries

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_query` | nvidia-smi - query GPU properties | Query arbitrary GPU properties as CSV |
| `:NV_smi_query_common` | nvidia-smi - query common GPU metrics | Query temp, utilization, memory, power |
| `:NV_smi_query_clocks` | nvidia-smi - query GPU clock speeds | Query graphics, memory, SM clocks |
| `:NV_smi_query_ecc` | nvidia-smi - query ECC error counts | Query corrected and uncorrected ECC errors |
| `:NV_smi_query_procs` | nvidia-smi - query processes using GPUs | List processes consuming GPU memory |

### nvidia-smi Device Monitoring

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_dmon` | nvidia-smi - device monitoring (dmon) | Monitor device metrics at interval |
| `:NV_smi_dmon_all` | nvidia-smi - dmon all metrics | Monitor all available dmon metrics |
| `:NV_smi_pmon` | nvidia-smi - process monitoring (pmon) | Monitor per-process GPU utilization |

### nvidia-smi Power and Clocks

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_persistence_on` | nvidia-smi - enable persistence mode | Keep GPU driver loaded when idle |
| `:NV_smi_persistence_off` | nvidia-smi - disable persistence mode | Disable persistence mode |
| `:NV_smi_power_limit` | nvidia-smi - set power limit | Set GPU power cap in watts |
| `:NV_smi_set_clocks` | nvidia-smi - set application clocks | Lock memory and graphics clocks |
| `:NV_smi_reset_clocks` | nvidia-smi - reset application clocks | Release clock locks |
| `:NV_smi_auto_boost_off` | nvidia-smi - disable auto boost clocks | Disable automatic clock boosting |

### nvidia-smi ECC

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_ecc_on` | nvidia-smi - enable ECC | Enable ECC memory (requires reboot) |
| `:NV_smi_ecc_off` | nvidia-smi - disable ECC | Disable ECC memory (requires reboot) |
| `:NV_smi_ecc_clear` | nvidia-smi - clear ECC error counts | Clear volatile ECC error counters |

### nvidia-smi MIG

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_mig_on` | nvidia-smi - enable MIG mode | Enable Multi-Instance GPU mode |
| `:NV_smi_mig_off` | nvidia-smi - disable MIG mode | Disable Multi-Instance GPU mode |
| `:NV_smi_mig_list` | nvidia-smi - list MIG instances | List GPU instances |
| `:NV_smi_mig_list_ci` | nvidia-smi - list MIG compute instances | List compute instances |
| `:NV_smi_mig_create_gi` | nvidia-smi - create MIG GPU instance | Create a GPU instance by profile |
| `:NV_smi_mig_delete_gi` | nvidia-smi - delete MIG GPU instance | Delete a GPU instance |
| `:NV_smi_mig_profiles` | nvidia-smi - list available MIG profiles | List valid MIG partition profiles |

### nvidia-smi NVLink

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_nvlink_status` | nvidia-smi - show NVLink status | Show NVLink lane status |
| `:NV_smi_nvlink_errors` | nvidia-smi - show NVLink error counters | Show NVLink error counts |
| `:NV_smi_nvlink_caps` | nvidia-smi - show NVLink capabilities | Show NVLink capabilities |

### nvidia-smi Reset and Drain

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_smi_reset` | nvidia-smi - reset GPU | Hard reset a GPU |
| `:NV_smi_drain` | nvidia-smi - drain GPU | Remove GPU from use (fabric drain) |
| `:NV_smi_undrain` | nvidia-smi - undrain GPU | Restore GPU to use |

### DCGM Discovery

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_list` | DCGM - list all GPUs | List GPUs visible to DCGM |
| `:DCGM_list_verbose` | DCGM - list GPUs verbose | List GPUs with full detail |

### DCGM Groups

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_group_list` | DCGM - list GPU groups | List all DCGM groups |
| `:DCGM_group_create` | DCGM - create GPU group | Create a new DCGM group |
| `:DCGM_group_delete` | DCGM - delete GPU group | Delete a DCGM group |
| `:DCGM_group_add` | DCGM - add GPU to group | Add a GPU to a group |
| `:DCGM_group_info` | DCGM - show group info | Show details for a group |

### DCGM Diagnostics

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_diag_quick` | DCGM - run quick diagnostic (level 1) | Fast health check (~1 min) |
| `:DCGM_diag_medium` | DCGM - run medium diagnostic (level 2) | Medium depth diagnostic (~2 min) |
| `:DCGM_diag_long` | DCGM - run long diagnostic (level 3) | Full stress diagnostic (~12 min) |
| `:DCGM_diag_plugin` | DCGM - run specific diagnostic plugin | Run a named diagnostic plugin |

### DCGM Health

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_health_set` | DCGM - set health watches | Enable all health monitoring watches |
| `:DCGM_health_check` | DCGM - check group health | Check current health status |

### DCGM Job Statistics

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_stats_enable` | DCGM - enable job stats collection | Enable stats gathering on group |
| `:DCGM_stats_disable` | DCGM - disable job stats collection | Disable stats gathering on group |
| `:DCGM_stats_start` | DCGM - start collecting stats for job | Begin per-job GPU stat collection |
| `:DCGM_stats_stop` | DCGM - stop collecting stats for job | Stop per-job GPU stat collection |
| `:DCGM_stats_view` | DCGM - view stats for job | Display collected job GPU stats |

### DCGM Field Groups and Monitoring

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_fieldgroup_list` | DCGM - list field groups | List all DCGM field groups |
| `:DCGM_dmon` | DCGM - device monitoring | Continuously monitor GPU metrics |
| `:DCGM_dmon_fields` | DCGM - device monitoring with specific fields | Monitor specific DCGM field IDs |

### DCGM Host Engine

| Trigger | Label | Description |
|---------|-------|-------------|
| `:DCGM_hostengine_start` | DCGM - start host engine | Start the DCGM host engine daemon |
| `:DCGM_hostengine_stop` | DCGM - stop host engine | Stop the DCGM host engine daemon |

### CUDA Compilation

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_nvcc` | NVIDIA - compile CUDA program | Compile .cu source for a compute capability |
| `:NV_nvcc_debug` | NVIDIA - compile CUDA program with debug | Compile with host and device debug symbols |
| `:NV_nvcc_version` | NVIDIA - show NVCC version | Print CUDA compiler version |

### Miscellaneous

| Trigger | Label | Description |
|---------|-------|-------------|
| `:NV_bug_report` | NVIDIA - generate bug report | Run nvidia-bug-report.sh |
| `:NV_smi_xml` | nvidia-smi - full XML output | Dump full GPU info as XML |
| `:NV_smi_query_all` | nvidia-smi - full detail query all GPUs | Verbose query of all GPU properties |
