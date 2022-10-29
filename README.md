# Internet Monitor

Installs Prometheus and Grafana, to monitor http servers. 

## Pre-requisites

Make sure Docker and [Docker Compose](https://docs.docker.com/compose/install/) are installed on your Docker host machine.
## Running

Start with 

`docker-compose up --detach`

## Interesting urls

http://localhost:3030 graphana front end

Username is `admin` and default password is also `admin`.

http://localhost:9090/targets shows status of monitored targets as seen from prometheus - in this case which hosts being monitored.

http://localhost:9090/graph?g0.expr=probe_http_status_code&g0.tab=1 shows prometheus value for `probe_http_status_code` for each host. You can edit/play with additional values. Useful to check everything is okey in prometheus (in case Grafana is not showing the data you expect).

http://localhost:9115 blackbox exporter endpoint. Lets you see what have failed/succeded.