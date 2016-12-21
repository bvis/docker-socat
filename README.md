# TCP Socat

Provides the possibility of cat a TCP connection to a defined PORT.

## Use cases

If you want to export something from the Docker API in a service this can be useful.

For example it comes with default values to expose the `docker_gwbridge`.

Imagine you are exposing the "metrics" endpoint that comes with docker 1.13 in the 4999 port.

```bash
$ docker run -d --name socat-test -p 4998:4999 localhost:5000/basi/socat:v0.1.0
$ curl localhost:4998/metrics
# HELP engine_daemon_container_actions_seconds The number of seconds it takes to process each container action
# TYPE engine_daemon_container_actions_seconds histogram
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.005"} 1
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.01"} 1
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.025"} 1
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.05"} 1
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.1"} 1
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.25"} 1
engine_daemon_container_actions_seconds_bucket{action="changes",le="0.5"} 1
...
```
