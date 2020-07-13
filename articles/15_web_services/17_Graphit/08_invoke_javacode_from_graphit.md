# Invoking Java Code from Graphit


## JavaScript Functions
Javascript functions can be added to the Graphit file using the graphit editor in Fabric studio. To do so, add a new node to any already-defined root, and define it as a function used to run a code in order to determine the value of the node. Values extracted from datasets in parent nodes can be parsed down to the Javascript function.
Note: You can refer to parameters, using directly the name they have been defined in the Parameters Window.

### Example
In the example below, we define a Graphit Web-Service that retrieves the sum of all payments made by a customer from all the received invoices.
We then decide whether to convert this amount to GBP or EUR currency depending on the value of a parameter called convGBP (set to True to display the amount in GBP, and False to display the amount in EUR):

Defining the datasets nodes and Javascript node as a child of the Balance node:
![](/articles/15_web_services/17_Graphit/images/50_invoke_javacode_from_graphit.PNG)


Running on debug mode with customer_id set to 1000, and conversion currency set to False (i.e. GBP currency):
![](/articles/15_web_services/17_Graphit/images/51_invoke_javacode_from_graphit.PNG)


After deploying and launching the web-service in Swagger:
![](/articles/15_web_services/17_Graphit/images/52_invoke_javacode_from_graphit.PNG)


Note the http link that has been generated to invoke the web-service for customer_id = 1000, and convGBP flag set to false, meaning the conversion will be set to EUR currency:
"http://10.21.1.76:3213/api/grSql?customer_id=1000&convGBP=false"




## Lambda Functions
Java functions can be bound to the Graphit scope when using a web service. For this matter, a Lambda expression based on the Scripter.F functional interface needs to be created with the following signature:

  ▪ Object f(Object... var1);

Limitation:
  ▪ This cannot be debugged in the Graphit editor (as the functional parameters cannot be created in the studio). 
  Nevertheless, the code can be tested by deploying it to Fabric or by debugging the web service code using the the IntelliJ editor. 
  
 

[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/07_invoking_graphit_files.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/17_Graphit/09_invoke_graphit_from_outside_studio.md)

