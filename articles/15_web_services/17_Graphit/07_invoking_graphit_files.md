# Invoke Graphit files

Graphit files can be invoked from 2 different  

## Direct Calls
When creating a Graphit file, parameters can be defined using the ${} symbols to refer to the value that will be parametered from the Parameter window.
In this particular case, a debug value will need to be set in the Parameter window as well, otherwise the response will be empty.

## Web-services Calls
Let's invoke graphit using a basic web-service, containing the following command that parses Customer_Id as a parameter: 
*Object response = graphit("grSql.graphit",Customer_Id);*

After deploying and invoking the web-service deployed:
![](/articles/15_web_services/17_Graphit/images/45_graphit_with_parameters.PNG)

We will then, using swagger, observe that the customer_id parameter has been successfully parsed:
![](/articles/15_web_services/17_Graphit/images/46_graphit_with_parameters.PNG)

Note, multiple parameters can be parsed to Graphit using either:
- by passing a map as a parameter in which the parameters and their values will have been stored as key/value pairs
- by passing a list of arguments and then loop over that list
