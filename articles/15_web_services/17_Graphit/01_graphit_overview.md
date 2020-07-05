# Graphit Overview

A Fabric tool, Graphit is used create dynamic CSV, XML and JSON documents and is very useful for generating Fabric [Web Service](/articles/15_web_services/01_web_services_overview.md) responses. The content of a response content is defined at execution time, according to specific parameters relevant to each Web Service call and the employed [LUI](/articles/01_fabric_overview/02_fabric_glossary.md#lui), or by retrieving dynamic information from other databases or interfaces.

### Graphit Main Features

Graphit has the following main features: 
- Supports the creation of dynamic CSV, XML and JSON documents. 
- Accepts external input as variables. 
- Uses variables in queries.
- Executes queries on the LUDB, iterates over the results and uses the returned values to create the response document.
- Executes queries on any interface (not just Fabric)
- Supporting prepared statements
- Supporting the hierarchical nature of  XML and JSON, including the ability for a query in one of the inner levels of the hierarchy. Use any "outer level" query result as an argument. 
- Recursively generating nested tags and structures
- Allowing value format customization and defining whether to generate a tag when the values are null or empty



[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/02_create_and_edit_a_graphit_file.md)

