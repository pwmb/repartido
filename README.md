# Repartido

`GO Lang`

### Introduction
All the nodes have the freedom to **join** or **leave** the cluster any time.
Every nodes have a complete master and client, in a cluster there must be at-least one master node, user can specify a master node, else the cluster will poll and elect a master.
### Flow
* Whenever a node joins the cluster, it will kick-start the ***master-server-service***.
* Then it will start broadcasting all of its available ***services,*** to the all the other nodes.
* Once all the services are hosted it will query for the elected master node, if there is none a polling service will be called throughout the cluster and one master node will be elected.
* At any arbitrary point there must be one ***active-master-node*** and rest all the ***passive-master-node*** have the identical replicas in-case of any downtime.
* All the ***master-nodes*** will have the option to request for tasks to be **automated**, but their priority will be determined only by the ***active-master-node***, once a batch of tasks/ task is sent to the cluster, its put to the waiting queue of the *master* of the issuer itself, that is later replicated to each of the ***passive-master-node***, based on the priority task will be picked by one of the ***slaves*** and later that might or might not be resolved.
