### Recording

### Stats

Count events for the specified process:

    perf stat -e LLC-loads,LLC-load-misses,LLC-stores,LLC-prefetches -p PID

### Events

Show events

    perf list

or

    perf list 'sched:*'