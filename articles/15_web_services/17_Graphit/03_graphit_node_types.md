# Graphit Node Types

The Node type options, define the way the content is constructed and the presentation  of the respective tag in the output document. By default, the created nodes are not assigned any type or property.

Following are the available Node types:

#### Field

Node type **Field** is the simplest type of a node – it turns the node to a tag in the XML/JSON

![](/articles/15_web_services/Graphit/images/08_node_type_field.png)

#### Function

Node type **Function** is used to run code in order to determine the value of the node. **Note**, The code should be written in java script

![](/articles/15_web_services/Graphit/images/09_node_type_function.png)

#### SQL and SQL non-prepared

Node types **sql** and **sql non-prepared** provide a way to write an SQL statement to retrieve information from either Fabric or from any other database interface. 

**Note**, If the interface is other than Fabric, the interface name should be specified as a node property, as described in the [Node Properties](/articles/15_web_services/Graphit/04_graphit_node_properties.md) section. 

![](/articles/15_web_services/Graphit/images/12_node_type_sql.png)

You can either enter the SQL statement manually or by selecting the ![](/articles/15_web_services/Graphit/images/10_DB.png)  icon (appear when hovering on the **sql** or  **sql** non-prepared ). 

If you have selected the Query Buider option:

- The executed query on the query builder is than copied into the Graphit implementation 

- Fields can be expanded automatically according to the sql statement defined in the Query Builder. ( required the you approval upon a message). 

  ![](/articles/15_web_services/Graphit/images/11_create_fields.png)

At run time, the SQL will be executed and the results can be used in the nested nodes. SQL type, also allows looping on all results and execution of nested nodes for each of the returned rows:

![](/articles/15_web_services/Graphit/images/13_node_type_sql2.png)

**Note**, it is recommended to set the ‘type’ of SQL statements to **sql** in order to use a prepared statement and parameter binding, however, to build a SQL for every call—for example, build a dynamic SQL (‘select X, Y from $table name’)—set the type of the query to ‘sql non-prepared’

#### String

Node type **String** , allows concatenation of two or more values

![](/articles/15_web_services/Graphit/images/14_node_type_string.png)

#### Condition

Node type **Condition**, allows building “if-else”  statements. Statements should include a condition, and according to the condition result, nested nodes will be executed or not

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

