# Invoking Graphit files

Graphit files can be invoked in 2 different ways, as a web-service itself, or embedded into an existing web-service.  

## Direct Calls
Right-click on the graphit file located in the tree under Web Services -> Resources.
Deploy it to the server you are using, and then select the Invoke as a Web Service option. 
Refer to example in [Using Parameters]<a href="/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md"></a> to see how to deploy and invoke a graphit file as a web-service:
![](/articles/15_web_services/17_Graphit/images/47_invoking_graphit_files.PNG)

## Web-services Calls

Graphit can also be invoked using a basic web-service, containing the following command (that parses Customer_Id as a parameter): 
*Object response = graphit("grSql.graphit",Customer_Id);*

![](/articles/15_web_services/17_Graphit/images/48_invoking_graphit_files.PNG)


After deploying and invoking the web-service deployed:
![](/articles/15_web_services/17_Graphit/images/45_graphit_with_parameters.PNG)

We will then, using swagger, observe that the customer_id parameter has been successfully parsed:
![](/articles/15_web_services/17_Graphit/images/46_graphit_with_parameters.PNG)

Note, multiple parameters can be parsed to Graphit using either:
- by passing a map as a parameter in which the parameters and their values will have been stored as key/value pairs
- by passing a list of arguments and then loop over that list

More over when designing your web-service you can rely on [all the REST APIs and requests] <a href="/articles/15_web_services/12_Supported_Verbs_Get.md"></a> supported generally supported by webservices. You can therefore design complex schemes whereby different graphit files can be invoked depending on the data you are retrieving from your sources or LUI. 





[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/17_Graphit/08_invoke_javacode_from_graphit.md)
