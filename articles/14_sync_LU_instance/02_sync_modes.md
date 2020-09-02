# Sync Modes

## Set Sync Command 
The Fabric **Set Sync** command is used to define the synchronization mode of an instance from source systems. Default value is ON.

SYNTAX: SET SYNC [SYNC MODE];

## Sync Modes
<table style="width: 560px;">
<tbody>
<tr>
<td style="width: 76px;">
<p><strong>Sync Mode</strong></p>
</td>
<td style="width: 146px;">
<p><strong>Description</strong></p>
</td>
<td style="width: 316px;">
<p><strong>When is an Instance Synced?</strong></p>
</td>
</tr>
<tr>
<td style="width: 76px;">
<p>ON</p>
</td>
<td style="width: 146px;">
<p>Run the sync according to the <a href="/articles/14_sync_LU_instance/04_sync_methods.md">Sync method</a>: None, Time Interval, Inherited and Decision Function.</p>
</td>
<td style="width: 316px;">
<ul>
<li>The <a href="/articles/03_logical_units/03_LU_schema_window.md"> LU Schema </a> has changed and is redeployed.</li>
<li>First sync, the instance does not yet exist in Fabric.</li>
<li>Sync the instance according to the predefined Sync method set for each <a href="/articles/06_LU_tables/01_LU_tables_overview.md">LU table</a> and <a href="/articles/07_table_population/01_table_population_overview.md">table population object</a>./li>
</ul>
</td>
</tr>
<tr>
<td style="width: 76px;">
<p>OFF</p>
</td>
<td style="width: 146px;">
<p>Don&rsquo;t sync./p>
</td>
<td style="width: 316px;">
<ul>
<li>Synchronization is not performed, however if the LU instance already exists in Fabric it will bring the existing LU instance data based on the most updated LU Schema definition./li>
<li>If the LU instance does not yet exist in Fabric, the following warning message is displayed:</li>
<li>Instance '&lt;LU Name&gt;:&lt;Instance ID&gt;' was not found and sync is disabled./li>
</ul>
</td>
</tr>
<tr>
<td style="width: 76px;">
<p>FORCE</p>
</td>
<td style="width: 146px;">
<p>Always sync./p>
</td>
<td style="width: 316px;">
<p>Synchronization is performed on every operation on the Fabric LU instance, regardless of the Sync method defined for the LU.</p>
<p>The only exception to this rule is when using a <a href="/articles/14_sync_LU_instance/05_sync_decision_functions.md">Decision function</a>. If the Decision function returns False, the data will not be synced.</p>
</td>
</tr>
</tbody>
</table>

Note that the Sync returns an error message when a source is not available. To change this behavior, use the  ignore_source_exception true](/articles/14_sync_LU_instance/03_sync_ignore_source_exception.md) command.

## Sync ON Protection

When set  on the same LUI and Fabric node, Sync On mode improves the response time of multiple GET requests. For example, executing a stress test by running a Web Service with the same LUI on multiple threads. 
In principle, multiple requests on the same LUI and Fabric node are executed sequentially if they all implement Sync On mode, since each request requires a write lock in the LUI's MicroDB. This means that even when LUI populations are not run, a short check can take a long time before the last GET is successful.
To avoid checking each LUI, Fabric implements Sync On mode only on the first GET request on the LUI. Remaining requests are executed in parallel to the first request when executed in Sync Off mode.
SYNC_PROTECTION can be edited in the config.ini file. The default value is zero. 
Fabric implements Sync On mode only on the first request. If this parameter is set to -1, Sync On protection is disabled and Fabric implements a Sync On for each request.
This parameter can be set in milliseconds. For example, if set to 1000, all Sync requests executed on the same LUI and Fabric node during the 1000ms after the first request, run in Sync On mode. After 1000ms, and until the first GET request on the LUI is completed, Fabric sets the Sync mode to Off.


## Fabric Studio Server Configuration - Force Upgrade Post Deploy Checkbox
The **Force Upgrade Post Deploy** checkbox is defined for each predefined Fabric server in the [Server Configuration](/articles/04_fabric_studio/04_user_preferences.md#what-is-the-purpose-of-the-server-configuration-tab) window.

![image](/articles/14_sync_LU_instance/images/6_2_server_configuration_window.png)

This checkbox defines the Sync mode of the first GET of each LU instance after the LU is deployed to the server:
* If checked, the Sync mode is set to FORCE.
* When unchecked, the Sync mode is set to ON.

**Notes:**
* Checking / unchecking the **Force Upgrade Post Deploy** checkbox impacts the LU only after redeployment of the LU to the checked / unchecked Fabric server. It does not impact retroactively.
* The Sync mode is set to FORCE only for the first GET of each LU instance after redeployment of the LU.  
* The Sync mode is set to FORCE for the first GET of each LU instance even if the **Force Upgrade Post Deploy** checkbox is later unchecked, the LU is redeployed and the instance was not synchronized when the **Force Upgrade Post Deploy** checkbox is still checked.

**Example 1:**
* Set the [Sync Method](/articles/14_sync_LU_instance/04_sync_methods.md) of Customer LU to **None**.
* Get Customer 1.
* Update the source DB for Customer 1. 
* Check the **Force Upgrade Post Deploy** checkbox for Fabric development server and redeploy the Customer LU to this server. 
* Get Customer 1 again. The customer is synchronized and their data is updated, since the  **Force Upgrade Post Deploy** checkbox set the Sync mode to FORCE.
* Update the source DB for Customer 1 again.
* Get Customer 1 again.  This time Customer 1 is **not** synchronized, since the Sync mode is set back to ON for the Customer after their first sync**, initiated after checking the **Force Upgrade Post Deploy** checkbox.

**Example 2:**
* Set the [sync method](/articles/14_sync_LU_instance/04_sync_methods.md) of the Customer LU to **None**.
* Get Customers 1 and 2.
* Update the source DB for Customers 1 and 2.
* Check the **Force Upgrade Post Deploy** checkbox for the Fabric development server and redeploy the Customer LU to this server. 
* Get Customer 2 again. This Customer is synchronized, and their data is updated. 
* Uncheck the **Force Upgrade Post Deploy** checkbox for the Fabric development server and redeploy the Customer LU to this server. 
* Get Customers 1 and 2 again: 
  * Customer 1 is synchronized, since this is the first GET of this customer after checking the **Force Upgrade Post Deploy** checkbox, even though this checkbox was later unchecked.
  * Customer 2 is **not** synchronized, since it has already been synchronized after checking the **Force Upgrade Post Deploy** checkbox.

* Click for more information about the Get Instance Fabric Command.

## Get Sync Mode
The Fabric UserCode class holds the method that returns the sync mode set for the current session: 

**public static String getSyncMode();**

This method can be invoked by a [Decision function](/articles/14_sync_LU_instance/05_sync_decision_functions.md). For example:
If the sync mode is FORCE, then return True to sync the instance. Else, do not sync the instance.

Click to open the list of Fabric APIs: **http://[Fabric IP address]:3213/static/doc/user-api/index.html**

## Always Sync
Always Sync mode enables synchronizing an attached LUI when running select queries on the LUI. The sync of the LUI is executed before the execution of the select queries.
To define Always Sync mode either:
   - Set the ALWAYS_SYNC parameter of the [config.ini](/articles/02_fabric_architecture/04_fabric_commands.md#fabric-commands) file to True. Default value is false.
   - Run the **SET ALWAYS_SYNC=TRUE** [Fabric command](/articles/02_fabric_architecture/04_fabric_commands.md#fabric-commands) to override the **Always Sync** mode and set it to True on the session's level. 

[![Previous](/articles/images/Previous.png)](/articles/14_sync_LU_instance/01_sync_LUI_overview.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/14_sync_LU_instance/03_sync_ignore_source_exception.md)

