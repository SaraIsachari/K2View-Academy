# Graphit - Code Examples
### Simple example of a Customer Info Web Service that brings data for an LUI

The following Graphit file gets an input LUI which extracts customer data from the CUSTOMER LU, calculates its balance and sets its status accordingly. 

Output data is returned in JSON structure and adds information on whether the customer is either a:
-  VIP member, with a total balance of over USD 10,000.
-  Gold member, with a total balance of over USD 1,000. 

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/58_graphit_examples.PNG" width="700" height="400" ></img>

After deploying and invoking the Graphit file directly as a Web Service:

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/59_graphit_examples.PNG" width="700" height="400"></img>


###  Example of a Web Service that invokes the relevant Graphit file depending on a specific condition    
The following wsGraphitExample2 Web Service gets an input LUI for the CUSTOMER LU and returns a response stating whether a customer has a Bronze, Gold or Platinum status in their subscription lines.

Code:

```java
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

The first Graphit file displays the customer's basic information and their subscriber lines with a Gold or Platinum VIP status while the second Graphit file displays the customer's basic information and corresponding subscriber lines in Bronze VIP status.

Graphit file 1: grSQLGldPlus.graphit:

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/60_graphit_examples.PNG" width="700" height="400"></img>


Graphit file 2: grSQLBrz.graphit:

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/62_graphit_examples.PNG" width="700" height="400"></img>


Output from the Swagger GUI for grSQLGldPlus.graphit with Customer Instance ID = 1234:

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/59_graphit_examples.PNG" width="700" height="400"></img>


Output from the Swagger GUI for grSQLBrz.graphit with Customer Instance ID = 1000:
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/59a_graphit_examples.PNG" width="700" height="400"></img>

### Simple example of a CSV generated by a JOIN query between subscriber and invoice tables from the external Billing_DB database
This example displays how to retrieve data from multiple tables in the Billing_DB database and use Graphit to prepare a CSV-formatted response:

Graphit file: grCSV.graphit:

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/63_graphit_examples.PNG" width="700" height="400"></img>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/64_graphit_examples.PNG" width="700" height="400"></img>

Running the Graphit file in Debug mode with 2 and 3 as consecutive values for the SubscriberID:

<img src="/articles/15_web_services_and_graphit/17_Graphit/images/65_graphit_examples.PNG"></img>

Note the different tags used and their respective effect on the output CSV document:
e.g. csvHeader: false -> removes fields headers from the response.



###  Graphit Node Types Examples
#### grFormat.graphit
In this example, you will find that all the children nodes of the CRM_DB node are defined as field. The response will populate the document with the names and values of these specific fields.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/09_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grFunction.graphit
This example illustrates a simple javascript routine that returns the highest of random number x and random number y.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/10_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grSQL.graphit
In this file we describe a parent node defined as SQL non-prepared, while its children nodes are defined as SQL.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/11_graphit_examples_tags.png" width="700" height="400"></img>

#### grString.graphit
This example shows how to concatenate 2 values retrieved from a previously-defined SQL query.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/12_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grCondition.graphit
The condition defined in this file will trigger either the TRUE or FALSE node depending on the randomly generated values of x and y.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/13_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grGroup.graphit
The ${x} string has been added to both TRUE and FALSE groups, while the ${y} value is declared outside the groups. The display ${x} of  will also show which group originated it.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/14_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grCollect.graphit
This example shows how both subscriber and billing datasets are collected into one single array.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/15_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grRaw.graphit
This example illustrates an example of XML output in raw format. Observe the header value displayed in the response: (?xml version="1.0" encoding="UTF-8"...)<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/16_graphit_examples_tags.PNG" width="700" height="400"></img>


###  Graphit Node Properties Examples

#### grShowFormat.graphit
The sessionProvider flag is set to CRM_DB thus enabling direct references to CRM_DB tables and fields.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/17_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grShowEnabled.graphit
The response comes back empty since the entire CRM_DB node and its children nodes are affected by the "enabled" flag.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/18_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grShowEnabled.graphit
The "nice" flag is set to TRUE and has been activated at the root node level. The response comes back with each tag appearing in a new line and with the indentation corresponding to the location of the tag in the document's hierarchy.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/19_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grOne.graphit
The "ONE" flag is set to TRUE and has been applied to the Billing_DB2 node. The response only brings the first value for {"BILLING_DB2":{"SUBSCRIBER_ID":2}}, instead of the 10 values expected for this tag (if the "ONE" flag had not been activated).<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/20_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grEntry.graphit
The Entry flag has been set to the subscribers node. The XML response therefore shows and tags around each value of subscriber_id.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/21_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grAttribute.graphit
The Attribute flag has been activated to all children nodes of the CRM_DB node.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/22_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grFormat.graphit
The Format flag has been set to XML in the root node. The response format will only be displayed if the Output value (on the right side of the run button) is set to XML. Running the file with other output selections such as JSON or CSV will return an error.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/23_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grShowEmpty.graphit
The ShowEmpty flag has been set to False and applied to the CRM_DB node. Empty nodes are not shown in the response.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/24_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grShowNull.graphit
The ShowNull flag has been set to False and applied to the CRM_DB node. Null values will therefore be ignored and not shown in the part of the response that deals with the CRM_DB. Since the flag has not been applied to the Billing_DB node, null values will be shown.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/25_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grNumberFormat.graphit
The flag has been set to 000.00 and applied to the NumberFormat node. All responses displays "Number Format" with 3 digits before the floating point and another 2 after.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/26_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grKeys.graphit
The response has been re-organized using the subscriber_id as a key.<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/27_graphit_examples_tags.PNG" width="700" height="400"></img>

#### grCSV.graphit
The csvRow has been set to the SUBSCRIBER_ID node and csvHeader has been set to False in the Subscriber_info node. The header is removed from the CSV output, while a new line is created for wach new subscriber_id entry<br></br>
<img src="/articles/15_web_services_and_graphit/17_Graphit/images/28_graphit_examples_tags.PNG" width="700" height="400"></img>

[![Previous](/articles/images/Previous.png)](/articles/15_web_services_and_graphit/17_Graphit/09_invoke_graphit_from_outside_studio.md)