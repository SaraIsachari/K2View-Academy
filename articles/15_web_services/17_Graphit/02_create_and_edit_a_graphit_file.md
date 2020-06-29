# Create and Edit a Graphit file

### How Do I Create a New Graphit File?

The following are the steps to create a new Graphit Files:

1. Go to **Project Tree**,  click **Web Services**  > **Resource Files**
2. Right-click **Resource Files** and select **New Graphit File** from the context menu

![](/articles/15_web_services/Graphit/images/01_new_graphit_file.png)

3. The new file is opened , assign a name to the New Graphit File and Save it. **Note**: The file name must start with **gr%** and contain alpha-numeric characters
4. Once the file is saved, it is displayed under as part of the Resources Files under the Project's Web Services componenet

![](/articles/15_web_services/Graphit/images/02_graphit_resource_file.png)



### How Do I Edit a Graphit File?

Once a new Graphit file is created, you can edit it in order to create the required CSV/XML/JSON document structure. 

The Graphit file is structured as a hierarchical representation of nodes, where each node defines a tag or condition in the structure of the resulted CSV, XML or JSON document. 

Each of the nodes can have child nodes and the child nodes can also have child nodes, thus creating nested tags in the resulted document. 

For each of the nodes, node Name, Type and properties can be defined in order to instruct how to generate the result. 

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

