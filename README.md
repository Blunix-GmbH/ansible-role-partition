# Partition Ansible Role (ansible-role-partition) from Blunix GmbH

This Ansible role partitions and mounts disks according to `partition_disks`, used across many hosts to prepare data volumes (GitLab, backup, logging, web data, etc.).

The Ansible Role is written and actively maintained by <a href="https://www.blunix.com" target="_blank">Blunix GmbH</a>.
It is used in the Blunix <a href="https://www.blunix.com/linux-managed-hosting.html" target="_blank">Linux Managed Hosting</a> Stack.
Its usage is documented at our <a href="https://www.blunix.com/manual" target="_blank">Linux Managed Hosting Documentation</a>.


## Features

- Partitions and formats specified block devices.
- Creates and mounts the target directories with desired ownership and mode.
- Supports per-disk mount and mkfs options.


## Requirements

- Ansible: **>= 2.20.0**
- Managed operating systems: Debian **bullseye**



## Role variables, inventory and example playbook

Define disks to partition/mount in inventory via `partition_disks`. Each item sets the device, mountpoint, filesystem options, and ownership.

### Example files under `example/`

- <a href="https://github.com/Blunix-GmbH/ansible-role-partition/blob/main/example/inventory/group_vars/util_backup.yml" target="_blank">`example/inventory/group_vars/util_backup.yml`</a> — disk definition for backup host.
- <a href="https://github.com/Blunix-GmbH/ansible-role-partition/blob/main/example/play.yml" target="_blank">`example/play.yml`</a> — play applying the role to util_backup.

Add more disks in host/group vars for GitLab, logging, NFS, or web data servers as needed.


## Author Information

Blunix GmbH Berlin  

`root@Linux:~# Support | Consulting | Hosting | Training`

Blunix GmbH provides 24/7/365 Linux emergency support and consulting, Service Level Agreements for Debian Linux managed hosting using Ansible Configuration Management as well as Linux trainings and workshops.

Learn more at <a href="https://www.blunix.com" target="_blank">https://www.blunix.com</a>.

## Contact Information

Click here to see our <a href="https://www.blunix.com/#contact" target="_blank">Contact Information</a>.

For bug reports and feature requests, please open an issue in this repository’s GitHub issue tracker.


## License

Apache-2.0

Please refer to the `LICENSE` file in the root of this repository.

### Tests

The directory `test/` contains an example `play.yml` as well as `inventory/group_vars/`, if applicable to the role. the script `example/run-tests.sh` creates a IONOS cloud instance with terraform, uses the example inventory and playbook to run the role and then run pytest tests located in `example/tests/`. Destroy the terraform using `./run-tests.sh -d`.
