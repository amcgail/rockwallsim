Ideas which have been gestating for a while.

The way the hardware works here is each block is connected to one of the ones next to it, and can only communicate with this block.
The goal is to make amazing animations and entertainment.
The problem is the latency. With the microprocessors (mid-range PICs) embedded in each block running EUSART communication at ~10kbps to 100kbps to the next, and each message having to go through all others before it, that's anywhere from about .2 seconds per command to 2 seconds per command.
This is not to mention that the latency will be different depending on which square you're sending the message to, there being anywhere from a 400us to 4ms square-to-square latency.
Each square individually can operate and change its color without messages, so impressive animations can still be created, but it takes some extra effort.

These facts, coupled with the size and nature of the construction of this project (the budget being somewhere around $3,000), this simulation will act as a tool to convince possible investors (namely myself) of the quality of this idea.
