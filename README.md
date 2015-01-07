Factom Command Line Interface
===

Synopsis
---
	factom-cli
		help [command]
			# Print a help message about the command
		mkchain
			-n "name[0];name[1]"
			-e [extid]
			data on stdin
			
		put
			-c [ChainID]	"hex encoded chainid for the entry"
			-e [extid]		"external id for the entry"			# -e may be used multiple times
			-s				"path to the factomclient"			# default: localhost:8083
			data on stdin
		get
			# print some data on an entry/chain

Description
---
factom-cli takes data from the command arguments and stdin and constructs a json message to send to the factomclient.

Examples
---
	# Submit arbitrary data to factom
	echo "Some data to save in factom" | factom-cli put -c <my chainid> -e mydata -e somekey
	
	# Submit a file
	factom-cli put -s "facom.org/demo" -c <my chainid> -e filename <file