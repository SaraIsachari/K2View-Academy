# Graphit Node Properties

### What are Node Properties?

Node Properties are additional instructions that can be given for each node, for example, how to format a number, what database to query, or if the node is active or disabled. 

To assign a property to a node, Click the right side  **(+)** sign . Assign the required property from the drop down menu. 

**Note**, for each of the listed properties, there is a short description associated to it in the drop down menu:

![](/articles/15_web_services/Graphit/images/19_node_properties_menu.png)

Following are the availble Node Properties:

#### Session Provider

The Node property **sessionProvider**, defines which interface should be used for a query. This property should be defined each time a node is defined as **sql** or **sql non-prepared** and the database to be queried is not Fabric itself. 

**Note**, this property affects the node and all its child nodes

![](/articles/15_web_services/Graphit/images/13_node_type_sql2.png)

#### Nice

The Node property **nice**, defines whether the output format will be formatted in a “nice” layout. Once set to **true**,  every tag is printed in a new line and indent. This property affects the specified node and all of its child nodes. 

![](/articles/15_web_services/Graphit/images/20_node_properties_nice.png)

