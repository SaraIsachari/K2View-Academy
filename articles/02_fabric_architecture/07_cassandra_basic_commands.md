# Cassandra Basic Commands

Fabric uses the Cassandra DB as a storage layer. CQL commands can be run to check Cassandra tables on [Fabric keyspaces](/articles/02_fabric_architecture/06_cassandra_keyspaces_for_fabric.md).

### Login Cassandra DB

Use the following command to connect the Cassandra DB from the Cassandra server:

<p><strong>cqlsh -u &lt;username&gt; -p &lt;password&gt; &lt;ip_address&gt;</strong>;</p>

Note that if the **ip_address** is not populated, the login command connects to the local host of the Fabric server.

### Cassandra Useful Commands

The following table holds useful **cqlsh** commands.

For more information, see https://docs.datastax.com/en/cql-oss/3.x/cql/cql_reference/cqlCommandsTOC.html.

<table>
<tbody>
<tr>
<td width="200pxl">
<p><strong>Command Name</strong></p>
</td>
<td width="350pxl">
<p><strong>Command Description</strong></p>
</td>
<td width="350pxl">
<p><strong>Examples</strong></p>
</td>
</tr>
<tr>
<td width="200pxl">
<p>HELP</p>
</td>
<td width="350pxl">
<p>Get information about the list of Cassandra commands or a specific Cassandra command. </p>
</td>
<td width="350pxl">
<ul>
<li>Help describe;</li>
</ul>
</td>
</tr>
<tr>
<td width="200pxl">
<p>USE</p>
</td>
<td width="350pxl">
<p>Move into a specific&nbsp;keyspace</p>
</td>
<td width="350pxl">
<ul>
<li>Use k2view_customer;</li>
</ul>
</td>
</tr>
<tr>
<td width="200pxl">
<p>DESCRIBE (shorthand: DESC)</p>
</td>
<td width="350pxl">
<p>Describe Cassandra objects.</p>
<p>Note that Describe command is run in a keyspace and returns information about the objects in the keyspace.</p>
<p>&nbsp;For more information, see</p>
<p><a href="https://docs.datastax.com/en/cql-oss/3.x/cql/cql_reference/cqlshDescribe.html">https://docs.datastax.com/en/cql-oss/3.x/cql/cql_reference/cqlshDescribe.html</a></p>
</td>
<td width="350pxl">
<ul>
<li><strong>desc keyspaces</strong>- returns the list of the keyspaces in the Cassandra cluster.</li>
<li><strong>desc tables</strong>- returns the list of Cassandra keyspaces and the related tables of each keyspace</li>
<li><strong>desc schema</strong>- returns the details for all non-system objects in the Cassandra cluster.</li>
<li><strong>desc keyspace &lt;keyspace name&gt;</strong> - returns the details for the specified keyspace and objects it contains.</li>
</ul>
</td>
</tr>
<tr>
<td width="200pxl">
<p>EXIT/QUIT</p>
</td>
<td width="350pxl">
<p>Exit Cassandra</p>
</td>
<td width="350pxl">
<p>&nbsp;</p>
</td>
</tr>
</tbody>
</table>


#### Run CQLSH on Local Cassandra 

When working on the local Fabric server installed on a Windows machine,  you must install Python 2.7.x to run the **cqlsh** on your local Cassandra server. Add the Python to the PATH environment variable on your Window machine, and open the command line window from the following Windows directory: **C:\k2view\[Fabric version]\apache-cassandra-3.11.4\bin**.

Login to Cassandra from the command line (cmd) window:

<p><strong>cqlsh -u &lt;username&gt; -p &lt;password&gt;</strong>;</p>

Notes:

- Python 2.7.x is not part of the Fabric Studio installation. 
- Use **cassandra** as user and password when connecting the local Cassandra server.

Alternatively, you can do the following steps:

- Run queries on Cassandra inside Fabric server using [cql command](/articles/02_fabric_architecture/04_fabric_commands.md#run-queries-on-cassandra).
- Define a Cassandra [DB interface](/articles/05_DB_interfaces/04_creating_a_new_database_interface.md) on Fabric Studio and set the host to localhost. Set the user and password to **cassandra**. Then open the [Query Builder](/articles/11_query_builder/01_query_builder_overview.md) to view the list of Cassandra keyspaces and run SQL queries on Cassandra tables. 

[![Previous](/articles/images/Previous.png)](/articles/02_fabric_architecture/06_cassandra_keyspaces_for_fabric.md)




