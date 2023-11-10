# Solace Management Tools with SEMP
---

This repository has python Scripts for provisioning and managing [Solace PubSub+ event broker](https://solace.com/products/event-broker/)  using [SEMPv2](https://docs.solace.com/Admin/SEMP/Using-SEMP.htm) protocol.

# Pre Requsites
The scripts in this repository require the followig:
- Python 3.6 or better
- The following Python Modules:
  - datetime
  - json
  - glob
  - pandas
  - pathlib
  - requests
  - shutil
  - urllib
  - zipfile
- Solace event broker version 10.0 or better

# Directory Organization
| File/Folder | Description 
| -- | -- 
| README.md | This file 
| [common](/common/) | Common Python modules used by all scripts 
| [config](/config/) | Config files used by all scripts
| [docs](/docs/) | Documentation, Notes
| [input](/input) | Input file required for some scripts
| [logs](/logs/) | Logs (unused now)
| [output](/output) | Outputs generated from the scripts
| [private](/private/) | Private config and input files that are NOT pushed to GitHub
| [scripts](/scripts/) | Python scripts 
| [templates](/templates) | Tempates used by some scripts
| [tmp](/tmp) | Temporary files not pushed to Github

# Config Files
All scripts take in this repository take a config file that has the broeke access info, default values for many configurations, etc. 

# Scripts

1. [Get VPN Config](/docs/get-vpn-config.md)
	
	This script capturs the entire Solace message service config and creates a local repository. This can be used for backing up config or to promote it to another environment later.

1. [Apply VPN Config](/docs/apply-vpn-config.md)

	This script takes config repository generated by Get VPN Config and clones it on same or different Solace PubSub+ broker. This can be used for promoting VPN config from one environment to another.

1. [Create Queues](/docs/create-queues.md)

	This script takes in an input file with list of Queues to create or update a batch of Queues with common properties.

1. [Move or copy messages across Queues](docs/move-messages.md)

	This script can copy or move messages from one Queue to anothe Queue.

---
ramesh.natarajan@solace.com
