# This folder is meant to be used from the HPC scripts

## Server side

First daemon: `iperf3 -s`
Second daemon: `iperf3 -s -p 5202`


## Client side

First client: `iperf3 -c IP --parallel 10 -i 1 -t 60 -V | grep SUM`
Second client: `iperf3 -c IP -p 5202 --parallel 10 -i 1 -t 60 -V | grep SUM`
