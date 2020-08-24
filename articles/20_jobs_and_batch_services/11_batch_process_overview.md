# **Fabric Batch Overview** 
The Batch process is a Fabric utility that can be used to run multiple commands on a population's instances, regardless of its size or type. 

The Batch process is used to trigger the following:
- [Sync instances](/articles/14_sync_LU_instance/01_sync_LUI_overview.md), to perform multiple syncs on all (or a subset of) instances for a specific Logical Unit. This process is also referred to as the Migration Process, handled by the *migrate* command.
- [Broadway flow](/articles/19_Broadway/01_broadway_overview.md), to run multiple flows.
- Publish changes and republish data using the [CDC](/articles/18_cdc_and_search/02_cdc_messages.md) notification mechanism.


# **Fabric Batch Features**
Fabric's integrated Batch process provides the following advantages to ensure the smooth execution of heavy-resources demanding processes:
- Efficient distribution of jobs between nodes.
- Dynamic adjusting of work balance configuration between nodes during execution phases.
- Monitoring of instances' synchronization progress (batch sync) at cluster, DC or node levels.
- Process failure recovering. (e.g non-responding nodes).
- Stopping and resuming of the migration process (LUI synchronization).
- Process tracking at entity level. (e.g. timing, duration, handling node or failure management).

# **Fabric Batch Use Cases**

**Instances Migration**

```BATCH LUT ('LUI','LUI2','LUI3','LUI4') FABRIC_COMMAND="sync_instance LUT.?" with ASYNC='true';```

**Broadway Flows Execution**

```BATCH LUT FABRIC_COMMAND="broadway LUT.SampleFlow SampleIID=?" with async=true;```

**CDC Republish**

```BATCH LUT from fabric FABRIC_COMMAND="cdc_republish_instance OracleLU.?" with async=true;```



[![Previous](/articles/images/Previous.png)](/articles/20_jobs_and_batch_services/10_jobs_and_batches_affinity.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/20_jobs_and_batch_services/12_batch_sync_commands.md)