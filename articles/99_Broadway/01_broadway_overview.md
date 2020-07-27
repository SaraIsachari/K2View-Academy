# Broadway Overview 


A Fabric module, Broadway can be used to design data movement, its transformation and the orchestration of business flows. Featuring a powerful user interface for creating and debugging business and data flows, Broadway also provides a high-performance execution engine that can be activated by Fabric.

Broadway is used throughout Fabric, wherever data movement and orchestration is needed. For example:
* [Logical Unit](/articles/03_logical_units/01_LU_overview.md) data population from external databases or REST APIs.
* Moving data from Fabric to external systems based on [CDC](/articles/18_cdc_and_search/02_cdc_messages.md) or batch processes.
* Subscribing to a message bus and consuming messages.
* Orchestration of scheduled activities through Fabric's job system.
* Data transformation for [Web Services](/articles/15_web_services_and_graphit/01_web_services_overview.md).

Broadway is a flexible engine and is seamlessly integrated into the Fabric command system. Its power can be leveraged anywhere in Fabric's architecture layers for limitless use cases.


## Orchestration and Business Process

A Broadway flow is built from [Stages](/articles/99_Broadway/19_broadway_flow_stages.md) which are executed from left to right. A flow can be split into different execution paths based on conditions. More than one Stage can be executed in each fork in the path.

![image](/articles/99_Broadway/images/Broadway_flow.png)

In the example above, the **Fetch** Stage is executed first. The system then executes either the **Transform Consumer** or (else) the **Transform Business** Stage and finally the **Load** Stage.


## Logic and Data Transformation

Each Stage can contain one or more [Actor](/articles/99_Broadway/03_broadway_actor.md) which are reusable pieces of logic with input and output arguments that can be assembled together to create complex logic. Actors are executed by Stages.

![image](/articles/99_Broadway/images/Broadway_actors.png)

In the example above, **Fetch** Stage queries data and transfers it as input to the Actors in the next Stages. Based on the data, either the **Transform Consumer** Stage or the **Transform Business** Stage is executed. In turn, these Stages execute the Actors that build data for the **DbLoad** Actor in the last Stage.

Note that an entire Broadway flow can be exported and encapsulated into an Actor and then be reused between flows. This is powerful tool for reusing logic and working with highly-complex flows.

[Click for more information Broadway flows.](/articles/99_Broadway/16_broadway_flow_overview.md)


## Data Inspection

When Broadway transfers data between Actors, the data is displayed in the Broadway Studio. Complex data types (objects, arrays) are automatically detected and analyzed, and both metadata and data are visually rendered for easy debugging and extraction.

![image](/articles/99_Broadway/images/Broadway_data_inspection.png)

The example above displays how the system automatically identifies the data structure of the **FetchCustomer** Actor. This enables selecting specific fields from the data and transferring them to the appropriate Actors.

[Click for more information about Data Inspection.](/articles/99_Broadway/27_broadway_data_inspection.md)


## Learning Broadway

Broadway gets its name from its powerful execution of flows in Stages and its ability to encapsulate logic into Actors which when coupled with its data and metadata inspection engine, act as its main pillars.

Broadway has additional capabilities that together provide a great way to model data movement and orchestration. These and other capabilities are explored in other articles in the Knowledge Base.

Another great way to learn how to use Broadway is from the built-in Tutorial which can be accessed when creating any Broadway flow. Go to **Actions** > **Examples** and checkout the documented sample flows. 

The **a-broadway-tutorial.flow** takes you through the major Broadway features and capabilities and can act as a good starting point. Other example flows focus on a single feature or capability, demonstrating and explaining them in depth.

[Click for more information about Broadway Tutorial and flow examples.](/articles/99_Broadway/17_tutorial_and_flow_examples.md)


[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/99_Broadway/02_broadway_high_level_components.md)