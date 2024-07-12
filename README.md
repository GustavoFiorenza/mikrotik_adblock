This project produces a curated list of active DNS hosts based on known blacklisted address lists.

The problem with most medium and small sized Mikrotik routers is that after adding enough static DNS entries the booting time increases drastically, specially since this is only handled by a single core in RouteOS currently. There are also RAM limitations to keep in mind. The lists, while quite complete, include very old / inexistent hosts and thus the need to curate them.

Currently in order to process the list within a realistic timeframe four worker threads are deployed, splitting the workload onto four sections. Each thread will immediately commit data to the output file.

This intermediary file is then sorted and the final output file is created.

Currently around 76k items are processed from the various lists, the ntire process takes a long time as each host is resolved and then pinged if possible to determine whether to include it or not.

It is entirely possible some hosts may not respond to you, locally, but may be active throughout other portions of the world so the list, in my opinion, should be curated individually for every particular case.
