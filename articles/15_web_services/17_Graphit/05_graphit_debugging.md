# Graphit Debugging

The Graphit **Debug** option can be used to test JSON, XML or CSV output without deploying an implementation. 
A Debug process can be run on an LUBD file that has been generated in the Fabric LUBD viewer or by pointing to either the local Fabric or the Fabric server that is defined for the project's deployment. 
To define input parameter values, click Parameters on the top left side of the Graphit window.
[Click here ro learn about Graphit Input parameters](https://github.com/k2view-academy/K2View-Academy/tree/master/articles/demo_project)

### What are the Graphit Debug Options ? 

In order to debug Graphit, let's understand what are  the Graphit top menu bar components :
<table>
<tbody>
<tr>
<td valign="top" width="300pxl">
<p><strong>Debug Option</strong></p>
</td>
<td valign="top" width="600pxl">
<p><strong>Description</strong></p>
</td>
</tr>
<tr>
<td valign="top" width="300pxl">Parameters&nbsp;</td>
<td valign="top" width="600pxl">&nbsp;Click to open the Parameters window to populate the Debug parameters. These settings are also used when Graphit is invoked&nbsp;[swagger](/articles/15_web_services/09_swagger.md)</td>
</tr>
<tr>
<td valign="top" width="300pxl">Server</td>
<td valign="top" width="600pxl">Select the server used during the simulation. See [User Configuration] (/articles/04_fabric_studio/04_user_preferences.md#).<br />What Is the Purpose of the Server Configuration Tab?) server list from the frop down menu or LOCAL for using the latest ludb files</td>
</tr>
<tr>
<td valign="top" width="300pxl">Run</td>
<td valign="top" width="600pxl">Click to Debug the Graphit file. Debug results are displayed in the right corner of the window.&nbsp;</td>
</tr>
<tr>
<td valign="top" width="300pxl">Output</td>
<td valign="top" width="600pxl">
<p>The following Output types can be selected:  
-  JSON</p>
-  CSV  
-  XML  
-  Profiler, profiles the performance of the Graphic code and provides run time for each Graphit section. Note that after the Profiler is selected for the first time, it automatically runs and the option is disabled.&nbsp;</p>
</td>
</tr>
</tbody>
</table>
<p><a href="https://github.com/k2view-academy/K2View-Academy/blob/KB_DROP2_15a_Graphit_Merav/articles/15_web_services/Graphit/images/18_node_type_raw.png" target="_blank" rel="noopener noreferrer"><img src="https://github.com/k2view-academy/K2View-Academy/raw/KB_DROP2_15a_Graphit_Merav/articles/15_web_services/Graphit/images/18_node_type_raw.png" alt="" /></a></p>


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

