# web-site-DR-solution
the web site HA architecture within a region further consists of web tier HA, app tier HA and DB tier HA. web tier HA and app tier HA could be achieved by applying **ELB (ALB/NLB for different scenarios) and auto-scaling** to ditribute workloads among different worker instances. while DB tier HA could be achieved by applying **multi-AZ feature** (deploy standby instances in other AZs within the same region, the data replication mechanism between primary and standy is synchronous).

however, this level of DR design cannot cover the case when all the region encounter a fail over. as result, in order to achive the across-region DR, we need to further design a solution that meets the requirement, which is exactly the objective of this doc.

