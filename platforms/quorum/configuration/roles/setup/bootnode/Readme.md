[//]: # (##############################################################################################)
[//]: # (Copyright Accenture. All Rights Reserved.)
[//]: # (SPDX-License-Identifier: Apache-2.0)
[//]: # (##############################################################################################)

## ROLE: setup/bootnode
This role installs the bootnode binary if it doesn't exist

### Tasks

1. Check bootnode
This task check if bootnode is already installed or not

stat: This module checks if bootnode is installed or not with path variable.

Output Variables
bootnode_stat_result: This variable stores the info on availibility on bootnode binary
2. Copy bootnode binary to destination directory
This task will copy bootnode binary to destination directory

copy: This module copies the bootnode binary which is build in the above task and paste it in bin directory

when: It runs when bootnode_stat_result.stat.exists == False, i.e. when bootnode is not installed and network.config.consensus == 'ibft'.