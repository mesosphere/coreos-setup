# coreos-setup

This repository used to contain some partial scripts for trying to get Mesos
working inside Docker containers on CoreOS. This isn't supported, and doesn't
work particularly well.

[DCOS](https://docs.mesosphere.com/install/awscluster/) Captures all the knowledge that was gained through doing it along with more that has been learned since. It automates a lot of the operational needs around DCOS (Setup a Exhibitor cluster, Setup Mesos-DNS, set DNS resolution to use Mesos-DNS only after Mesos Masters come up and it starts properly resolving recursive DNS queries, etc).

It also handles shipping Mesos binaries to the hosts outside of docker containers, has infrastructure for doing Mesos version upgrades, and running Mesos according to the [Mesos Operation Guide](http://mesos.apache.org/documentation/latest/operational-guide/)


Mesos-slave inside a docker container doesn't work at the moment [MESOS-2183](https://issues.apache.org/jira/browse/MESOS-2183). It will post Mesos 0.23 to a certain extent, although shouldn't be used in production.

There are also a bunch of corellary problems why it shouldn't be used in production:
 - https://github.com/mesosphere/docker-containers/issues/6
 - https://github.com/mesosphere/docker-containers/issues/9
 - https://github.com/mesosphere/docker-containers/issues/17
