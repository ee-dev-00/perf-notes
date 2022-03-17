### Recording

### Stats

Count events for the specified process:

    perf stat -e LLC-loads,LLC-load-misses,LLC-stores,LLC-prefetches -p PID sleep 5

### Events

Show events

    perf list

or

    perf list 'sched:*'