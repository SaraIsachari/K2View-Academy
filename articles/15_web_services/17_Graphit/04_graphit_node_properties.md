# Graphit Node Properties

### What are Node Properties?

Node Properties are additional instructions that can be given to a node. For example, how to format a number, which database to query, or if the node is active or disabled. 

To assign a property to a node, click the **(+)** adjacent to the node and select the  property from the dropdown menu. 

Note that there is a short description of each property in the dropdown menu.

![](/articles/15_web_services/Graphit/images/19_node_properties_menu.png)

### Node Properties 

#### Session Provider

The Node property **sessionProvider**, defines which interface should be used for a query. This property should be defined each time a node is defined as **sql** or **sql non-prepared** and the database to be queried is not Fabric itself. 

**Note**, this property affects the node and all its child nodes

![](/articles/15_web_services/Graphit/images/13_node_type_sql2.png)

#### Nice

The Node property **nice**, defines whether the output format will be formatted in a “nice” layout. Once set to **true**,  every tag is printed in a new line and indent. This property affects the specified node and all of its child nodes. 

![](/articles/15_web_services/Graphit/images/20_node_properties_nice.png)

#### One

The Node property **one**, defines  whether the node is treated as an array or single value.If set to **true**, the result is always a single entry, even if the query that it is based on returns multiple rows

![](/articles/15_web_services/Graphit/images/21_node_properties_one.png)

#### Entry Tag

The Node property **entryTag**,  defines the tag that surrounds <u>XML</u> array entries.

![](/articles/15_web_services/Graphit/images/22_node_entry_tag.png)

 If not in used or set to **none**, the value [entry] is used.

![](/articles/15_web_services/Graphit/images/23_node_properties_entry_tag_na.png)

#### Attribute

The Node property **attribute**, defines in  <u>XML</u>— if value is set as an attribute or child node. **Note**,  child node is the default.

![](/articles/15_web_services/Graphit/images/24_node_properties_attribute.png)

#### Format

The Node property **format**, if defined, the node will be evaluated and added if the output format matches the format value-JSON,XML or CSV. **Note**, this property only affects the node it is set on

![](/articles/15_web_services/Graphit/images/25_node_properties_format.png)

#### Show Empty

The Node property **showEmpty**,  defines whether empty arrays are shown in the output. **True** is the default. 

**Note**, this property affects the node and all its child nodes

![](/articles/15_web_services/Graphit/images/26_node_properties_show_empty.png)

#### Show Null

The Node property **showNull**,  defines whether null entries are shown in the output. **True** is the default. 

**Note**, this property affects the node and all its child nodes

![](/articles/15_web_services/Graphit/images/27_node_properties_show_null.png)

#### Number Format

The Node property **numberFormat** ,controls how numbers are formatted in the output. You can use one of the built in formats or specify your own using the following syntax:

```
0  Digit
#  Digit, zero shows as absent
.  Decimal separator or monetary decimal separator
-  Minus sign
,  Grouping separator
E  Separates mantissa and exponent in scientific notation.
;  Separates positive and negative subpatterns
%  Multiply by 100 and show as percentage
```

**Note**, this property affects the node and all its child nodes

![](/articles/15_web_services/Graphit/images/28_node_properties_number_format.png)

#### Keys

The Node property **Keys**,  is used as an advanced mechanism to replace nested queries by joining the data on the root query, and grouping it by key.

In the scope of a query, **keys** is used to select a subset of rows to group for each invocation of the node. When **Keys** is specified in child nodes, each node will group the rows of its parent nodes, according to the key 

![](/articles/15_web_services/Graphit/images/29_node_properties_keys.png)

#### CSVHeader, CSVRow, CSVCol and CSVEnclose

These node properties are controling the CSV format:

- CSVHeader - Allows disabling of a header row
- CSVRow - Defines the delimiter between rows in the CSV format. The default is the CR (\n ) sign.
- CSVCol - Defines the delimiter between columns in the CSV format. The default is the the comma sign. 
- CSVEnclose - Defines the character used to enclose a value in the CSV format. This is only used in case the value contains a special character (csvEnclose, csvRow, csvCol)

![](/articles/15_web_services/Graphit/images/30_node_properties_csv.png)



[![Previous](/articles/images/Previous.png)](/articles/15_web_services/Graphit/03_graphit_node_types.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/05_graphit_debugging.md)

