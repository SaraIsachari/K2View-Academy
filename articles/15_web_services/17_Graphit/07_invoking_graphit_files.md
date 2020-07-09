# Invokink Graphit files

Graphit files can be invoked in 2 different ways, as a web-service itself, or embedded into an existing web-service.  

## Direct Calls
Right-click on the graphit file located in the tree under Web Services -> Resources.
Deploy it to the server you are using, and then select the Invoke as a Web Service option. 
Refer to example in [Using Parameters]<a href="/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md"></a> to see how to deploy and invoke a graphit file as a web-service:
![](/articles/15_web_services/17_Graphit/images/47_invoking_graphit_files.png)

## Web-services Calls

Graphit can also be invoked using a basic web-service, containing the following command (that parses Customer_Id as a parameter): 
*Object response = graphit("grSql.graphit",Customer_Id);*

![](/articles/15_web_services/17_Graphit/images/48_invoking_graphit_files.png)


After deploying and invoking the web-service deployed:
![](/articles/15_web_services/17_Graphit/images/45_graphit_with_parameters.PNG)

We will then, using swagger, observe that the customer_id parameter has been successfully parsed:
![](/articles/15_web_services/17_Graphit/images/46_graphit_with_parameters.PNG)

Note, multiple parameters can be parsed to Graphit using either:
- by passing a map as a parameter in which the parameters and their values will have been stored as key/value pairs
- by passing a list of arguments and then loop over that list
