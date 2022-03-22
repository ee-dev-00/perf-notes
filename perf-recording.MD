### Stats

Count events for the specified process:

    perf stat -e LLC-loads,LLC-load-misses,LLC-stores,LLC-prefetches -p <PID> sleep 5

### Recording

Profile by CPU with frequency (-g from 4.11 kernel)

    sudo perf record -F 10000 -g -p 5574 sleep 1

Profile by CPU for docker container

    perf record -F 99 -e cpu-clock --cgroup=docker/1d567f4393190204...etc... -a -- sleep 10

Profile by cache-misses

    perf record -e L1-dcache-load-misses -c 10000 -g -p <PID> -- sleep 5

### Report

Show data with stacktraces:

    perf report -n --stdio

### Events

Show events

    perf list

or

    perf list 'sched:*'

### Tracing

Add a tracepoint for the kernel tcp_sendmsg() function entry ("--add" is optional)

    perf probe --add tcp_sendmsg

### Cache profiling

Record cacheline events (Linux 4.10+):
    
    perf c2c record -a -- sleep 10

Report cacheline events from previous recording (Linux 4.10+):

    perf c2c report