# Graphit Parameters

Graphit allows you to define input parameters whereby the generated documents are executed using various settings like LUIs, LU table fields and other specific parameters that require processing.

Parameters can be set when:
- Running Graphit in Debug mode in the Fabric Studio.
- Invoking Graphit directly from Swagger or another http link.
- Calling Graphit from a Web Service whereby parameters are parsed as a mapped object. 

## Graphit Window - Parameters Setup
Click **Parameters** in the **Graphit window** to open the **Graphit Parameters** dialog box. 

![](/articles/15_web_services/17_Graphit/images/38_graphit_with_parameters.PNG)

Graphit Parameters are added to support the following:
- Running Graphit from the Fabric Studio in Debug mode.
- Running a GET request for the Graphit file according to the parameters defined in the Graphit Parameters dialog box. The parameters are added to the [URL](/articles/15_web_services/12_Supported_Verbs_Get.md#get-based-on-graphit-file). In addition, the input parameters are dispayed when invoking the Graphit file using [Swagger](/articles/15_web_services/09_swagger.md).

Note that if the parameters have not been added to the Graphit Parameters dialog box, you can create a POST request for the Graphit file and add the parameters in the Request body. Alternatively, you can wrap the Graphit file using a Web Service and send the parameters to the Graphit file via the Web Service. 

## Parameters Setup When Running Graphit From Fabric Studio
When creating a Graphit file, parameters can be defined using the ${} symbols to refer to the value that is set in the Parameters window. In this specific case, you must also define a debug value in the Parameter window. If not, the response is empty.


**Example using grSql.graphit**
 
 Generation of a JSON file that returns the values of the following fields:
- Customer_ID, SSN, first_name and last_name for a customer whose Instance ID = 547.  
- Date and status for Case ID = 1394.
- Generic SELECT statement that retrieves Instance 547: get Customer.${customer_id}.

The corresponding queries for the SELECT statements are:
- Select customer_id,ssn,first_name,last_name From Customer.CUSTOMER where CUSTOMER_ID = ${customer_id}.
- Select * from CASE_NOTE where case_id = ${case_id}

Refer to the full Graphit file:

![](/articles/15_web_services/17_Graphit/images/35_graphit_with_parameters.PNG)

Before running the file, a **Debug** value is assigned to the **${customer_id}** and **${case_id} []**(/articles/15_web_services/17_Graphit/images/38_graphit_with_parameters.PNG) input parameters. 

Click **Run**, and view the results on the right side in the output window:
![](/articles/15_web_services/17_Graphit/images/39_graphit_with_parameters.PNG)

## Parameters Setup When Calling Graphit Directly From Swagger
Add the parameters to the Parameters window to allow creating a GET request for the Graphit file and populating the parameters in Swagger. 

Note that to execute the Graphit file, populate the parameter's value in Swagger. The debug values are taken only when debugging the Graphit file.

Example:

Using the same grSql.graphit Graphit file used in the previous example, in the following screenshot, the customer_id Debug value has been left empty intentionaly.
![](/articles/15_web_services/17_Graphit/images/40_graphit_with_parameters.PNG)
Following its deployment, the Graphit file is deployed as a Web Service. 
![](/articles/15_web_services/17_Graphit/images/41_graphit_with_parameters.PNG)

As indicated below, the two Parameters fields are marked as required,
![](/articles/15_web_services/17_Graphit/images/42_graphit_with_parameters.PNG)

The customer_id=547, and case_id=1394 values are filled in the Parameters fields. 
![](/articles/15_web_services/17_Graphit/images/43_graphit_with_parameters.PNG)

Note that when deleting all parameters in the Parameters dialog box together, the values in the GET section in the Swagger GUI cannot be specified but can be injected in the POST section, with a succedful response upon execution:
![](/articles/15_web_services/17_Graphit/images/44_graphit_with_parameters.PNG)


## Parameters Setup When Invoking Graphit From a Web Service 
A Graphit file can be invoked directly or be wrapped by a WS. When wrapped by the WS, the WS sends the parameters to Graphit which then parses them accordingly when generating the XML, JSON or CSV documents.

Parameters can be parsed using a map objects as illustrated in the java web-service below::
Map<String, Object> temp = new HashMap<>();
temp.put("input1",1000);
temp.put("input2",2463);
return graphit("grSql2.graphit", temp);

This code calls the following graphit file which uses ${input1} and ${input2} as parameters respectively for customer_id and subscriber_id to populate the JSON with relevant invoices:
![](/articles/15_web_services/17_Graphit/images/46a_graphit_with_parameters.PNG)
        
        






[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/05_graphit_debugging.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/17_Graphit/07_invoking_graphit_files.md)









