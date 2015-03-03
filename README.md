Factom Command Line Interface
===

Synopsis
---
	factom-cli [options] [subcommand]
		-s [server]				"address for the api server"
		-w [wallet]				"address for the wallet"
		
		balance
			ec					"entry credit balance of 'wallet'"
			factoid				"factoid balance of 'wallet'"

		buy
			amt #n				"buy n entry credits for 'wallet'"

		fatoidtx [dest] [amt]	"create and submit a factoid transaction"

		get						"not yet defined"

		help [command]			"print help message for the sub-command"

		mkchain [opt] [name]	"create a new factom chain with 'name'. read"
								"the data for the first entry from stdin"
			-e externalid		"externalid for the first entry

		put						"read data from stdin and write to factom"
			-e [externalid]		"specify an exteral id for the factom entry. -e" 								"can be used multiple times"
			-c [chainid]		"spesify the chain that the entry belongs to"
			
		
			
			
Description
---
factom-cli takes data from the command arguments and stdin and constructs a json message to send to the factomclient.

Examples
---
	# Submit arbitrary data to factom
	echo "Some data to save in factom" | factom-cli put -c [chainid] -e mydata -e somekey
	
	# Submit a file
	factom-cli -s "facom.org/demo" put -c [chainid] -e filename <file
	
	factom-cli balance ec
	factom-cli factoidtx [wallet] 100