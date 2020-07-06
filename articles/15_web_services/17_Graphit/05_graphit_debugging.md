# Graphit Debugging

The Graphit **Debug** option can be used to test JSON, XML or CSV output without deploying an implementation. 
A Debug process can be run on an LUBD file that has been generated in the Fabric LUBD viewer or by pointing to either the local Fabric or the Fabric server that is defined for the project deployment. 

In both cases, you can set input parameters values of any use case by clicking the Parameters option on the top left side of the Graphit window. [Click here ro learn about Graphit Input parameters](https://github.com/k2view-academy/K2View-Academy/tree/master/articles/demo_project)

### What are the Graphit Debug Options ? 

In order to debug Graphit, let's understand what are  the Graphit top menu bar components :

- **Parameters**  - The Parameters window tab , is used for populating the parameters that are used at debugging. The defined parameters will be also used when invoking Garphit by [swagger](/articles/15_web_services/09_swagger.md). 

  ![](/articles/15_web_services/Graphit/images/31_input_parameters.png)

-  **Server** - A user can select the server which the simulation is executed on :the [user configuration](/articles/04_fabric_studio/04_user_preferences.md#What Is the Purpose of the Server Configuration Tab?) server list  from the frop down menu or LOCAL for using the latest ludb files 

  ![](/articles/15_web_services/Graphit/images/32_servers.png)

-  **RUN** - The Run button is used to debug the Graphit. The result will be shown on the right corner white window area:

  ![](/articles/15_web_services/Graphit/images/33_run.png)

- **Output**  - Following are the outputs that can be selected:

  - JSON  
  - CSV
  - XML 
  - **Profiler** - This option is used, in order to profile the performance of the Graphit code and to provide running time for each one of the Graphit sections.  Note, once the profiler is selected for the first time, the execution start automatically (Run option is greyed out)

![](/articles/15_web_services/Graphit/images/34_profiler.png)



[![Previous](/articles/images/Previous.png)](/articles/15_web_services/Graphit/04_graphit_node_properties.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/06_.md)

