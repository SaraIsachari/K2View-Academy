# Create and Edit a Graphit file

### How Do I Create a New Graphit File?

1. Go to **Project Tree**, click **Web Services** > **Resource Files**. 
2. Right click **Resource Files** and select **New Graphit File**.  
![](/articles/15_web_services/Graphit/images/01_new_graphit_file.png)

3. Assign a **name** to the new Graphit file and **Save** it. Note that the filename must have a **gr%** prefix and contain alpha-numeric characters. Once the file is saved, it is displayed under the project's Web Services folder under Resources files.

![](/articles/15_web_services/Graphit/images/02_graphit_resource_file.png)



### How Do I Edit a Graphit File?

Once a new Graphit file is created, you can edit it to create the required CSV / XML / JSON document structure. A Graphit file is structured as a hierarchical representation of nodes, where each node defines a tag or condition in the structure of the CSV, XML or JSON document. 
Nodes can have child nodes, and child node can have child nodes, whereby creating nested tags in the resulting document. When creating a document the Node Name, Type and Properties can be defined for  each node. 

![](/articles/15_web_services/Graphit/images/03_edit_graphit_file.png)

Following are the hierarchical structure options:

- To create a **parent node**, click the ![](/articles/15_web_services/Graphit/images/04_plus.png)  button. A new node at the same level is created under the original node.
- To create a **child node**, click the ![](/articles/15_web_services/Graphit/images/05_arrow.png) button. A new child node is created under the parent node.
- To delete a node, click the ![](/articles/15_web_services/Graphit/images/06_trash_bin.png) icon on the node level. The node is deleted.
- To change the node location inside the hierarchy, **click** and **drag** the desired node (using the ![](/articles/15_web_services/Graphit/images/07_hamburger.png icon) to another location.

### Assigning Name to a Node

Every node must be assigned a name in order to appear in the output document.

If no name is assigned, the node will not appear in the output. Node without name may be used for internal purposes.

To assign name to a node, set your mouse on the left side of the frame created for the node, and write the node name. This name will be the tag name, if this node is presented in the output document

[![Previous](/articles/images/Previous.png)](/articles/15_web_services/Graphit/01_graphit_overview.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/03_graphit_node_types_.md)

