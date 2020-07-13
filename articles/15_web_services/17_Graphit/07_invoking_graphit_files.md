# Invoking Graphit files

Graphit files can be invoked in 2 different ways, as a web-service itself, or embedded into a web-service.  

## Direct Calls
Right-click on the graphit file located in the tree under Web Services -> Resources.
Deploy it to the server you are using, and then select the Invoke as a Web Service option. 
Refer to example in [Using Parameters](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md) to see how to deploy and invoke a graphit file as a web-service.
![](/articles/15_web_services/17_Graphit/images/47_invoking_graphit_files.png)

Note that the Graphit file can be invoked in both GET or POST mode, but you must set the parameters in the Graphit window to enable using a GET method. Consult this [article] (/articles/15_web_services/12_Supported_Verbs_Get.md In ) to refer to the full list of supported verbs.

## Web-services Calls

### Call from WS code
The most frequent use of the Graphit file is within a web service, with the purpose of constructing the web service response. In order to use the Graphit file, include the following code in your web service implementation: New Object response = graphit(<file name> , <Input parameters>).
The “response” variable will get the CSV, JSON or XML response string, and can then be returned as the web service output.
  
The function parameters are:
######File_name: the name you assign the Graphit file that should generate the response document. If the web service name is the same as the Graphit file name, this parameter can be set to null.
######Input parameters: comma separated list of the parameters expected by Graphit file, for example, the logical unit instance key:

Using grSQL graphit file and Customer_Id as input parameters: 
Object response = graphit("grSql.graphit",Customer_Id);

![](/articles/15_web_services/17_Graphit/images/48_invoking_graphit_files.PNG)


After deploying and invoking the web-service deployed:
![](/articles/15_web_services/17_Graphit/images/45_graphit_with_parameters.PNG)

We will then, using swagger, observe that the customer_id parameter has been successfully parsed:
![](/articles/15_web_services/17_Graphit/images/46_graphit_with_parameters.PNG)


### Call from HTTP link
Graphit can also be invoked as a parameter from the IP address link corresponding to the web-service.
Enter the following parameters inside the link of the browser's address field:
     http://10.21.1.76:3213/api/GraphitWS1?Customer_Id=1472&Case_Id=3707&token=test&graphitProfiler=true&format=json

The response will be displayed within the browser tab:
![](/articles/15_web_services/17_Graphit/images/49_invoking_graphit_files.PNG)




Note, multiple parameters can be parsed to Graphit using either:
- by passing a map as a parameter in which the parameters and their values will have been stored as key/value pairs
- by passing a list of arguments and then loop over that list

More over when designing your web-service you can rely on all [REST APIs and requests formats](/articles/15_web_services/12_Supported_Verbs_Get.md) generally supported by webservices. Complex requests schemes can be designed whereby different graphit files will be invoked depending on the data you are retrieving from your sources or LUI. 



[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/17_Graphit/08_invoke_javacode_from_graphit.md)
