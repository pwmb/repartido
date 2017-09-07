# Repartido

`GO Lang` `HLD`

### Introduction
All the nodes have the freedom to **join** or **leave** the cluster any time.
Every nodes have a complete master and client, in a cluster there must be atleast one master node, user can specify a master node, else the cluster will poll and elect a master.
### Flow
* Whenever a node joins the cluster, it will kick-start the ***master-server-service***
* Then it will start broadcasting all of its available ***services,*** to the all the other nodes
* Once all the servces are hosted it will query for the elected master node, if there is none a polling service will be called throughout the cluster and one master node will be elected
* At any arbitrary point there must be one ***active-master-node*** and rest all the ***passive-master-node*** have the identical replicas in-case of any downtime.
