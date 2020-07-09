# Graphit Parameters

Graphit allows users to define input parameters so any generated document can be executed with different parameters such as LUIs, fields within LU tables or any other specific parameter that you need to be processed. 
Parameters can be set in the following case:
- when running Graphit in debug mode within the Fabric studio
- when invoking Graphit directly from swagger or any http link
- when calling Graphit from a Web-Service in which case parameters will be parsed as a map object 

## Graphit Window- Parameters Setup

Click the Parameters in the Graphit window. A popup window is opened:
![](/articles/15_web_services/17_Graphit/images/38_graphit_with_parameters.PNG)

You need to add Graphit parameters to the parameters window to support the following:

- Run the Graphit from the Fabric Studio in a debug mode.
- Run a GET request for the Graphit file- the prameters, defined in the Parameters popup window. The parameters are added to the [URL](/articles/15_web_services/12_Supported_Verbs_Get.md#get-based-on-graphit-file). In addition the input parameters are dispayed when invoking the Graphit file using [Swagger](/articles/15_web_services/09_swagger.md).
  Note that even if you do not add the parameters to the parameters window, you can still create a POST request for the Graphit file and add the parameters in the Request body. Alternatively- you can wrap the Graphit by a Web-Service and send the parameters to the Graphit file by the Web-Service. 

## Parameters setup when running Graphit from Fabric studio
When creating a Graphit file, parameters can be defined using the ${} symbols to refer to the value that will be parametered from the Parameter window.
In this particular case, a debug value will need to be set in the Parameter window as well, otherwise the response will be empty.


Example: grSql.graphit
Generation of a JSON file that will return the values of the following fields:
- Customer_ID, SSN, first_name, last_name for customer with instance ID = 547
- Notes date and status for case ID = 1394

First lets write the generic select statement to retrieve instance 547:
get Customer.${customer_id}


The corresponding queries for the select statements will be as follow:
- select  customer_id,ssn,first_name,last_name From Customer.CUSTOMER where CUSTOMER_ID = ${customer_id}
- select * from CASE_NOTE where case_id = ${case_id}

See below the full graphit file:
![](/articles/15_web_services/17_Graphit/images/35_graphit_with_parameters.PNG)

Before running the file, we need to assign a debug value to the input parameters: ${customer_id} and ${case_id}
![](/articles/15_web_services/17_Graphit/images/38_graphit_with_parameters.PNG)

Click Run, and view the result on the right side in the output window:
![](/articles/15_web_services/17_Graphit/images/39_graphit_with_parameters.PNG)


## Parameters setup when calling Graphit directly from swagger
You must add the parameters to the parameters window to allow creating a GET request for the Graphit file and populate the parameters in the Swagger. You must populate the parameter's value in the Swagger for the Graphit execution (the debug values are taken only when debugging the Graphit file).

Example:
Let's use the same graphit file used in the previous example: grSql.graphit
As you can see in the picture below, one of the 2 debug value (customer_id) has been left intentionaly empty.
![](/articles/15_web_services/17_Graphit/images/40_graphit_with_parameters.PNG)

Let's now invoke this graphit file as a web service (after having deployed it first):
![](/articles/15_web_services/17_Graphit/images/41_graphit_with_parameters.PNG)

As indicated below, the 2 parameters fields are marked as required:
![](/articles/15_web_services/17_Graphit/images/42_graphit_with_parameters.PNG)

Let's now fill in the following values into the parameters fields: customer_id=547, and case_id=1394
![](/articles/15_web_services/17_Graphit/images/43_graphit_with_parameters.PNG)

Note: When deleting the parameters from the Parameters box all together, you will not be be able to specify the patrameters values in the GET section of the swagger GUI, yet the values can be injected in the POST section, with a succedful response upon execution:
![](/articles/15_web_services/17_Graphit/images/44_graphit_with_parameters.PNG)


## Parameters setup when invoking Graphit from a webservice 
A Graphit file an be invoked directly or be wrapped by a WS. If it is wrapped by the WS, then the WS sends the parameters to the Graphit which then parses them accordingly when generating the XML, JSON or CSV documents







[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/05_graphit_debugging.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/17_Graphit/07_invoking_graphit_files.md)









