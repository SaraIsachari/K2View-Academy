# Broadway Flow - Linking Actors

**A Broadway Flow** is a main Broadway object that represents a business process. A flow has several [Stages](16_broadway_flow_overview.md) where each Stage includes one or more [Actors](03_broadway_actor.md). Stages are executed consecutively from left to right whereas the Actors in each Stage of the flow are executed top-down.

Each actor has [data input and output parameters](03_broadway_actor_window.md#actors-inputs-and-outputs). Input parameters can be populated  by either a:

- **Link**, which gets an input value as an input parameter from another Actor.
- **Const**, a constant value that is set for the parameter.
- **External**, which gets an input value as a parameter from an external process that executes the Broadway flow.

The output of a source Actor can be linked to the input of a target Actor that runs after the source Actor.

Note that an Actor can only be linked to input parameters with Population Type = **Link**.

**Example 1: Valid Link**

Two **Const** Actors are linked to a **DbCommand** Actor and send input for a DB query. 

![link-example1](images/valid_link_example.png)

This link is valid since the source Const Actors run before the target DbCommand Actor.

**Example 2: Invalid Link**

A **Const** Actor named FileName sends the file name as a parameter to the **FileRead** Actor and the source **Const** Actor runs **after** the target FileRead Actor:

![link-example2](images/invalid_link_example.png)

## Link Object Properties

A link holds the following settings:

<table width="900pxl">
<tbody>
<tr>
<td valign="top" width="300pxl"><img src="images/99_20_link_attributes.PNG" alt="Link properties" /></td>
<td valign="top" width="600pxl">
<ul class="unchanged rich-diff-level-one">
<li class="unchanged">
<p class="unchanged"><strong>From (source) parameters</strong>, From Actor, From Parameter and From Parameter Type. These parameters are read-only parameters and cannot be edited.</p>
</li>
<li class="unchanged">
<p class="unchanged"><strong>To (target) parameters</strong>, To Actor, To Parameter and To Parameter Type. These parameters are read-only and cannot be edited. Note that Broadway attempts to handle the differences between the source and target types. For example: if the source type is Integer and the target type is String, then Broadway casts the source integer to a String.</p>
</li>
<li class="unchanged">
<p class="unchanged"><strong>Link Type</strong>, can be edited to set one of the following link types:</p>
<ul class="unchanged">
<li class="unchanged">
<p class="unchanged"><strong>Value</strong>, (default option). Sends the value of the parameter.</p>
</li>
<li class="unchanged">
<p class="unchanged"><strong>Iterate</strong>, opens a loop on the transferred parameter. When set, the link line is displayed as a double-dashed line. Note that if an array is linked to an output with a single element of the same type - for example, linking an array of string to a string output - the link is created automatically with an <strong>Iterate</strong> link type.</p>
<p class="unchanged">[Click for more information about handling loops.]</p>
</li>
<li class="unchanged">
<p class="unchanged"><strong>First</strong>, sends the first value of the parameter. For example, sends the first record of the result set.</p>
</li>
</ul>
</li>
<li class="unchanged">
<p class="unchanged"><strong>Varargs</strong>&nbsp;(variable arguments). When set to ON, the target Actor accepts an arbitrary number of values by updating the target parameter to an array and linking each source parameter to a different element in the array. This can be useful when the source parameter has an <strong>any</strong> (unknown) Type.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Example:**

- **Const1.value** is linked to **DbCommand1.params**. The Varargs setting is OFF:

    ![varagrs-off](images/link_varargs_off.png)
  
   
- Updating the Varargs setting to ON updates the params input variable and changes it to an array that holds two elements - the first is linked to the **Const1.value** and the second is available for an additional link:
  
  ![varargs-on1](images/link_varargs_on_1.png)

 
- Linking the **Const2.value** to the second element in the params array again adds an element to the params array and enables linking additional inputs to the params array:
  
  ![varagrs-on2](images/link_varargs_on_2.png)
  
  
  **Notes:**

  - All additional links to the output array are created automatically when **Varagrs** is set to ON.
  - When the Varargs of one of these links is set to OFF, the target array returns to its original type as created by Varargs and removes other links to this target parameter.
  
  
## How Do I Add Links to the Flow?

To create a **Link** do either:

- Click the **output parameter** of the source Actor and drag the **connection line** to the **input parameter** of the target Actor.
- Click the **input parameter** of the target Actor and drag the **connection line** to the **output parameter** of the source Actor.
- Click ![image](images/99_19_dots.PNG) in the source Actor > **Link**. Populate the **Target Actor**, **Target Parameter** and the **Selection Parameter** (source parameter) and then click **V** to save the changes.

    ![Adding link](images/99_20_add_link_1.PNG)
    

### Linking a Schema Object 

A Schema contains different elements. 

**Example:** 

The source parameter holds the following Schema:

```
{
    "type": "object",
    "properties": {
        "name": {
            "type": "string"
        },
        "family_name": {
            "type": "string"
        },
        "age": {
            "type": "integer"
        },
        "car": {
            "type": "string"
        }
    }
} 
```

To connect a specific element in the Schema, click ![image](images/99_27_red_cross.PNG) adjacent to the Actor's output argument to expand the **yellow segment** of the **Data Inspection** and view the parameters list in the object:

![data inspection](images/99_20_data_inspection_example.PNG)

 To link a Schema to a target Actor do either:
- Click the parameter name in the **Data Inspection** and drag the **connection line** to the **input parameter** of the target Actor.
- Click ![image](images/99_19_dots.PNG) in the right corner of the Actor to open the [Actor's context menu](18_broadway_flow_window.md#actors-context-menu) and select **Link**. Populate the **Target Actor**, **Target Parameter**, **Selection Parameter** (source Schema parameter) and **Selection Schema** (parameter name in the source Schema). Click **V** to save the changes.

    ![Adding link](images/99_20_add_link_2.PNG)

A Schema can be connected to another Actor. For example, connecting the output Schema to the **params** input parameter of the **DbLoad** Actor. Note that if a specific element of the Data Inspection object is connected to another input parameter of the **DbLoad** Actor, the specific link overrides the link of the Schema to the **params** input parameter.  

## How Do I Remove Links from the Flow?

Click the link's connection line and press **Delete** on  your keyboard.

## How Do I Edit Links in the Flow?

Click the link's connection line to open the [Link Object Properties window](20_broadway_flow_linking_actors.md#link-object-properties) on the right of the Flow window. Edit the **Link Type** or **Varargs** settings. 

## Show Only Connected Objects

Click ![image](images/99_19_dots.PNG) > **Show only connected** in [Actor's context menu](18_broadway_flow_window.md#actors-context-menu) to display only Actors linked to this Actor.
Click **Show only connected** again to remove this filter and display all Actors in the flow.

This option is useful when tracking complex flows.

**Example:**

A complex String handling flow:

![String flow](images/string_flow_example.png)

To view only the  Actors connected to **Regex1** Actor, click ![image](images/99_19_dots.PNG) in the Actor's right corner > **Show only connected** . The following Actors are displayed:

![show connected-example](images/show_connected_examples.png)

[![Previous](/articles/images/Previous.png)](19_broadway_flow_stages)[<img align="right" width="60" height="54" src="/articles/images/Next.png">]()