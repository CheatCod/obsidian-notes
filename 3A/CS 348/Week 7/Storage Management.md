Single most important metric in database processing is (oftentimes) the number of disk I/O's performed

# Random Disk Access

Seek time + rotational delay + transfer time

# Sequential Disk Access

Seek time: 0

Rotational delay: 0

# Consequences:

All about reducing IOs.

Cached block from stable storage in memory
Updated memory block is flushed back to disk
Sequential is much faster than random

# Performance tricks:

- Disk layout strategy, keep related things close
- Prefetching
- Prallel I/O: multiple disk heads
- Disk scheduling:
- Track buffer

# Record Layout
Record = row in table

Fixed-format records:
- Fixed-length fields only or
- possible variable-length fields