# Graphit Parameters

Graphit allows users to define input parameters so any generated document can be executed with different parameters such as LUIs, fields within LU tables or any other specific parameter that you need to be processed. 
Parameters can be set in the following case:
- when running Graphit in debug mode within the Fabric studio
- when invoking Graphit directly from swagger or any http link
- when calling Graphit from a webservice in which case parameters will be parsed as a map object 

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
select  customer_id,ssn,first_name,last_name From Customer.CUSTOMER where CUSTOMER_ID = ${customer_id}
select * from CASE_NOTE where case_id = ${case_id}

See below the full graphit file:
![](/articles/15_web_services/17_Graphit/images/35_graphit_with_parameters.PNG)

Before running the file, we need to set the parameters. This is usually used for debugging, so you will need to set the Server value to debug in the menu on the left side of the Run command:
![](/articles/15_web_services/17_Graphit/images/36_graphit_with_parameters.png)

Let's now assign a debug value to the input parameters: ${customer_id} and ${case_id}
![](/articles/15_web_services/17_Graphit/images/38_graphit_with_parameters.PNG)

Click Run, and view the result on the right side in the output window:
![](/articles/15_web_services/17_Graphit/images/39_graphit_with_parameters.PNG)


## Parameters setup when calling Graphit directly from swagger
Graphit allows the parsing of parameters that will be interpreted by swagger. In this case the parameter needs to be refered to within the graphit file, but also explicitly added to the Parameter window. Please note that no debug value needs to be added there since Swagger will prompt you to add it within the parameter field of the Swagger GUI.
Example:
Let's use the same graphit file used in the previous example: grSql.graphit








