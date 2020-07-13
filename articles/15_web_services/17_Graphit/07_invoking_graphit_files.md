# Invoking Graphit files
Graphit files can be invoked either as a Web Service or embedded into an existing Web Service.  

## How Do I Invoke Direct Calls?
1.  Go to **Web Sources** > **Resources** and right click the **Graphit file**. 
2.  Deploy the **Graphit file** to the **server** and then select **Invoke as a Web Service**.

For more information refer to the example in [Using Parameters](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md) to see how to deploy and invoke a Graphit file as a Web Service
![](/articles/15_web_services/17_Graphit/images/47_invoking_graphit_files.PNG).

<<<<<<< HEAD
Note that the Graphit file can be invoked in both GET or POST mode, but you must set the parameters in the Graphit parameter window to enable using a GET method. (debug value does not need to be added as the values can be added from the swagger GUI)

Consult this [article] (/articles/15_web_services/12_Supported_Verbs_Get.md In ) to refer to the full list of supported verbs.
=======
## Web Services Calls
Graphit files are mainly used in a Web Servive to structure the Web Service's response. 
### How Do I Invoke a Call from WS Code?
To use the Graphit file, include the following code in the Web Service implementation:
>>>>>>> ee3815b206ba29cb9857a8a3189fd7dc2e5b7fe7

New Object response = graphit(<file name>, <Input parameters>).

<<<<<<< HEAD
### Call from WS code
The most frequent use of the Graphit file is within a web service, with the purpose of constructing the web service response. In order to use the Graphit file, include the following code in your web service implementation: New Object response = graphit(<file name> , <Input parameters>).
The “response” variable will get the CSV, JSON or XML response string, and can then be returned as the web service output.

The function parameters are:
  ▪ File_name = the name you assign the Graphit file that should generate the response document. If the web service name is the same as the Graphit file name, this parameter can be set to null.
  ▪ Input parameters – comma separated list of the parameters expected by Graphit file, for example, the logical unit instance key:
=======
The Response variable gets the CSV, JSON or XML response string which can then be returned as the Web Service output.
  
The function's parameters are:
>>>>>>> ee3815b206ba29cb9857a8a3189fd7dc2e5b7fe7

-  File_name = the name assigned to the Graphit file to generate the Response document. If the Web Service's name and the Graphit file's name are the same, set this parameter  to Null.

-  Input parameters, comma separated list of the parameters expected by the Graphit file, for example, the LUI key. Using the grSQL Graphit file and Customer_Id as input parameters, the Object response = 

  graphit("grSql.graphit",Customer_Id); 

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
