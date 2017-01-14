# IOTA-Spammer
An application to contribute to IOTA network efficiency by sending spam transactions.
Optionally, it can also be used to re-broadcast transactions that the node received since the last milestone.


## INSTALLATION
To use this app you'll first need a working (**IOTA IRI node**)[https://github.com/iotaledger/iri].  You'll also need (**node**)[https://nodejs.org] and **npm** (included with node) installed on your system.  

To install, clone this repo, open a terminal to the directory of the cloned repo and type:

`npm install`

Now you are ready to configure and use this tool.

## CONFIGURATION
You can run the application 'out of the box' with a local IRI node, or you can take a choice:

1) Run repeater only, without spammer (REPEATER_ON=true|false).
2) Run spammer only, without repeater (SPAM_ON=true|false).
3) Set the spammers time interval (SPAM_FREQUENCY=90, seconds, deliberate delays between spams).
4) Set your personal spam message and tag (recommended).
5) Set the search depth for 'transactions to approve', default SPAM_DEPTH=5.

You find those parameters declarations in the top section of repeater.js.

## EXECUTION

node spammer.js

node spammer.js 5665 (set the milestone index from botbox)

./spammer.sh        (make sure execution permission flag (`chmod +x ./spammer.sh`) is set!)

./spammer.sh 5665   (with botbox milestone index)

The 'spammer.sh' is a wrapper around the basic command call. It restarts node automatically if an exception occurs and the repeater stopped working. This is likely to happen at some point, because the underlying iota javascript lib and the IOTA ledger are still works in progress.
