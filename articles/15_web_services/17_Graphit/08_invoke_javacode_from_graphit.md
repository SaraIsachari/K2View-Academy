# Invoking Java code from Graphit


## Lambda Functions
You can bind java functions to the Graphit scope using a web service. You need to create a Lambda expression based on the Scripter.F functional interface which has the following signature:
  ▪ Object f(Object... var1);
Limitation:
  ▪ This cannot be debugged in the Graphit editor (as the functional parameters cannot be created in the studio). You can test your code by deploying to Fabric or debugging the web service code using the IntelliJ editor. 
  
 
## Examples




Refer to example in [Using Parameters](/articles/15_web_services/17_Graphit/06_using_graphit_files_with_parameters.md) to see how to deploy and invoke a graphit file as a web-service:
![](/articles/15_web_services/17_Graphit/images/47_invoking_graphit_files.PNG)
