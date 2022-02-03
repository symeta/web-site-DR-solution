# web-site-DR-solution
the web site HA architecture within a region further consists of web tier HA, app tier HA and DB tier HA. web tier HA and app tier HA could be achieved by applying **ELB (ALB/NLB for different scenarios) and auto-scaling** to ditribute workloads among different worker instances, achieve flexible scalability as well. while DB tier HA could be achieved by applying **multi-AZ feature** (deploy standby instances in other AZs within the same region, the data replication mechanism between primary and standy is synchronous).

however, this level of DR design cannot cover the case when the entire region encounter a fail over. as result, a further solution dealing with the cross-region DR  needs to be designed, which is exactly the objective of this blog.

this blog discusses
1. the migration of exisiting enterprise domain name, and use route53 as well as ELB to achieve cross-region web site entrance automatic switch over;
2. comparison between DMS and read-replica under cross-region DR scenario.
