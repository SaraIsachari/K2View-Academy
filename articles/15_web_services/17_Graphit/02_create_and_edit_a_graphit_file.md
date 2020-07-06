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

**Hierarchical Structure Options**

- Click ![](/articles/15_web_services/Graphit/images/04_plus.png)  **Parent Node** to create a new parent node under the original node on the same level.
- Click ![](/articles/15_web_services/Graphit/images/05_arrow.png)  **Child Node** to create a new child node under the parent node.
- Click ![](/articles/15_web_services/Graphit/images/06_trash_bin.png) **Delete** to delete a node on the node level.  
- Click ![](/articles/15_web_services/Graphit/images/07_hamburger.png icon) and drag a node to another location in the hierarchy.

### Assigning a Name to a Node
To be displayed in the generated document nodes must have a Tag Name. Nodes without tag names can be used for internal purposes.
To assign a Tag Name to a node, place your mouse on the left side of the node's frame and type in the Name.  

[![Previous](/articles/images/Previous.png)](/articles/15_web_services/Graphit/01_graphit_overview.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/03_graphit_node_types_.md)

