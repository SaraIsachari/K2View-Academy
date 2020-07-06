# Graphit Node Types

Node Type options define how content is structured and how a tag is presented in an output document. By default, when created, nodes are not assigned a Type or Property.

**Node Types Options**
<table>
<tbody>
<tr>
<td valign="top" width="300pxl">
<p><strong>&nbsp;Node Type</strong></p>
</td>
<td valign="top" width="600pxl">
<p><strong>Description</strong></p>
</td>
</tr>
<tr>
<td valign="top" width="300pxl">Field</td>
<td valign="top" width="600pxl">Basic node type. Defines the node as a tag in XML / JSON format<a href="https://github.com/k2view-academy/K2View-Academy/blob/KB_DROP2_15a_Graphit_Merav/articles/15_web_services/Graphit/images/08_node_type_field.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/k2view-academy/K2View-Academy/raw/KB_DROP2_15a_Graphit_Merav/articles/15_web_services/Graphit/images/08_node_type_field.png" alt="" /></a>.</td>
</tr>
<tr>
<td valign="top" width="300pxl">Function</td>
<td valign="top" width="600pxl">Runs the code to determine the value of the node. Note that the code must be written in JavaScript.&nbsp;</td>
</tr>
<tr>
<td valign="top" width="300pxl">SQL and Non-prepared SQL</td>
<td valign="top" width="600pxl">Defines how an SQL statement retrieves information from Fabric or other database interfaces.&nbsp;<br />Enter the SQL statement manually or, hover over SQL or Non-prepared SQL fields and click&nbsp; .&nbsp;<br />Note that if the database is not a Fabric database, the Interface Name must be defined as a Node Property the&nbsp;<a href="https://github.com/k2view-academy/K2View-Academy/blob/KB_DROP2_15a_Graphit_Merav/articles/15_web_services/Graphit/04_graphit_node_properties.md">Node Properties</a>.<br />If the Query Builder option is selected, the executed query is copied into the Graphit implmentation. Fields can be expanded automatically according to the SQL statement defined in the Query Builder.&nbsp;<br />During runtime, the SQL query is executed and the results can be used in the nested nodes. The SQL Type also enables looping results and executing nested codes on each returned row.&nbsp;&nbsp;<br />Note that it is recommended to set the SQL Statement Type to SQL to use a prepared statement and prepared binding.&nbsp;<br />To build an SQL statement for every call, set the query Type to Non-prepared SQL. For example, to build dynamic SQL, Select X,Y from $table name.</td>
</tr>
<tr>
<td valign="top" width="300pxl">String</td>
<td valign="top" width="600pxl">Concatenates two or more values.&nbsp;</td>
</tr>
<tr>
<td valign="top" width="300pxl">Condition</td>
<td valign="top" width="600pxl">Builds IF-ELSE statements which should include a condition. The nested nodes are / not executed according to the result of the condition.&nbsp;</td>
</tr>
<tr>
<td valign="top" width="300pxl">Group&nbsp;</td>
<td valign="top" width="600pxl">Groups several elements. Mainly used with Condition nodes.</td>
</tr>
<tr>
<td valign="top" width="300pxl">Collect</td>
<td valign="top" width="600pxl">Iterates multiple data sets into one unified array.&nbsp;</td>
</tr>
<tr>
<td valign="top" width="300pxl">Raw</td>
<td valign="top" width="600pxl">Presents data as output without manipulation. For example, a header for XML format.&nbsp;</td>
</tr>
</tbody>
</table>

#### Field
The basic node type that defines the node as a tag in XML / JSON format![](/articles/15_web_services/Graphit/images/08_node_type_field.png).

#### Function
Runs the code to determine the value of the node. Note that the code must be written in JavaScript. ![](/articles/15_web_services/Graphit/images/09_node_type_function.png)

#### SQL and SQL Non-prepared
Defines how an SQL statement is created to retrieve information from either a Fabric or another database interface. Note that if the interface is not Fabric, the Interface Name must be specified as a Node Property, as described in the [Node Properties](/articles/15_web_services/Graphit/04_graphit_node_properties.md) section. 
![](/articles/15_web_services/Graphit/images/12_node_type_sql.png) 

Either enter the **SQL Statement** manually or hover over the **SQL** or **sql Non-prepared** fields and click ![](/articles/15_web_services/Graphit/images/10_DB.png).   

If you have selected the Query Buider option:

- The executed query on the Query Builder is copied into the Graphit implementation. 

- Fields can be expanded automatically according to the SQL Statement defined in the Query Builder. ( required the you approval upon a message). 

  ![](/articles/15_web_services/Graphit/images/11_create_fields.png)

During runtime, the SQL is executed and the results can be used in the nested nodes. The SQL Type also enables looping results and executing nested nodes on each returned row:

![](/articles/15_web_services/Graphit/images/13_node_type_sql2.png)

**Note**, it is recommended to set the SQL Statement Type to **SQL** in order to use a prepared statement and parameter binding. However, to build a SQL for every call. For example, build a dynamic SQL (‘select X, Y from $table name’)—set the type of the query to ‘sql non-prepared’

#### String

**String** nodes can be used to concatenation two or more values.

![](/articles/15_web_services/Graphit/images/14_node_type_string.png)

#### Condition

Enable building **if-else** statements which should include a condition, and according to the condition result, nested nodes will be executed or not

![](/articles/15_web_services/Graphit/images/15_node_type_condition.png)

#### Group

Node type **Group**, allows grouping of several elements together. It is mainly used in conjunction with **Condition** node type

![](/articles/15_web_services/Graphit/images/16_node_type_group.png)

#### Collect

Node type **Collect**, allows iteration over multiple data sets to unify them into a single array

![](/articles/15_web_services/Graphit/images/17_node_type_collect.png)

#### Raw

Node type **Raw**, present the data as output with no manipulation. For example header for xml format

![](/articles/15_web_services/Graphit/images/18_node_type_raw.png)

[![Previous](/articles/images/Previous.png)](/articles/15_web_services/Graphit/02_create_and_edit_a_graphit_file.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/04_graphit_node_properties.md)

