# Graphit - Code Examples
### Simple example of a CustomerInfo Web Service that brings a line of data for a given instance, and all cumulated balance from the customer

The following Graphit Web Service gets an input LUI for the CUSTOMER LU and returns data from the CUSTOMER table and balance table in the CUSTOMER LU. 
Output data is returned in JSON structure and adds information on whether the customer is a VIP member (total balance of over USD 10,000), or a Gold member(total balance of over USD 1,000) 

![](/articles/15_web_services/17_Graphit/images/58_graphit_examples.PNG)

After deploying and running the graphit file as a web-service:
![](/articles/15_web_services/17_Graphit/images/59_graphit_examples.PNG)


###  Example of a wsGraphitExample2 Web Service that invokes a different graphit file depending on a specific condition    
The following Web Service gets an input LUI for the CUSTOMER LU and returns a response stating whether a customer has a Bronze, Gold or Platinum Status on one of his subscription lines.

Code:

```
String val_brz="Bronze";
String val_gld="Gold";
String val_plt="Platinum";

String CUST_STATUS = "SELECT count(*) FROM SUBSCRIBER where SUBSCRIBER.VIP_STATUS=?";
String cnt_brz = ludb("Customer", i_id).fetch(CUST_STATUS,val_brz).firstValue().toString();
String cnt_gld = ludb("Customer", i_id).fetch(CUST_STATUS,val_gld).firstValue().toString();
String cnt_plt = ludb("Customer", i_id).fetch(CUST_STATUS,val_plt).firstValue().toString();


if ((Integer.parseInt(cnt_brz)==0)&&((Integer.parseInt(cnt_gld) !=0)||(Integer.parseInt(cnt_plt) !=0))){
	return graphit("grSqlGldPlus.graphit",i_id);}
else{
	return graphit("grSqlBrz.graphit",i_id);}
```


Graphit file 1: grSQLGldPlus.graphit
![](/articles/15_web_services/17_Graphit/images/61_graphit_examples.PNG)


Graphit file 2: grSQLBrz.graphit
![](/articles/15_web_services/17_Graphit/images/62_graphit_examples.PNG)


Output from Swagger GUI:
![](/articles/15_web_services/17_Graphit/images/60_graphit_examples.PNG)



[![Previous](/articles/images/Previous.png)](/articles/15_web_services/17_Graphit/09_invoke_graphit_from_outside_studio.md)
