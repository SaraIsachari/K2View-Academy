# Invoking Graphit files
Graphit files can be invoked either directly as a Web Service or embedded into a Web Service. 
Note that the Graphit files must be deployed to Fabric server in advance. 

## How Do I Invoke Direct Calls?
- Go the the **Project Tree**, click the **Resources** under the **Web Services**. Right click the selected Graphit file > Invoke Graphit Web Service > Fabric server.
Note that the Fabric server must be defined in advance in the [Server Configuration Tab](/articles/04_fabric_studio/04_user_preferences.md#what-is-the-purpose-of-the-server-configuration-tab) of the User Configuration.

For more information refer to the example in [Using Parameters](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md#parameters-setup-when-calling-graphit-directly-from-swagger) to see how to deploy and invoke a Graphit file as a Web Service
![](/articles/15_web_services/17_Graphit/images/47_invoking_graphit_files.png).

Note that the Graphit file can be invoked in both GET or POST mode, but you must set the parameters in the Graphit parameter window to enable using a GET method. (debug value does not need to be added as the values can be added from the swagger GUI)

Refer to the following articles to consult the full [GET](/articles/15_web_services/12_Supported_Verbs_Get.md) or [POST](/articles/15_web_services/12_Supported_Verbs_Post.md) verbose.

## How Do I Invoke a Call from WS Code?
Graphit files are mainly used in a Web Servive to structure the Web Service's response. To use the Graphit file, include the following code in the Web Service implementation:

<p><br />Object response = graphit(&lt;file name&gt;, &lt;Input parameters&gt;).</p>

### Call from WS code
The most frequent use of the Graphit file is within a web service, with the purpose of constructing the web service response. In order to use the Graphit file, include the following code in your web service implementation: New Object response = graphit(<file name> , <Input parameters>).
The “response” variable will get the CSV, JSON or XML response string, and can then be returned as the web service output.

The function parameters are:
  ▪ File_name: the name you assign the Graphit file that should generate the response document. If the web service name is the same as the Graphit file name, this parameter can be set to null.
  ▪ Input parameters: comma separated list of the parameters expected by Graphit file, for example, the LUI key.
  
The Response variable gets the CSV, JSON or XML response string which can then be returned as the Web Service output.
  
 Using the grSQL Graphit file and Customer_Id as input parameters:
 Object response = graphit("grSql.graphit",Customer_Id); 

![](/articles/15_web_services/17_Graphit/images/48_invoking_graphit_files.PNG)


After deploying and invoking the Web Service:
![](/articles/15_web_services/17_Graphit/images/45_graphit_with_parameters.PNG)

Open Swagger and check that the Customer_id has been successfully parsed:
![](/articles/15_web_services/17_Graphit/images/46_graphit_with_parameters.PNG)


### How Can I Invoke a Call from an HTTP Link?
Graphit can also be invoked as a parameter from the IP address link corresponding to the Web Service.
Enter the following parameters inside the link of the browser's address field:

     http://10.21.1.76:3213/api/GraphitWS1?Customer_Id=1472&Case_Id=3707&token=test&graphitProfiler=true&format=json

The response is displayed in the Vrowser tab:
![](/articles/15_web_services/17_Graphit/images/49_invoking_graphit_files.PNG)

Note that multiple parameters can be parsed to Graphit by:
- Passing a map as a parameter in which the parameters and their values will have been stored as key / value pairs.
- Passing a list of arguments and then looping over the list.

In addition when designing a Web Service you can rely on all [REST APIs and requests formats](/articles/15_web_services/12_Supported_Verbs_Get.md) generally supported by Web Services. Complex requests schemes can be designed whereby different Graphit files can be invoked depending on the data retrieved from its sources or LUI. 


[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/17_Graphit/08_invoke_javacode_from_graphit.md)
