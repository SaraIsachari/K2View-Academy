# **Fabric Batch Overview** 
The Batch process is a Fabric utility that can be used to run multiple commands on a population's instances, regardless of its size or type. 

The Batch process is used to trigger the following:
- Sync instances, to perform multiple syncs on a set or group of LUIs.
- Broadway flow, to run multiple flows.
- Publish changes, to republish data using the CDC notification mechanism.


# **Fabric Batch Features**
The Batch process enables:
- Efficient distribution of jobs between nodes.
- Dynamically changing the configuration of the work balance between nodes during execution phases.
- Monitoring an instance's synchronization progress (batch sync) at cluster, DC or node levels.
- Recovery of a process due to a failure during the process. For example, nodes that are down.
- Stopping and resuming the migration process (LUI synchronization).
- Tracking processes at an entity level. For example, timing, duration, handling nodes or failure management.



[![Previous](/articles/images/Previous.png)](/articles/20_jobs_and_batch_services/06_jobs_configuration.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/20_jobs_and_batch_services/08_batch_process_commands.md)