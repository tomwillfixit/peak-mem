# peak-mem

Reports peak memory usage of all PIDS inside a container. This may be useful when debugging which PIDs are using the most memory during container startup.

## Usage

Mount in peak-mem when starting a container.

```
docker run -d -v $PWD/peak-mem:/usr/bin/peak-mem --name rabbitmq rabbitmq
```

Run peak-mem.

```
# docker exec rabbitmq peak-mem

*** Peak Memory Usage per PID ***

[rabbitmq-server] : 2.55469 MB
[epmd] : 3.80078 MB
[beam.smp] : 2765.23 MB
[erl_child_setup] : 2.44531 MB
[sh] : 2.55469 MB

[beam.smp] peak memory usage : 2765.23 MB

```

Disclaimer : This code was written in my spare time and can be used as is.
