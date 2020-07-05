# Graphit Overview

A Fabric tool, Graphit is used create dynamic CSV, XML and JSON documents. Graphit is very useful for generating Fabric [Web Service](/articles/15_web_services/01_web_services_overview.md) responses whereby response content is defined at execution time, according to specific parameters relevant to each Web Service call and the employed [LUI](/articles/01_fabric_overview/02_fabric_glossary.md#lui), or by retrieving dynamic information from other databases or interfaces.

### Graphit Main Features

Following are Graphit main features and use cases:

- Supporting creation of dynamic CSV, XML and JSON documents 
- Accepting external input as variables 
- Using variables in queries
- Executing a query on the LUDB, iterating over the results and using the returned values in the creation of the response document
- Executing queries on any interface (not just Fabric)
- Supporting prepared statements
- Supporting the hierarchical nature of  XML and JSON, including the ability for a query in one of the inner levels of the hierarchy. Use any "outer level" query result as an argument. 
- Recursively generating nested tags and structures
- Allowing value format customization and defining whether to generate a tag when the values are null or empty



[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/02_create_and_edit_a_graphit_file.md)

